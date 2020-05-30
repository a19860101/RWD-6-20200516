# 響應式網頁 0530 課程綱要

## CSS
### CSS分類
#### 嵌入式樣式
```html
<h1 style="color:red;">Title</h1>
```
#### 內部樣式
```html
<head>
	<title>標題</title>
	<style>
		h1 {
			color: red;
		}
	</style>
</head>
```
#### 外部樣式表
```html
<head>
	<title>標題</title>
	<link rel="stylesheet" href="style.css">
	<style>
		@import url("style.css");
	</style>
</head>
```
### 基本選取器
#### 標籤 tag
```css
p {
	color: red;
}
```
#### 類別 class
使用點開頭命名，可重複使用
```css
.abc {
	color: blue;
}
```
#### ID
使用#開頭，不可重複使用
```css
#xyz {
	color: yellow;
}
```
#### 萬用選取器 * 
預設套用在網頁的所有元素
```css
* {
	font-family: "Segoe UI";
}
```
### CSS 權重
當CSS發生衝突時，CSS會以權重去做區分。CSS影響的範圍愈小，權重就越重，權重越重，優先順序越高。
在預設的狀態下，權重大小：ID > CLASS > TAG
### CSS 文字相關樣式 
#### color --- 文字顏色

>快速鍵 c

```css
h1 {
    color: red;                /*色彩名稱*/
    color: rgb(255,0,0);       /*RGB色碼*/
    color: rgba(255,0,0,.5);   /*RGBA色碼*/
    color: #ff0000;            /*16進位*/
    color: #f00;               /*16進位縮寫*/
    color: hsl(112, 80%, 36%)  /*色相飽和度明度*/
}
```
>16進位算法
rgb(30,0,200)
30 / 16 = 1...14
0 / 16 = 0...0
200 / 16 = 12...8
#商餘商餘商餘
如果遇到十位數就轉換為A，所以16進位的16個分別為
0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F
rgb(30,0,200) => #1E00C8
***
#### text-align --- 文字對齊

>快速鍵:ta

*  left
* center
* right
* justify
***
#### text-decoration --- 文字裝飾

>快速鍵:td

* none
* underline
* overline
* line-through
***
#### font-size --- 字體大小

> 快速鍵:fz
>
單位:
* px
* em
* rem

> em 與 rem 的差別
> em 的比例是依循最靠近的父元素；rem 的比例是依循根的比例。假設父元素是 24px，子元素是 1.6em，最後的大小就是 24 x 1.6；若子元素是1.6rem，則還是維持 16 x 1.6。
***
#### font-family --- 字體種類

>快速鍵:ff

```css
font-family: "字體名稱" ;
```
常用預設字體
* Arial
* tahoma
* verdana
* gill sans mt
* segoe ui
除了使用預設的字體以外，也可以使用 Google 網路字體(Web Font)。
[Google Fonts](https://fonts.google.com/)
***
#### font-weight --- 粗體字

>快速鍵:fw
* bold
* 100-900
* normal
***
####  font-style --- 斜體字
>快速鍵:fs
* italic
* normal

***
#### letter-spacing --- 字元間距
>快速鍵:ls
字元之間的距離。
***
#### word-spacing --- 文字間距
>快速鍵:wos
英文單字之間的距離，中文無效
***
#### line-height --- 行高
>快速鍵:lh
行與行之間的距離，文字會在行高的正中間
***
#### text-transform
文字變形。指的是文字大小寫。
>快速鍵:tt 
* uppercase
* lowercase
* capitalize
***
#### font-variant
小型大寫字母
>快速鍵:fv

***
***
### CSS背景相關樣式 
#### background-color背景色

> 快速鍵: bgc
> 
```css
background-color: 色碼 ;
```
#### background-image 背景圖片或漸層

> 快速鍵: bgi
> 
* url() - 圖片
```css
background-image: url("圖片位置") ;
```
* linear-gradient() - 線性漸層
```css
background-image: linear-gradient(to right, red 30%,blue 40%, yellow 50%, green 60% );
```
* repeating-linear-gradient() - 線性重複漸層
```css
background-image: repeating-linear-gradient(45deg,transparent 0px,transparent 10px,blue 10px,blue 20px); 
```
* radial-gradient() - 放射性漸層
```css
background-image: radial-gradient(red 30%,blue 30%,blue 40%,yellow 40%, yellow 50%,green 50% );
```
* repeating-radial-gradient() - 放射性重複漸層
```css

```
***
#### background-repeat背景的重複方式

> 快速鍵: bgr
> 
* repeat - 完全重複
* repeat-x - x軸重複
* repeat-y - y軸重複
* no-repeat - 不重複

```css
background-repeat: repeat ;
```
***
#### background-position背景的位置

> 快速鍵: bgp
> 
```css
background-position: 100px 50px ;
/*背景水平偏移100px，垂直偏移50px*/
```
除了用數值表示，也可以使用方位
* top
* bottom
* center
* left
* right
```css
background-position: right top;
/*背景靠右上*/
```
***
#### background-attachment背景固定方式

> 快速鍵: bga
> 
* scroll - 捲動
* fixed - 固定

```css
background-attachment: fixed ;
```
***
#### background-size背景的大小

>快速鍵: bgz
> 
* contain - 等比例符合內容
* cover - 等比例填滿內容
***
***
### 清單相關樣式
#### list-style---清單樣式
* none
* disc
* circle
* square
* decimal
* upper-alpha
* lower-alpha
* upper-roman
* lower-roman
* cjk-ideographic
* hiragana
* katakana
* lower-greek
* armenian
* georgian
* hebrew
***
***
### 排版相關
#### width ---寬度
元素寬度
#### height--- 高度
元素高度。
> 若要讓高度可以滿版，有以下兩種做法
```css
/*作法一*/
html,body {
	height: 100%;
}
.box {
	height: 100%;
}
/*作法二*/
.box {
	height: 100vh;
}
```
***
#### border--- 邊框
```css
border:color style width;/*順序可交換*/

border-left:color style width;
border-right:color style width;
border-top:color style width;
border-bottom:color style width;

border-left-color: color;
border-right-color: color;
border-top-color: color;
border-bottom-color: color;

border-left-width: width;
border-right-width: width;
border-top-width:width;
border-bottom-width: width;

border-left-style:style;
border-right-style:style;
border-top-style:style;
border-bottom-style:style;
```
可使用的樣式-style
* solid
* double
* dotted
* dashed
* inset
* outset
* groove
* ridge

***
#### padding ---內距
邊框到內容之間的距離
* padding-left
* padding-right
* padding-top
* padding-bottom
* padding
***
#### margin--- 外距
邊框以外到下一個元素之間的距離
* margin-left
* margin-right
* margin-top
* margin-bottom
* margin
***
#### 縮寫(僅margin、padding有效):
在margin與padding中可使用縮寫的方式設定不同位置的距離。

```css
margin:10px;                /*上下左右*/
margin:10px 30px;           /*上下10px,左右30px*/
margin:10px 30px 0px;       /*上10px,左右30px,下0px*/
margin:10px 30px 0px 20px;  /*上10px,右30px,下0px,左20px*/
```
***
#### block與inline的差異
##### block
1. block永遠都會往下換行，如果有設定寬度，右方空缺的部分會由margin自動填滿；如果沒有設定寬度，則寬度會視為100%
2. 在block元素中，width、height、margin、padding、border都有作用
##### inline
1. 內容有多少，範圍就有多少
2. width、height、margin-top、margin-bottom沒有作用
3. padding-top、padding-bottom、border-top、border-bottom看的見效果，但不影響實際空間

> 基本上只要是行內元素，就不建議使用width,height,border,margin,padding這些屬性，如果要使用就轉換成block或是inline-block之類的其他模式
> 
#### display --- 轉換元素
* block
* inline
* inline-block
* table
* table-cell
* table-row
* flex
* inline-flex
* grid
### 補充網站
* [Color Hunt](https://colorhunt.co/)
* [Coolors](https://coolors.co/)
* [Nippon Colors](https://nipponcolors.com/)
* [Google Fonts](https://fonts.google.com/)
* [CanIUse](https://caniuse.com/)
