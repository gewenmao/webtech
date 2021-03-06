# 函数柯里化

实现如下代码：

```js
one(add(two()))
two(add(one()))
```

实现方式如下：

```js
const one = fn => typeof fn === 'function' ? fn(1) : 1;

const two = fn => typeof fn === 'function' ? fn(2) : 2; 

const add = num1 => num2 => num1 + num2;


one(add(two())); // 3
two(add(one())); // 3
```

也可以如下：

```js
const number = num => fn => typeof fn === 'function' ? fn(num) : num;
const add = num1 => num2 => num1 + num2;

const one = number(1);
const two = number(2);


one(add(two())); // 3
two(add(one())); // 3
```
