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
Индентацията между различните нива на HTML & CSS трябва да бъде точно 4 интервала. [Тук](http://css-tricks.com/changing-spaces-tabs-sublime-text/) можете да погледнете как да си настроите табулацията на Вашият Sublime.
Също така никога не смесвайте space интервали и табулация за да поставите отстъп.

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

###Използвай UTF-8 (no BOM)
Бъдете сигурни, че Вашият едитор използва UTF-8 като character encoding without BOM и не забравяйте да добавите HTML тага към Вашият темплейт:

```html
<meta charset="utf-8">
```

###Пишете коментари
Коментарите са изключително важна част от Вашият код - НЕ ги забравяйте. Грешна практика е да НЕ се пишат коментари за се спести от големината на файла, за тази цел си има минифициране. Направете Вашият код четлив и разбираем, а не Вашият колега да "гадае" какво се случва.

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
.white-color {
    color: #fff;
}
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
###Не използвайте type атрибута при инклудването на файл
Когато инклудвате някой style или script файл НЕ поставяйте type атрибут. Използвайте го само когато пишете стил или javascript.

Грешно:
```html
<link rel="stylesheet" href="//www.google.com/css/maia.css" type="text/css">
<script src="//www.google.com/js/gweb/analytics/autotrack.js" type="text/javascript"></script>
```

Правилно:
```html
<link rel="stylesheet" href="//www.google.com/css/maia.css">
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>
```

Използвайте го в следните ситуации:
```html
<script type="text/javascript" >
	var base = {
			url: 'http://vzonata.com/',
			rating: '9.5/10',
		};
</script>

<style type="text/css" >
	.bold {
		font-weight: bold;
	}
</style>
```
###Кавички в HTML елементите
Използвайте двойни (" ") кавички, когато се налага да обградите атрибутни стойности

Грешно:
```html
<a class='maia-button maia-button-secondary'>Sign in</a>
```

Правилно:
```html
<a class="maia-button maia-button-secondary">Sign in</a>
```

###Кавички в CSS елементите
Използвайте двойни (' ') кавички, когато се налага да обградите атрибут селектори

Грешно:
```html
@import url("//www.google.com/css/maia.css");

html {
  font-family: "open sans", arial, sans-serif;
}
```

Правилно:
```html
@import url(//www.google.com/css/maia.css);

html {
  font-family: 'open sans', arial, sans-serif;
}
```

###Кръщавайте с подходящи имена ID-тата и class-овете
Използвайте подходящи имена за Вашите елементи. Те трябва да бъдат с минимална дължина, но да са разбираеми:

Грешни имена на селектори:
```css
#yee-1901 {
	
}

.button-green {
	
}

#navigation {
	
}
```

Правилни имена:
```css
.video {
	
}

#login {
	
}

#nav {
	
}
```

В слаучай, че името на Вашият class или ID се състои от няколко думи, правилният начин за изписването на класа е чрез свързващият символ "-". Не използвайте долно тире или CamelCase.

Грешно:
```css
.blue_text {
	
}
.blueText {
	
}
```

Правилно:
```css
.blue-text {
	
}
```

###Използвайте Shorthand свойства
CSS предоставя възможност за изписване на по-кратък начин на някои свойства - използвайте ги при възможност.

Грешно:
```css
border-top-style: none;
font-family: palatino, georgia, serif;
font-size: 100%;
line-height: 1.6;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;
```

Правилно:
```css
border-top: 0;
font: 100%/1.6 palatino, georgia, serif;
padding: 0 1em 2em;
```

###Не използвайте единици след стойност "0"
```css
margin: 0;
padding: 0 1em 2em;
```

###Не използвайте "водеща" нула за стойност
Не използвайте "0"-та за стойности, който се намират между интервала -1 и 1.

Грешно:
```css
font-size: 0.8em;
```

Правилно:
```css
font-size: .8em;
```
###Поставяйте интервал между селетора и деклариращият блок
Винаги поставяйте по един празен интервал между селетора и деклариращият блок. Никога не ги разделяйте на редове:

Грешно:
```css
#video{
    margin-top: 1em;
}

#video
{
    margin-top: 1em;
}
```

Правилно:
```css
#video {
    margin-top: 1em;
}
```

###Поставяйте интервал между свойствата и съответната стойност

Грешно:
```css
.example {
    color:blue;
}
```

Правилно:
```css
.example {
    color: blue;
}
```

###Винаги започвайте всеки селектор на нов ред

Грешно:
```css
a:focus, a:active {
    position: relative; top: 1px;
}
```

Правилно:
```css
h1,
h2,
h3 {
    font-weight: normal;
    line-height: 1.2;
}
```
###Разделяйте стилизиращите правила с нов ред

Грешно:
```css
html {
  background: #fff;
}
body {
  margin: auto;
  width: 50%;
}
```

Правилно:
```css
html {
  background: #fff;
}

body {
  margin: auto;
  width: 50%;
}
```