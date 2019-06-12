# SCSS 与 Sass 异同

SCSS 是 Sass 3 引入新的语法，其语法完全兼容 CSS3，并且继承了 Sass 的强大功能。也就是说，任何标准的 CSS3 样式表都是具有相同语义的有效的 SCSS 文件。另外，SCSS 还能识别大部分 CSS hacks（一些 CSS 小技巧）和特定于浏览器的语法，例如：[古老的 IE `filter` 语法](http://msdn.microsoft.com/en-us/library/ms532847(v=vs.85).aspx#Defining_Visual_Filt)。

由于 SCSS 是 CSS 的扩展，因此，所有在 CSS 中正常工作的代码也能在 SCSS 中正常工作。也就是说，对于一个 Sass 用户，只需要理解 Sass 扩展部分如何工作的，就能完全理解 SCSS。大部分扩展，例如变量、parent references 和 指令都是一致的；唯一不同的是，SCSS 需要使用分号和花括号而不是换行和缩进。 例如，以下这段简单的 Sass 代码：

```scss
#sidebar
  width: 30%
  background-color: #faa
```

只需添加花括号和分号就能转换为 SCSS 语法：

```scss
#sidebar {
  width: 30%;
  background-color: #faa;
}
```

另外，SCSS 对空白符号不敏感。上面的代码也可以书写成下面的样子：

```scss
#sidebar {width: 30%; background-color: #faa}
```

还有一些不同是比较复杂的。这些将在下面进行详细讲解。建议先看看[Sass 3 语法差异](http://sass.bootcss.com/sass-changelog/#3-0-0-syntax-changes)。在继续学习 SCSS 之前请务必理解下面这些内容。