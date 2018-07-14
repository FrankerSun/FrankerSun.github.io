---
layout: post
title: "jekyll about"
category: 
excerpt: ""
tags: []
---

## jekyll 相关记录

```shell
$ gem install bundler jekyll
$ jekyll new my-awesome-site
$ cd my-awesome-site
$ bundle exec jekyll serve
# => Now browse to http://localhost:4000
```


#### RubyGems更新

```shell
$ gem update --system # 这里请翻墙一下
$ gem -v
2.6.3
```


#### bundle使用国内镜像

```shell
$ bundle config mirror.https://rubygems.org https://gems.ruby-china.com
```


#### gem update/bundle install 证书验证错误  

```
方法  
下载 https://curl.haxx.se/ca/cacert.pem  
设置环境变量SSL_CERT_FILE=${cacert.path}\cacert.pem  
```



#### 3 本地运行jekyll

```shell
$ bundle exec jekyll serve
```

  　　


#### 参考资料
<a href="http://gems.ruby-china.org/" target="_blank">RubyGems中国镜像</a>  
<a href="https://jekyllrb.com/" target="_blank">Jeykll</a>  