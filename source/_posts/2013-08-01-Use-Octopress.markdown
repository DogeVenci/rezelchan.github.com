---
layout: post
title: "Use Octopress"
date: 2013-08-01 11:35
comments: true
categories: [web,github,jekyll,octopress,ruby]
---
**Blogging like a Geek!** 
<!--more-->
###Install
**In Windows:**  
[Msysgit](https://code.google.com/p/msysgit/downloads/list)  
[Ruby](http://files.rubyforge.vm.bytemark.co.uk/rubyinstaller/rubyinstaller-1.9.3-p429.exe)  
[DevKit](http://cloud.github.com/downloads/oneclick/rubyinstaller/DevKit-tdm-32-4.5.2-20111229-1559-sfx.exe)  
[Python](http://www.python.org/download/)  
Octopress:`git://github.com/imathis/octopress.git`  
----------------------------------
#### Install DevKit  
```
cd DevKit
ruby dk.rb init
ruby dk.rb install
```
#### Install pygments
安装Python,[easy_install](https://pypi.python.org/pypi/setuptools)  
`easy_install pygments`
#### Install Octopress
```
git clone git://github.com/imathis/octopress.git octopress
```
更改源:  
```
gem sources -a http://ruby.taobao.org/
gem sources -r http://rubygems.org/
gem sources -l
```
同时修改Octopress目录下的Gemfile里的源.  
安装依赖项:  
```
gem install bundler
bundle install
rake install
```
#### In Linux
```
sudo apt-get update; sudo apt-get install git
curl -L https://get.rvm.io | bash -s stable --ruby
gem install bundler
bundle install
```  
----------------------------
### Preview
```
rake new_post['Hello World']
```
编辑在**source/_posts** 生成Markdown文件.[Markdown Reference](http://wowubuntu.com/markdown/)  
```
rake generate #生成
rake preview #可以在浏览器localhost:4000预览
```
#### **中文问题**
```
set LANG=zh_CN.UTF-8 
set LC_ALL=zh_CN.UTF-8
```
含有中文的文件需要**Save whit Encoding UTF-8 without BOM**,
修改ruby目录`\lib\ruby\gems\1.9.1\gems\jekyll-0.12.0\lib\jekyll\convertible.rb`文件中  
`self.content = File.read(File.join(base, name), :encoding => 'utf-8')`  
----------------------------
### Deploy
在github上新建一个以自己用户名**username**.github.com的repository.  
在Octopress中`rake setup_github_pages` 安装提示输入新建的repository地址,
最后`rake deploy`部署到github page.  
提交source分支备份.
