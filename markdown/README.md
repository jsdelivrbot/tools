# Markdown

[Markdown](https://en.wikipedia.org/wiki/Markdown) (маркдаун) — облегчённый язык разметки.

## Синтаксис

### Заголовки
Создание заголовков производится путём помещения знака решетки перед текстом заголовка. Количество знаков `#` соответствует уровню заголовка. Как и в HTML доступно 6 уровней заголовков.

```markdown
# Заголовок первого уровня
## Заголовок второго уровня
...
###### Заголовок шестого уровня
```

### Параграфы
Для создания параграфов строки текста следует отделить друг от друга пустой строкой. Пустыми также считаются строки, которые содержат только пробельные символы.

```markdown
Параграф 1

Параграф 2
```

### Выделение текста
Текст можно выделять с помощью полужирного или курсивного начертания. Для полужирного выделения текст следует обернуть в символы `**` или `__`, для курсивного начертания — в символы `*` или `-`. Альтернативный синтаксис позволяет делать вложенные выделения.

```markdown
Текст можно выделять с помощью **полужирного** или *курсивного* начертания.
Альтернативный синтаксис позволяет делать **_вложенные_ выделения**.
```

Также текст можно сделать зачеркнутым, если обернуть его в символы `~~`.

```markdown
Вот так можно сделать ~~зачеркнутый~~ текст.
```

### Цитаты
Для обозначения цитат следует вставить символ `>` в начало строки.

```markdown
> Это текст будет цитатой.
```

Цитаты могут быть вложенными.

```markdown
> Это цитата первого уровня.
> > Это вложенная цитата.
> Назад на первый уровень.
```

### Ссылки
Чтобы поставить гиперссылку, текст ссылки следует обернуть в квадратные скобки, затем в круглых скобках нужно указать адрес ссылки. Также можно указать заголовок ссылки.

```markdown
[Текст ссылки](http://example.com/ "Заголовок ссылки")
```

### Изображения
Чтобы вставить изображение в квадратных скобках следует указать альтернативный текст, перед которым должен стоять символ `!`, затем в круглых скобках путь к изображению. Опциально можно указать заголовок изображения.

```markdown
![Альтернативный текст](/path/to/image.png "Заголовок изображения")
```

### Списки

#### Ненумерованные
Для создания ненумерованных списков следует использовать символ `*`, `+` или `-`, после которого нужно поставить пробел.

```markdown
- Красный
- Желтый
- Зеленый
```

#### Нумерованные
Для создания нумерованных списков следует использовать цифры с точкой и пробел.

```markdown
1. Один
1. Два
1. Три
```

Причем цифры необязательно должны следовать по порядку.

```markdown
1. Это первый элемент списка
5. Это второй элемент списка
2. Это третий элемент списка
```

#### Вложенные
Вложенные списки создаются с помощью с помощью отступов в два пробела.

```markdown
* Это список первого уровня
  * Это список второго уровня
    * Это список третьего уровня
```

### Форматирование кода
Чтобы выделить код в строке следует обернуть его в символы `````.

```markdown
Экранирование в Markdown осуществляется с помощью символа `\`.
```

Для оформления блока кода в начале и в конце следует использовать по три символа ```````.

### Разделители
Для создания горизонтальной линии следует использовать три или более символа `*`, `-` или `_`. При желании между ними можно вставлять пробелы.

```markdown
***
-----
* * *
```

### Экранирование
Символы, которые обычно рассматриваются в Markdown как специальные, могут быть экранированы с помощью обратного слеша. Например, последовательность `\*` выведет символ `*`, а не будет являться признаком начала выделенного текста.

## Ссылки
- [Markdown: Syntax](http://daringfireball.net/projects/markdown/syntax)
- [Markdown cheat sheet](http://warpedvisions.org/projects/markdown-cheat-sheet/)