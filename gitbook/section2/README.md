# 安装

## 安装 CLI

全局安装它，您将可以在系统的任何位置访问 gitbook 命令。
```
$ npm install gitbook-cli -g
```

使用上面命令安装，依赖的 graceful-fs 版本有问题，降低版本安装
```
$ npm install -g gitbook-cli@2.2.0
$ gitbook fetch 3.2.3
```

安装完成之后，你可以使用下面的命令来检验是否安装成功
```
$ gitbook -V
CLI version: 2.2.0
GitBook version: 3.2.3
```

## GitbookCLI命令行使用
GitbookCLI 是一个命令行工具，使用方法：

## 初始化
初始化一本书

```
$ gitbook init
```
在使用 gitbook init 之后本地会生成两个文件 README.md 和 SUMMARY.md ，这两个文件都是必须的，一个为介绍，一个为目录结构。

## 编辑目录
也可以自己预先定义好 SUMMARY.md 中的目录结构，然后再用 init 命令初始化，程序将会根据我们的目录结构生成目录和文件，目录结构示例：

```
# Summary

* [介绍](README.md)
* [安装](section1/安装.md)
* [目录结构](section2/目录结构.md)
    * [README.md 与 SUMMARY.md 编写](section2/README.md与SUMMARY.md编写.md)
```

## 本地预览
当内容书写完毕后，可以在终端中输入如下命令，实现实时预览

```
$ gitbook serve
$ gitbook serve ./{book_name}
```
gitbook serve 命令实际会先调用 gitbook build 编译书籍，完成后打开 web 服务器，默认监听本地 4000 端口，在浏览器打开 http://localhost:4000 即可浏览电子书。

## 发布电子书

```
$ gitbook build
$ gitbook build ./{book_name} --output=./{outputFolde}
$ gitbook build ./ --log=debug --debug
```
当电子书内容制作好之后，可以使用如下命令来生成 HTML 静态网页版电子书。该命令会在当前文件夹中生成 _book 文件夹，这个文件夹中的内容就是静态网页版电子书。

使用 --log=debug --debug 可以用来调试，会打印出 stack trace。

## 查看帮助

```
$ gitbook -h

  Usage: gitbook [options] [command]

  Commands:

    build [options] [source_dir] Build a gitbook from a directory
    serve [options] [source_dir] Build then serve a gitbook from a directory
    install [options] [source_dir] Install plugins for a book
    pdf [options] [source_dir] Build a gitbook as a PDF
    epub [options] [source_dir] Build a gitbook as a ePub book
    mobi [options] [source_dir] Build a gitbook as a Mobi book
    init [source_dir]      Create files and folders based on contents of SUMMARY.md
    publish [source_dir]   Publish content to the associated gitbook.io book
    git:remote [source_dir] [book_id] Adds a git remote to a book repository

  Options:

    -h, --help     output usage information
    -V, --version  output the version number

```

## gitbook init 报错：
TypeError [ERR_INVALID_ARG_TYPE]: The "data" argument must be of type string or an instance of Buffer, TypedArray, or DataView. Received an instance of Promise

(node.js 版本问题，不影响使用)