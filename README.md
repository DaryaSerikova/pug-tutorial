# Pug
***
### Для установки
npm install pug
(npm pug -v - для проверки, что все удачно установилось)
npm install pug-cli -g
<!-- npm install pug --save-dev (из директории проекта) -->

### Чтобы скомпилировать:
##### 1 способ
<pug index.pug --pretty>
Но нужно в определенную папку, поэтому лучше с флагами
pug index.pug --pretty --watch --out ./build/
Сокращенный вид:
pug index.pug --pretty -w -o ./build/
-o - флаг, после которого пишется путь к директории, куда должен компилироваться файл
-w - флаг для отслеживания файлов и компиляции в случае изменения
--pretty - (для читабельного вида) cкомпилировать в папку build без сокращения пробелов и сжатия в одну строку кода 

##### 2 способ
Ctrl+Shift+P
Выбрать Start Pug Compiler

### Помощники:
ul>li*5 - Emmet для быстрого написания списка:
ul
  li 
  li 
  li 
  li 
  li 

loremru20 - lorem 20 русских слов


### Многострочный текст

##### 1 способ - экранирование
  .block 
  | Далеко-далеко за словесными горами в стране, гласных и 
  | согласных живут рыбные тексты. 
  | Образ страну переписали если напоивший строчка? 
  | Выйти путь заманивший семь.

##### 2 способ - точка сразу после .block
  .block. 
    Далеко-далеко за словесными горами в стране, гласных и 
    согласных живут рыбные тексты. 
    Образ страну переписали если напоивший строчка? 
    Выйти путь заманивший семь.

### HTML в Pug
Можно писать html прям внутри pug

### Комментарии
//-
Ctrl+/


### Подключение файла base.pug

##### extends
Для подключения используем extends:
extends base
extends  позволяет наследовать шаблон внутри pug, т.е. base - это некий шаблон, который будет подключаться ко всем страничкам.

##### include
include же это вставка кусочка кода в другой файл. 
Если мы хотим подключить файл через include, тогда в index.pug, внутри блока block content пишем:
  include header
Не забываем ставить Tab'ы! Без них нет блока!

