# HTML Conventions

## Не забравяйте да пишете doctype и указвайте lang атрибутa на документа
```html
<!DOCTYPE HTML>
<html lang="en">
```

## Използвай UTF-8 (no BOM)
Бъдете сигурни, че Вашият едитор използва UTF-8 като character encoding without BOM и не забравяйте да добавите HTML тага към Вашият темплейт:

```html
<meta charset="utf-8" />
```

## Protocols
По възможност пропускайте протоколната част (http:, https:) при инклудването на стилове или скриптове

Грешно:
```html
<script src="http://www.google.com/js/gweb/analytics/autotrack.js"></script>
```
Правилно:
```html
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>
```

## Пишете коментари
Коментарите са изключително важна част от Вашият код - НЕ ги забравяйте.

При HTML страниците поставяйте коментари над block частта, като го изпишете по следният начин:
```html
<!-- Тук напиши своят смислен коментар -->
<header>
    <p>Красиво параграфче</p>
</header>
```

Ако е нужно да поставяте някъде TODO коментар, то правилния начин за изписването му е следният:
```html
<!-- TODO: remove optional tags -->
<ul>
    <li>Apples</li>
    <li>Oranges</li>
</ul>
```

## Как да използваме кавичките
Използвайте двойни (" ") кавички, когато се налага да обградите атрибутни стойности

Грешно:
```html
<a href="javascript:;" class='maia-button maia-button-secondary'>Sign in</a>
```
Правилно:
```html
<a href="javascript:;" class="maia-button maia-button-secondary">Sign in</a>
```

## Кръщавайте с подходящи имена ID-тата и class-овете
В слаучай, че името на Вашият class или ID се състои от няколко думи, правилният начин за изписването на класа е чрез свързващият символ "-". Не използвайте долно тире или CamelCase.

Грешно:
```html
<div class="blue_text"></div>
<div class="blueText"></div>
```
Правилно:
```html
<div class="blue-text"></div>
```

Използвайте подходящи имена за Вашите елементи. Те трябва да бъдат с минимална дължина, но да са разбираеми:

Грешни имена на селектори:
```html
<div id="menu-1901" class="green-button nivagtion"></div>
```
Правилни имена:
```html
<div id="main-menu" class="main-button nav"></div>
```

## Не забравяйте затварящия таг
За елементи, които са self-closing преди затварящият таг се поставя един празен интервал

Грешно:
```html
<meta charset="utf-8">
<img src="http://devlabs.bg/img/DevLabs_Logo.png" alt="Devlabs logo"/>
<br/>
```

Правилно:
```html
<meta charset="utf-8" />
<img src="http://devlabs.bg/img/DevLabs_Logo.png" alt="Devlabs logo" />
<br />
```

## Добавяйте IE Compatible таг
[The X-UA-Compatible meta tag](http://stackoverflow.com/questions/6771258/whats-the-difference-if-meta-http-equiv-x-ua-compatible-content-ie-edge-e) allows web authors to choose what version of Internet Explorer the page should be rendered as. IE11+ have changes to these modes. The version that will be released after IE 11, will only honor X-UA-Compatible meta tag in certain circumstances.
```html
<!--[if IE]>
    <meta http-equiv="X-UA-Compatible" content="IE=Edge">
<![endif]-->
```

## Пишете семантичен HTML
Семантичния HTML е най-обикновен HTML. Семантичен го прави начина, по който той бива използван. Семантичен буквално означава "значещ". За да е "значещ" HTML кода трябва да е максимално добре структуриран и да описва максимално точно съдържанието което представя. Той конкретизира вида на съдържанието и указва неговата йерархия. Един сайт може да бъде изграден единствено със <div></div> елементи и за крайния потребител това да не е проблем, но:
- програмистите които ще четат кода ти много трудно ще се ориентират
- когато уеб паяците (web crawler) минат от там, за тях всичко ще е еднакво и те няма да индексират добре съответния сайт. Поради тези причини семантичният HTML е много важен и за Search Engine оптимизацията.