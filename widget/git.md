# git 如何忽略已经加入到版本控制的文件

1. 增加 .gitignore 文件，里面添加需要忽略的文件(file_not_wanted)；
2. 执行命令 git rm -r --cached .  注意，最后的点。不要省略。
3. 最后重新将所有文件添加到追踪项。

## git rm 与 git rm --cached

当我们需要删除暂存区或分支上的文件, 同时工作区也不需要这个文件了, 可以使用

```git
git rm file_path
git commit -m 'delete somefile'
git push
```

当我们需要删除暂存区或分支上的文件, 但本地又需要使用, 只是不希望这个文件被版本控制, 可以使用

```git
git rm --cached file_path
git commit -m 'delete remote somefile'
git push
```

## git 强制拉取

```git
git fetch --all
git reset --hard origin/master
```
