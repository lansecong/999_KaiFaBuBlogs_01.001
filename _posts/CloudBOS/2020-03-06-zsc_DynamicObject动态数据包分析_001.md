---
layout: post
title:  "DynamicObject动态数据包分析"
date:   2020-03-06
tags:  zsc
categories: CloudBOS
---
 
#### DynamicObjectType动态实体类型，DynamicObject动态数据包，DynamicProperty动态属性说明
1. 下面都使用简称，动态实体类型：实体类型；动态数据包：数据包；
2. 实体类型是由动态属性构成的，动态属性来源于单据字段，动态属性中的属性也来源字段属性；          
3. 动态属性的名称，默认值，类型等都是来源字段
4. 数据包有实体类型构成，以字典结构显示，key为动态属性名（也是字段名），value 为字段值
5. 数据包以数组形式保存字段值，并不保存key，数据包通过索引来关联其中的key和value，索引保存在动态属性的属性Ordinal中
6. 数据包中的值都是有类型的，虽然显示的时候都是object，但在赋值的时候都会根据动态属性中的类型对值做验证。
7. 单据只有一份元数据，只有一个实体类型，多份数据包；一个字段只有一个动态属性，多个值（不同单据值不一样）；

#### 创建数据包
1. 先创建实体类型，并注册动态属性，最后把实体类型作为参数创建动态数据包,FirstDynType也是数据包的名称
    ```
    DynamicObjectType objType = new DynamicObjectType("FirstDynType")
    ```
2. 注册简单属性"intProperty"，intProperty也是数据包数据项的key, typeof(int)数据项的类型，0数据项的默认值
    ```
    DynamicProperty intProperty = objType.RegisterSimpleProperty("intProperty", typeof(int), 0);
    DynamicProperty stringProperty = objType.RegisterSimpleProperty("stringProperty", typeof(string), string.Empty);
    ```
3. 创建动态数据包，主要做两件事
    ```
    //1.把实体类型objType赋给数据包的属性DynamicObjectType
    //2.根据objType.Properties.Count初始化数据包的大小
    DynamicObject dynData = new DynamicObject(objType);
    ```

#### 得到数据包所有Key
1. 可以看到名称为FirstDynType，数据项[{intProperty，0},{stringProperty,}]的数据包，但数据包并没有保存key，
    只是在显示的时候把两者结合起来了
2. 数据包{intProperty，0}中intProperty来源动态属性名，0动态属性的默认值。
3. 数据包key只能是通过实体类型中的动态属性来取。
    ```
    List<string> dynDataKeys = new List<string>();
    foreach(var propery in dynData.DynamicObjectType.Properties)
    {
        dynDataKeys.Add(propery.Name);
    }
    ```

#### 数据包赋值
1. 有3种方式直接给数据包赋值，其实这3种方式都是通过找到实体类型中的动态属性，
      然后通过动态属性给其赋值，所以他们的本质都是一样的。intProperty.SetValue(dynData, 123);
2. 动态属性又是怎样给数据包赋值的？动态属性中有个属性Ordinal，其实Ordinal就是数据包中的数组值得索引。
3. 为什么不直接赋值而要通过动态属性？这是因为动态属性可以对值进行控制，可以设置默认值，类型验证，改变事件等。
    ```
    dynData[0] = 111; //1.索引
    dynData["intProperty"] = 222;//2.动态属性名
    dynData[intProperty] = 333;//动态属性
    intProperty.SetValue(dynData, 123); //动态属性给其赋值
    ```

#### 数据包结构
1. 简单项(名称+简单值)，复杂项（名称+数据包），集合项（名称+数据包集合）
2. 一般字段都是简单项，有内码的实体数据包中的key都是“Id”,也是第一项。
3. 基础资料字段包含一个以内码的简单项和以数据包的复杂项。
4. 子单据头，单据体，子单据体都是集合项，多选辅助资料，多选基础资料都是集合项
5. [参考帖](https://club.kingdee.com/forum.php?mod=viewthread&tid=1009805)
    ```
    DynamicObjectType secondObjType = new DynamicObjectType("SecongdDynType");
    objType.RegisterComplexProperty("SecongdDynType", secondObjType, false);//注册复杂项
    DynamicObjectCollection objColl = new DynamicObjectCollection(secondObjType);
    objType.RegisterCollectionProperty("", secondObjType, objColl.GetType());//注册集合数据包
    ```

#### 有必要去判断数据包是否包含key，或某值是什么类型？
1. 数据包中的key都是来源元数据中的字段名，所以单据中有的字段名，数据包一定是有的，除一些特殊字段，比如代理字段等，所以没有必要去判断。
2. value的类型有必要去判断？也是没有必要的，在构建数据包时，类型都是根据字段固定好的。

#### 常见错误
1. 实体类型{0}中不存在名为{1}的属性;
    * 这是因为实体类型中的动态属性没有名称为{0}的动态属性.比如：dynData["不存在的属性名"]，很可能是元数据跟代码版本不一致,或者打补丁后二开的字段丢失。
2. 寻找实体上{0}对应的属性描述符失败，实体不存在此属性！[EntityType：{0} Propeyties:{1}];
    * 同1
3. 索引超出范围。必须为非负值并小于集合大小。
    * 这往往是因为创建了动态数据包后又去修改实体类型。其实我们看到的数据包是会动态改变大小的，在数据包中索引没有超出，这里的超出往往是触发了动态属性改变事件，记录值有改过时而发生的。
4. 输入的字符串格式不正确。
    * 给数据包赋值跟动态属性的类型不一致。




