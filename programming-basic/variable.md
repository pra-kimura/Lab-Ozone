# 変数  
変数とは、値の容器です。
```
let [変数名]: [型]
```  
と書くと作り出せます。
JavaScriptには「let」でなく「var」がありますが、わかりやすくするために「let」に統一します。  

## number型  
数字が入ります。  
```
let x: number;
x = 1;
x = 2;
```

### const   
今後値を変えない定数をつくるときに使います。
```
const x = 3;
```
constは作るとき以外に代入できません。また、作るときに代入しなければなりません。
```
const x; //ダメ
```
```
const x = 4;
x = 5; //ダメ
```

## string型
文字列が入ります。
```
let name: string;
name = "Alice";
name = "Bob";
```
定数も作れます。
```
const aiueo = "あいうえお";
```

## 複合型
```
let charlie: {
    address: string,
    age: number
};
```
定数も作れます。
```
const david = {
    address: "京都市下京区",
    age: 29
};
```

これらはすぐに覚える必要はありません。これを見ながらコードを書くことによって身についていきます。  