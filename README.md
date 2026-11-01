# Git 练习沙盒

这个文件夹是给你练手用的。里面故意放了几个文件，用来演示"改动 → 暂存 → 提交"的完整过程。

## 现在就可以做的第一步

打开终端，进入这个目录：

```bash
cd "C:/Users/jgdf/WorkBuddy/2026-11-01-16-54-32/git-practice"
```

然后按顺序敲，每敲一条就用 `git status` 看一眼状态变化：

```bash
git init
git status
git add .
git status
git commit -m "第一次提交：建立练习项目"
git log --oneline
```

## 第二步：制造一点改动

打开 `notes.txt`，随便改一行或者加一行，保存。然后：

```bash
git status          # 会看到 notes.txt 变红，说明有未跟踪/未暂存的改动
git diff            # 看具体改了什么，按 q 退出
git add notes.txt
git commit -m "更新笔记"
git log --oneline   # 现在应该有两条记录了
```

## 第三步：体会 .gitignore

`.gitignore` 里写了 `*.log` 和 `secret/`。现在新建一个文件试试：

```bash
echo "test" > debug.log
git status          # debug.log 不会出现在列表里，被忽略了
```

这就是防止把日志、密钥、依赖包误传上去的机制。

## 第四步（等注册好 GitHub 再做）

```bash
git remote add origin https://github.com/你的用户名/仓库名.git
git push -u origin main
```

## 卡住了怎么办

任何一步不确定，先敲 `git status`。Git 本身会告诉你当前在哪个分支、有哪些改动、下一步大概该做什么。
