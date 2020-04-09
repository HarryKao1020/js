# D O M 文件物件模型

## 存取元件
### 1.  選取單一元件節點
#### 方法:getElementById(),querySelector()

```javascript
// 選取Id:one存在el變數中
var el = document.getElementById('one')

// 變更元件class屬性
el.className = 'cool'
```
### 2.  多個元件的DOM查詢(節點串列)
##### 特性: length :節點串列中的項目數量
##### 方法: item() :取的串列中某個節點
HTML
```htmlmixed=
<ul>
  <li class="hot" id="one">one</li>
  <li class="hot" id="two">two</li>
  <li class="hot" id="three">three</li>
</ul>
```
JS:取的li的每個東西，每個li都有一個索引值(index)，並利用item(index)方法取出某個節點項目
```javascript=
var items = document.getElementsByTagName('li')
console.log(items.item(0))
console.log(items.item(1))
console.log(items.item(2))
var elements=document.getElementsByClassName('hot')
console.log(elements.length)
```
結果:
```htmlmixed=
<!-- 0 --> "<li class='hot' id='one'>one</li>" 
<!-- 1 --> "<li class='hot' id='two'>two</li>"
<!-- 2 --> "<li class='hot' id='three'>three</li>"

<!-- 長度 --> 3
```

### 3.  節點之間的巡訪
* #### parentNode : 尋找目前節點的父節點
* #### firstChild : 尋找目前節點的第一個子節點
* #### lastChild : 尋找目前節點的最後一個子節點
HTML
```htmlmixed=
<ul>
  <li class="hot" id="one">one</li>
  <li class="hot" id="two">two</li>
  <li class="hot" id="three">three</li>
</ul>
```
JS
```javascript=
// 取得某個節點
var startItem = document.getElementById('one')

// 尋訪他的父節點
var parentItem = startItem.parentNode

console.log(parentItem)
// 更改父節點的class
parentItem.className = 'cool'
console.log(parentItem)
```
結果:

```htmlmixed=
第一個console:
<ul>
<li class='cool' id='one'>one</li>
<li class='hot' id='two'>two</li>
<li class='hot' id='three'>three</li>
</ul>

<!--  -->
第二個console
<ul class='cool'>
<li class='cool' id='one'>one</li>
<li class='hot' id='two'>two</li>
<li class='hot' id='three'>three</li>
</ul>
```

