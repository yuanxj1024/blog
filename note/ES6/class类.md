

# Class

- 问题
  - Babel 如何实现Class？
  - ES5 如何实现 Class?

- 一种语法糖，写法清晰、面向对象编程

- 类的数据类型就是函数，类本身就指向构造函数

## constructor()方法

是类的默认方法,使用 new 关键字时自动调用该方法.

类必须有constructor() 没有时，会默认添加。

默认返回实例对象（this）

**类的属性和方法，除非显式定义在其本身（即定义在this对象上），否则都是定义在原型上（即定义在class上）。**

** 与 ES5 一样，类的所有实例共享一个原型对象。 **

使用 Object.getPrototypeOf() 方法来获取实例对象的原型

## 属性表达式

```js
const methodName = 'getArea';

class Square {
  constructor(length) {
    // ...
  }

  [methodName]() {
    // ...
  }
}
```

## 私有属性

早期写法： 使用 call 调用定义好的纯函数

```js
class Widget {
  foo (baz) {
    bar.call(this, baz);
  }

  // ...
}

function bar(baz) {
  return this.snaf = baz;
}
```

标准写法（ES2022)

> 属性名之前使用#表示。

不管在类的内部或外部，读取一个不存在的私有属性，也都会报错

```js
class Person {
  // 私有属性，外部无法访问
  #address = '';
  constructor(name) {
    this.name = name;
  }

  getAddress() {
    return this.#address;
  }
}
```

私有属性和私有方法前面，也可以加上static关键字，表示这是一个静态的私有属性或私有方法。

# 静态块 static block

> 允许在类的内部设置一个代码块，在类生成时运行且只运行一次，主要作用是对静态属性进行初始化。以后，新建类的实例时，这个块就不运行了。

```js
class C {
  static x = ...;
  static y;
  static z;

  static {
    try {
      const obj = doSomethingWith(this.x);
      this.y = obj.y;
      this.z = obj.z;
    }
    catch {
      this.y = ...;
      this.z = ...;
    }
  }
}
```

# new.target 属性

> 只能在构造函数中使用

new是从构造函数生成实例对象的命令。ES6 为new命令引入了一个new.target属性，该属性一般用在构造函数之中，返回new命令作用于的那个构造函数。如果构造函数不是通过new命令或Reflect.construct()调用的，new.target会返回undefined，因此这个属性可以用来确定构造函数是怎么调用的。