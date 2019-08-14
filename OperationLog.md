# OperationLog

按照 `https://github.com/101camp/writer` 操作

执行到 `pip install -r requirements.txt` 出错

报错界面如下

![mkA8Rs.jpg](https://s2.ax1x.com/2019/08/14/mkA8Rs.jpg)
 
大妈提醒：

> 果然, 都说了, Python 3.5.* 以上, 
> Py2 官方都已经停止维护了...



![mkAHyt.jpg](https://s2.ax1x.com/2019/08/14/mkAHyt.jpg)

> 推荐通过 Pyenv 来部署用户目录中的安全 Python 版本环境吧...

给了个班长的链接：[怎么才能放飞自我的玩儿Python · Yixuan](https://yixuan.li/geek/2018/07/31/pyenvVirtualenv/)

一顿操作过之后，还是不行，报错如下

![mkAQIg.png](https://s2.ax1x.com/2019/08/14/mkAQIg.png)
 
 大妈又说：
 
>安装错地方了...
>根据官方文档来吧...

> pyenv/pyenv: Simple Python version management
> https://github.com/pyenv/pyenv

> 大致了解一下, 然后,根据:
> pyenv/pyenv-installer: This tool is used to install `pyenv` and friends.
> https://github.com/pyenv/pyenv-installer

> 安装
> 编译新 Python 版本前, 要增补一些编译支持包:
> Common build problems · pyenv/pyenv Wiki
> https://github.com/pyenv/pyenv/wiki/Common-build-problems


> 然后, 参考班长的说明, 
> 配合 pyenv/pyenv-virtualenv: a pyenv plugin to manage virtualenv (a.k.a. python-virtualenv)
> https://github.com/pyenv/pyenv-virtualenv

> 就可以自在了...

> 比如, 俺都是安装一个主版本

> $ pyenv install 3.7.5

> 然后,根据项目情况复制一个工程版本

> $ pyenv virtualenv 3.7.5 101camp

> 然后, 将工程版本绑定到对应工程目录根

> cd path/2/101camp/0wr
> pyenv local 101camp

> 就完成了独立环境部署,
> 和其它工程以及系统都是分离的


然后我就

1、补了个编译包：

```brew install readline xz```

2、重装了 `python`

https://www.python.org/

3、重装了 `pyenv`： 

```
brew update
brew reinstall pyenv
```

4、安装 `pyenv-virtualenv` ：

```brew install pyenv-virtualenv```

5、在 `/.bash_profile` 中加入

```
export PATH="~/.pyenv/bin:$PATH"    
eval "$(pyenv init -)"    
eval "$(pyenv virtualenv-init -)"
```

6、再回到 `writer`：

```
pip install -r requirements.txt
```

继续报错

![mkVnUS.png](https://s2.ax1x.com/2019/08/14/mkVnUS.png)

大妈云

> 终于到最后了, 这是俺的问题....
> 是也乎,(￣▽￣)
> 还真的...俺忘记了, 网站 theme 也得安装的...
> 俺增补到  requirements.txt 中了,
> 重新 pip install -r requirements.txt 
> 就好...
> 对应少的应该是
> mkdocs-bootswatch


接着大妈分享他的 `alias`

```
[alias]
    st = status
    re = remote
    br = branch
    ci = commit
    co = checkout
    pu = push
    pl = pull
    del = rm
    brdr = push origin --delete
    brd = branch -D
    f = fetch
    rvl = commit --amend
    ls = ls-files
    lt = ls-tree
    cat = cat-file
    l = log
    l1 = log --pretty=oneline
    lgs = log --graph --pretty=oneline --abbrev-commit
    ll = log --graph --pretty=format:'%C(yellow)%h%Creset -%C(magenta)%d%Creset %s \n\t%cn %C(cyan)%cr%Creset' --date=relative --abbrev-commit

    # https://docs.gitignore.io/install/command-line
    #   git config --global alias.ignore '!gi() { curl -L -s https://www.gitignore.io/api/$@ ;}; gi'
    ig = "!gi() { curl -L -s https://www.gitignore.io/api/$@ ;}; gi"

    #   https://github.com/ahmadawais/Emoji-Log/
    # Git Commit, Add all and Push — in one step.
    cap = "!f() { git add .; git commit -m \"$@\"; git push; }; f"

    # NEW.
    new = "!f() { git cap \"📦 NEW: $@\"; }; f"
    # IMPROVE.
    imp = "!f() { git cap \"👌 IMPROVE: $@\"; }; f"
    # FIX.
    fix = "!f() { git cap \"🐛 FIX: $@\"; }; f"
    # RELEASE.
    rlz = "!f() { git cap \"🚀 RELEASE: $@\"; }; f"
    # DOC.
    doc = "!f() { git cap \"📖 DOC: $@\"; }; f"
    # TEST.
    tst = "!f() { git cap \"✅ TEST: $@\"; }; f"

    # DEBUG.
    dbg = "!f() { git cap \"💊 DEBUG: $@\"; }; f"
    # APPEND.
    apd = "!f() { git cap \"📎 APPEND: $@\"; }; f"
    # BACKUP.
    bak = "!f() { git cap \"♻️ BACKUP: $@\"; }; f"
    # PUBLISH.
    pub = "!f() { git cap \"🛎 PUBLISH: $@\"; }; f"
```

感觉不用大妈的 `alias` 应该也可以

我就不动  `~/.gitconfig` 了

直接同步大妈已在仓库更新的 `requirements.txt`

继续在 `writer`

```
pip install -r requirements.txt
```

再执行 `inv pub`

终于发现 `wr.101.camp` 中的文件更新了

![mkALef.jpg](https://s2.ax1x.com/2019/08/14/mkALef.jpg)

接着 push `wr.101.camp` 

我测试写的几行小字终于更新在官网了

![mkAvFg.jpg](https://s2.ax1x.com/2019/08/14/mkAvFg.jpg)

感动……

## 相关链接

- https://github.com/101camp/writer
- https://github.com/101camp/wr.101.camp
- https://wr.101.camp
