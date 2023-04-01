## 如何在github上在线演示项目

### 首先创建一个新的项目，创建就不多说了，相信用过github的小伙伴都会


### 然后克隆你的项目到本地
```javascript
git clone 项目地址
```
### 然后正常的创建项目和提交代码
```javascript
cd  创建的项目
git add .
git commit -m '提交master上代码' //注意我们是在master主分支上。（当前是只有master分支的）
git push
```
### 最关键的来了，建立gh-pages分支，再将项目重新上传到该分支上
master分支仅是浏览代码，而无法将页面直接在网页打开，而gh-pages分支则是用于直接浏览源码页面的分支。当我们写项目的时候，需要部署一个预览页面，就可以采用github的gh-pages分支制作GitHub Pages
```javascript

git checkout -b gh-pages  //新建一个gh-pages分支并切换到该分支 创建分支

//分开来就是 创建分支：git branch <分支名>    git checkout <分支名>

git add .
git commit -m "提交gh-pages上代码"
git push -u origin gh-pages

接下来就可以成功访问啦!

`访问地址 https://用户名.github.io/项目名称/文件路径`

网址实在记不住的话可以点击github上你项目右上角Settings->左边pages->第一行GitHub Pages就有你的网址
```
例如我的：https://c-aurora.github.io/online_demo/

### 但是，我每次都要上传两份代码，太繁琐了

master修改后如何自动同步到gh-pages分支
每次当作品发生更改变动后，要先提交到master分支然后切换到gh-pages分支又重新提交一次，显然这个过程非常繁琐。接下我们介绍一种方法，只需提交到master分支即可，gh-pages分支无需重新提交，就可实现在线预览：

打开github项目文件的根目录，先找到.git 这个文件夹（文件夹默认是隐藏的），然后找到config这个文件，并打开该文件，将以下两行添加到[remote "origin"]部分

push = +refs/heads/master:refs/heads/gh-pages
 
push = +refs/heads/master:refs/heads/master

测试了下，可以