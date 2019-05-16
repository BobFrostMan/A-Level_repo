# Небольшая инструкция по использованию git

Перед вами небольшая инструкция которая покажет что нужно сделать, чтобы залить код в git репозиторий организованный на github. 

1. Завести аккаунт на github
2. Залогиниться на github в браузере по https://github.com
3. Создать новый репозиторий на github. Необходимо создать ваш **удалённый репозиторий**.
![create new repository](https://github.com/BobFrostMan/A-Level_repo/blob/master/resources/1_create_repo.jpg)
4. Теперь когда у вас есть репозиторий на github, нужно создать **локальный репозиторий**. 
Что такое локальный репозиторий? Это папка на жестком диске вашего компьютера, в которой вы будете хранить ваш код локально. 
После изменения кода, используя git вы будете заливать изменения из локального репозитория на удалённый (из папки на вашем компьютере в github).
Создайте папку в любом месте на жестком диске вашего компьютера. Очень желательно чтобы путь к папке был без пробелов.
5. Теперь необходимо инициализировать папку, которую вы создали, как локальный git репозиторий.
Для этого необходимо
* Вернуться на github вкладку в браузере.
* Перейти к вашему удалённому репозиторию.
* Нажимаем на кнопку **Clone or download**
* Скопируйте ссылку начинающийся с https
![copy link](https://github.com/BobFrostMan/A-Level_repo/blob/master/resources/2_copy_link.jpg)
* Откройте git консоль в на жестком диске в папке локального репозитория. На windows, git bash можно открыть перейдя в папку локального репозитория и зажав Shift после чего кликнуть на пустой месте правой кнопкой мыши. В этом случае в контекстном меню становится доступной опция **Open Git Bash here**
![open bash here](https://github.com/BobFrostMan/A-Level_repo/blob/master/resources/3_open_bash_here.jpg)
* В открывшемся окне консоли, выполните команду git clone и вставьте скопированную ссылку на удалённый репозиторий (github)
```
git clone <ссылка с github>
```
![git clone](https://github.com/BobFrostMan/A-Level_repo/blob/master/resources/4_git_clone.jpg)
6. В папке с локальным репозиторием необходимо создать новый проект используя intelij idea.
![open project](https://github.com/BobFrostMan/A-Level_repo/blob/master/resources/5_open_project.jpg)
7. В корне проекта необходимо создать файл с именем **.gitignore**, как показано на скриншоте:
![create gitignore](https://github.com/BobFrostMan/A-Level_repo/blob/master/resources/6_create_gitignore.jpg)
Этот файл как правило содержит имена или расширения тех файлов которые будут игнорироваться git-ом
```
.idea
out
*.class
*.iml
```
Для java проекта, следует исключать файлы с расширением **.class** или папка **out** (всё где хранится скомпилированный байт-код). Для Intelij Idea проекта следует исключать папку **.idea** и файл **.iml** (проектный файлы которые могут различаться если проект открыть на другом компьютере)
8. Теперь можно выполнять домашнее задание :) или вносить изменения в проект. После создания новых классов или внесения изменений переходим к следующему пункту, где начнём процедуру заливки изменений на удалённый репозиторий.
9. В git bash выполним команду git add чтобы добавить изменения в commit.
```
git add .
```
После git add следует указать конкретное имя файла или же указать точку. Точка означает добавить все изменения в commit.

10. git status - команда, которая показывает состояние изменений в репозитории. Все добавленные/удалённые изменённый файлы будут указаны в выводе команды. Зелёным цветом будут выделены те файлы которые попадут в git commit (те которые успешно добавлены git-ом)
![git add git status](https://github.com/BobFrostMan/A-Level_repo/blob/master/resources/7_git_add_git_status.jpg)

11. Выполнить чтобы добавить все изменения в commit. 
```
git commit -m "тут написать коментарий на латиннице, например: Implemented task with arrays или fixed issue with strings"
```

12. Теперь изменения сохранены в локальном git репозитории. Чтобы залить изменения из локального репозитория в удалённый необходимо выполнить команду git push
![git commit git push](https://github.com/BobFrostMan/A-Level_repo/blob/master/resources/8_git_commit_git_push.jpg)
```
git push origin master
```
origin - имя удалённого репозитория на github (по умолчанию удалённый репозиторий носит имя origin)

master - имя ветки в удалённом репозитории (основная ветка как правило называется master)

В ходе команды вас возможно попросят ввести логин и пароль от аккаунта на github-е.

Готово. Теперь измения отображаются и на github.

---
***Как жить дальше?***
Обычная последовательность команд для заливки изменений на git следующая:
1. Забираем себе локально последние изменения с удалённого git репозитория
```
git pull origin master
```
2. Открываем java проект выполняем задание
3. Добавляем изменения в commit
```
git add .
git commit -m "some comment about changes"
```
4. Заливаем изменения в удалённый репозиторий
```
git push origin master
```
