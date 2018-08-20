## git 常用命令

- 查看当前分支
```
git branch
```


- 切换分支
```
git checkout  分支名称
```

- 创建分支并切换到创建的分支上
```
git checkout -b 分支名
```

- 检出远程分支到新建的分支上
```
git checkout -b 本地分支名 origin/远程分支名
```

- 检出 (暂存区 |  历史区) 的内容覆盖 工作区的内容
```
// （ 暂存区 | 历史区最后一个commit版本 ） =》  工作区  就是让这个文件回到最近一次git commit或git add时的状态。
//检出（暂存区或者历史区） 指定文件
git checkout 文件
// 当文件路径和分支名称一样时。加--表示检出文件名  如果不加就表示是切换分支
git checkout -- a
```

- 检出 某个(分支 | 提交id | tag )的内容 覆盖工作区内容 
```
// 将commitId 对应的文件内容 覆盖到当前工作 和 暂存区(会丢失暂存区相同文件名的暂存数据)
git checkout commitId -- 文件路径
// 将分支最后一次提交的文件内容  覆盖到当前工作 和 暂存区(会丢失暂存区相同文件名的暂存数据)
git checkout 分支名 -- 文件路径

``` 


[参考文献](https://www.cnblogs.com/kuyuecs/p/7111749.html)


- 暂存区文件恢复到工作区
```
git reset HEAD 文件路径
```

- 拉取远程分支到当前分支上（必须是同意分支）
```
git pull origin 远程分支名
```


- 合并分支代码
```
git merge 分支名
```


- 查看版本库
```
git log | --pretty=oneline(简化的版本信息) 
```

- 查看指定文件相关的commit记录
```
git log 文件名  
```

- 查看指定文件相关的commit记录,每次提交的diff
```
git log -p 文件名 
```

- 用来记录你的每一次命令
```
git reflog
```

- 分支回滚~~
```
git reset --hard 回滚哈希值
```

- 工作区 =》 暂存区 
```
// 单个文件转移
git add （ 文件路径 ) 
// 多个文件转移 
git add （ . | -All ) 
```

- 比较工作区 和 暂存区的差异
```
// 所有文件的不同
git diff 
// 单个文件的不同
git diff 文件路径
```

- 比较 工作区 和 历史区（最后一次commit）代码的不同
```
// 比较所有文件
git diff HEAD 
// 比较指定文件
git diff HEAD 文件路径
```

- 比较 工作区 和 指定commit-id 的差异
```
// 比较所有文件
git diff commit-id
// 比较指定的文件
git diff commit-id 文件路径 
```

- 比较 暂存区 和 历史区(最后一次commit)代码的不同
```
// 所有文件的不同
git diff --cached
// 比较指定文件的不同
git diff --cached git.md
```

- 比较 暂存区 和 指定commit-id 的差异
```
// 所有文件的差异
git diff --cached commit-id 
// 比较指定文件的差异
git diff --cached commit-id 文件路径
```

- 比较 两个commit 之间的差异
```
git diff commit-id  commit-id
```

- 比较两个分支的文件的差异
```
// 比较分支branch1和branch2 的差异 --stat不显示详细差异 只显示差异的文件名
git diff branch1 branch2 --stat 
// 比较分支branch1 和 branch2 的差异 显示差异详情
git diff branch1 branch2 
// 比较分支branch1 和 branch2 中指定文件的差异
git diff branch1 branch2 git.md
```


