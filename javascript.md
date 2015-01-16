#JavaScript Conventions:

###General
- Javascript кодът винаги е в отделен файл. <br />
- Javascript директно в HTML-a може да се използва само и единствено, когато кода е специфичен за съответната сесия. <br />
- Javascript файловете се include-ват възможно най в края на документа. <br />
- Организирайте кодa си във функции, обекти и структури. <br />
- Избягвайте просто да нахвърлите всичко в document.ready, кодът ви има логика и последователност - организирайте го. <br />
- Намалете до минимум използваните обекти в глобалния scope. <br />

###Дължина на реда
Ограничавайте дължината на реда до 80 символа. Ако не можете да съберете съдържанието в 80 символа пренесете на нов ред, в най-добрия случай след логически оператор. Ако редът е прекалено дълъг се замислете дали не е нужно да се премисли логиката и да се опрости израза.

###Идентиране (Табулация с интервали)
Идентирането се извършва с 4 интервала вместо табулация. Ако ви притеснява нарастването на големината на файловете се запитайте защо не си минифицирате файловете.

### #Коментари
Пишете коментари. <br />
Пишете смислени коментари. <br />
След време ще благодарите на себе си и на мен. <br />
По възможност слагайте коментарите над самата функция с обяснения, какво точно се случва в нея, за какво служи, как се използва. Коментари може да сложите из кода в случай на по-сложна логика, която има нужда от обяснение. Ако логиката е прекалено сложна спрете и помислете как може да се опрости. <br />
Използвайте DocBlock коментари.

```js
/**
 * This is an example docblock comment. It describes a function called
 * marmite.
 *
 * It adds a number of jars of marmite to the cupboard.
 *
 * @method addMarmite
 * @param {Number} [jarCount=1] The number of jars of marmite to add to the
 * cupboard. This parameter is optional and defaults to 1.
 * @chainable
 */
```


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

В JSON:
```js
var json = '{"foo":"bar"}';
```
###Отварящата скоба е на същия ред.
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
    `Променлива за запазване на e-mail адрес на клиент.`

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
 * @method stopLocationPoller
 * @param  {LocationPoller} locationPoller The location poller object we want to stop
 * @return boolean Indicating if the location poller has actually stopped
 */
function stopLocationPoller(locationPoller) {
    //
}
```

###Когато в променливата пазим jQuery обект използваме $ за начало на името
Така при много променливи и работа с jQuery лесно ще се ориентираме на кои обекти
можем да извикваме jQuery функции.
```js
var $email = $("#email"); // refers to the jQuery object representation of the dom object
var emailField = $("#email").get(0); // refers to the dom object itself
var email = 'hasan@abv.bg'; //Refers to a non-jQuery object
```

###Сложните условия - отделно
Всички по-сложни условия в if да бъдат отделени в ясно говорима променлива преди самата проверка.

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
    console.log('what the hell did i just check');
}
```

###Boolean променливите да бъдат говорими
Имената им да започват с is, has, equals, isNot.. etc. <br />
Така ще се знае какво точно означава значение `true` или `false` за дадена променлива.

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

### #Функции
Намалете nesting-a до минимум. Избягвайте използването на повече от 3 нива функции във функции. 
Освен четимост на кода ще постигнем и възможност за преизползване на функциите и логиката в тях, както и ще можем да ги документираме четимо.  

Правилно:
```js
function doSomething() {
    var onAwesomeClick = function(){
        var doSomethingWithPerson = function(){
            //
        }
    
        $(this).find('.person').each(doSomethingWithPerson);
    }
    $('.stuff').each(function(){
        $('#awesome').on('click', onAwesomeClick);
    });
}
```

Грешно:
```js
function doSomething(){
    $('.stuff').each(function(){
        $('#awesome').on('click', function(){
            $(this).find('.person').each(function(){
                //etc. etc. etc.
            });
        });
    });
}
```
 
###Whitespace
Отделяйте с един празен ред логически свързаните части от кода. <br />
Не използвайте повече от един празен ред за отделяне на елементи.

###{} и []

Използвайте `{}` вместо `new Object()` и `[]` вместо `new Array()`.

###eval is Evil

Не използвайте eval. Ако не сте чували за eval, не го търсете. <br />
Не слагайте стрингове в setTimeout и setInterval, използвайте директно функции.

###Важно
Не смесвайте HTML-а с Javascript. <br />
Използвайте минимално HTML в Javascript-a и *НЕ* използвайте Javascript в HTML-a. <br />
За да използвате HTML в Javascript-a използвайте темплейти от DOM-a или под друга форма. <br />
Вместо да пишете логика в `onclick=""` и прочие - задайте евента с Javascript, ако ви трябват някакви стойности използвайте `data-` атрибута.
