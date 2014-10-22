#JavaScript Conventions:
###Единични кавички вместо двойни.
Използваме единични кавички, освен ако не пишем JSON. Тогава кавичките са двойни.

Правилно:
```js
var foo = 'bar';
```
Грешно:
```js
var foo = "bar";
```
###Отварящата скоба е на същата линия.
Празни разстояния оставяме от двете страни на условието.

Правилно:
```js
if (true) {
  console.log('winning');
}
```
Грешно:
```js
if (true)
{
  console.log('winning');
}
if ( true ) {
  console.log('winning');
}
if(true){
  console.log('winning');
}
```

###Променливите се декларират с отделен var
С цел по-лесно разместване/добавяне.

Правилно:
```js
var keys   = ['foo', 'bar'];
var values = [23, 42];
```
Грешно:
```js
var keys = ['foo', 'bar'],
    values = [23, 42];
```

###Масиви и обекти могат да се запишат на един ред само когато са кратки. 
Ако имат над 3 елемента се записват на нов ред.

Правилно: 
```js
var a = ['hello', 'world'];
var b = {
    good: 'code',
    'is generally': 'pretty',
};
var largeArray = [
    'there', 
    'are',
    'some',
    'things',
    'better',
    'left',
    'on',
    'their',
    'own',
    'line',
] 
var b = {
    'if': 'im',
    'nested': 'i',
    'go': 'like',
    'this': {
        'goes': 'like',
        'this': 'yey',
    }
};
```

Грешно: 
```js
var a = [
    'hello', 'world'
];
var b = { "good": 'code',
        'is generally': 'pretty'};
var b = [ "twenty", 'different', 'stuff', 'on', 'one', 'line', 'go', 'figure', 'what', {they:'are'} ];
 
```


###Запетайка след последния елемент
При деклариране на многоредов масив/обект слагаме запетайка дори след последния елемент. Това няма да наруши кода синтактично и ще позволи по-лесно добавяне на нови елементи. 

Правилно:
```js
var a = {
    'easy': 'to',
    'add': 'at',
    'the': 'end',
}
```

Грешно:
```js
var a = {
    'whenIAdd': 'atTheEnd',
    'iGet': 'syntaxError',
    'ifIm': 'notCareful'
}
```


##Наименование на променливите:

###За всички променливи използваме camelCase
Правилно:
```js
var userPassword = '1234bhbh';
```
Грешно:
```js
var user_Password = '1234bhbh';
var userpassword = '1234bhbh';
var UserPassword = '1234bhbh';
var USERPASSWORD = '1234bhbh';
```

###Константи пишем с главни букви
Защото са константи

```js
var MINUTE = 60000;

function File() {
}
File.FULL_PERMISSIONS = 0777;
```

###Класове дефинираме с PascalCase/UpperCamelCase 
```js
function UserLocation() {
}
```

###Използваме смислени и ясни наименования, на английски език.
Пример: 
    `Променлива за запазване на e-mail адрес на потребителя.`

Правилно:
```js
var customerEmail;
```
Грешно:
```js
var mail; //Възможно е да бъдем по-конкретни
var mailche; //no-comment
var poshta; //Шльокавица
var adres; //Грешно спелуване/шльокавица + объркващо
var address; //Объркващо в случай, че става въпрос за Email адрес
```
TODO: Say something about difference in customerEmail / emailCustomer

###Наименованието на функциите следва същите принципи:

Пример: 
    `Функция, която прекратява обект от клас LocationPoller`

Грешно:
```js
function omgPleaseStop(poller) {
    //
}
```

Правилно:
```js
function stopLocationPoller(locationPoller) {
    //
}
```
И след документиране става:
```js
/**
 * Stops the specified location poller, completely releasing it from memory
 * 
 * @param  LocationPoller locationPoller The location poller object we want to stop
 * @return void
 */
function stopLocationPoller(locationPoller) {
    //
}
```

###Сложните условия - отделно / Use descriptive conditions
Всички по-сложни условия в if да бъдат отделени в ясно говорима променлива преди самата проверка. /
Any non-trivial conditions should be assigned to a descriptively named variable or function:

Right:
```js
var isValidPassword = password.length >= 4 && /^(?=.*\d).{4,}$/.test(password);

if (isValidPassword) {
    console.log('winning');
}
```
Wrong:
```js
if (password.length >= 4 && /^(?=.*\d).{4,}$/.test(password)) {
    console.log('losing');
}
```

###Boolean променливите да бъдат говорими
Имената им да започват с is, has, equals, isNot.. etc.

Правилно:
```js
var hasMoney = false;
var isRich = false;
var equalsZero = true;
```
Грешно:
```js
var flagMoney = false;
var richBich = false;
var moneys = true;
```