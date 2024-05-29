# 简易官网 EasyHomePage

这个项目是我用来做我个人主页的，采用 Vue3 + Vite 构建。

做这个项目的初衷是，我想要一个简单个人官网，但遇到 2 个问题：

1. 我希望更新网页里的内容是简单的，简单到可以使用 Markdown 文件来更新
2. 我希望可以直接托管在 Github Pages 上，而不需要自己搭建服务器

对于第 2 个原因，很直接的思考不是服务器需要多少费用，而是，总有一天我会离开这个世界，而我相信 Github 可能会比我活的时间更长。

## 项目结构

* 页面代码在 `src` 目录下，`public` 目录下是一些静态资源。
* 根目录下的 `contents` 目录是用来存放 Markdown 文件的，这些文件在编译时会被读取，然后生成对应的页面。
* `.github/workflows` 目录下是 Github Actions 的配置文件，用来自动部署到 Github Pages。

## 如何使用

1. 克隆这个项目
2. 在你的项目里创建一个新分支：`gh-pages` ，然后在项目设置里配置好你的域名
3. 在项目的 Actions 里配置，允许 Workflow 进行读写操作
4. 修改 `contents` 目录下的 Markdown 文件，以及你希望修改的其它页面，推送回 `main` 分支
5. 等待 Actions 自动部署，然后访问你的域名，搞定！

当然，你也可以在本地运行这个项目，方法也非常简单：

进入开发环境：

```bash
npm install && npm run dev
```

写完后，构建和运行：

```bash
npm run build && npm start
```

接着用 Nginx 设置一下反向代理，套个 SSL 证书，就可以直接访问了。
