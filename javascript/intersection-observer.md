# Intersection Observer

- [Intersection Observer](#intersection-observer)
  - [Create observer](#create-observer)
  - [Option setting](#option-setting)
  - [Method](#method)
  - [Code Example](#code-example)

> IE 11 Not support, need to add polyfill

## Create observer

```js
const observer = new IntersectionObserver(callback, { option });
```

## Option setting

```js
{
  root:null,
  rootMargin:'0px 0px 0px 0px',
  threshold:[0]
}
```

- root:viewport
- rootMargin:viewport margin
- threshold:target display percentage in viewport
  - ex. threshold:[0]:callback when touch viewport
  - ex. threshold:[0,0.25,0.50]:callback when show 0%, 25% and 50%

## Method

- watch element

```js
observer.observer(element);
```

- disable watch element

```js
observer.unobserver(element);
```

- close watch

```js
observer.disconnect();
```

## Code Example

```js
const target=document,querSelector('#target');
const handle=(entry)=>{
  if(entry[0].isInsecting){
    //do sth.
  }
}

const server=new IntersectionObserver(handle,{
  //setting option
});

observer.observer(target);
```
