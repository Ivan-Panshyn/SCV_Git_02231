![Logo](Git-Logo-1788C.png)
# Работа с Git

## 1. Проверка наличия установленного Git
***

В терминале выполнить команду `git --version`
Если Git установлке, появится сообщение с информацией о версии программы. Иначе будет сообщение об ошибке.

## 2. Установка Git
***
Загружаем последнюю версию Git с сайта https://git-scm.com/download.
Устанавливаем с настройками по умолчанию.

## 3. Настройка Git
---
При первом использовании Git необходимо представиться. Для этого нужно ввести в терминале 2 команды:
```
git config --global user.name <<Ваше имя английскими буквами>>
git config --global user.email <<Ваша почта@gmail.com>>

```
## 4. Инициализация репозитория
---
Обычно выэффективный репозиторий Git из двух сторон:
* Вы можете взять локальный каталог, который в настоящее время не находится под версионным контролем, и произойдет его в репозиторий Git, либо
* Вы можете клонировать Существующий репозиторий Git из любого места.

### Для создания нового репозитория используется команда git init. Команду git init выполняют только один раз для первоначальной настройки нового репозитория. Выполнение команды приведет к созданию нового подкаталога .git в вашем рабочем каталоге. Кроме того, будет создана новая главная ветка.

## 5. Изменений в репозиторий (git status, git add, git commit, git diff)
***
 * Команда **Git status** относительно проста в использовании. Она показывает, какие изменения были внесены с помощью команд git add и git commit. Сообщения о состоянии также содержат инструкции по индексированию файлов либо отмене этой операции
 * **Сравнение** — это функция, анализирующая два входных набора данных и отображающая различия между ними. **Git diff** представляет собой многоцелевую команду Git, которая инициирует функцию сравнения источников данных Git — коммитов, веток, файлов и т. д. В этом документе описываются типичные варианты вызова git diff и схемы рабочего процесса сравнения. Зачастую вместе с командой git diff используются git status и git log для анализа текущего состояния репозитория Git.

 * Команда **Git add** добавляет изменение из рабочего каталога в раздел проиндексированных файлов. Она сообщает Git, что вы хотите включить изменения в конкретном файле в следующий коммит. Однако на самом деле команда git add не оказывает существенного влияния на репозиторий: изменения регистрируются в нем только после выполнения команды git commit.
Наряду с этими командами вам понадобится команда git status, которая показывает состояние рабочего каталога и раздела проиндексированных файлов.

 * Коммиты — основные конструктивные элементы временной шкалы проекта Git. Их можно рассматривать как снимки состояния или контрольные точки на временной шкале проекта Git. Коммиты создаются с помощью команды **git commit**, которая делает снимок состояния проекта на текущий момент времени. Коммиты снимков состояния Git всегда выполняются в локальный репозиторий. В этом и заключается фундаментальное отличие от SVN, где коммит рабочей копии выполняется в центральный репозиторий

## 6. Конфигурирование: git config
---

Git хранит варианты конфигурации в трех различных файлах, позволяющих ограничивать область видимости на уровне отдельных репозиториев (локальный), пользователя (глобальный) или всей системы (системный):

1.  Локальный: /.git/config — настройки на уровне репозитория.

2.  Глобальный: /.gitconfig — настройки на уровне пользователя. Здесь хранятся настройки с флагом --global.
3.  Системный: $(prefix)/etc/gitconfig — настройки на уровне всей системы.

## 7. Знакомство с git log (историей)
---

**Git log**

Данная команда предназначена для отображения всей вашей истории. Она может быть весьма удобна, если вам понадобилось узнать, какие изменения вы вносили ранее. Или если вам нужно откатиться до определенного места в истории, либо если есть нужда её отредактировать.

## 8. Перемещение между сохранениями (git checkout).
---

Команда __git checkout HEAD__ <файл> приводит к тому же результату, что и git reset --hard HEAD <файл> — перезаписывает версию файла в области подготовленных файлов и в рабочей директорией версией из HEAD, то есть отменяет изменения после последнего коммита.

С другой стороны, __git checkout__ <файл> (уже без HEAD) перезаписывает версию файла в рабочей директории версией в области подготовленных файлов, то есть отменяет изменения с момента последней подготовленной версии.

Наконец, git rm <файл> отменяет отслеживание файла и удаляет его из рабочей директории, опция --cached позволит сохранить файл.

Команда git checkout часто используется вместе с командой git branch. С помощью команды git branch можно создать новую ветку. Когда вы захотите начать работу над новой функцией, создайте новое ответвление от ветки main с помощью команды git branch new_branch. Затем переключитесь на новую ветку с помощью команды git checkout new_branch. Команда git checkout также принимает аргумент -b, который действует как вспомогательный метод, позволяя создать новую ветку и сразу переключиться на нее. Вы можете работать сразу с несколькими функциями в одном репозитории, переключаясь между ними с помощью git checkout.


## 9. Заключение
--- 

Мы рассмотрели самые основные приемы работы с Git. Моей задачей было сформировать в вас некоторое понимание - что есть система контроля версий и познакомить с одной из них. Мы разобрали структуру Git проекта, и теперь у вас есть представление о том, как он работает. Мы познакомились с самыми важными командами в Git.



Более подробную  информацию можно узнать на официальном сайте  https://git-scm.com 


## 10. Игнорирование файлов
Для того, чтобы исключить отслеживания в репозитории определённые файлы или папки необходимо создать там файл .***gitIgnore*** и записать в него их названия или шаблоны, соответсвующих таким файлам или папкам.

## 11. Создание веток в Git
Ветка в Git - это простой перемещаемый указатель на один из коммитов, обычно последний в цепочке коммитов.
По умолчанию имя основной ветки в Git - **master**.
Создать вутку можно командой:
```
git branch <название новой ветки>
```
В результате создаётся новый указатель на текущий коммит.
![Logo](github-logo-7880D80B8D-seeklogo.com.png)

## 12. Слияние веток в Git
Слияние используется в Git, чтобы собрать воедино разветвленную историю. Команда `git merge` выполняет слияние отдельных направлений разработки, созданных с помощью команды git branch, в единую ветку.

## 13. Разрешение конфликтов между ветками

Для предотвращения конфликтов разработчики работают в отдельных изолированных ветках. Основная задача команды `git merge` заключается в слиянии отдельных веток и разрешении любых конфликтующих правок.

### Общие инструменты для разрешения конфликта:

+ `git status`
Команда status часто используется во время работы с Git и помогает идентифицировать конфликтующие во время слияния файлы.

+ `git log --merge`
При передаче аргумента --merge для команды git log будет создан журнал со списком конфликтов коммитов между ветками, для которых выполняется слияние.
+ `git diff`
Команда diff помогает найти различия между состояниями репозитория/файлов. Она полезна для выявления и предупреждения конфликтов слияния.

## 14. Удаление ветки 

Команда для удаления локальной ветки в Git:

### `git branch -d  local_branch_name`

``git branch`` – команда для удаления локальной ветки.

`-d` – флаг, опция команды git branch, сокращенный вариант записи --delete. Как и следует из названия, предназначен для удаления ветки.

`local_branch_name` – имя удаляемой ветки.

Если в ветке присутствуют несмерженные изменения или незапушенные коммиты, флаг -d не позволит удалить такую локальную ветку.

Это связано с тем, что эти коммиты нигде более не отслеживаются, и Git защищает вас от случайной потери этих данных.

Если все же попытаться удалить такую ветку, Git выдаст ошибку:


Как предложено в тексте ошибки, вы должны воспользоваться флагом -D:

`git branch -D local_branch_name` 

Флаг `-D` с большой D (сокращенная запись опции --delete --force), принудительно удаляет локальную ветку, вне зависимости от ее статуса мержа.


# Работа с удаленными репозиториями
1. Создать аккаунт на GitHub
2. Создать локальный репозитори
3. Создать удаленный репозиторий
4. Связать удаленный репозиторий с локальным
Как добавит удаленный репозиторий к проекту: 
```
git remote add  <имя для репозито> <url-адрес репозиторий в сети>
```

5. git branch - проверка веток
6. git branch new - создаем новую ветку с именем new
7. git checkout new - переход на новую ветку 
8. Создаем новую файл например (WORDDZ.md) 
9. Проверяем git status
10. В терминале вводим 
```
git coomit -am "текст"
```
11. git add . сохраняем изменения
12. git status - проверяем эти изменения
13. git push -u origin main переносим информацию с локального репозитория в удаленный
14. При изменение информации на удаленном репозитории, чтобы перенести его в локальный репозиторий следует зайти на локальный. И при помощи команды перенести всю измененую информацию:
```
git pull 
``` 

# Для изменения другого репозитория
1. Заходим на сайт GitHub
2. Находим интересесующий нас репозиторий
3. При помощи команды Fork сохраняем к себе в папку репозитории
4. Копируем ссылку данного репозитория
5. Заходим в VSC
6. Переходим в корневую папку командой cd ..
7. После вводим команду git clone "ссылка на репозиторий"
8. Переходим в созданную папку cd "имя папки"
9. Git branch - проверяем количество веток
10. Git branch new - создаем новую ветку
11. Git checkout new - переходим на новую  ветку
12. Создаем новый файл в этой папке
13. Вводим нужный текст 
14. Проверяем статус в терминале git status
15. Git add "имя файла"
16. Добавляем комментарий git commit -m "Текст"
17. Git log - проверяем историю ветки
18. Git status
19. Для отправления изменения удаленный репозиторий использовать команду git push, но она не сработает и там предлагается другая команда, которую копируем и вставляем в терминале
20. Переходим на удаленный репозиторий
21. Нажимаем на кнопку Pull Request -> new pull request -> compare "new" -> create pull request
22. После оставляем сообщение для автора, например "Добавили новый файл"
23. Creat pull request


Спасибо!