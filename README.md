<h1>DevLabs Code Conventions</h1>
Основни настройки на Code Editor-а:
<ul>
    <li>4 space-чета за indentation</li>
    <li>"indentation using spaces", а не "using tabs".</li>
    <li>Line endings: Unix</li>
</ul>

JavaScript Conventions:
========================
<h5>Единични кавички вместо двойни.</h5>
Use single quotes, unless you are writing JSON.

Правилно:
```
var foo = 'bar';
```
Грешно:
```
var foo = "bar";
```

<h4>Отварящата скоба е на същата линия. Празни разстояния оставяме от двете страни на условието.</h4>
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