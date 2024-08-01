# Шпаргалка по работе с Git  
## Базовые команды в консоли  
### Навигация  
- `pwd` (от англ. ***p****rint ****w****orking ********directory*, «показать рабочую папку») — покажи, в какой я папке;  
- `ls` (от англ. ***l****ist ****d****irectory ****c****ontents*, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;  
- `ls -a` покажи также скрытые файлы и папки, названия которых начинаются с символа `.`;  
- `cd first-project` - (от англ. ***c****hange ****d****irectory*, «сменить директорию») — перейди в папку `first-project`;  
- `cd first-project/html` — перейди в папку ``html, которая находится в папке `first-project`;  
- `cd ..` — перейди на уровень выше, в родительскую папку;  
- `cd ~` — перейди в домашнюю директорию (`/Users/Username`);  
- `cd /` — перейди в корневую директорию.

### Работа с файлами и папками
**Создание**  
- `touch index.html` (англ. *touch*, «коснуться») — создай файл `index.html` в текущей папке;
- `touch index.html style.css script.js` — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;
- `mkdir second-project` (от англ. ***m****ake ****d****irectory*, «создать директорию») — создай папку с именем `second-project` в текущей папке.

**Копирование и перемещение**  
- `cp file.txt ~/my-dir` (от англ. ***c****o****p****y*, «копировать») — скопируй файл в другое место;
- `mv file.txt ~/my-dir` (от англ. ***m****o****v****e*, «переместить») — перемести файл или папку в другое место.

**Чтение**  
- `cat file.txt` (от англ. *con****cat****enate and print*, «объединить и распечатать») — распечатай содержимое текстового файла `file.txt`.

**Удаление**
- `rm about.html` (от англ. ***r****e****m****ove*, «удалить») — удали файл `about.html`;
- `rmdir images` (от англ. ***r****e****m****ove ****dir****ectory*, «удалить директорию») — удали папку `images`;
- `rm -r second-project` (от англ. ***r****e****m****ove*, «удалить» + ***r****ecursive*, «рекурсивный») — удали папку `second-project` и всё, что она содержит.

### Полезные возможности
- Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (`&&`).  
- У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (`↑`) и вниз (`↓`).  
- Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать `Tab`. Если файл или папка есть в текущей директории, командная строка допишет путь сама.  
- Например, вы находитесь в папке `dev`. Начните вводить `cd first` и дважды нажмите `Tab`. Если папка `first-project` есть внутри `dev`, командная строка автоматически подставит её имя. Останется только нажать `Enter`.


## Работа с репозиториями
- `git init` (от англ. ***init****ialize* — «инициализировать») - сделать папку Git-репозиторием;  
- `rm -rf .git` - "разгитить" папку, удалить скрытую подпапку `.git`;  
- `git status` (от англ. *status* — «статус», «состояние») - оказывает текущее состояние репозитория;  
- `git add readme.md` (от англ. *add* — «добавить») - подготовить файл `readme.md` к сохранению, отслеживать состояние;  
- `git add --all` (от англ. *add* — «добавить» + от англ. *all* — «всё») - подготовить к сохранению все файлы в репозитории;  
- `git add .` - подготовить к сохранению всю папку целиком;  
- `git commit` - сделать коммит;  
- `git commit -m "шпаргалка"` (от англ. ***m****essage* — «сообщение») - сделать коммит с присвоением сообщения `"шпаргалка"`;  
- `git log` (от англ. *log* — «журнал [записей]») - просмотреть историю коммитов.


## Статусы файлов в Git
- `untracked` (англ. «неотслеживаемый») - новые файлы в Git-репозитории помечаются как `untracked`, то есть неотслеживаемые. Git «видит», что такой файл существует, но не следит за изменениями в нём;  
- `staged` (англ. «подготовленный») - после выполнения команды `git add` файл попадает в **staging area** (от англ. stage — «сцена», «этап [процесса]» и area — «область»), то есть в список файлов, которые войдут в коммит. В этот момент файл находится в состоянии `staged`;  
- `tracked` (англ. «отслеживаемый») - в него попадают файлы, которые уже были зафиксированы с помощью `git commit`, а также файлы, которые были добавлены в staging area командой `git add`;  
- `modified` (англ. «изменённый») - содержимое файла отличается от последней сохраненной версии.