# Git

Первоначальная конфигурация

```bash
git config --global user.name "name"
git config --global user.email "email"
```

```bash
git fetch
git status
git pull
```

```bash
git add .
git add *
git add -A
```

Сбросить все добавленное перед коммитом

```bash
git reset
```

Вернуться к версии файла

```bash
git checkout -- <filename>
```

```bash
git checkout 03ecdd7
git checkout HEAD
git checkout HEAD^
git checkout HEAD^^^
git checkout HEAD~6
```

```bash
git log --pretty=oneline
git log --pretty=oneline --all -> ???
git log --pretty=oneline --graph
git log --pretty=format:'%h %ad | %s%d' --date=short
```

```bash
git revert HEAD -> отменить коммит
git revert HEAD --no-edit -> отменить без редактирования
если произошли конфликты git status
git revert --continue
git revert --abort -> отменить процесс реверта
добавить или удалить конфликтные файлы git add/rm, затем закоммитить
```

Список веток

```bash
git branch
```

Новая ветка

```bash
git branch <newbranch>
```

Перейти на ветку

```bash
git checkout <branchname>
```

Создайть и перейти на ветку

```bash
git checkout -b <newbranch>
```

Залить в текущую ветку из somebranch

```bash
git merge <somebranch>
```

```bash
Команда git cherry-pick используется для того чтобы взять изменения, 
внесённые каким-либо коммитом, и попытаться применить их заново в виде 
нового коммита наверху текущей ветки. Это может оказаться полезным 
чтобы забрать парочку коммитов из другой ветки без полного слияния с той веткой.
$ git cherry-pick <commitnumber>
```