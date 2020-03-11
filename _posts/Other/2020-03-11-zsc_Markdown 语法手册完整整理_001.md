---
layout: post
title:  "Markdown 语法手册完整整理"
date:   2020-03-11
tags:  zsc
categories: 其他
---


<article class="_2rhmJa"><p>（Markdown语法没有一个统一的标准,不同的工具或平台采用的标准不一样，所以有些语法规则和功能是有差异的）</p>
<h2>0. 目录 {#index}</h2>
<p>[TOC]  （<em>注：简书Markdown不支持目录功能</em>）</p>
<h2>1. 斜体和粗体</h2>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-undefined"><code class="  language-undefined">*斜体*或_斜体_
**粗体**
***加粗斜体***
~~删除线~~
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<ul>
<li><em>这是一段斜体</em></li>
<li><strong>这是一段粗体</strong></li>
<li><strong><em>这是一段加粗斜体</em></strong></li>
<li><del>这是一段删除线</del></li>
</ul>
<hr>
<h2>2. 分级标题</h2>
<p>第一种写法：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-undefined"><code class="  language-undefined">这是一个一级标题
============================

这是一个二级标题
--------------------------------------------------

<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p>第二种写法：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-bash"><code class="  language-bash"># 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题

<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p>由于用了[TOC]标记编辑器会把所有标题写到目录大纲中，在这里写的演示标题也会列进去，所以就不演示了。同学们自己在编辑器中观察，很简单，一级标题字号最大，依级递减。（<em>注：简书Markdown不支持目录功能</em>）</p>
<hr>
<h2>3. 超链接</h2>
<p>Markdown 支持两种形式的链接语法： 行内式和参考式两种形式，行内式一般使用较多。</p>
<h3>3.1. 行内式</h3>
<p><strong>语法说明：</strong></p>
<ul>
<li>[]里写链接文字，()里写链接地址, ()中的""中可以为链接指定title属性，title属性可加可不加。title属性的效果是鼠标悬停在链接上会出现指定的 title文字。[链接文字](链接地址 "链接标题")这样的形式。<strong><em>链接地址与链接标题前有一个空格。</em></strong>
</li>
</ul>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-cpp"><code class="  language-cpp">欢迎来到<span class="token punctuation">[</span>迟道的主页<span class="token punctuation">]</span><span class="token punctuation">(</span>http<span class="token operator">:</span><span class="token operator">/</span><span class="token operator">/</span>www<span class="token punctuation">.</span>jianshu<span class="token punctuation">.</span>com<span class="token operator">/</span>u<span class="token operator">/</span>de4923b06bfc<span class="token punctuation">)</span>

欢迎来到<span class="token punctuation">[</span>迟道的主页<span class="token punctuation">]</span><span class="token punctuation">(</span>http<span class="token operator">:</span><span class="token operator">/</span><span class="token operator">/</span>www<span class="token punctuation">.</span>jianshu<span class="token punctuation">.</span>com<span class="token operator">/</span>u<span class="token operator">/</span>de4923b06bfc <span class="token string">"迟道的主页"</span><span class="token punctuation">)</span>

<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong><br>
欢迎来到<a href="https://www.jianshu.com/u/de4923b06bfc" target="_blank">迟道的主页</a><br>
欢迎来到<a href="https://www.jianshu.com/u/de4923b06bfc" target="_blank">迟道的主页</a></p>
<h3>3.2. 参考式</h3>
<p>参考式超链接一般用在学术论文上面，或者另一种情况，如果某一个链接在文章中多处使用，那么使用引用 的方式创建链接将非常好，它可以让你对链接进行统一的管理。</p>
<p><strong>语法说明：</strong><br>
参考式链接分为两部分，文中的写法 [链接文字][链接标记]，在文本的任意位置添加[链接标记]:链接地址 "链接标题"，<strong><em>链接地址与链接标题前有一个空格。</em></strong></p>
<p>如果链接文字本身可以做为链接标记，你也可以写成[链接文字][]<br>
[链接文字]：链接地址的形式，见代码的最后一行。</p>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-ruby"><code class="  language-ruby">我经常去的几个网站<span class="token punctuation">[</span><span class="token constant">GitHub</span><span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span>、<span class="token punctuation">[</span>知乎<span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token number">2</span><span class="token punctuation">]</span>以及<span class="token punctuation">[</span>简书<span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token number">3</span><span class="token punctuation">]</span>
<span class="token punctuation">[</span>简书<span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token number">3</span><span class="token punctuation">]</span>是一个不错的<span class="token punctuation">[</span>写作社区<span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token punctuation">]</span>。

<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token symbol">:https</span><span class="token punctuation">:</span><span class="token operator">/</span><span class="token operator">/</span>github<span class="token punctuation">.</span>com <span class="token string">"GitHub"</span>
<span class="token punctuation">[</span><span class="token number">2</span><span class="token punctuation">]</span><span class="token symbol">:https</span><span class="token punctuation">:</span><span class="token operator">/</span><span class="token operator">/</span>www<span class="token punctuation">.</span>zhihu<span class="token punctuation">.</span>com <span class="token string">"知乎"</span>
<span class="token punctuation">[</span><span class="token number">3</span><span class="token punctuation">]</span><span class="token symbol">:http</span><span class="token punctuation">:</span><span class="token operator">/</span><span class="token operator">/</span>www<span class="token punctuation">.</span>jianshu<span class="token punctuation">.</span>com <span class="token string">"简书"</span>
<span class="token punctuation">[</span>写作社区<span class="token punctuation">]</span><span class="token symbol">:http</span><span class="token punctuation">:</span><span class="token operator">/</span><span class="token operator">/</span>www<span class="token punctuation">.</span>jianshu<span class="token punctuation">.</span>com

<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong><br>
我经常去的几个网站<a href="https://github.com" target="_blank" rel="nofollow">GitHub</a>、<a href="https://www.zhihu.com" target="_blank" rel="nofollow">知乎</a>以及<a href="https://www.jianshu.com" target="_blank">简书</a><br>
<a href="https://www.jianshu.com" target="_blank">简书</a>是一个不错的<a href="https://www.jianshu.com" target="_blank">写作社区</a>。</p>
<h3>3.3. 自动链接</h3>
<p><strong>语法说明：</strong><br>
Markdown 支持以比较简短的自动链接形式来处理网址和电子邮件信箱，只要是用&lt;&gt;;包起来， Markdown 就会自动把它转成链接。一般网址的链接文字就和链接地址一样，例如：</p>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-dart"><code class="  language-dart"><span class="token operator">&lt;</span>http<span class="token punctuation">:</span><span class="token operator">/</span><span class="token operator">/</span>example<span class="token punctuation">.</span>com<span class="token operator">/</span><span class="token operator">&gt;</span>
<span class="token operator">&lt;</span>address<span class="token metadata symbol">@example</span><span class="token punctuation">.</span>com<span class="token operator">&gt;</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong><br>
<a href="http://example.com/" target="_blank" rel="nofollow">http://example.com/</a><br>
<a href="mailto:address@example.com" target="_blank" rel="nofollow">address@example.com</a></p>
<hr>
<h2>4. 锚点</h2>
<p>网页中，锚点其实就是页内超链接，也就是链接本文档内部的某些元素，实现当前页面中的跳转。比如我这里写下一个锚点，点击回到目录，就能跳转到目录。 在目录中点击这一节，就能跳过来。还有下一节的注脚。这些根本上都是用锚点来实现的。</p>
<p><strong>注意</strong>： Markdown Extra 只支持在标题后插入锚点，其它地方无效。</p>
<p><strong>语法描述：</strong><br>
在你准备跳转到的指定标题后插入锚点{#标记}，然后在文档的其它地方写上连接到锚点的链接。</p>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-bash"><code class="  language-bash">## 0. 目录{#index}
跳转到[目录](#index)
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<p>跳转到<a href="#index" target="_blank">目录</a></p>
<hr>
<h2>5. 列表</h2>
<h3>5.1. 无序列表</h3>
<p>使用 *，+，- 表示无序列表。</p>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-undefined"><code class="  language-undefined">- 无序列表项 一
- 无序列表项 二
- 无序列表项 三
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<ul>
<li>无序列表项 一</li>
<li>无序列表项 二</li>
<li>无序列表项 三</li>
</ul>
<h3>5.2. 有序列表</h3>
<p>有序列表则使用数字接着一个英文句点。<br>
<strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-undefined"><code class="  language-undefined">1. 有序列表项 一
2. 有序列表项 二
3. 有序列表项 三
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<ol>
<li>有序列表项 一</li>
<li>有序列表项 二</li>
<li>有序列表项 三</li>
</ol>
<h3>5.3. 定义型列表</h3>
<p><strong>语法说明：</strong></p>
<p>定义型列表由名词和解释组成。一行写上定义，紧跟一行写上解释。解释的写法:紧跟一个缩进(Tab)</p>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-undefined"><code class="  language-undefined">Markdown
:    轻量级文本标记语言，可以转换成html，pdf等格式（左侧有一个可见的冒号和四个不可见的空格）

代码块 2
:   这是代码块的定义（左侧有一个可见的冒号和四个不可见的空格）

        代码块（左侧有八个不可见的空格）
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong><br>
Markdown<br>
:    轻量级文本标记语言，可以转换成html，pdf等格式</p>
<p>代码块 2<br>
:   这是代码块的定义</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-undefined"><code class="  language-undefined">    代码块（左侧有八个不可见的空格）
<span aria-hidden="true" class="line-numbers-rows"><span></span></span></code></pre></div>
<h3>5.4. 列表缩进</h3>
<p><strong>语法说明：</strong></p>
<p>列表项目标记通常是放在最左边，但是其实也可以缩进，最多 3 个空格，项目标记后面则一定要接着至少一个空格或制表符。</p>
<p>要让列表看起来更漂亮，你可以把内容用固定的缩进整理好（显示效果与代码一致）：</p>
<ul>
<li>轻轻的我走了， 正如我轻轻的来； 我轻轻的招手， 作别西天的云彩。<br>
那河畔的金柳， 是夕阳中的新娘； 波光里的艳影， 在我的心头荡漾。<br>
软泥上的青荇， 油油的在水底招摇； 在康河的柔波里， 我甘心做一条水草！</li>
<li>那榆荫下的一潭， 不是清泉， 是天上虹； 揉碎在浮藻间， 沉淀着彩虹似的梦。<br>
寻梦？撑一支长篙， 向青草更青处漫溯； 满载一船星辉， 在星辉斑斓里放歌。<br>
但我不能放歌， 悄悄是别离的笙箫； 夏虫也为我沉默， 沉默是今晚的康桥！<br>
悄悄的我走了， 正如我悄悄的来； 我挥一挥衣袖， 不带走一片云彩。</li>
</ul>
<p>但是如果你懒，那也行：<br>
<strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-undefined"><code class="  language-undefined">*   轻轻的我走了， 正如我轻轻的来； 我轻轻的招手， 作别西天的云彩。
那河畔的金柳， 是夕阳中的新娘； 波光里的艳影， 在我的心头荡漾。 
软泥上的青荇， 油油的在水底招摇； 在康河的柔波里， 我甘心做一条水草！ 
*   那榆荫下的一潭， 不是清泉， 是天上虹； 揉碎在浮藻间， 沉淀着彩虹似的梦。 
寻梦？撑一支长篙， 向青草更青处漫溯； 满载一船星辉， 在星辉斑斓里放歌。 
但我不能放歌， 悄悄是别离的笙箫； 夏虫也为我沉默， 沉默是今晚的康桥！ 
悄悄的我走了， 正如我悄悄的来； 我挥一挥衣袖， 不带走一片云彩。
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<ul>
<li>轻轻的我走了， 正如我轻轻的来； 我轻轻的招手， 作别西天的云彩。<br>
那河畔的金柳， 是夕阳中的新娘； 波光里的艳影， 在我的心头荡漾。<br>
软泥上的青荇， 油油的在水底招摇； 在康河的柔波里， 我甘心做一条水草！</li>
<li>那榆荫下的一潭， 不是清泉， 是天上虹； 揉碎在浮藻间， 沉淀着彩虹似的梦。<br>
寻梦？撑一支长篙， 向青草更青处漫溯； 满载一船星辉， 在星辉斑斓里放歌。<br>
但我不能放歌， 悄悄是别离的笙箫； 夏虫也为我沉默， 沉默是今晚的康桥！<br>
悄悄的我走了， 正如我悄悄的来； 我挥一挥衣袖， 不带走一片云彩。</li>
</ul>
<h3>5.5. 包含段落的列表</h3>
<p><strong>语法说明：</strong><br>
列表项目可以包含多个段落，每个项目下的段落都必须缩进 4 个空格或是 1 个制表符（显示效果与代码一致）：</p>
<ul>
<li>
<p>轻轻的我走了， 正如我轻轻的来； 我轻轻的招手， 作别西天的云彩。<br>
那河畔的金柳， 是夕阳中的新娘； 波光里的艳影， 在我的心头荡漾。<br>
软泥上的青荇， 油油的在水底招摇； 在康河的柔波里， 我甘心做一条水草！</p>
<p>那榆荫下的一潭， 不是清泉， 是天上虹； 揉碎在浮藻间， 沉淀着彩虹似的梦。<br>
寻梦？撑一支长篙， 向青草更青处漫溯； 满载一船星辉， 在星辉斑斓里放歌。<br>
但我不能放歌， 悄悄是别离的笙箫； 夏虫也为我沉默， 沉默是今晚的康桥！</p>
</li>
<li><p>悄悄的我走了， 正如我悄悄的来； 我挥一挥衣袖， 不带走一片云彩。</p></li>
</ul>
<p>如果你每行都有缩进，看起来会看好很多，当然，再次地，如果你很懒惰，Markdown 也允许：<br>
<strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-undefined"><code class="  language-undefined">*   轻轻的我走了， 正如我轻轻的来； 我轻轻的招手， 作别西天的云彩。
那河畔的金柳， 是夕阳中的新娘； 波光里的艳影， 在我的心头荡漾。 
软泥上的青荇， 油油的在水底招摇； 在康河的柔波里， 我甘心做一条水草！

     那榆荫下的一潭， 不是清泉， 是天上虹； 揉碎在浮藻间， 沉淀着彩虹似的梦。 
寻梦？撑一支长篙， 向青草更青处漫溯； 满载一船星辉， 在星辉斑斓里放歌。 
但我不能放歌， 悄悄是别离的笙箫； 夏虫也为我沉默， 沉默是今晚的康桥！ 

*    悄悄的我走了， 正如我悄悄的来； 我挥一挥衣袖， 不带走一片云彩。
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<ul>
<li>
<p>轻轻的我走了， 正如我轻轻的来； 我轻轻的招手， 作别西天的云彩。<br>
那河畔的金柳， 是夕阳中的新娘； 波光里的艳影， 在我的心头荡漾。<br>
软泥上的青荇， 油油的在水底招摇； 在康河的柔波里， 我甘心做一条水草！</p>
<p>那榆荫下的一潭， 不是清泉， 是天上虹； 揉碎在浮藻间， 沉淀着彩虹似的梦。<br>
寻梦？撑一支长篙， 向青草更青处漫溯； 满载一船星辉， 在星辉斑斓里放歌。<br>
但我不能放歌， 悄悄是别离的笙箫； 夏虫也为我沉默， 沉默是今晚的康桥！</p>
</li>
<li><p>悄悄的我走了， 正如我悄悄的来； 我挥一挥衣袖， 不带走一片云彩。</p></li>
</ul>
<h3>5.6. 包含引用的列表</h3>
<p><strong>语法说明：</strong><br>
如果要在列表项目内放进引用，那 &gt; 就需要缩进：</p>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-undefined"><code class="  language-undefined">*   阅读的方法:

    &gt; 打开书本。
    &gt; 打开电灯。
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<ul>
<li>
<p>阅读的方法:</p>
<blockquote>
<p>打开书本。<br>
打开电灯。</p>
</blockquote>
</li>
</ul>
<h3>5.7. 包含代码区块的引用</h3>
<p><strong>语法说明：</strong><br>
如果要放代码区块的话，该区块就需要缩进两次，也就是 8 个空格或是 2 个制表符：</p>
<ul>
<li>
<p>一列表项包含一个列表区块：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-xml"><code class="  language-xml"><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>代码写在这</span><span class="token punctuation">&gt;</span></span>
<span aria-hidden="true" class="line-numbers-rows"><span></span></span></code></pre></div>
</li>
</ul>
<h3>5.8. 一个特殊情况</h3>
<p>在特殊情况下，项目列表很可能会不小心产生，像是下面这样的写法：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-undefined"><code class="  language-undefined">1986. What a great season.
<span aria-hidden="true" class="line-numbers-rows"><span></span></span></code></pre></div>
<p>会显示成：</p>
<ol start="1986">
<li>What a great season.</li>
</ol>
<p>换句话说，也就是在行首出现数字-句点-空白，要避免这样的状况，你可以在句点前面加上反斜杠：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-undefined"><code class="  language-undefined">1986\. What a great season.
<span aria-hidden="true" class="line-numbers-rows"><span></span></span></code></pre></div>
<p>会显示成：</p>
<p>1986. What a great season.</p>
<hr>
<h2>6. 引用</h2>
<p><strong>语法说明：</strong><br>
引用需要在被引用的文本前加上&gt;符号。</p>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-undefined"><code class="  language-undefined">&gt; 这是一个有两段文字的引用,
&gt;无意义的占行文字1.
&gt;无意义的占行文字2.
&gt;
&gt;无意义的占行文字3.
&gt;无意义的占行文字4.
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<blockquote>
<p>这是一个有两段文字的引用,<br>
无意义的占行文字1.<br>
无意义的占行文字2.</p>
<p>无意义的占行文字3.<br>
无意义的占行文字4.</p>
</blockquote>
<p>Markdown 也允许你偷懒只在整个段落的第一行最前面加上 &gt;：</p>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-undefined"><code class="  language-undefined">&gt; 这是一个有两段文字的引用,
无意义的占行文字1.
无意义的占行文字2.

&gt;无意义的占行文字3.
无意义的占行文字4.
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<blockquote>
<p>这是一个有两段文字的引用,<br>
无意义的占行文字1.<br>
无意义的占行文字2.</p>
</blockquote>
<blockquote>
<p>无意义的占行文字3.<br>
无意义的占行文字4.</p>
</blockquote>
<h3>6.1. 引用的多层嵌套</h3>
<p>区块引用可以嵌套（例如：引用内的引用），只要根据层次加上不同数量的 &gt;：</p>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-ruby"><code class="  language-ruby"><span class="token operator">&gt;</span><span class="token operator">&gt;</span><span class="token operator">&gt;</span> 请问 <span class="token constant">Markdwon</span> 怎么用？ <span class="token operator">-</span> 小白

<span class="token operator">&gt;</span><span class="token operator">&gt;</span>自己看教程！ <span class="token operator">-</span> 愤青

<span class="token operator">&gt;</span>教程在哪？ <span class="token operator">-</span> 小白
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<blockquote>
<blockquote>
<blockquote>
<p>请问 Markdwon 怎么用？ - 小白</p>
</blockquote>
</blockquote>
</blockquote>
<blockquote>
<blockquote>
<p>自己看教程！ - 愤青</p>
</blockquote>
</blockquote>
<blockquote>
<p>教程在哪？ - 小白</p>
</blockquote>
<h3>6.2. 引用其它要素</h3>
<p>引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等：<br>
<strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-kotlin"><code class="  language-kotlin"><span class="token operator">&gt;</span> <span class="token number">1</span><span class="token punctuation">.</span>   这是第一行列表项。
<span class="token operator">&gt;</span> <span class="token number">2</span><span class="token punctuation">.</span>   这是第二行列表项。
<span class="token operator">&gt;</span>
<span class="token operator">&gt;</span> 给出一些例子代码：
<span class="token operator">&gt;</span> 
<span class="token operator">&gt;</span>     <span class="token keyword">return</span> <span class="token function">shell_exec</span><span class="token punctuation">(</span><span class="token string">"echo <span class="token interpolation variable">$input</span> | <span class="token interpolation variable">$markdown_script</span>"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<blockquote>
<ol>
<li>这是第一行列表项。</li>
<li>这是第二行列表项。</li>
</ol>
<p>给出一些例子代码：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-kotlin"><code class="  language-kotlin"><span class="token keyword">return</span> <span class="token function">shell_exec</span><span class="token punctuation">(</span><span class="token string">"echo <span class="token interpolation variable">$input</span> | <span class="token interpolation variable">$markdown_script</span>"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span></span></code></pre></div>
</blockquote>
<hr>
<h2>7.  插入图像</h2>
<p>图片的创建方式与超链接相似，而且和超链接一样也有两种写法，行内式和参考式写法。</p>
<p>语法中图片Alt的意思是如果图片因为某些原因不能显示，就用定义的图片Alt文字来代替图片。 图片Title则和链接中的Title一样，表示鼠标悬停与图片上时出现的文字。 Alt 和 Title 都不是必须的，可以省略，但建议写上。</p>
<h3>7.1. 行内式</h3>
<p><strong>语法说明：</strong> ![图片Alt](图片地址 "图片Title")</p>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-ruby"><code class="  language-ruby">快乐学习： 
<span class="token operator">!</span><span class="token punctuation">[</span>快乐学习<span class="token punctuation">]</span><span class="token punctuation">(</span>http<span class="token punctuation">:</span><span class="token operator">/</span><span class="token operator">/</span>upload<span class="token operator">-</span>images<span class="token punctuation">.</span>jianshu<span class="token punctuation">.</span>io<span class="token operator">/</span>upload_images<span class="token operator">/</span><span class="token number">1001659</span><span class="token operator">-</span><span class="token number">7535</span>c9e3fe16240d<span class="token operator">?</span>imageMogr2<span class="token operator">/</span>auto<span class="token operator">-</span>orient<span class="token operator">/</span>strip<span class="token operator">%</span><span class="token number">7</span>CimageView2<span class="token operator">/</span><span class="token number">2</span><span class="token operator">/</span>w<span class="token operator">/</span><span class="token number">1240</span> <span class="token string">"快乐学习"</span><span class="token punctuation">)</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<p>快乐学习：</p>
<br>
<div class="image-package">
<div class="image-container" style="max-width: 600px; max-height: 360px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 60.0%;"></div>
<div class="image-view" data-width="600" data-height="360"><img data-original-src="http://upload-images.jianshu.io/upload_images/1001659-7535c9e3fe16240d" data-original-width="600" data-original-height="360" data-original-format="" data-original-filesize="504142" data-image-index="0" style="cursor: zoom-in;" class="" src="http://upload-images.jianshu.io/upload_images/1001659-7535c9e3fe16240d?imageMogr2/auto-orient/strip|imageView2/2/w/600/format/webp"></div>
</div>
<div class="image-caption">快乐学习</div>
</div>
<h3>7.2. 参考式</h3>
<p><strong>语法说明：</strong><br>
在文档要插入图片的地方写![图片Alt][标记]</p>
<p>在文档的最后写上[标记]:图片地址 "Title"</p>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-ruby"><code class="  language-ruby">快乐学习：
<span class="token operator">!</span><span class="token punctuation">[</span>快乐学习<span class="token punctuation">]</span><span class="token punctuation">[</span>study<span class="token punctuation">]</span>

<span class="token punctuation">[</span>study<span class="token punctuation">]</span><span class="token symbol">:http</span><span class="token punctuation">:</span><span class="token operator">/</span><span class="token operator">/</span>upload<span class="token operator">-</span>images<span class="token punctuation">.</span>jianshu<span class="token punctuation">.</span>io<span class="token operator">/</span>upload_images<span class="token operator">/</span><span class="token number">1001659</span><span class="token operator">-</span><span class="token number">7535</span>c9e3fe16240d<span class="token operator">?</span>imageMogr2<span class="token operator">/</span>auto<span class="token operator">-</span>orient<span class="token operator">/</span>strip<span class="token operator">%</span><span class="token number">7</span>CimageView2<span class="token operator">/</span><span class="token number">2</span><span class="token operator">/</span>w<span class="token operator">/</span><span class="token number">1240</span> <span class="token string">"快乐学习"</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong><br>
快乐学习：<br>
</p><div class="image-package">
<div class="image-container" style="max-width: 600px; max-height: 360px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 60.0%;"></div>
<div class="image-view" data-width="600" data-height="360"><img data-original-src="http://upload-images.jianshu.io/upload_images/1001659-7535c9e3fe16240d" data-original-width="600" data-original-height="360" data-original-format="" data-original-filesize="504142" data-image-index="1" style="cursor: zoom-in;" class="" src="http://upload-images.jianshu.io/upload_images/1001659-7535c9e3fe16240d?imageMogr2/auto-orient/strip|imageView2/2/w/600/format/webp"></div>
</div>
<div class="image-caption">快乐学习</div>
</div><p></p>
<hr>
<h2>8. 内容目录 （<em>注：简书Markdown不支持目录功能</em>）</h2>
<p>在段落中填写 <code>[TOC]</code> 以显示全文内容的目录结构。</p>
<p>效果参见最上方的目录</p>
<hr>
<h2>9. 注脚</h2>
<p><strong>语法说明：</strong></p>
<p>在需要添加注脚的文字后加上脚注<code>[^注脚名字]</code>,称为加注。 然后在文本的任意位置(一般在最后)添加脚注，脚注前必须有对应的脚注名字。</p>
<p>注意：经测试注脚与注脚之间必须空一行，不然会失效。成功后会发现，即使你没有把注脚写在文末，经Markdown转换后，也会自动归类到文章的最后。</p>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-css"><code class="  language-css">使用 Markdown[^1]可以效率的书写文档<span class="token punctuation">,</span> 直接转换成 HTML[^2]<span class="token punctuation">,</span> 你可以使用简书或者支持Markdown的编辑器进行书写。

[^1]<span class="token punctuation">:</span>Markdown是一种纯文本标记语言

[^2]<span class="token punctuation">:</span>HyperText Markup Language 超文本标记语言
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<p>使用 Markdown<sup><a href="#fn1" id="fnref1">[1]</a></sup>可以效率的书写文档, 直接转换成 HTML<sup><a href="#fn2" id="fnref2">[2]</a></sup>, 你可以使用简书或者支持Markdown的编辑器进行书写。</p>
<p><strong>注：脚注自动被搬运到最后面，请到文章末尾查看，并且脚注后方的链接可以直接跳转回到加注的地方。</strong></p>
<hr>
<h2>10. 数学公式</h2>
<h3>10.1. $ 表示行内公式： （<em>注：简书Markdown不支持此公式写法</em>）</h3>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-ruby"><code class="  language-ruby">质能守恒方程可以用一个很简洁的方程式 <span class="token variable">$E</span><span class="token operator">=</span>mc<span class="token operator">^</span><span class="token number">2</span>$ 来表达。
<span aria-hidden="true" class="line-numbers-rows"><span></span></span></code></pre></div>
<p><strong>显示效果：</strong><br>
质能守恒方程可以用一个很简洁的方程式 <img class="math-inline" src="https://math.jianshu.com/math?formula=E%3Dmc%5E2" alt="E=mc^2" mathimg="1"> 来表达。</p>
<h3>10.2 $$ 表示整行公式：（<em>注：简书Markdown不支持此公式写法</em>）</h3>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-ruby"><code class="  language-ruby">$$\sum_<span class="token punctuation">{</span>i<span class="token operator">=</span><span class="token number">1</span><span class="token punctuation">}</span><span class="token operator">^</span>n a_i<span class="token operator">=</span><span class="token number">0</span>$$

<span class="token variable">$$f</span><span class="token punctuation">(</span>x_1<span class="token punctuation">,</span>x_x<span class="token punctuation">,</span>\ldots<span class="token punctuation">,</span>x_n<span class="token punctuation">)</span> <span class="token operator">=</span> x_1<span class="token operator">^</span><span class="token number">2</span> <span class="token operator">+</span> x_2<span class="token operator">^</span><span class="token number">2</span> <span class="token operator">+</span> \cdots <span class="token operator">+</span> x_n<span class="token operator">^</span><span class="token number">2</span> $$

$$\sum<span class="token operator">^</span><span class="token punctuation">{</span>j<span class="token operator">-</span><span class="token number">1</span><span class="token punctuation">}</span>_<span class="token punctuation">{</span>k<span class="token operator">=</span><span class="token number">0</span><span class="token punctuation">}</span><span class="token punctuation">{</span>\widehat<span class="token punctuation">{</span>\gamma<span class="token punctuation">}</span>_<span class="token punctuation">{</span>kj<span class="token punctuation">}</span> z_k<span class="token punctuation">}</span>$$
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong><br>
<img class="math-block" src="https://math.jianshu.com/math?formula=%5Csum_%7Bi%3D1%7D%5En%20a_i%3D0" alt="\sum_{i=1}^n a_i=0" mathimg="1"><br>
<img class="math-block" src="https://math.jianshu.com/math?formula=f(x_1%2Cx_x%2C%5Cldots%2Cx_n)%20%3D%20x_1%5E2%20%2B%20x_2%5E2%20%2B%20%5Ccdots%20%2B%20x_n%5E2" alt="f(x_1,x_x,\ldots,x_n) = x_1^2 + x_2^2 + \cdots + x_n^2" mathimg="1"><br>
<img class="math-block" src="https://math.jianshu.com/math?formula=%5Csum%5E%7Bj-1%7D_%7Bk%3D0%7D%7B%5Cwidehat%7B%5Cgamma%7D_%7Bkj%7D%20z_k%7D" alt="\sum^{j-1}_{k=0}{\widehat{\gamma}_{kj} z_k}" mathimg="1"></p>
<p>访问 <a href="http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference" target="_blank" rel="nofollow">MathJax</a> 参考更多使用方法。</p>
<h3>10.3 简书公式写法：</h3>
<p>使用forkosh服务器，forkosh上提供了关于Latex公式的一份简短而很有用的帮助，参考[4]和[5].<br>
[4]:<a href="http://www.forkosh.com/mathtextutorial.html" target="_blank" rel="nofollow">http://www.forkosh.com/mathtextutorial.html</a><br>
[5]:<a href="http://www.forkosh.com/mathtex.html" target="_blank" rel="nofollow">http://www.forkosh.com/mathtex.html</a><br>
使用forkosh插入公式的方法是：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-cpp"><code class="  language-cpp"><span class="token operator">!</span><span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">(</span>http<span class="token operator">:</span><span class="token operator">/</span><span class="token operator">/</span>www<span class="token punctuation">.</span>forkosh<span class="token punctuation">.</span>com<span class="token operator">/</span>mathtex<span class="token punctuation">.</span>cgi<span class="token operator">?</span> 在此处插入Latex公式<span class="token punctuation">)</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span></span></code></pre></div>
<p>示例1：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-cpp"><code class="  language-cpp"><span class="token operator">!</span><span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">(</span>http<span class="token operator">:</span><span class="token operator">/</span><span class="token operator">/</span>www<span class="token punctuation">.</span>forkosh<span class="token punctuation">.</span>com<span class="token operator">/</span>mathtex<span class="token punctuation">.</span>cgi<span class="token operator">?</span> E<span class="token operator">=</span>mc<span class="token operator">^</span><span class="token number">2</span><span class="token punctuation">)</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span></span></code></pre></div>
<p>效果：<br>
[图片上传失败...(image-a87a9e-1541470046355)]<br>
示例2：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-cpp"><code class="  language-cpp"><span class="token operator">!</span><span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">(</span>http<span class="token operator">:</span><span class="token operator">/</span><span class="token operator">/</span>www<span class="token punctuation">.</span>forkosh<span class="token punctuation">.</span>com<span class="token operator">/</span>mathtex<span class="token punctuation">.</span>cgi<span class="token operator">?</span> \sum_<span class="token punctuation">{</span>i<span class="token operator">=</span><span class="token number">1</span><span class="token punctuation">}</span><span class="token operator">^</span>n a_i<span class="token operator">=</span><span class="token number">0</span><span class="token punctuation">)</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span></span></code></pre></div>
<p>效果：<br>
[图片上传失败...(image-3e19a0-1541470046355)]</p>
<p>示例3：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-cpp"><code class="  language-cpp"><span class="token operator">!</span><span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">(</span>http<span class="token operator">:</span><span class="token operator">/</span><span class="token operator">/</span>www<span class="token punctuation">.</span>forkosh<span class="token punctuation">.</span>com<span class="token operator">/</span>mathtex<span class="token punctuation">.</span>cgi<span class="token operator">?</span>  <span class="token function">f</span><span class="token punctuation">(</span>x_1<span class="token punctuation">,</span>x_x<span class="token punctuation">,</span>\ldots<span class="token punctuation">,</span>x_n<span class="token punctuation">)</span> <span class="token operator">=</span> x_1<span class="token operator">^</span><span class="token number">2</span> <span class="token operator">+</span> x_2<span class="token operator">^</span><span class="token number">2</span> <span class="token operator">+</span> \cdots <span class="token operator">+</span> x_n<span class="token operator">^</span><span class="token number">2</span><span class="token punctuation">)</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span></span></code></pre></div>
<p>效果：<br>
[图片上传失败...(image-ef1b76-1541470046355)] = x_1^2 + x_2^2 + \cdots + x_n^2)</p>
<p>示例4：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-cpp"><code class="  language-cpp"><span class="token operator">!</span><span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">(</span>http<span class="token operator">:</span><span class="token operator">/</span><span class="token operator">/</span>www<span class="token punctuation">.</span>forkosh<span class="token punctuation">.</span>com<span class="token operator">/</span>mathtex<span class="token punctuation">.</span>cgi<span class="token operator">?</span>  \sum<span class="token operator">^</span><span class="token punctuation">{</span>j<span class="token operator">-</span><span class="token number">1</span><span class="token punctuation">}</span>_<span class="token punctuation">{</span>k<span class="token operator">=</span><span class="token number">0</span><span class="token punctuation">}</span><span class="token punctuation">{</span>\widehat<span class="token punctuation">{</span>\gamma<span class="token punctuation">}</span>_<span class="token punctuation">{</span>kj<span class="token punctuation">}</span> z_k<span class="token punctuation">}</span><span class="token punctuation">)</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span></span></code></pre></div>
<p>效果：<br>
[图片上传失败...(image-abbf39-1541470046355)]</p>
<hr>
<h2>11 .表格</h2>
<p><strong>语法说明：</strong></p>
<ol>
<li>不管是哪种方式，第一行为表头，第二行分隔表头和主体部分，第三行开始每一行为一个表格行。</li>
<li>列于列之间用管道符|隔开。原生方式的表格每一行的两边也要有管道符。</li>
<li>第二行还可以为不同的列指定对齐方向。默认为左对齐，在-右边加上:就右对齐。</li>
</ol>
<p><strong>代码：</strong></p>
<p>简单方式写表格：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-ruby"><code class="  language-ruby">学号<span class="token operator">|</span>姓名<span class="token operator">|</span>分数
<span class="token operator">-</span><span class="token operator">|</span><span class="token operator">-</span><span class="token operator">|</span><span class="token operator">-</span>
小明<span class="token operator">|</span>男<span class="token operator">|</span><span class="token number">75</span>
小红<span class="token operator">|</span>女<span class="token operator">|</span><span class="token number">79</span>
小陆<span class="token operator">|</span>男<span class="token operator">|</span><span class="token number">92</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p>原生方式写表格：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-ruby"><code class="  language-ruby"><span class="token operator">|</span>学号<span class="token operator">|</span>姓名<span class="token operator">|</span>分数<span class="token operator">|</span>
<span class="token operator">|</span><span class="token operator">-</span><span class="token operator">|</span><span class="token operator">-</span><span class="token operator">|</span><span class="token operator">-</span><span class="token operator">|</span>
<span class="token operator">|</span>小明<span class="token operator">|</span>男<span class="token operator">|</span><span class="token number">75</span><span class="token operator">|</span>
<span class="token operator">|</span>小红<span class="token operator">|</span>女<span class="token operator">|</span><span class="token number">79</span><span class="token operator">|</span>
<span class="token operator">|</span>小陆<span class="token operator">|</span>男<span class="token operator">|</span><span class="token number">92</span><span class="token operator">|</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p>为表格第二列指定方向：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-ruby"><code class="  language-ruby">产品<span class="token operator">|</span>价格
<span class="token operator">-</span><span class="token operator">|</span><span class="token operator">-</span><span class="token punctuation">:</span>
<span class="token constant">Leanote</span> 高级账号<span class="token operator">|</span><span class="token number">60</span>元<span class="token operator">/</span>年
<span class="token constant">Leanote</span> 超级账号<span class="token operator">|</span><span class="token number">120</span>元<span class="token operator">/</span>年
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong><br>
简单方式写表格：</p>
<table>
<thead>
<tr>
<th>学号</th>
<th>姓名</th>
<th>分数</th>
</tr>
</thead>
<tbody>
<tr>
<td>小明</td>
<td>男</td>
<td>75</td>
</tr>
<tr>
<td>小红</td>
<td>女</td>
<td>79</td>
</tr>
<tr>
<td>小陆</td>
<td>男</td>
<td>92</td>
</tr>
</tbody>
</table>
<p>原生方式写表格：</p>
<table>
<thead>
<tr>
<th>学号</th>
<th>姓名</th>
<th>分数</th>
</tr>
</thead>
<tbody>
<tr>
<td>小明</td>
<td>男</td>
<td>75</td>
</tr>
<tr>
<td>小红</td>
<td>女</td>
<td>79</td>
</tr>
<tr>
<td>小陆</td>
<td>男</td>
<td>92</td>
</tr>
</tbody>
</table>
<p>为表格第二列指定方向：</p>
<table>
<thead>
<tr>
<th>产品</th>
<th style="text-align:right">价格</th>
</tr>
</thead>
<tbody>
<tr>
<td>为知笔记VIP</td>
<td style="text-align:right">60元/年</td>
</tr>
<tr>
<td>有道云笔记会员</td>
<td style="text-align:right">198元/年</td>
</tr>
</tbody>
</table>
<hr>
<h2>12. 分隔线</h2>
<p>你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：</p>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-undefined"><code class="  language-undefined">* * *

***

*****

- - -

---------------------------------------
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果都一样：</strong></p>
<hr>
<h2>13. 代码</h2>
<p>对于程序员来说这个功能是必不可少的，插入程序代码的方式有两种，一种是利用缩进(Tab), 另一种是利用“`”符号（一般在ESC键下方）包裹代码。</p>
<p><strong>语法说明：</strong></p>
<ol>
<li>插入行内代码，即插入一个单词或者一句代码的情况，使用`code`这样的形式插入。</li>
<li>插入多行代码，可以使用缩进或者``` code ```,具体看示例。</li>
</ol>
<p><strong>注意： 缩进式插入前方必须有空行</strong></p>
<h3>13.1. 行内式</h3>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-cpp"><code class="  language-cpp">C语言里的函数 `<span class="token function">scanf</span><span class="token punctuation">(</span><span class="token punctuation">)</span>` 怎么使用？
<span aria-hidden="true" class="line-numbers-rows"><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<p>C语言里的函数 <code>scanf()</code> 怎么使用？</p>
<h3>13.2. 缩进式多行代码</h3>
<p>缩进 4 个空格或是 1 个制表符</p>
<p>一个代码区块会一直持续到没有缩进的那一行（或是文件结尾）。</p>
<p><strong>代码：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-cpp"><code class="  language-cpp">    <span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;stdio.h&gt;</span></span>
    <span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token keyword">void</span><span class="token punctuation">)</span>
    <span class="token punctuation">{</span>
        <span class="token function">printf</span><span class="token punctuation">(</span><span class="token string">"Hello world\n"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-cpp"><code class="  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;stdio.h&gt;</span></span>
<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token keyword">void</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token function">printf</span><span class="token punctuation">(</span><span class="token string">"Hello world\n"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<h3>13.3. 用六个`包裹多行代码</h3>
<p><strong>代码：</strong></p>
<p>```<br>
#include &lt;stdio.h&gt;<br>
int main(void)<br>
{<br>
printf("Hello world\n");<br>
}<br>
```</p>
<p><strong>显示效果：</strong></p>
<div class="_2Uzcx_"><pre class="line-numbers  language-cpp"><code class="  language-cpp"><span class="token macro property">#<span class="token directive keyword">include</span> <span class="token string">&lt;stdio.h&gt;</span></span>
<span class="token keyword">int</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token keyword">void</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    <span class="token function">printf</span><span class="token punctuation">(</span><span class="token string">"Hello world\n"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<h3>13.4. 代码高亮</h3>
<p>代码高亮示例:</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-javascript"><code class="javascript  language-javascript"><span class="token comment">/**
* nth element in the fibonacci series.
* @param n &gt;= 0
* @return the nth element, &gt;= 0.
*/</span>
<span class="token keyword">function</span> <span class="token function">fib</span><span class="token punctuation">(</span><span class="token parameter">n</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
  <span class="token keyword">var</span> a <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">,</span> b <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
  <span class="token keyword">var</span> tmp<span class="token punctuation">;</span>
  <span class="token keyword">while</span> <span class="token punctuation">(</span><span class="token operator">--</span>n <span class="token operator">&gt;=</span> <span class="token number">0</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    tmp <span class="token operator">=</span> a<span class="token punctuation">;</span>
    a <span class="token operator">+=</span> b<span class="token punctuation">;</span>
    b <span class="token operator">=</span> tmp<span class="token punctuation">;</span>
  <span class="token punctuation">}</span>
  <span class="token keyword">return</span> a<span class="token punctuation">;</span>
<span class="token punctuation">}</span>
 
document<span class="token punctuation">.</span><span class="token function">write</span><span class="token punctuation">(</span><span class="token function">fib</span><span class="token punctuation">(</span><span class="token number">10</span><span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<div class="_2Uzcx_"><pre class="line-numbers  language-python"><code class="python  language-python"><span class="token keyword">class</span> <span class="token class-name">Employee</span><span class="token punctuation">:</span>
   empCount <span class="token operator">=</span> <span class="token number">0</span>
 
   <span class="token keyword">def</span> <span class="token function">__init__</span><span class="token punctuation">(</span>self<span class="token punctuation">,</span> name<span class="token punctuation">,</span> salary<span class="token punctuation">)</span><span class="token punctuation">:</span>
        self<span class="token punctuation">.</span>name <span class="token operator">=</span> name
        self<span class="token punctuation">.</span>salary <span class="token operator">=</span> salary
        Employee<span class="token punctuation">.</span>empCount <span class="token operator">+=</span> <span class="token number">1</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<h3>13.5. HTML 原始码 （<em>注：简书Markdown不支持HTML原始码</em>）</h3>
<p>在代码区块里面， &amp; 、 &lt; 和 &gt; 会自动转成 HTML 实体，这样的方式让你非常容易使用 Markdown 插入范例用的 HTML 原始码，只需要复制贴上，剩下的 Markdown 都会帮你处理，例如：</p>
<p><strong>代码：</strong></p>
<p>第一个例子：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-csharp"><code class="  language-csharp"><span class="token operator">&lt;</span>div <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"footer"</span><span class="token operator">&gt;</span>
   © <span class="token number">2004</span> <span class="token class-name">Foo</span> Corporation
<span class="token operator">&lt;</span><span class="token operator">/</span>div<span class="token operator">&gt;</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span></span></code></pre></div>
<p>第二个例子：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-xml"><code class="  language-xml"><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>table</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>tr</span><span class="token punctuation">&gt;</span></span>
        <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>th</span> <span class="token attr-name">rowspan</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>2<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>值班人员<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>th</span><span class="token punctuation">&gt;</span></span>
        <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>th</span><span class="token punctuation">&gt;</span></span>星期一<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>th</span><span class="token punctuation">&gt;</span></span>
        <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>th</span><span class="token punctuation">&gt;</span></span>星期二<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>th</span><span class="token punctuation">&gt;</span></span>
        <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>th</span><span class="token punctuation">&gt;</span></span>星期三<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>th</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>tr</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>tr</span><span class="token punctuation">&gt;</span></span>
        <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>td</span><span class="token punctuation">&gt;</span></span>李强<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>td</span><span class="token punctuation">&gt;</span></span>
        <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>td</span><span class="token punctuation">&gt;</span></span>张明<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>td</span><span class="token punctuation">&gt;</span></span>
        <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>td</span><span class="token punctuation">&gt;</span></span>王平<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>td</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>tr</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>table</span><span class="token punctuation">&gt;</span></span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p><strong>显示效果：</strong></p>
<p>第一个例子：</p>
<div class="image-package">
<div class="image-container" style="max-width: 207px; max-height: 47px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 22.71%;"></div>
<div class="image-view" data-width="207" data-height="47"><img data-original-src="http://upload-images.jianshu.io/upload_images/1001659-0270afa6180253e3.png" data-original-width="207" data-original-height="47" data-original-format="" data-original-filesize="2063" data-image-index="2" style="cursor: zoom-in;" class="" src="http://upload-images.jianshu.io/upload_images/1001659-0270afa6180253e3.png?imageMogr2/auto-orient/strip|imageView2/2/w/207/format/webp"></div>
</div>
<div class="image-caption">HTML源码效果</div>
</div>
<p>第二个例子：</p>
<div class="image-package">
<div class="image-container" style="max-width: 329px; max-height: 94px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 28.57%;"></div>
<div class="image-view" data-width="329" data-height="94"><img data-original-src="//upload-images.jianshu.io/upload_images/1001659-fc5bf3320d05a673.png" data-original-width="329" data-original-height="94" data-original-format="" data-original-filesize="4666" data-image-index="3" style="cursor: zoom-in;" class="" src="//upload-images.jianshu.io/upload_images/1001659-fc5bf3320d05a673.png?imageMogr2/auto-orient/strip|imageView2/2/w/329/format/webp"></div>
</div>
<div class="image-caption">HTML表格</div>
</div>
<h2>14. todo list （<em>注：简书Markdown不支持todo list</em>）</h2>
<p>代码：</p>
<div class="_2Uzcx_"><pre class="line-numbers  language-css"><code class="  language-css"><span class="token property">近期任务安排</span><span class="token punctuation">:</span>
- [x] 整理Markdown手册
- [ ] 改善项目
   - [x] 优化首页显示方式
   - [x] 修复闪退问题
   - [ ] 修复视频卡顿
- [ ] A3项目修复
   - [x] 修复数值错误
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre></div>
<p>效果：</p>
<div class="image-package">
<div class="image-container" style="max-width: 257px; max-height: 285px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 110.89%;"></div>
<div class="image-view" data-width="257" data-height="285"><img data-original-src="//upload-images.jianshu.io/upload_images/1001659-420fea3d68612ca5.png" data-original-width="257" data-original-height="285" data-original-format="" data-original-filesize="25016" data-image-index="4" style="cursor: zoom-in;" class="" src="http://upload-images.jianshu.io/upload_images/1001659-420fea3d68612ca5.png?imageMogr2/auto-orient/strip|imageView2/2/w/257/format/webp"></div>
</div>
<div class="image-caption">todo list</div>
</div>
<h2>15. 时序图 （<em>注：简书Markdown不支持时序图</em>）</h2>
<blockquote>
<ul>
<li><a href="http://bramp.github.io/js-sequence-diagrams/" target="_blank" rel="nofollow">时序图语法</a></li>
</ul>
</blockquote>
<p>代码：</p>
<p>```sequence<br>
participant 客户端 as A<br>
participant 服务端 as B<br>
participant 通行证中心 as C<br>
Note over A:用户输入通行证账号、密码<br>
A-&gt;C: 发送账号、密码<br>
Note over C:验证账号、密码<br>
C--&gt;&gt;A:返回token<br>
A-&gt;B:发送token<br>
B-&gt;C:验证token<br>
C--&gt;&gt;B:验证成功<br>
B--&gt;&gt;A:登陆成功<br>
Note left of A:左边注释<br>
B-&gt;B:自交互<br>
Note right of C:右边注释<br>
```<br>
效果：</p>
<div class="image-package">
<div class="image-container" style="max-width: 529px; max-height: 582px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 110.02000000000001%;"></div>
<div class="image-view" data-width="529" data-height="582"><img data-original-src="//upload-images.jianshu.io/upload_images/1001659-64faecc6a368b855.png" data-original-width="529" data-original-height="582" data-original-format="" data-original-filesize="17797" data-image-index="5" style="cursor: zoom-in;" class="" src="http://upload-images.jianshu.io/upload_images/1001659-64faecc6a368b855.png?imageMogr2/auto-orient/strip|imageView2/2/w/529/format/webp"></div>
</div>
<div class="image-caption">时序图</div>
</div>
<h2>16. 流程图 （<em>注：简书Markdown不支持流程图</em>）</h2>
<blockquote>
<ul>
<li><a href="http://adrai.github.io/flowchart.js" target="_blank" rel="nofollow">流程图语法</a></li>
</ul>
</blockquote>
<p>```flow<br>
st=&gt;start: 开始<br>
io=&gt;inputoutput: 验证<br>
op=&gt;operation: 选项<br>
cond=&gt;condition: 是 或 否？<br>
sub=&gt;subroutine: 子程序<br>
e=&gt;end: 结束</p>
<p>st-&gt;io-&gt;op-&gt;cond<br>
cond(yes)-&gt;e<br>
cond(no)-&gt;sub-&gt;io<br>
```<br>
效果：</p>
<div class="image-package">
<div class="image-container" style="max-width: 492px; max-height: 552px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 112.20000000000002%;"></div>
<div class="image-view" data-width="492" data-height="552"><img data-original-src="http://upload-images.jianshu.io/upload_images/1001659-c405b4a255236f33.png" data-original-width="492" data-original-height="552" data-original-format="" data-original-filesize="14047" data-image-index="6" style="cursor: zoom-in;" class="" src="http://upload-images.jianshu.io/upload_images/1001659-c405b4a255236f33.png?imageMogr2/auto-orient/strip|imageView2/2/w/492/format/webp"></div>
</div>
<div class="image-caption">流程图</div>
</div>
<h2>17. 甘特图 （<em>注：简书Markdown不支持甘特图</em>）</h2>
<blockquote>
<ul>
<li><a href="http://knsv.github.io/mermaid/#configuration41" target="_blank" rel="nofollow">甘特图语法</a></li>
</ul>
</blockquote>
<p>```<br>
gantt<br>
dateFormat YYYY-MM-DD<br>
title 产品计划表<br>
section 初期阶段<br>
明确需求: 2017-03-01, 10d<br>
section 中期阶段<br>
跟进开发: 2017-03-11, 9d<br>
section 后期阶段<br>
抽查测试: 2017-03-20, 9d<br>
```<br>
效果：</p>
<div class="image-package">
<div class="image-container" style="max-width: 700px; max-height: 218px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 17.48%;"></div>
<div class="image-view" data-width="1247" data-height="218"><img data-original-src="http://upload-images.jianshu.io/upload_images/1001659-6b71c70b047b0fcb.png" data-original-width="1247" data-original-height="218" data-original-format="" data-original-filesize="28522" data-image-index="7" style="cursor: zoom-in;" class="" src="http://upload-images.jianshu.io/upload_images/1001659-6b71c70b047b0fcb.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200/format/webp"></div>
</div>
<div class="image-caption">甘特图</div>
</div>
<hr>
 
<ol>
<li id="fn1" class="footnote-item">
<p>Markdown是一种纯文本标记语言 <a href="#fnref1" class="footnote-backref">↩</a></p>
</li>
<li id="fn2" class="footnote-item">
<p>HyperText Markup Language 超文本标记语言 <a href="#fnref2" class="footnote-backref">↩</a></p>
</li>
</ol>
 
</article>