# 函式(function)
## *什麼是函式 ?*
#### 如果你經常執行或重複執行的某區段程式，此時就可以將這些寫成一個函式，未來只要呼叫這些函式就可以執行那些區段程式 

---
## *如何宣告函式 ?*
### function 函式名稱(參數){你的程式碼}
* #### 一般函式
##### EX: 建立一個名叫sayHello的函式，不須設定參數
HTML
```htmlmixed=
<div id='message'>Wellcome to our site!</div>
```
JS
```javascript=
var msg ='This is function tutorial'
function sayHello(){
    var newText = document.getElementById('message')
    newText.textContent = msg
}
// 呼叫函式
sayHello()
```
#### 結果: HTML的message裡面的內容被改成 This is function tutorial
---
* #### 函式取得一個回傳值(return的東西)
##### EX: 建立一個名叫add的函式，並把參數設成(a,b)，呼叫此函數會回傳a+b的值
```javascript=
function add(a,b){
    return a+b
}

var addResult = add(11,12)
// 11,12稱為引數
console.log(addResult)
```
#### 結果: 23
---
* #### 函式取得多個回傳值(return的東西)
```javascript=
function getSize(width,height,depth){
	var area = width*height
	var volum = width*height*depth
	var sizes= [area,volum]
	return sizes
}
// 取得sizes裡的area
var areaOne=getSize(5,8,10)[0];
// 取得sizes裡的volum
var volumeOne = getSize(5,8,10)[1];
```
#### 結果: areaOne=40 ， volumeOne=400

## 匿名函式
#### 使用目的:在匿名函式中宣告的變數可以有效地與其他腳本中的相同名稱變數互相隔離保護，避免互相干擾
* ### 立即執行函式—IIFE(Immediately Invoked Function Expression)
#### 此種函式不具名稱，為匿名函式
#### EX: area將會儲存函式傳回來的值，且此函式無法再次呼叫
```javascript=
var area =(function(){
	var w= 3
	var h= 2
	return w*h
}())

console.log(area)
```
#### 結果:6

* ### 函式運算式
#### EX:函式被儲存在變數:area中
```javascript=
var area = function(w,h){
    return w*h
}
var size = area(3,4)
cosole.log(size)
```
#### 結果:12