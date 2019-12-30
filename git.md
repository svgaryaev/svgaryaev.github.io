# Git

## Первоначальная конфигурация

```bash
git config --global user.name "name"
git config --global user.email "email"
git config --global core.editor "nano"
git config --global core.autocrlf true # автоматически конвертирует CRLF в LF и обратно
```

## Создание

```bash
$ git init <название проекта>
$ git clone <url-адрес>
```

## Синхронизация

```bash
git status
git fetch [remote] # скачивает историю с удаленного репозитория
git merge [remote]/[branch] # сливает изменения из ветки удаленного репозитория в текущую ветку локального
git pull # сочетание git fetch и git merge
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
git commit --amend # поменять название последнего коммита
git add <file>
git commit --amend # добавить файл к последнему коммиту
```

```bash
git reset # отменить индексирование
git reset --soft HEAD^ # отменить последний коммит (изменения останутся в индексе)
git reset --soft <commit_hash> # откатиться до конкретного коммита (изменения останутся в индексе)
git reset --hard # отменить все изменения и откатиться
git checkout -- <filename> # вернуться к версии файла
git reset --hard origin/master # сбросить ветку до текущего состояния другой ветки
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

## Сохранение фрагментов

```bash
git stash # временно сохраняет все незафиксированные изменения отслеживаемых файлов
git stash push -u -m "Message" # с учетом неотслеживаемых файлов и сообщением
git stash list # выводит список всех временных сохранений
git stash apply # восстанавливает состояние ранее сохранённых версий файлов
git stash pop # восстанавливает состояние ранее сохранённых версий файлов и удаляет их из сохранений
git stash drop # сбрасывает последние временно сохраненныe изменения
git stash show # показать информацию о последнем временном сохранении
git stash show -p # показать подробную информацию о последнем временном сохранении
git stash apply|pop|drop|show <stash@{2}> # производит действие с выбранным сохранением
git stash --keep-index # не учитывает stage файлы
```

## Слияние коммитов - сквош

Заранее лучше указать предпочитаемый редактор, чтобы vim не застал врасплох.

```bash
git rebase -i HEAD~6 # количество коммитов для сквоша
```

Затем в интерактивном режиме пометить сливаемые коммиты меткой "squash" или просто "s". Коммиты идут не как в git log, а от более раннего к позднему, поэтому первый коммит оставляем "pick", а все остальные помечаем. Сохраняем изменения. В новом окне удаляем лишние названия коммитов, оставляя одно. Сохраняем изменения.

```bash
git reset --soft `git merge-base HEAD <base-branch>` # работает в gnu окружении из-за вызова
# git merge-base возвращает хеш подходящего для слияния коммита
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
git merge <branch> # сливает изменения из указанной ветки в текущую ветку
```

### cherry-pick

Команда git cherry-pick используется для того чтобы взять изменения, внесённые каким-либо коммитом, и попытаться применить их заново в виде нового коммита наверху текущей ветки. Это может оказаться полезным чтобы забрать парочку коммитов из другой ветки без полного слияния с той веткой.

```bash
git cherry-pick <commitnumber>
```

## Алиасы

```bash
git config --global alias.co checkout
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.br branch
git config --global alias.hist "log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short"
```

## Уход за репозиторием

В больших репозиториях при переключении с ветки на ветку, коммитах, ребейзе может появляться сообщение

> `Auto packing the repository for optimum performance`

В этот момент запустится сборщик мусора. Отключить его запуск можно командой

```bash
git config gc.auto 0
git config --unset gc.auto # вернуть обратно
```
