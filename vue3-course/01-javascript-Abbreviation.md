## Javascript Abbreviation

1. ES6 有新增語法糖(縮寫)以及新增語法

原始

```js
const obj = {
  myName: 'object',
  fn: function () {
    return this.myName;
  },
};

obj.fn(); // 'object'
```

語法糖 -> 不會影響運作

```js
const obj = {
  myName: 'object',
  fn() {
    return this.myName;
  },
};

obj.fn(); // 'object'
```

新增語法 -> 會影響運作

```js
const obj = {
  myName: 'object',
  fn() {
    return this.myName;
  },
};

obj.fn(); // undefined
```

2. 物件內的變數如果和 key 相同，可省略前面名稱

```js
const person = { name: 'andy' };

const people = { person };

people; //{person:{name:'andy'}}
```

3. 陣列展開合併

原始

```js
const groupA = ['a', 'b', 'c'];

const groupB = ['d', 'e'];

const groupAll = groupA.concat(groupB);

groupAll; //['a','b','c','d','e']
```

ES6 spread

```js
const groupA = ['a', 'b', 'c'];

const groupB = ['d', 'e'];

const groupAll = [...groupA, ...groupB];

groupAll; //['a','b','c','d','e']
```

4. 物件展開合併

```js
const methods = {
  fn1() {
    console.log(1);
  },
  fn2() {
    console.log(1);
  },
};

const newMethods={
  fn(){
    console.log(1)
  }
  ...methods
}

newMethods // {fn:fn(),fn1:fn1(),fn2:fn2()}
```

5. 展開轉換成純陣列

```js
const doms = document.querySelectorAll('li');

doms; //NodeList (_proto_並未包含陣列所有可取用方法)

const newDoms = [...doms];

newDoms; //Array (_proto_包含陣列所有可取用方法)
```

6. 預設值

未給予預設值

```js
function sum(a, b) {
  return a + b;
}
sum(1); //NaN
```

給予預設值

```js
function sum(a, b = 2) {
  return a + b;
}
sum(1); // 3

function sum(a, b = 2) {
  return a + b;
}
sum(1, 5); // 6
```
