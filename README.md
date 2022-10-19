# Pug
***
## Подготовка к использованию

### Для установки
```
npm install pug
```

```
(npm pug -v - для проверки, что все удачно установилось)
```


```
npm install pug-cli -g
```
<!-- npm install pug --save-dev (из директории проекта) -->

### Чтобы скомпилировать:
##### 1 способ
```
pug index.pug --pretty
```
Но нужно в определенную папку, поэтому лучше с флагами
```
pug index.pug --pretty --watch --out ./build/
```
Сокращенный вид:
```
pug index.pug --pretty -w -o ./build/
```

`-o` - флаг, после которого пишется путь к директории, куда должен компилироваться файл

`-w` - флаг для отслеживания файлов и компиляции в случае изменения

`--pretty` - (для читабельного вида) cкомпилировать в папку build без сокращения пробелов и сжатия в одну строку кода 

##### 2 способ

Установить расширение Live Pug Compiler

Нажать: `Ctrl+Shift+P`

Выбрать: `Start Pug Compiler`


***

## Использование

### 0.Помощники:
##### `ul>li*5` 
Emmet для быстрого написания списка:
```
ul
  li 
  li 
  li 
  li 
  li 
```
##### `loremru20`
`lorem` 20 русских слов

### 1.Многострочный текст

#### 1 способ - экранирование
```
  .block 
  | Далеко-далеко за словесными горами в стране, гласных и 
  | согласных живут рыбные тексты. 
  | Образ страну переписали если напоивший строчка? 
  | Выйти путь заманивший семь.
```
#### 2 способ - точка сразу после .block (`.block.`)
```
  .block. 
    Далеко-далеко за словесными горами в стране, гласных и 
    согласных живут рыбные тексты. 
    Образ страну переписали если напоивший строчка? 
    Выйти путь заманивший семь.
```

### 3.HTML в Pug
Можно писать html прям внутри pug

### 4.Комментарии
//-
Ctrl+/


### 5.Подключение файла base.pug

#### `extends`
Для подключения используем `extends`:
```
extends base
```
`extends` позволяет наследовать шаблон внутри `pug`, т.е. base - это некий шаблон, который будет подключаться ко всем страничкам.

#### `include`

`include` же это вставка кусочка кода в другой файл. 

Если мы хотим подключить файл через `include`, тогда в `index.pug`, внутри блока `block content` пишем:

```
  include header
```

Не забываем ставить Tab'ы! Без них нет блока!

### 6.Переменные
Создать переменные можно двумя способами:

#### 1 способ
```
-
  var siteTitle = 'title of this site'
  var lang = 'ru';
```
#### 2 способ
```
block vars
  - var siteTitle = 'title of this site';
  - var lang = 'ru';
  ```

### 7.Условия
Так же переменные можно изменять. Например, как в этом примере с условиями (`text` уже задан):

```
- var text = 'это текст';
```
Если `text` существует, тогда выводим `<p>{text}</p>`. Иначе - `<p>это хэдзр</p>`.
```
  if text
    p #{text}
  else 
    p это хэдэр
```

### 8.Циклы
Создадим массив:
```
- var menuValues = ['Главная', 'О нас', 'Работы', 'Контакты'];
```
Затем пробежимся циклом (аналог `for..in`):
```
  nav.nav 
    ul
      each value in menuValues
        li #{value}
```
Выводится список слов из массива.

### 9.Миксины
//

### 10.Источники
1. [MaxGraph](https://www.youtube.com/watch?v=HHBRbyTTSjk)

2. [Туториал](https://zaurmag.ru/html5-css3/html-preprotsessor-pug-jade.html)