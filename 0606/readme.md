# 響應式網頁 0606 課程綱要

## CSS
### CSS排版相關
#### box-sizing
元素在預設的狀態時，總寬度=width+border+padding、總高度=height+border+padding，設定box-sizing之後不管padding與border設定多少，寬度依然保持原始的值
```css
* {
    box-sizing: border-box;
}
```
#### inline-block
行內區塊。讓元素保有行內與區塊的特性

##### 產生的問題
1. inline-block之間會有一個約4像素間距
> 解決方式：將父元素的font-size設定為0，
2. 文字會消失
> 解決方式：將元素本體的font-size還原。若區塊中沒有文字需求可省略。 
3. 預設的垂直對齊方式為baseline，區塊對齊在下方。
> 解決方式：設定vertical-align
#### vertical-align 垂直對齊
元素垂直對齊的方式，只對inline-block、table內元素有效
* baseline
* top
* middle
* bottom

#### 區塊置中
預設狀態下，區塊右邊剩餘的空間都是margin，預設為margin-right: auto，在這邊auto可以視為自動填滿margin；若將margin-left設定為auto時，則變成左邊填滿，區塊就會移到右邊；左右同時設定auto，區塊就會置中。

#### calc  運算
如果是有數值的屬性，皆可使用calc()做計算
```css
.container {
    width: calc(100% / 3);
    height: calc(100px + 50px);
}
```
> 在運算子的前後要加上空格，否則會造成解析錯誤