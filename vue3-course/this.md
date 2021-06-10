## This

1. 開啟 browser debugger

```js
function method() {
  console.log('apple');
  debugger; //需開啟dev tool，運作程式碼會自動停留在此程式片段
}

method();
```

2. const,let 與 var 宣告的不同

```js
const myName='apple';

const obj1={
  myName='pen';
  callName:()=>{
    console.log(this.myName);
  }
}

const obj2={
  myName='apple';
  callName(){
    console.log(this.myName);
  }
}

obj1.callName(); // undefined

obj2.callName(); // 'apple'
```

obj1.callName()的原因為外部使用 const 宣告變數，const 及 let 宣告之變數有數與自己的作用域，故並非於全域作用域宣告變數，使用 `myName='apple'`或`var myName='apple'`，才會宣告於全域(global)底下

3. simple call

```js
name = 'global';

function callName() {
  console.log(this.name);
}

const obj3 = {
  name: 'apple',
  fn() {
    callName();
  },
};

obj3.fn(); // 'global'
```

simple call 指向為 global 但通常不太會照樣調用 this

解決方法：

- this 先指向其它變數

```js
var name = 'global';

const obj = {
  name: 'apple',
  callName: function () {
    console.log(this.name);
    const vm =this;
    setTimeout(function {
      console.log(vm.name);
    });
  },
};

obj.callName(); // 'apple','apple'
```

- 使用 arrow function

3. setTimeout，callback function 也是 simple call 形式，this 通常指向為 global

4. 一般函式與箭頭函式 this 的差別

```js
item = 'global';

const fn = {
  item: 'apple',
  callName() {
    console.log(this.item);
  },
};

const arrowFn = {
  item: 'apple',
  callName: () => {
    console.log(this.item);
  },
};

fn.callName(); // 'apple'

arrowFn.callName(); // 'global'
```
