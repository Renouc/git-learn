# Git 基础

## 获取 Git 仓库

### 将尚未进行版本控制的本地目录转换为 Git 仓库

```bash
git init
```

### 从其它服务器 克隆 一个已存在的 Git 仓库。

```bash
git clone https://github.com/libgit2/libgit2
```

> 上述命令会将项目克隆到 libgit2 目录下。

```bash
git clone https://github.com/libgit2/libgit2 mylibgit
```

> 上述命令会将项目克隆到 mylibgit 目录下。

## 检查仓库状态

```bash
git status
```

```bash
git status -s
```

> -s 显示更简洁的输出。

## 忽略文件

```bash
# 忽略所有的 .a 文件
*.a
# 但跟踪所有的 lib.a，即便你在前面忽略了 .a 文件
!lib.a
# 只忽略当前目录下的 TODO 文件，而不忽略 subdir/TODO
/TODO
# 忽略任何目录下名为 build 的文件夹
build/
# 忽略 doc/notes.txt，但不忽略 doc/server/arch.txt
doc/*.txt
# 忽略 doc/ 目录及其所有子目录下的 .pdf 文件
doc/**/*.pdf
```

> GitHub 有一个十分详细的针对数十种项目及语言的 .gitignore 文件列表， 你可以在 https://github.com/github/gitignore 找到它。

## 删除文件

当在工作目录中手动删除文件之后，需要将暂存区中的文件也删除。

````bash
git add <file>
```bash
````

或者

```bash
git rm <file>
```

## 将文件从暂存区移除

```bash
git rm --cached <file>
```

```bash
git reset HEAD <file>
```

> 将文件从暂存区移除，但保留在工作目录中。

## 移动文件

```bash
git mv <file> <new-file>
```

这样会将文件从暂存区中移除，并添加到新的文件名。

其实运行了三个命令：

```bash
mv <file> <new-file>

git rm <file>

git add <new-file>
```

## 查看提交历史

```bash
git log
```

- `-p` 显示提交文件的修改内容

- `-stat` 显示提交文件的修改统计

- `--decorate` 显示分支信息，如标签等；在最新版本中默认开启

```bash
git log --graph
```

> 显示提交历史树状图

```bash
git log --oneline --graph
```

## 替换上一次提交

```bash
git commit --amend
```

## 查看远程仓库

```bash
git remote
```

```bash
git remote -v
```

> -v 显示所有远程仓库的 URL

```bash
git remote show <remote>
```

> 显示指定远程仓库的信息

## 添加远程仓库

```bash
git remote add <shortname> <url>
```

## 推送到远程仓库

```bash
git push <remote> <branch>
```

## 远程仓库重命名

```bash
git remote rename <oldname> <newname>
```

## 远程仓库删除

```bash
git remote rm <name>
```
