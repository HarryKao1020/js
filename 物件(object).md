# 物件(object)
## *什麼是物件?*
### 物件就是把一群變數跟函式組合在一起成為一個模型
* #### 物件中的變數稱為:特性
* #### 物件中的函式稱為:方法
#### EX: 一個旅館有五個特性和一個方法
```javascript=
var hotel={
// 特性:
// 鍵:name,rooms,booked,gym,roomTypes

	name: 'LoveHotel',   --string
	rooms: 30,           --num
	booked: 15,          --num  
	gym: true,           --boolean
	roomTypes:['twin','single','double'],   --array
// 方法:
	checkAvailability: function(){          --方法
		return this.rooms-this.booked;
	}
}

存取物件和句點標示法
var hotelName = hotel.name
var hotelName = hotel['name']
// 方法無法用中括號語法
var roomsFree = hotel.checkAvailability();


```

### 範例建造一個停車場車位狀況
HTML
```htmlmixed=
<div id='parkName'>

</div>
<div id='spaces'>

</div>
```
JS
```javascript=
var parking={
	name:'HaHa Parking lot',
	space: 100,
	full_space: 84,
	remain: function(){
		return this.space - this.full_space
	}
}
var elName = document.getElementById('parkName')
elName.textContent= parking.name
var elSpace = document.getElementById('spaces')
elSpace.textContent=parking.remain()
```
#### 結果:HTML指定的ID被填入name跟remain的結果
---

### 新增和移除特性
#### EX:以上面parking為例
```javascript=
var parking={
	name:'HaHa Parking lot',
	space: 100,
	full_space: 84,
    gym: true,
	remain: function(){
		return this.space - this.full_space
	}
}
// 新增和刪除特性
parking.motoSpace = true
parking.pool = false
delect parking.gym;

var elName = document.getElementById('parkName')
elName.textContent= parking.name
var elSpace = document.getElementById('spaces')
elSpace.textContent=parking.remain()
```

---



## *建構式*
#### 使用 function 來建立物件樣板 (只能使用 function，亦不能使用箭頭函式)。

這個結構與上面所使用的結構接近，不同的是：
* this 則是代表此物件的屬性
* 可以透過參數來傳入數值
* 使用 new 來套用此樣板，且最終一樣會產生物件
#### EX:以上面Hotel為例:
```javascript=
function ObjectTemplate(name,rooms,booked){
	this.name = name;
	this.rooms = rooms;
	this.booked = booked;
	this.checkAvailability = function(){
		return this.rooms - this.booked;
	};
}

var AppleHotel = new ObjectTemplate('Apple',80,60)
var BananaParkinglot = new ObjectTemplate('Banana',200,30)
console.log(AppleHotel.checkAvailability())
// 印出 20
```


