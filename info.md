 # Инструкция по работе с git репозиторием

  ## Для начала работы:
   
   > git init

   Если имя пользователя и почта ещё не были заданы:

   > git config --global user.name

   > git config --global user.email

   ## Работа с файлами:

  Для того,чтобы добавить файл нужно:

   1. > git add file_name
 добавляем файл с именем  file_name для отслеживания

   2. > git_commit -m"some massage"

     * добавляем текущие изменения в репозиторий и подписываем их с помощью тега -m

     * если добавить тег -а перед тегом -m,то к коммиту добавятся все изменненые файлы ,которые уже отслеживались(позволяет пропустить git add перед коммитом)


 Чтобы отслеживать состояние репозитория:
  
   1. > git status
   2. > git log  

   Чтобы показать ветки:

   >  git log --graph
   3. > git diff

  ## Работа с коммитами

  Для того чтобы перейти к определенному коммиту, можно использовать команду 
  > git checkout code_commit

  code_commit-код коммита, к которому хотим перейти, его можно посмотреть в git log

  Чтобы вернуться к последнему состоянию:
  > git checkout main
  

  ![Flower](3551025b-5bea-4000-ab45-f1cbf6a245b8.png)
  
# Cовет

 * Коммитьте как можно чаще

 * одно изменение-один коммит,разделите их,чтобы было проще откатиться.

 ## Ветки в git
  Чтобы посмотреть все ветки :
> git branch

Для создания новой ветки с именем branch_name:
> git branch branch name
 
 Переместиться к ветке с именем branch_name:
> git checkout branch_name
 
 ## Слияние веток и решение конфликтов
 Чтобы слитьинформацию из ветки branch_name в текущую:
 > git merge branch_name


 В случае конфликта нужно удалить все лишние строки и оставить ту часть,которая нам нужна. Усли необзодимо , то можно отредактирвать её.
## Удаление веток

 Для того ,чтобы удалить ветку с именем branche_ name:

 > git branche -d branche_name

Удаление с игнорированием ошибок:

> git branch -D branch_name

## Справка
Чтобы вызвать справку по команде, допишите тег:
> --help
 примеры:
 > git ad --help
 > git branch --help


## Игнорирование файлов.

Часто есть файлы или группа файлов,которые не хотим автоматически добавлять в репозиторий,но и видеть их в списках неотслеживаемых. К таким файлам обычно относятся автоматически генерируемые файлы(различные логи,результаты сборки программ и т. п.). В таком случае, мы можем создать файл .gitignore. с перечислением шаблонов соответствующих таким файлам. Вот пример файла .gitignore:

> $ cat .gitignore

>*.[oa]

 > *~  
 
Первая строка предписывает Git игнорировать любые файлы заканчивающие на ".о" или ".а"-объектные и архивные файлы,которые могут появиться во время сборки кода. Вторая строка предписывает игнорировать все файлы заканчивающиеся на тильду(~),которая используется во многих текстовых редактораx ,например Emacs,для обозачения временных файлов. 
 
 Также можем включить каталоги log,tmp, или pid ; автоматически создаваемую документацию; и т.д. и т.п.. Хорошая практика заключается в настройке файла .gitignore до того ,как начать серьёзно работать,это защитит от случайного добавления в репозиторий файлов,которые мы там не хотим видеть.


К шаблонам в файле .gitignore применяются следующие правила:

* Пустые строки,а также строки,начинающиеся с #, игнорируются.

* Стандартные шаблоны являются глобальными и применяются рекурсивно для всего дерева каталогов.

* Чтобы избежать рекурсии используйте символ слеш(/) в начале шаблона.
* Чтобы исключить каталог добывьте слеш (/)в конец шаблона.

* Можно инвертировать шаблон ,использовав восклицательный знак(!)в качестве первого символа.
