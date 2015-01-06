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
