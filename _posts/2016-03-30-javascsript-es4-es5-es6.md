---
layout: post
title: javascript es4 es5 es6
categories: [javaScript]
---


## javascript 规范简书

1、es 262、es263

> 以上为常见的浏览器通用标准。

2、es4 

> 此版本过于复杂，未被广大厂商接受

3、es5 

```

> strict模式

`` use strict `` 

> Array 增加方法

`` every、some、forEach、filter、indexOf、lastIndexOf、isArray、map、reduce、reduceRight ``

> Object 增加方法

`` 

Object.getPrototypeOf

Object.create

Object.getOwnPropertyNames

Object.defineProperty

Object.getOwnPropertyDescriptor

Object.defineProperties

Object.keys

Object.preventExtensions / Object.isExtensible

Object.seal / Object.isSealed

Object.freeze / Object.isFrozen ``

> 其他增加方法

`` Function.prototype.bind、String.prototype.trim、Date.now 等``

es5主要为语言标准函数增强


```


## es6

```

ECMAScript6在保证向下兼容的前提下，提供大量新特性

1、块级作用域 关键字let, 常量const

2、对象字面量的属性赋值简写 

3、赋值解构

4、函数参数 - 默认值、参数打包、数组展开

5、箭头函数 Arrow functions

6、字符串模板 Template strings

7、Iterators（迭代器）+ for..of

8、生成器 （Generators）

9、Class 有constructor、extends、super，但本质上是语法糖，实际还是prototype

10、Modules ES6的内置模块功能借鉴了CommonJS和AMD各自的优点，类似python的import ... from ...

11、Map + Set + WeakMap + WeakSet 四种集合类型，WeakMap、WeakSet作为属性键的对象如果没有别的变量在引用它们，则会被回收释放掉。

12、Math + Number + String + Array + Object APIs

`` 

Number.EPSILON
Number.isInteger(Infinity) // false
Number.isNaN("NaN") // false
Math.acosh(3) // 1.762747174039086
Math.hypot(3, 4) // 5
Math.imul(Math.pow(2, 32) - 1, Math.pow(2, 32) - 2) // 2
"abcde".includes("cd") // true
"abc".repeat(3) // "abcabcabc"
Array.from(document.querySelectorAll('*')) // Returns a real Array
Array.of(1, 2, 3) // Similar to new Array(...), but without special one-arg behavior
[0, 0, 0].fill(7, 1) // [0,7,7]
[1, 2, 3].find(x => x == 3) // 3
[1, 2, 3].findIndex(x => x == 2) // 1
[1, 2, 3, 4, 5].copyWithin(3, 0) // [1, 2, 3, 1, 2]
["a", "b", "c"].entries() // iterator [0, "a"], [1,"b"], [2,"c"]
["a", "b", "c"].keys() // iterator 0, 1, 2
["a", "b", "c"].values() // iterator "a", "b", "c"
Object.assign(Point, { origin: new Point(0,0) }) 

``

13、Proxies 使用代理（Proxy）监听对象的操作，然后可以做一些相应事情

``
var target = {};
var handler = {
get: function (receiver, name) {
return `Hello, ${name}!`;
}
};
var p = new Proxy(target, handler);
p.world === 'Hello, world!'; 

可监听的操作： get、set、has、deleteProperty、apply、construct、getOwnPropertyDescriptor、defineProperty、getPrototypeOf、setPrototypeOf、enumerate、ownKeys、preventExtensions、isExtensible。

``

14、Symbols Symbol是一种基本类型。Symbol 通过调用symbol函数产生，它接收一个可选的名字参数，该函数返回的symbol是唯一的。

`` 
var key = Symbol("key");
var key2 = Symbol("key");
key == key2 //false

``

15、Promises Promises是处理异步操作的对象，使用了 Promise 对象之后可以用一种链式调用的方式来组织代码，让代码更加直观（类似jQuery的 deferred 对象）。 

总体来说es6有较多的特性，有些好有些一般。


```
