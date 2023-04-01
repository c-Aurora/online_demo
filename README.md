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
```
例如我的：https://c-aurora.github.io/online_demo/