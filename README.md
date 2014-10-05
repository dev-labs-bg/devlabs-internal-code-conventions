<h1>DevLabs Code Conventions</h1>
Основни настройки на Code Editor-а:
<ul>
    <li>4 space-чета за indentation</li>
    <li>"indentation using spaces", а не "using tabs".</li>
    <li>Line endings: Unix</li>
</ul>

<h2>JavaScript Conventions:</h2>
<h3>Единични кавички вместо двойни.</h3>
Използваме единични кавички, освен ако не пишем JSON. Тогава кавичките са двойни.

Правилно:
```
var foo = 'bar';
```
Грешно:
```
var foo = "bar";
```

<h3>Отварящата скоба е на същата линия.</h3>
Празни разстояния оставяме от двете страни на условието.

Правилно:
```
if (true) {
  console.log('winning');
}
```
Грешно:
```
if (true)
{
  console.log('winning');
}
```
Грешно:
```
if ( true ) {
  console.log('winning');
}
```
Грешно:
```
if(true){
  console.log('winning');
}
```