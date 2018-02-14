一个高效的博客系统

https://hexo.io/zh-cn/docs/index.html#%E4%BB%80%E4%B9%88%E6%98%AF-Hexo%EF%BC%9F

一个hexo的皮肤

https://github.com/iissnan/hexo-theme-next

how to make a hexo

http://windrunnerlihuan.com/2016/05/27/%E5%8D%9A%E5%AE%A2%E6%90%AD%E5%BB%BA%E5%8E%86%E7%A8%8B/#more
http://www.lovebxm.com/2017/05/30/buildBlog

FAQ   
Q: 我输入hexo server后在4000端口并没有显示网页。有时会循环打印HEART，这是怎么回事   
A: 端口占用，hexo server -p 4001,或者其它的
    
Q: 备份源代码1    
A1： 换了一台新电脑需要重新部署hexo，首先按照网上搭建hexo的过程一步步重新在新电脑上操作，之后只要用原电脑的scaffolds, source, themes 和 _config.yml替换新生成的文件就行了    
A2:    
```
可以更新使用最新的 hexo-deployer-git 插件，因为没有发布到 npm 的原因，必须得从 github 安装npm install git+git@github.com:hexojs/hexo-deployer-git.git --save
在项目根目录下的 _config.yml 里面就可以这样配置# _config.yaml
deploy:
  - type: git
    repo: git@github.com:<username>/<username>.github.io.git
    branch: master
  - type: git
    repo: git@github.com:<username>/<username>.github.io.git
    branch: src
    extend_dirs: /
    ignore_hidden: false
    ignore_pattern:
        public: .
这样，在每次写完博客的时候时候使用 hexo d 命令就能将所有其他文件发布到 src 分支换电脑的时候就能通过 git 重新下载下来整个项目，然后本地切换到远端的 src 分支git checkout origin/src
就能重新获得所有的源文件，就能重新 hexo d 发布对于每一个从 git 下载下来的项目或者主题，最好把每个的 .git 文件夹删掉，否则得通过 submodule 的方式来安装。
```
