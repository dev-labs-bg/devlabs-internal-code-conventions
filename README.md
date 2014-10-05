<h1>DevLabs Code Conventions</h1>
Основни настройки на Code Editor-а:
<ul>
    <li>4 space-чета за indentation</li>
    <li>"indentation using spaces", а не "using tabs".</li>
    <li>Line endings: Unix</li>
</ul>

JavaScript Conventions:
========================
1. Единични кавички вместо двойни.
Use single quotes, unless you are writing JSON.

Правилно:
```
var foo = 'bar';
```
Грешно:
```
var foo = "bar";
```

2. Отварящата скоба е на същата линия. Празни разстояния оставяме от двете страни на условието.
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