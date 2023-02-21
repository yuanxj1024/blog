

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




