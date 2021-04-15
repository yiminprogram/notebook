## Arrow Function

1. callback function 改成箭頭函式的差異

function

```js
var name = 'global';

const obj = {
  name: 'apple',
  callName: function () {
    console.log(this.name);
    setTimeout(function () {
      console.log(this.name);
    });
  },
};

obj.callName(); // 'apple','global'
```

arrow function

```js
var name = 'global';

const obj = {
  name: 'apple',
  callName: function () {
    console.log(this.name);
    setTimeout(() => {
      console.log(this.name);
    });
  },
};

obj.callName(); // 'apple','apple'
```
