# CDN

推荐使用 [Jsdelivr](//jsdelivr.com) —— 国内外访问速度都很优异。

## 获取最新版本

Jsdelivr暂时没有获取最新版的规则，频繁地版本更新有可能引入未知 Bug，保持稳定版本也有利于开发。

```html
<!-- 引入 css -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/docsify@4.8.6/lib/themes/vue.css">

<!-- 引入 script -->
<script src="https://cdn.jsdelivr.net/npm/docsify@4.8.6/lib/docsify.js"></script>
```

## 压缩版

CSS 的压缩文件位于 `/lib/themes/` 目录下

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/docsify@4.8.6/lib/themes/vue.min.css">
```

JS 的压缩文件是原有文件路径的基础上加 `.min`后缀

```html
<script src="https://cdn.jsdelivr.net/npm/docsify@4.8.6/lib/docsify.min.js"></script>
```

## 其他 CDN

由于其他CDN服务商没有国内线路，故均不推荐。
