# 介绍

```sh
gitbook install
```

```sh
gitbook server
```

```sh
gitbook build
```

GitBook 是一个支持用 MarkDown 编写文档的软件，支持输出 HTML、PDF、eBook 格式文档。

GitBook 团队曾经提供过一个离线的命令行工具和 Node.js 类库 - gitbook，用来在本地离线环境使用 Markdown 或 AsciiDoc 构建一个电子书，遗憾的是目前这个项目已经被弃用了。

虽然 GitbookIO 的这个 gitbook 工具已经不再维护了，但其仍是目前通过 Markdown 编写可导出的电子书的比较好的工具，且简单易用。


## 支持格式
GitBook支持输出多种文档格式，如：

- 静态站点：GitBook默认输出该种格式，生成的静态站点可直接托管搭载Github Pages服务上；
- PDF：需要安装ebook-concert依赖；
- eBook：需要安装ebook-concert；
- 单HTML网页：支持将内容输出为单页的HTML，不过一般用在将电子书格式转换为PDF或eBook的中间过程；
- JSON：一般用于电子书的调试或元数据提取。

## Gitbook项目地址
- GitBook项目官网：http://www.gitbook.io
- GitBook Github地址：https://github.com/GitbookIO/gitbook
- toolchain https://toolchain.gitbook.com/

