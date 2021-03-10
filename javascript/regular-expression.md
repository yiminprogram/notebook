# Regular Expression

## 1. 普通字元

- /a/

  -> This is `a` `a`pple

- /is/

  -> Th`is` `is` a apple

<br/>

## 2. 特殊字元 [\^\$|?\*+()

- /1\+2=3/

  -> 1 + 2 = 3

<br/>

## 3. 任意字元

- /a.man/

  -> I'm `a man`

- /.a/

  -> A `banana`

<br/>

## 4. 多個字元

- /[aA]/

  -> `Ａ a`pple

- /aeiou/

  -> Th`e`r`e` `i`s `a` `a`ppl`e`

- /[a-z]/

  -> T`here is a apple`

- /[a-zA-Z]/

  -> `I`'`m` `20 years old`.

- /[5-8]/

  -> 09`12345678`9

- /[^a]/

  -> `There is` a a`pple`

- /[^0-9]/

  -> `I'm` 20 `years old`

<br/>

## 5. 多個字元縮寫

- \d - digit [0-9]

- \w - word [A-Za-z0-9_]

- \s - space [\n\r\t]

- /\we/

  -> T`here` is a app`le`

- /\d\d/

  -> I'm `20` years old.

---

- \D - non-digit [^\d]

- \W - non-word [^\w]

- \S - non-space [^\s]

- /\D/

  -> 1`+`2`=`3

- /\W/

  -> I`'`m 20 years old

<br/>

## 6. 出現次數

- \* 任意次數

- \+ 至少一次

- ? 零或一次

- /I\*/

  -> He`ll`o Wor`l`d

- /n?a/

  -> b`anana`

---

- {次數}

- {最少次數，最多次數}

- /I{2}/

  -> He`ll`o World

- /I{1,}/

  -> He`ll`o Wor`l`d

<br/>

## 7. 頭尾

- ^ 開頭

- \$ 結尾

- /^He/

  -> `He`llo Hello

- /llo\$/

  -> Hello He`llo`

- /^He.\*llo\$/

  -> `Hello Hello`

## 8. 或

- /and|android/

  -> ios `and` `and`roid

- /android|and/

  -> ios `and android`

## 9. 常見用法

- Date `/^[1-9]\d{3}-\d{2}-\d{2}\$/`

  -> "2021-01-01"

- ID `/^[A-Z]\d{9}\$/`

  -> "A123456789"

- Email `/^\w+@gmail\.com\$/`

  -> "email@<span></span>gmail.com"

- Math `/^[\d\+\-\*\/]\*\$/`

  -> "1 + 2 \* 3 / 4"

## 10. 字串取代

```js
'banana'.replace(/na/, 'NA'); //'baNAna'

'banana'.replace(/n./, 'NA'); //'baNAna'

'banana'.replace(/na.*/, 'NA'); //'baNA'

'banaNA'.replace(/NA/, 'na'); //'baNAna'

'banana'.replace(/na/g, 'NA'); //'baNANA'

'baNanA'.replace(/na/gi, 'NA'); //'baNANA'

//g => global search

//i => ignore case
```

## 11. 字串選取

```js
'apple'.match(/(a.)(p.)e/);
//$1 = 'ap'
//$2 = 'pl'

'apple'.replace(/(a.)(p.)e/, '$1$2'); //'appl'
'apple'.replace(/(a.)(p.)e/, '$1$1'); //'apap'

'banana'.match(/(.)(a)/g);
//$1 = ['b','n','n']
//$2 = ['a','a','a']

'banana'.replace(/(.)(a)/g, '$1$2'); //'banana'
'banana'.replace(/(.)(a)/g, '$1'); //'bnn'
```

```js
'2021/01/02'.match(/(.*)\/(.*)\/(.*)/);
//['2021/01/02','2021','01','02']

Json.parse(
  '2021/01/02'.match(/(.*)\/(.*)\/(.*)/),
  '{"year":"$1","month":"$2","day":"$3"}',
);
//{year:'2021',month:'01',day:'02'}
```
