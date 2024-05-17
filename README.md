<h2>What are <span style="color:pink">Hoisting</span> and <span style="color:pink">Scope</span> in JavaScript?</h2>


####  Podnytaie ili Hoisting - eto mekhanizm v JS, v kotorom peremenie i obyavlennie function-i peredvigaytsya vverkh ⬆️ `yanne vaqte ki kodi mo ba bolo meravad dar oblast vidimost pesh az on ki kod ijro karda meshavad`

>[!TIP]
>hoisting yane boloravi dar `function declaration` dar lyuboi moment kor mekunda chi mo functionro dar bolo faryod kunem chi dar tag ammo dar `function expression` va `IIFE` mo tanxo dar poyon Hoisting karda metavon chun ki `TypeError and ReferenceError` medixad
:Misol

``` js
console.log(expression(2,2));//ReferenceError: Cannot access 'declaration' before initialization
let expression=function(a,b){
    return a*b
}
```

>[!TIP]
>ammo dar `function declration` hoisting mewavad 

:Misol

``` js
function declration(a,b) {
    return a*b
}
console.log(declration(2,2));//4
```

# 👀 Рассмотрим следующий пример:


```js
var myname = "John";
function fn() {
  console.log(myname);
  var myname = "Tom";
  console.log(myname);
}

fn();

// undefined
// Tom
```

>[!TIP]
>`var имеет область действия функции;
объявления var поднимаются, но не инициализируются.`

```js
console.log(name); // undefined
var name = "Alex";//baroi chi underfined baroi on ki in var hast hamewa hoist meshavad ammo dar tori var log nameshavad
```
```js 
var name;
console.log(name); // undefined
name = "Alex";
```
 # const and let 

>[TIP]
# const и let имеют область видимости блока.

```js
{
  console.log ( x )
  // [ временная мёртвая зона ][tdz][temporarl dead zone]
  let x = 10 // Объявленные с помощью let, будут недоступны до тех пор, пока выполнение кода не дойдёт до места фактического объявления переменной
}
```
# farqitawon dar in jo faxmonda wudaast
```js
console.log(a); // undefined
var a = 1;

console.log(b); // ReferenceError: Cannot access 'b' before initialization
let b = 2;

console.log(c); // ReferenceError: Cannot access 'c' before initialization
const c = 5;
```


<h2 style="color:yellow">Введение в JavaScript SCOPE</2>
<h6 style="color:brown">scope in oblast vidimosti dar JS meboshad</h6>


* Область видимости или Scope
* Глобальная область видимости или Global Scope
* Локальная область видимости или Local Scope
* Область видимости функции
* Область видимости блока
* Лексическая область видимости
* Динамическая область видимости

``` diff
-Область видимости (scope) определяет видимость или доступность переменной (другого ресурса) в области твоего кода.
```
```js

var num = 5;
console.log(num);   // 5

function getNum(){
  console.log(num); // num доступен здесь
}

getNum();           // 5 i chiz faqat var da mumkinai digaroda ne⬆️
```
 

# ⬆️   i GLOBAL SCOPE ai 


#### dar js mo dorem
# module scope
# block scope
# function scope
# global scope 

#### local scope peremennixoi daruni function a megan `local ni oblast megan ujara xar yak function oblast vidimosti xcha dora` ``Одна и та же переменная может использоваться в разных функциях, поскольку они связаны с соответствующими функциями и не являются взаимно видимыми.`yak peremenira dar chand funtion istifoda burda meshiday`


``` js
// Глобальная область

function foo1(){
    // Локальная область 1
  function foo2(){
    // Локальная область 2
  }
}

// Глобальная область
function foo3(){
  // Локальная область 3
}

// Глобальная область
```

>Локальная область видимости может быть разделена на область видимости функции и область видимости блока. Концепция область видимости блока или block scope была представлена в ECMAScript6 (ES6) вместе с новыми способами объявления переменных - const и let.

# Область видимости функции
> var a function scope am megan baroi on ki var lyuboijo rafta metona lekin var-a tolko function qapida metona

``` js
function foo(){
  var num = 10;
  console.log('inside function: ', num);
}

foo();                   // inside function: 10
console.log(num);       // ReferenceError: num is not defined
```