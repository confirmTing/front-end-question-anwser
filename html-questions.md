# What does a doctype do?

`DOCTYPE` 是必须的前导码
遗留原因需要 `DOCTYPE`，当省略时，浏览器倾向与某些不规范，不兼容的不同呈现模式。
在文档中包含 `DOCTYPE`，浏览器会尽最大努力遵循相关规范

当创作文档是 HTML 或 XHTML 时，添加 Doctype 声明很重要， 可以确保不同的浏览器以相同的方式解析文档。


参考链接：

- [w3c](https://www.w3.org/QA/2002/04/valid-dtd-list.html)

## How do you serve a page with content in multiple languages?

通过 `<html lang="en"></html>` 声明页面整体语言

##### 通过 `Content-Language` HTTP header 来声明有关文档的语言元数据

##### 通过 标签 属性 lang 指定语言

eg:
`<p>You'd say that in Chinese as <span lang="zh-Hans">中国科学院文献情报中心</span>.</p>`

注意事项：

* 不在 meta 中使用 Content-Language 指定语言 `<meta http-equiv="content-language" content="de" />`
* 不在 body 上声明，应该声明在 html 上

参考链接：

* [https://www.w3.org/TR/i18n-html-tech-lang/](https://www.w3.org/TR/i18n-html-tech-lang/)


## What kind of things must you be wary of when design or developing for multilingual sites?

* 采用统一的编码方式 utf-8
* 考虑不同语言的书写习惯，从左到右，还是从右到左
* 图片上面包含文字的使用需注意，虽然保持了好看的字体，但是开发，维护成本很高
* 因不同语言产生文字长度变化，会导致布局问题，最好使用不受文字长短的设计
* 颜色使用，在不同国家意义不同
* 日期和货币的显示不同
