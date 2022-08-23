
## 简述
下载本仓库代码，修改CNAME文件，添加自己的文章，将本仓库代码推送github，即可访问自己的博客。

## 使用步骤

#### 第一步 *获取源码* 下载这个hexo模板的代码

git 下载代码

`git clone https://e.coding.net/frednab/dev/blog-mould.git`

>未安装git可通过下载github源码获得该项目[源码](https://github.com/denalon/hexo-mould)

下载完毕后删除.git文件夹

`rm -rf .git` 或在windows平台显示隐藏文件，删除隐藏的.git文件夹。


#### 第二步 *修改配置* 修改hexo的配置

修改 **source/CNAME**文件里的域名


**此仓库已经预置butterfly主题**


通过修改_config.butterfly.yml来改变主题的配置，如主题颜色，样式，插件等。

通过修改_config.yml来改变hexo站点的配置，如站点标题，语言，目录等。

**其他文件不需要配置**

#### 第三步 *更新文章* 撰写或者将之前的文章复制到source/_posts目录下

通过`hexo new page 文章.md`新建文档

或者在source/_posts目录下撰写自己的文章


#### 第四步 *发布博客* 通过多种方式发布博客

##### 方式一 本地运行hexo的http服务来浏览博客

> 需要本地服务器安装nodejs和npm

执行如下命令安装hexo

```
npm install -g hexo-cli
```
执行如下命令安装该项目的依赖
```
npm ci
```
执行如下命令来运行hexo的http服务

```
hexo server
```

##### 方式二 生成静态文件,部署到nginx或IIS

> 需要本地服务器安装nodejs和npm

执行如下命令安装hexo

```
npm install -g hexo-cli
```

执行如下命令安装该项目的依赖
```
npm ci
```

执行如下命令生成html静态文件
```
hexo g
```

生成html静态文件夹public，配合nginx或iis来部署静态网站。或者上传到虚拟主机，云服务器上部署。



##### 方式三 将源码推送到github，触发github actions自动构建

通过以下命令将该仓库里的源码推送到github仓库

**删掉目录下的.git目录再执行如下操作**

```
git init //初始化仓库。
git add . //添加文件到暂存区。(注意有点号.)
git commit -m "更新说明" //将暂存区内容添加到仓库中。标识“更新说明”
git remote add origin XXXX.git  //添加到远程仓库操作，将xxxx.git设置为远程仓库origin
git push -u origin main  //推送main分支到origin仓库
```

>以上代码推送到远程分支的main分支，如果本地是master分支可以执行`git push origin master:main`推送本地master分支代码到远程main分支。

提示操作成功后，代码将推送到github上的main分支，github自动部署将启动，将hexo文件自动部署到gh-pages分支

**由于该仓库含有github自动构建文件，上传到github将触发自动部署**

github自动构建文件为 `.github/workflows/hexodeploy.yml`文件

#### 第五步 *开启pages* 登录github 设置界面配置pages服务

**请确保仓库里source/CNAME文件域名已经正确修改**

在github仓库 “Settings”选择“GitHub Pages” source项选择Branch:gh-pages
如图：![github pages设置](https://base.oribos.city/images/2020/10/20201022095332.png)

即可使用由github自动部署的 pages 服务。


