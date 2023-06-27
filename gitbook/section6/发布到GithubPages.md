# 发布到 Github Pages

## 将静态网站直接发布到Github Pages
可以将编写好的.md文件通过Gitbook处理成静态网站，然后发布到Github Pages上。


## 使用项目的Pages服务
除了上面的直接发布静态文件到Github Pages的方法以外，还可以使用一个单独的项目的Github Pages功能。

### 创建仓库与分支
登陆到Github，创建一个新的仓库，名称我们就命名为`gitbook-tutorial`，这样我就得到一个`gitbook-tutorial`仓库。
克隆仓库到本地： `git clone git@github.com:/USER_NAME/gitbook-tutorial.git`
创建一个新分支： `git checkout -b gh-pages`，注意，分支名必须为`gh-pages`。
将分支push到仓库： `git push -u origin gh-pages`
切换到主分支：`git checkout master`
经过这一步处理，我们已经创建了`gh-pages`分支了，有了这个分支，Github会自动为你分配一个网址。
```
http://USERNAME.github.io/gitbook-tutorial
```

你可以在项目页面右下角setting中看到：