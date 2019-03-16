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

## What are data- attributes good for?
什么是data-属性？

在 JavaScript 框架流行之前，经常使用此属性，可以存储与元素相关的数据,这依然是一个很好的解决方案。

使用现代化框架，不建议使用自定义属性，用户可以直接使用开发者工具修改属性值，数据最好存储在js变量中，利用数据绑定保持 DOM 更新

#### js 访问：

兼容性：ie11 支持，之前版本都不支持 dataset 可以通过 `getAttrbute()` 获取

性能上：通过 js `dataset` 读取数据相比 `getAttrbute()` 和 js 变量慢。

#### css 访问：
``` css
article::before {
  content: attr(data-parent);
}
```

参考链接：

[https://developer.mozilla.org/zh-CN/docs/Web/Guide/HTML/Using_data_attributes](https://developer.mozilla.org/zh-CN/docs/Web/Guide/HTML/Using_data_attributes)


## Consider HTML5 as an open web platform. What are the building blocks of HTML5?
HTML5 的组成是什么？

* 语义化标签，更准确的描述内容，便于seo
* 连通性，提供新的方式与服务器通讯，webRTC，webSockets
* 离线存储，SessionStorage，LocalStorage，IndexDB
* 多媒体，audio 和 video, webRTC, Camera API
* 2D/3D 图形效果，canvas，WebGL，SVG
* 性能和集成， Web Workers, 新一代引擎JIT
* 设备访问，允许输入，输出设备的访问，Camera API，触摸，地理位置，设备方向
* css3，动画，布局，过渡等...