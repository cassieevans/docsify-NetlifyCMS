# 插件列表

## 全文搜索 - Search

全文搜索插件会根据当前页面上的超链接获取文档内容，在 `localStorage` 内建立文档索引。默认过期时间为一天，当然我们可以自己指定需要缓存的文件列表或者配置过期时间。

```html
<script>
  window.$docsify = {
    search: 'auto', // 默认值

    search : [
      '/',            // => /README.md
      '/guide',       // => /guide.md
      '/get-started', // => /get-started.md
      '/zh-cn/',      // => /zh-cn/README.md
    ],

    // 完整配置参数
    search: {
      maxAge: 86400000, // 过期时间，单位毫秒，默认一天
      paths: [], // or 'auto'
      placeholder: 'Type to search',

      // 支持本地化
      placeholder: {
        '/zh-cn/': '搜索',
        '/': 'Type to search'
      },

      noData: 'No Results!',

      // 支持本地化
      noData: {
        '/zh-cn/': '找不到结果',
        '/': 'No Results'
      },

      // 搜索标题的最大程级, 1 - 6
      depth: 2
    }
  }
</script>
<script src="https://cdn.jsdelivr.net/npm/docsify@4.8.6/lib/plugins/search.min.js"></script>
```

## 谷歌统计 - Google Analytics

需要配置 `track id` 才能使用。

```html
<script>
  window.$docsify = {
    ga: 'UA-XXXXX-Y'
  }
</script>
<script src="https://cdn.jsdelivr.net/npm/docsify@4.8.6/lib/plugins/ga.min.js"></script>
```

也可以通过 `data-ga` 配置 id。

```html
<script src="https://cdn.jsdelivr.net/npm/docsify@4.8.6/lib/docsify.min.js" data-ga="UA-XXXXX-Y"></script>
<script src="https://cdn.jsdelivr.net/npm/docsify@4.8.6/lib/plugins/ga.min.js"></script>
```

## emoji

默认是提供 emoji 解析的，能将类似 `:100:` 解析成 :100:。但是它不是精准的，因为没有处理非 emoji 的字符串。如果你需要正确解析 emoji 字符串，你可以引入这个插件。

```html
<script src="https://cdn.jsdelivr.net/npm/docsify@4.8.6/lib/plugins/emoji.min.js"></script>
```

## 外链脚本 - External Script

如果文档里的 script 是内联脚本，可以直接执行；而如果是外链脚本（即 js 文件内容由 `src` 属性引入），则需要使用此插件。

```html
<script src="https://cdn.jsdelivr.net/npm/docsify@4.8.6/lib/plugins/external-script.min.js"></script>
```

## 演示代码
> 具有即时预览和jsfiddle集成的演示代码

使用此插件，可以立即在页面上呈现示例代码，以便读者可以立即看到预览。当读者展开演示框时，会显示源代码和说明。如果他们单击按钮`Try in Jsfiddle`，`jsfiddle.net`将打开此示例的代码，这允许读者修改代码并自行尝试。

[Vue](https://njleonzhang.github.io/docsify-demo-box-vue/) 和 [React](https://njleonzhang.github.io/docsify-demo-box-react/) 都受支持。

## 图片缩放 - Zoom image

Medium's 风格的图片缩放插件. 基于 [medium-zoom](https://github.com/francoischalifour/medium-zoom)。

```html
<script src="https://cdn.jsdelivr.net/npm/docsify@4.8.6/lib/plugins/zoom-image.min.js"></script>
```

忽略某张图片

```markdown
![](image.png ':no-zoom')
```

## 在 Github 上编辑

在每一页上添加 `Edit on github` 按钮. 由第三方库提供, 查看 [文档](https://github.com/njleonzhang/docsify-edit-on-github)

## 复制到剪贴板 Copy to Clipboard

`Click to copy`为所有预先格式化的代码块添加一个简单的按钮，以便轻松地允许用户从您的文档中复制示例代码。由[@jperasmus](https://github.com/jperasmus)提供

```html
<script src="https://cdn.jsdelivr.net/npm/docsify-copy-code@2.0.2/dist/docsify-copy-code.min.js"></script>
```

有关详细信息 [此处](https://github.com/jperasmus/docsify-copy-code/blob/master/README.md)

## Disqus

Disqus 评论插件 更多信息请访问 [此处](https://disqus.com/)

```html
<script>
  window.$docsify = {
    disqus: 'shortname'
  }
</script>
<script src="https://cdn.jsdelivr.net/npm/docsify@4.8.6/lib/plugins/disqus.min.js"></script>
```

## Gitalk

[Gitalk](https://github.com/gitalk/gitalk) 是一个基于Github Issue和Preact的现代评论组件。

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/gitalk@1.4.1/dist/gitalk.css">

<script src="https://cdn.jsdelivr.net/npm/docsify@4.8.6/lib/plugins/gitalk.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/gitalk@1.4.1/dist/gitalk.min.js"></script>
<script>
  const gitalk = new Gitalk({
    clientID: 'Github Application Client ID',
    clientSecret: 'Github Application Client Secret',
    repo: 'Github repo',
    owner: 'Github repo owner',
    admin: ['Github repo collaborators, only these guys can initialize github issues'],
    // facebook-like distraction free mode
    distractionFreeMode: false
  })
</script>
```

## 分页 - Pagination

docsify 的分页插件. By [@imyelo](https://github.com/imyelo)

```html
<script src="https://cdn.jsdelivr.net/npm/docsify@4.8.6/lib/docsify.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/docsify-pagination@2.3.5/dist/docsify-pagination.min.js"></script>
```

## Code Fund

帮你快速接入[Code Fund](https://codesponsor.io/)的[插件](https://github.com/njleonzhang/docsify-plugin-codefund), 由[@njleonzhang](https://github.com/njleonzhang)提供。

> Code Fund 以前叫 codesponsor

```
<script src="https://cdn.jsdelivr.net/npm/docsify@4.8.6/lib/docsify.min.js"></script>

window.$docsify = {
  plugins: [
    DocsifyCodefund.create('51d43327-eea3-4e27-bd44-e075e67a84fb') // 把这个id改成你的codefund id
  ]
}
```
