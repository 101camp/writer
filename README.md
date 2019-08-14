# writer
> wr.101.camp

## bg.

蟒营实战网络课程...

- 101.camp
- 不仅仅针对编程
- 写作也可以


## How2
> 网站如何更新


### 准备
> 作一次就好

在本地创建空目录分别 clone:

- 发布仓库: https://github.com/101camp/wr.101.camp
- 内容仓库: https://github.com/101camp/writer

然后用软链接建立目录关联:

- 进入 writer
- 执行 `ln -s ../wr.101.camp site`
- 即, 在 writer 本地仓库中, 建立一个目录, 指向隔壁 wr.101.camp 仓库目录


### 环境
> 作一次就好


- 本地部署 Python 3.6.0 以上环境
- 使用用 pip 批量安装依赖模块
- 进入 writer
- 执行 `pip install -r requirements.txt`



### 编写+发布

- 所有文档在 docs 目录中
- 如果有新增, 对应:
    + 先在: mkdocs.yml 中配置
    + 然后, 回 docs 中对应文件中编辑
- 发布:
    + 回到 `writer` 根目录
    + 执行 `inv pub`
    + 将完成自动化:
        * 编译
        * 复制
        * 发布
        * 提交


## refer.

- [MkDocs](https://www.mkdocs.org/)

## logging

- 2019-08-14 cnfeat 执行发现反馈，并与大妈解决问题，见[操作日志](https://github.com/101camp/writer/blob/master/OperationLog.md)
- 190809 ZQ init.
