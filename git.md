# Git

git config --global user.name "name"  
git config --global user.email "email"

git fetch  
git status  
git pull  

git add . -> нормально отрабатывает изменение типа или перименование  
git add * -> нормально обрабатывает перименование только в дочерних папках, хз  
git add -A  

git reset -> сбросить все добавленное перед коммитом  

git checkout -- <filename> -> вернуться к версии файла  

git checkout master  
git checkout 03ecdd7  
git checkout HEAD  
git checkout HEAD^  
git checkout HEAD^^^  
git checkout HEAD~6  
git checkout -b <newbranch>  

git log --pretty=oneline  
git log --pretty=oneline --all -> ???  
git log --pretty=oneline --graph  
git log --pretty=format:'%h %ad | %s%d' --date=short  

git revert HEAD -> отменить коммит  
git revert HEAD --no-edit -> отменить без редактирования  
если произошли конфликты git status  
git revert --continue  
git revert --abort -> отменить процесс реверта  
добавить или удалить конфликтные файлы git add/rm, затем закоммитить  

git branch -> вывести ветки  
git branch <newbranch>  

git merge <somebranch> -> залить в текущую ветку из somebranch  

[back](/)