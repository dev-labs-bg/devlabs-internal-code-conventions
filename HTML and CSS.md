#HTML & CSS Conventions:

###Protocols
По възможност пропускайте протоколната част ( HTTP:, HTTPS: ) при инклудването на мултимедийни файлове, стилове или скриптове

Грешно:
```html
<script src="http://www.google.com/js/gweb/analytics/autotrack.js"></script>
```
Правилно:
```html
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>
```

Грешно:
```css
.example {
  background: url(http://www.google.com/images/example);
}
```
Правилно:
```css
.example {
  background: url(//www.google.com/images/example);
}
```
###Индентиране
Инденцията между различните нива на HTML & CSS трябва да бъде точно 4 интервала. [Тук](http://css-tricks.com/changing-spaces-tabs-sublime-text/) можете да погледнете как да си настроите табулацията на Вашият Sublime.

Правилно:
```html
<ul>
    <li>Fantastic
    <li>Great
</ul>
```
```css
.example {
    color: blue;
}
```

###Използва единствено lowercase
Целият код трябва да бъде написан lowercase. Това се отнася за HTML елементи, атрибути, селектори, стойности и т.н.

Грешно:
```html
<A HREF="/">Home</A>
```
Правилно:
```html
<img src="google.png" alt="Google">
```

Грешно:
```css
color: #E5E5E5;
```
Правилно:
```css
color: #e5e5e5;
```

###Използвай Use UTF-8 (no BOM)
Бъди сигурен, че твоят едитор използва UTF-8 as character encoding without BOM и не забравяй да добавиш HTML тага към твоят темплейт

```html
<meta charset="utf-8">
```

###Пиши коментари
Коментарите са изключително важна част от твоят код - НЕ ги забравяй.

При HTML страниците поставяйте коментари над block частта, като го изпишете по следният начин:
```html
<!-- Тук напиши своят смислен коментар -->
<header>
    <p>Красиво параграфче</p>
</header>
```

При CSS страниците поставяйте коментари над всеки един селектор, като го изпишете по следният начин:
```css
/* Вашият смислен коментар */
```

Понякога коменарите може да са прекалено дълги и се налага да се разбият на няколко реда:
```css
/**
 * Lorem Ipsum is simply dummy text
 * of the printing and typesetting industry.
 */
```

Ако е нужно да поставяте някъде TODO коментар, то правилния начин за изписването му е следният:
```html
<!-- TODO: remove optional tags -->
<ul>
    <li>Apples</li>
    <li>Oranges</li>
</ul>
```

```css
/**
 *
 * TODO: This is a todo statement that describes an atomic task to be completed
 *   at a later date. It wraps after 80 characters and following lines are
 *   indented by 2 spaces.
 */
```

Препоръчително е Вашият CSS файл да бъде "разбит" на секции и подсекции: по-четлив и структуриран е Вашият код
```css
/* ==========================================================================
   Section comment block
   ========================================================================== */
```

```css
/* Sub-section comment block
   ========================================================================== */
```

Ето и един пример в комбинация от всичко видове коментари:
```css
/* ==========================================================================
   Grid layout
   ========================================================================== */

/**
 * Grid container
 *
 * Must only contain `.cell` children.
 *
 * 1. Remove inter-cell whitespace
 * 2. Prevent inline-block cells wrapping
 */

.grid {
    height: 100%;
    font-size: 0; /* 1 */
    white-space: nowrap; /* 2 */
}

/* Cell states */

.cell.is-animating {
    background-color: #fffdec;
}

/* Cell dimensions
   ========================================================================== */

.cell-1 { width: 10%; }
.cell-2 { width: 20%; }
.cell-3 { width: 30%; }
.cell-4 { width: 40%; }
.cell-5 { width: 50%; }

/* Cell modifiers
   ========================================================================== */

.cell--detail,
.cell--important {
    border-width: 4px;
}
```