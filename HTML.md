#HTML Conventions:

###Protocols
По възможност пропускайте протоколната част ( HTTP:, HTTPS: ) при инклудването на стилове или скриптове

Грешно:
```html
<script src="http://www.google.com/js/gweb/analytics/autotrack.js"></script>
```
Правилно:
```html
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>
```

###Използвай UTF-8 (no BOM)
Бъдете сигурни, че Вашият едитор използва UTF-8 като character encoding without BOM и не забравяйте да добавите HTML тага към Вашият темплейт:

```html
<meta charset="utf-8">
```

###Пишете коментари
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

###Как да използваме кавичките
Използвайте двойни (" ") кавички, когато се налага да обградите атрибутни стойности

Грешно:
```html
<a class='maia-button maia-button-secondary'>Sign in</a>
```

Правилно:
```html
<a class="maia-button maia-button-secondary">Sign in</a>
```

###Кръщавайте с подходящи имена ID-тата и class-овете
Използвайте подходящи имена за Вашите елементи. Те трябва да бъдат с минимална дължина, но да са разбираеми:

Грешни имена на селектори:
```html
<div id="menu-1901" class="green-button nivagtion"></div>
```

Правилни имена:
```html
<div id="main-menu" class="main-button nav"></div>
```

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

###Не забравяйте затварящият таг
За елементи, които са self-closing преди затварящият таг се поставя един празен интервал

Грешно:
```html
<meta http-equiv="content-type" content="text/html; charset=utf-8">
<img src="http://devlabs.bg/img/DevLabs_Logo.png" alt="Devlabs logo"/>
<br/>
```

Правилно:
```html
<meta http-equiv="content-type" content="text/html; charset=utf-8" />
<img src="http://devlabs.bg/img/DevLabs_Logo.png" alt="Devlabs logo" />
<br />
```