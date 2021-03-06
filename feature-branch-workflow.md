# 功能分支工作流

功能分支工作流在集中式工作流的基础上又扩展了一下。在集中式工作流里，大家都往远程的一个 master 分支上 push 提交，使用功能分支工作流，开发者不直接向 master 上 push，他们在各自的本地创建新的分支，去开发新功能，去修复 Bug ，去实验自己的想法。

完成以后，开发者可以把这些功能分支 push 到远程仓库，然后可以提交一个 pull request，这样可以跟项目的其他协作开发者之间进行交流，确定没什么问题以后，就可以把推送上来的功能分支合并到 master 分支上。

## 练习

实践使用功能分支工作流进行开发。

### 小雪有了新任务

小雪收到新任务，她要去写一个关于 Git 工作流的文档。因为现在我们决定用功能分支工作流来协作开发了，所以对项目的修改不直接在 master 分支上做，需要去创建一个新的分支。小雪进入她的项目所在的目录（ xiaoxue-git） ，执行了：

```
git checkout -b workflow-doc master
```

基于 master 分支创建一个新分支（workflow-doc），并切换到这个新分支上。

小雪在项目下新建了一个文档：

```
touch workflow.md
```

做了一次提交：

```
git add .
git commit -m '添加介绍工作流的文档'
```

她又开始写这个文档：

```
# 工作流

* 集中式工作流
* 功能分支工作流
* Gitflow 工作流
```

又做了一次提交：

```
git commit -am '列出几种 Git 工作流'
```

### 小雪完成了任务

小雪觉得完成了任务，写完了关于介绍工作流的文档。她决定把自己的工作 push 到远程，让大家看看：

```
git push origin workflow-doc
```

返回：

```
Counting objects: 6, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (5/5), done.
Writing objects: 100% (6/6), 599 bytes | 0 bytes/s, done.
Total 6 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
To https://github.com/ninghao/ninghao-git.git
 * [new branch]      workflow-doc -> workflow-doc
```

push 成功~  她又决定去开一个 pull request ，跟大家讨论一下自己写的文档。

