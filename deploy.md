# 部署

和 GitBook 生成的文档一样，我们可以直接把文档网站部署到 GitHub Pages 或者 VPS 上。

## GitHub Pages

GitHub Pages 支持从三个地方读取文件

- `docs/` 目录
- master 分支
- gh-pages 分支

我们推荐直接将文档放在 `docs/` 目录下，在设置页面开启 **GitHub Pages** 功能并选择 `master branch /docs folder` 选项。

![github pages](../_images/deploy-github-pages.png)

!> 可以将文档放在根目录下，然后选择 **master 分支** 作为文档目录。

## GitLab Pages

如果你正在部署你的主分支, 在 `.gitlab-ci.yml` 中包含以下脚本：

?> `.public` 的解决方法是这样的，`cp` 不会无限循环的将 `public/` 复制到自身。

```YAML
pages:
  stage: deploy
  script:
  - mkdir .public
  - cp -r * .public
  - mv .public public
  artifacts:
    paths:
    - public
  only:
  - master
```

!> 你可以用 `- cp -r docs/. public` 替换脚本, 如果 `./docs` 是你的 docsify 子文件夹。

## VPS

和部署所有静态网站一样，只需将服务器的访问根目录设定为 `index.html` 文件。

例如 nginx 的配置

```nginx
server {
  listen 80;
  server_name  your.domain.com;

  location / {
    alias /path/to/dir/of/docs;
    index index.html;
  }
}
```

## Netlify

1.  登陆您的 [Netlify](https://www.netlify.com/) 账户。
2.  在 [仪表盘](https://app.netlify.com/) 页面, 点击 **New site from Git**.
3.  选择存储文档的存储库，将 **Build Command** 区域留空，在 **Publish directory** 区域填写 `index.html`, 例如，你的 `index.html`文件在 `docs` 目录，那么你应该填写 `docs/index.html`.

### HTML5 router

使用HTML5路由器时，您需要设置重定向规则，将所有请求重定向到您的`index.html`，当您使用Netlify时，它非常简单，在`docs`目录填写 `\redirects` 文件，你就完成设置了；

```sh
/*    /index.html   200
```
