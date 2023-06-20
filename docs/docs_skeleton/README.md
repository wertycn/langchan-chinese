# 网站

本网站使用[Docusaurus 2](https://docusaurus.io/)构建，这是一个现代静态网站生成器。

### 安装

```
$ yarn
```

### 本地开发

```
$ yarn start
```

该命令启动本地开发服务器并打开浏览器窗口。大多数更改都会即时反映在服务器上，无需重启服务器。

### 构建

```
$ yarn build
```

该命令将静态内容生成到`build`目录中，可以使用任何静态内容托管服务进行提供。

### 部署

使用SSH：

```
$ USE_SSH=true yarn deploy
```

不使用SSH:

```
$ GIT_USER=<Your GitHub username> yarn deploy
```

如果您正在使用GitHub Pages进行托管，这个命令是一种方便的方式来构建网站并推送到`gh-pages`分支。

### 持续集成

一些常见的代码检查和格式化默认设置已经为您设置好了。如果您将项目与一个开源的持续集成系统（如Travis CI、CircleCI）集成，您可以使用以下命令检查问题。

```
$ yarn ci
```
