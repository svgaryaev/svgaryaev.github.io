# Git

## Первоначальная конфигурация

```bash
git config --global user.name "name"
git config --global user.email "email"
```

## Синхронизация

```bash
git fetch
git status
git pull
git pull --rebase
```

## Индексация

```bash
git add .
git add *
git add -A
```

## Отмена изменений

### Отмена локальньных изменений

```bash
git reset # отменить индексирование
git reset --soft <commit_hash> - откатиться до конкретного коммита
git reset --hard # отменить все изменения
git checkout -- <filename> # вернуться к версии файла
```

### Отмена общих изменений

```bash
git revert HEAD -> отменить коммит
git revert HEAD --no-edit -> отменить без редактирования
если произошли конфликты git status
git revert --continue
git revert --abort -> отменить процесс реверта
добавить или удалить конфликтные файлы git add/rm, затем закоммитить
```

```bash
git checkout 03ecdd7
git checkout HEAD
git checkout HEAD^
git checkout HEAD^^^
git checkout HEAD~6
```

## История

```bash
git log --pretty=oneline
git log --pretty=oneline --all -> ???
git log --pretty=oneline --graph
git log --pretty=format:'%h %ad | %s%d' --date=short
```

## Stash

```bash
git stash # спрятать изменения
git stash apply # вернуть последние изменения
git stash list # вывести список
git stash apply <stash@{2}> # вернуть конкретные изменения
```

## Ветки

```bash
git branch # вывести список всех веток

git branch <newbranch> # создать новую ветку
git checkout <newbranch> # перейти на ветку

git checkout -b <newbranch> # сокращение для предыдущих двух

git push -u origin <newbranch> # добавить ветку на github
# -u is short for --set-upstream option
```

## Слияние

### merge

```bash
git merge <branch>
```

### cherry-pick

Команда git cherry-pick используется для того чтобы взять изменения, внесённые каким-либо коммитом, и попытаться применить их заново в виде нового коммита наверху текущей ветки. Это может оказаться полезным чтобы забрать парочку коммитов из другой ветки без полного слияния с той веткой.

```bash
git cherry-pick <commitnumber>
```
