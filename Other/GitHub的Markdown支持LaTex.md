# Markdown实用技巧－入门篇

自从接触了 Markdown 之后，就一直用 Markdown 作为自己的主要书写工具，不论是平时做一些简单的纪录，还是用来写博客，写文档都是非常方便。

我最早因为 GitHub 而了解到 Markdown，当是支持 Markdown 的平台并不多，现在发现很多平台都已经开始支持 Markdown了，不论是老牌的 CSDN 还是比较新的 简书、掘金 等都支持使用Markdown进行写作，借此趋势，向还不了解 Markdown 的魔法师强势安利一波。

**关于 Markdown 预计会有两三篇文章，总结分享一下个人使用 Markdown 的经验技巧，第一篇是基础篇，主要分析 Markdown 的优缺点，以及基础语法介绍，并没有什么干货，如果是对 Markdown 有一定了解的魔法师，可以跳过此篇，以避免浪费你的时间。**



## 什么是 Markdown ?

相比于 Markdown，想必大家对 HTML (~~How To Make Love~~) 更加了解一些，毕竟整天都在手机或者电脑上浏览这些东西。**HTML 全称 Hyper Text Markup Language (超文本标记语言)**，是现在网页的基本语言。

可以看到 HTML 里面有一个 Markup ，而本文主角是 Markdown，两者都是标记型文本语言，但 HTML 注重的是开放与连接，而 **Markdown 则更加精简，更加注重内容，其主要宗旨是「易读易写」**。



## 为什么选择 Markdown ?

**选择 Markdown 但理由只有一个：方便，节省时间! **

至于为什么这样说，请看下面内容：

* **语法简洁**，没有任何编程基础的人十几分钟语言即可入门。
* **注重内容**，专注于内容编写，不再因为拍版格式而苦恼 (word格式刷工具哭晕在厕所)。
* **易阅读性**，即便是没有经过转换的 Markdown 文件，大部分文字内容仍可阅读。
* **易编辑性**，任何文本编辑器都能编辑 Markdown 文件。
* **跨平台性**，任何平台均能打开 Markdown 文件，由于是纯文本文件，不存在格式兼容的问题。
* **导出方便**，支持导出为 HTML，PDF，Word(.docx)，LaTex 等常见格式(需要工具支持)。

> 之前很多在 Windows 上编写的文档，非常方便的就能在 Mac 上继续编辑，大大方便了我的数据迁移工作。



## Markdown 缺点

前面吹嘘了 Markdown 的那么多优点，下面就说一下其缺点：

> **后续文章中教大家如何克服这些缺点。**

* **图片问题**，很多人都觉得 Markdown 文件插入图片麻烦，还要自己上传。
* **语法兼容**，基础语法是兼容的，但不同工具(平台)的扩展语法不兼容(由于没有统一标准)。
* **细节控制**，Markdown只提供最基础的格式，其显示样式主要由CSS控制，很难针对性的控制部分内容。

> 以上应该是 Markdown 最常见的一些麻烦，不过不必担心，后续文章会帮助大家来解决这些问题，正所谓**取其精华，去其糟粕**。



## Markdown语法简介

### 文本

<table>
    <tr>
      <th>Markdown</th>
      <th>预览</th>
    </tr>
    <tr>
      <td>*强调*</td>
      <td>
        <em>强调</em>
      </td>
    </tr>
    <tr class="alternate">
      <td>**粗体**</td>
      <td><strong>粗体<strong></td>
    </tr>
    <tr>
      <td>
        &gt; 引用
      </td>
      <td>
        <blockquote>引用</blockquote>
      </td>
    </tr>
</table>


### 链接和图片

<table>
    <tr>
      <th width="200">Markdown</th>
      <th width="200">预览</th>
    </tr>
  <tr>
    <td>[Google](http://google.com)</td>
    <td><a href="http://google.com" target="_blank">Google</a></td>
  </tr>
  <tr class="alternate">
    <td>[bingdian@domain.com](bingdian@domain.com)</td>
    <td><a href="mailto:bingdian@domain.com">bingdian@domain.com</a></td>
  </tr>
  <tr class="alternate">
    <td>![The 37signals logo](http://www.37signals.com/images/logo-37signals.png)</td>
    <td><img src="http://www.37signals.com/images/logo-37signals.png" alt="The 37signals logo" /></td>
  </tr>
</table>


### 标题

<table>
    <tr>
      <th>Markdown</th>
      <th>预览</th>
    </tr>
  <tr>
    <td># 一级标题</td>
    <td><h1>一级标题</h1></td>
  </tr>
  <tr>
    <td>## 二级标题</td>
    <td><h2>二级标题</h2></td>
  </tr>
  <tr>
    <td>### 三级标题</td>
    <td><h3>三级标题</h3></td>
  </tr>
  <tr>
    <td>#### 四级标题</td>
    <td><h4>四级标题</h4></td>
  </tr>
  <tr>
    <td>##### 五级标题</td>
    <td><h5>五级标题</h5></td>
  </tr>
  <tr>
    <td>###### 六级标题</td>
    <td><h6>六级标题</h6></td>
  </tr>
</table>


### 列表

<table>
    <tr>
      <th>Markdown</th>
      <th>预览</th>
    </tr>
  <tr>
    <td>
      * 项目<br />
      * 项目<br />
      * 项目<br />
      &nbsp;&nbsp;* 子项目</span><br />
      &nbsp;&nbsp;* 子项目<br />
      * 项目
    </td>
    <td>
      <ul>
        <li>项目</li>
        <li>项目</li>
        <li>项目
          <ul>
            <li>子项目</li>
            <li>子项目</li>
          </ul>
        </li>
        <li>项目</li>
      </ul>
    </td>

  </tr>
  <tr class="alternate">
    <td>
      1. 项目<br />
      2. 项目<br />
      3. 项目<br />
      &nbsp;&nbsp;1. 子项目</span><br />
      &nbsp;&nbsp;2. 子项目<br />
      4. 项目
    </td>
    <td>
      <ol>
        <li>项目</li>
        <li>项目</li>
        <li>项目
          <ol>
            <li>子项目</li>
            <li>子项目</li>
          </ol>
        </li>
        <li>项目</li>
      </ol>
    </td>
  </tr>
</table>


### 下划线和特殊符号

<table>
    <tr>
      <th>Markdown</th>
      <th>预览</th>
    </tr>
  <tr>
    <td>
      你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线<br />
      ---
    </td>
    <td>
      <hr />
    </td>
  </tr>
  <tr class="alternate">
    <td>可以利用反斜杠来插入一些在语法中有其它意义的符号<br />
        \*Hi\*
    </td>
    <td>*Hi*</td>
  </tr>
</table>


<h2>表格</h2>

<p>Markdown：</p>

<pre><code>| First Header  | Second Header |
| ------------- | ------------- |
| Row 1 Cell 1  | Row 1 Cell 2  |
| Row 2 Cell 1  | Row 2 Cell 2  |
</code></pre>


<p>预览：</p>

<table>
<thead>
<tr>
<th> First Header  </th>
<th> Second Header </th>
</tr>
</thead>
<tbody>
<tr>
<td> Row 1 Cell 1  </td>
<td> Row 1 Cell 2  </td>
</tr>
<tr>
<td> Row 2 Cell 1  </td>
<td> Row 2 Cell 2  </td>
</tr>
</tbody>
</table>
