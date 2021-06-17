# javascript

## 介绍

### 历史

  1990年,浏览器出现

  1995年, 网景公司 布兰登`艾奇 10天 创建出一个脚本语言  Mocha

  9月  LiveScript

  11月 java的顺风车  javaScript

  ie: Jscript 

  1997年  欧洲计算机制造商协会 ECMA  

  生成的第一个标准: ECMAScript 

### js与ECMAScript的关系

javaScript是ECMAScript的表现 

ECMAScript是javascript的语法标准

### js的概念

js: 是一种基于对象和事件驱动的解释性脚本语言

### js的特点

1. 基于对象: 一切皆对象, js可以使用自己创建出来的对象

2. 事件驱动: 页面的效果由事件进行驱动的，浏览器会根据用户的操作进行响应

3. 解释性: 相对于后台的编译性来说, 浏览器可以不解释代码，直接识别并且执行

4. 跨平台性: 只要有浏览器, js就可以被执行

### js可以做什么

1. 表单提交验证

2. 云计算

3. 动态效果

4. 数据请求

5. ...

### js的版本介绍

​    ECMAScript  es5

​    es6...es10 

### js的组成部分

1. ECMAScript 语法标准

2. BOM： 浏览器对象模型

3. DOM: 文档对象模型

### js的引入方式

#### 分类

1. 行内
2. 内嵌
3. 外链

#### 行内

行内式  事件驱动: onclick="代码"

```html
<div class="a" style="width: 300px;" onclick="alert('这是一个盒子1')">这是一个div</div>
```

#### 内嵌

内嵌式  script 双标签 可以放在页面的任何位置，建议: body的结束标签之前

```html
<script>
    // 内嵌的js
    alert('3');
</script>
```

#### 外链

外链式  先有一个js的文件 后缀: .js 文件中直接写js代码  引入js文件 script双标签 src设置成文件的地址

​    注意 ： 在外链的script中，不能写其他的内嵌代码 因为内嵌代码不会执行

```html
<script src="index.js">
    alert('8');
</script>
```

#### 使用情况

1. 行内 少用 不用

2. 内嵌： 学习过程中多用 开发少用

3. 外链  开发常用

### 调试语句

1. 调试语句: 语法: alert('内容')    阻断页面

   ```javascript
   alert('5'); 
   ```

2. console.log('要输出的内容')

   console.log(值, 值1, ....)

   ```javascript
   box.onmousemove = function(){
       // alert('9');
       console.log('9');
   }
   ```

## 事件三部曲

1. 找，找到给谁加 获取元素

​          a. 通过id获取 document.getElementById('id')

​          document---文档

​          get---获取

​          Element--元素

​          ById: 通过id

2. 添加事件

​          元素.事件 = function(){}

3. 具体做的操作

​          元素.事件 = function(){

​            // 代码操作

​          }

```javascript
document.getElementById('box').onclick = function(){
    alert('1');
}
```

## 报错

没有效果的时候: 

1. 检查: console

2. 看是否有报错

​          Uncaught TypeError: Cannot set property 'onclick' of null 不能把onclick事件加给null

```javascript
alert(document.getElementById('box')); // null
document.getElementById('box').onclick = function(){
    alert('1');
}
```

## window.onload

等待页面及资源加载完成后再执行其中的代码

​      window.onload = function(){

​        // 所有页面操作

​      }

```javascript
window.onload = function () {
    alert(document.getElementById('box')); // null---> 加了window.onload之后可以获取到元素
    document.getElementById('box').onclick = function () {
        alert('1');
    }
}
```

## 鼠标事件

​      onclick: 单击

​      ondblclick: 双击

​      onmouseover: 滑入

​      onmouseenter: 滑入

​      onmouseout: 滑出

​      onmouseleave: 滑出

​      onmousedown: 按下

​      onmouseup: 抬起

​      onmousemove: 移动

​      oncontextmenu: 右键菜单

```javascript
// 单击
// document.getElementById('box').onclick = function(){
//     alert('1');
// }

// 双击   调试双击  注释掉单击的代码  两次快速单击是一次双击
// document.getElementById('box').ondblclick = function(){
//     alert('2');
// }

// // 滑入: onmouseover onmouseenter  当元素外面进入到元素里
// document.getElementById('box').onmouseover = function(){
//     alert('3');
// }

// document.getElementById('box').onmouseenter = function(){
//     alert('4 ');
// }

// // 滑出: onmouseout  onmouseleave  当从元素里面进入到元素外
// document.getElementById('box').onmouseout = function(){
//     alert('5');
// }

// document.getElementById('box').onmouseleave = function(){
//     alert('6 ');
// }

// 按下: 当鼠标在元素上按下
// document.getElementById('box').onmousedown = function(){
//     alert('7');
// }

// 抬起: 当鼠标在元素上抬起
// document.getElementById('box').onmouseup = function(){
//     alert('8');
// }

// 移动: 当鼠标在元素上移动的时候
document.getElementById('box').onmousemove = function(){
    // alert('9');
    console.log('9');
}

// 右键菜单: 当对元素右键
document.getElementById('box').oncontextmenu = function(){
    alert('10');
}
```

### over与enter的区别

onmouseover 与 onmouseout是一组对应的滑入滑出, over从父元素进入子元素的时候也会触发父元素的事件, enter不会触发父元素的事件

```javascript
// 事件三部曲
// document.getElementById('box').onmouseover = function () {
//     console.log(1);
// }

// document.getElementById('box1').onmouseenter = function () {
//     console.log(2);
// }

document.getElementById('box').onmouseout = function () {
    console.log(1);
}

document.getElementById('box1').onmouseleave = function () {
    console.log(2);
}
```

## 变量

### 变量声明

​      变量： 用来数据的容器 一切数据

​      用var来声明变量

​      语法: var 变量名 = 值;

​      用于存储数据的时候

```javascript
// 1. 先声明，后赋值   设x;  x = 10;
var a;
a = 20;
console.log(a);

// 2. 声明的同时并赋值
var b = 'abc'; // 除了变量以外的字母都加引号
console.log(b);

// 3. 声明多个, 先声明后赋值
var c, d, e; // 声明
c = 50;
d = e = 'cdf';
// console.log(c);
// console.log(d);
// console.log(e);
console.log(c, d, e);

// 4. 多个同时声明
var m = 20, n = 30;
console.log(m, n);

var o = p = 'abc';
console.log(o, p);
```

### 命名规范

强制：

1. 由字母、数字、_ 、$组成, 数字不能开头

2. 不能使用关键字和保留字

3. 不能重复, 如果重复后面的会覆盖前面的

建议：

1. 具有语义化 userName password

       2. 遵循小驼峰命名法 多个单词组成一个命名, 从第二个单词开始的首字母大写 userName userPassword userAgeAndName

```javascript
// var 1a = 30;  报错
var $a = 30;

// var var = 20;  报错
// var class = 40; 报错

var $a = 50;
console.log($a);
```

## 表单值得操作

### 获取

1. 语法: 表单元素.value

2. 注意: 如果option上, 有value属性, 获取的就是value中的内容 如果没有value, 获取option中间的内容

```javascript
// 获取input的值  先获取input元素
var inp = document.getElementById('inp');
// 调试
console.log(inp); // null表示获取失败
console.log(inp.value); // 123456

// 获取文本域
var text = document.getElementById('text');
console.log(text);
console.log(text.value);

// 获取下拉列表
var city = document.getElementById('city');
console.log(city);
console.log(city.value);
```

### 设置

1. 语法: 表单元素.value = 要设置的内容;

2. 注意: 如果option上, 有value属性, 设置的就是value中的内容 如果没有value, 设置option中间的内容

```javascript
// 设置inp的值为小乔
inp.value = '小乔';
text.value = '王者荣耀';
// city.value = 'bj';
city.value = 'bj '; // 选不中北京
```

## 闭合标签的内容

### 获取

双标签  闭合标签 

操作内容: 起始标签到结束标签中间的叫做内容

获取:

​        innerHTML: var 变量 = 标签.innerHTML;

​          \1. 可以识别标签的

​        innerText: var 变量 = 标签.innerText;

​          \1. 不可以识别标签的

```javascript
var box = document.getElementById('box');
console.log(box);
var html = box.innerHTML;
console.log(html);

var text = box.innerText;
console.log(text);
```

### 设置

标签.innerHTML = '要设置的内容';

标签.innerText = '要设置的内容';

1. 设置的时候会覆盖原有标签的内容

2. 后面的会覆盖前面的

3. 设置的时候innerHTML可以设置标签 innerText不可以设置标签

```javascript
box.innerHTML = '这是我通过js设置的内容';
box.innerHTML = '这是一个新的div';

box.innerText = '这是一个文本内容';
box.innerText = '<i>这是一个文本内容</i>';
box.innerHTML = '<i>这是一个文本内容</i>';
```

## 操作属性

在起始标签上, 除了起始标签名字以外的都是标签的属性

起始标签上 等号【=】左边的就是属性名 【=】右边的是属性值 

获取: var 变量 = 元素.属性名; var 变量名 = 元素['属性名']; var 变量1 = 元素[变量2];

设置: 元素.属性名 = '值';  元素['属性名'] = '值'; 元素[变量] = '值';

```javascript
// 获取元素
var box = document.getElementById('box');
console.log(box);
console.log(box.id); // box

box.id = 'b';

var idName = box['id'];
console.log(idName);

var aa = 'id'; // 变量
console.log(box[aa]);

box[aa] = 'bBox';
```

### 操作id

获取: var 变量 = 元素.id;

设置: 元素.id = '值';

```java
var box = document.getElementById('box');
console.log(box);
console.log(box.id); // box

box.id = 'b';
```

### 操作src

获取: 元素.src 获取到的是绝对路径 一般不用 用相对路径

设置: 元素.src = '地址'; 地址: 相对路径 相对于当前html的路径 ./同级 ../ 跳出一级 上一级

```javascript
var img = document.getElementById('img');
console.log(img);
console.log(img.src); // file:///E:/1026/day01/img/1.jpg  绝对路径

img.src = './img/2.jpg';
```

### 操作class

获取: var 变量 = 元素.className;

设置： 元素.className = '值';

什么时候使用className

1. 当批量设置样式

2. 样式随鼠标改变的时候 点击div改变div的样式

```javascript
aBox.className = 'aa';
aBox.onclick = function(){
    aBox.className = 'cc';
}
```

```css
div{
    width: 200px;
    height: 200px;
    background: red;
}
.aa{
    width: 500px;
    height: 500px;
    background: pink;
    border: 10px solid skyblue;
}
.cc{
    width: 200px;
    height: 300px;
    background: #f09811;
    padding: 30px;
}
```

### 操作样式

只能操作行内样式

#### 单个操作

​        获取: 元素.style.属性名(width height padding)

​        设置：元素.style.属性名 = '值';

​        样式可以累加 只改一个样式

```javascript
var box = document.getElementById('box');
console.log(box);
console.log(box.style.width);
console.log(box.style.height);

box.style.width = '1000px';
box.style.height = '1000px';
box.style.color = 'white';
```

**注意: js中不允许出现"-"， 将带有连字符的单词转成驼峰命名法**

​        **font-size: fontSize**

```javascript
// box.style.font-size = '100px'; // 报错
box.style.fontSize = '100px';
```

#### 批量操作

批量设置样式: 获取到的是行内的style上的所有的值

​        获取: 元素.style.cssText

​        设置: 元素.style.cssText = '值';

​        值: 与css样式表中的写法一致  用 :;

​        cssText会覆盖原来标签上的style的所有的值

​        设置初始样式 回归初始样式

```javascript
console.log(box.style.cssText); // width: 1000px; height: 1000px; color: white; font-size: 100px;
box.style.cssText = 'color: #f00; background: purple;width:1000px;height: 1000px;';
```

## 数据类型

 ### 分类

1. 基础数据类型
   + number: 数值
   + string: 字符串
   + boolean: 布尔值
   + null: 空
   + undefined: 空
2. 复杂/引用/复合数据类型
   + object: 对象 一切皆对象
   + array: 数组
   + function: 函数

### 检验数据类型

typeof  数据

typeof(数据)

### 基础数据类型

#### 数值类型

1. 整型: 整数

2. 浮点型: 数值中有一位小数点，并且小数点后不为0的

​          注意: 由于计算机精度问题, 导致小数计算不精确

3. 特殊值: 

   + NaN: Not a Number 不是一个数字 

     计算错误的时候会出现

     特性: 

     + NaN利用typeof检验以后的结果number
     + NaN与任何数值计算得到的结果都是NaN
     + NaN与任何数值都不相等，包括自身

   + 进制数 

     + 八进制： 以0为开头，并且后面没有超过8的数字 
     + 十六进制: 以0x为开头, 0-9a-f代表0-15 a--10 b--11

   + 无穷值  Infinity  -Infinity  除数为0

   + e--10的次幂

   ```javascript
   var a = 30;
   console.log(a);
   console.log(typeof a); // number
   console.log(typeof(a)); // number
   
   var b = 22.01;
   console.log(typeof b);
   
   console.log(0.1 + 0.2); // 由于计算机精度问题, 导致小数计算不精确   0.30000000000000004
   
   console.log(1/3);
   
   console.log(10 - 'a'); // NaN
   
   console.log(typeof NaN); // number
   
   console.log(NaN + 10);
   console.log(NaN - 10);
   
   console.log(1 == 1); // 成立
   console.log(NaN == NaN); // false
   console.log(NaN == 10);
   
   var c = 070;
   console.log(c);
   
   var d = 019;
   console.log(d);
   
   var m = 0xa;
   console.log(m);
   
   
   var n = Infinity;
   var n = -1/0;
   console.log(n);
   console.log(typeof n);
   
   var mn = 2e20;  // 2 * 10的10次
   console.log(mn);
   ```

#### string

string: 字符串, 用成对的单双引号包裹的就是字符串 '' ""

​        length: 字符串.length 得到当前字符串的长度

​        charAt: 字符串.charAt(下标) 

​        字符串[下标]: 与charAt作用一致  ie8以上才能用

​        下标: 序号 从第一个字符开始, 从开始字符开始计算, 从左往右, 从0开始的数字

```javascript
var str = "abc";
console.log(str);
console.log(typeof str); // string

var str1 = '30';
console.log(str1);
console.log(typeof str1); // string

var str2 = "11月23日0—24时，31个省(自治区、直辖市)和新疆生产建设兵团报告新增确诊病例22例，其中境外输入病例20例(福建4例，广东4例，上海3例，四川3例，江苏2例，陕西2例，内蒙古1例，河南1例)，本土病例2例(天津1例，上海1例);无新增死亡病例;新增疑似病例1例，为境外输入病例(在上海)。当日新增治愈出院病例15例，解除医学观察的密切接触者189人，重症病例与前一日持平。境外输入现有确诊病例303例(其中重症病例2例)，现有疑似病例1例。累计确诊病例3804例，累计治愈出院病例3501例，无死亡病例。截至11月23日24时，据31个省(自治区、直辖市)和新疆生产建设兵团报告，现有确诊病例322例(其中重症病例6例)，累计治愈出院病例81508例，计死亡病例4634例，累计报告确诊病例86464例，现有疑似病例1例。累计追踪到密切接触者877545人，尚在医学观察的密切接触者11857人。31个省(自治区、直辖市)和新疆生产建设兵团报告新增无症状感染者8例(均为境外输入);当日转为确诊病例6例(境外输入5例);当日解除医学观察11例(均为境外输入);尚在医学观察无症状感染者348例(境外输入345例)。";
console.log(str2.length);
// 想找到第52个字  序号: 51   第一个字: 序号 0
console.log(str2.charAt(51));
console.log(str2.charAt(0));
console.log(str2[51]);
```

#### boolean

boolean: 布尔值 true--真 false--假

使用情况： 

1. 比较运算符的结果

2. 判断条件或者判断条件的结果

```javascript
var t = true;
console.log(t);
console.log(typeof t); // boolean

var f = false;
console.log(f);
console.log(typeof f); // boolean

console.log(1 == 1); // true
console.log(1 == 2); // false
```

#### null

null: 真正的空 空对象 只有自身一个值

​        给数据占位的时候, 现在没数据，但是未来会有数据的时候

​        typeof检验以后返回结果： object

```javascript
var n = null;
console.log(null);
console.log(typeof null); // object
```

#### undefined

undefined: 当只声明变量，但是不赋值 只有自身一个值

​        是值得空缺

```javascript
var a;
console.log(a);
console.log(typeof a); // undefined
```

**注意： js中规定, null和undefined是相等的(==)**

```javascript
console.log(null == undefined); // true
```

### 复杂数据类型

#### object

1. object: 对象, 一切皆对象

2. 创建对象: var 变量名 = {};

3. 以json格式的方式: {'属性名': 属性值, '属性名1': 属性值1,....}

4. 取值: 对象名.属性名  对象名['属性名'] 对象名[变量]

```javascript
var box = document.getElementById('box');
console.log(box);
console.log(typeof box);
console.log(typeof document);
console.log(typeof window);

var obj = {
    'name': '彭于晏',
    'age': 33,
    'height': 185
};
console.log(obj);
console.log(typeof obj);

console.log(obj.name);
console.log(obj['name']);

var nn = 'age';
console.log(obj[nn]);
console.log(obj.nn); // undefined
```

#### array

1. 用来存储不定数量不定类型的数据的容器

2. 声明: var 变量名 = [值, 值1, ... , 值n];

​      索引: 下标 从0开始的数字

​      元素: 值  

3. 获取指定下标的元素: 数组[下标]

```javascript
var arr = [];
console.log(arr);

var arr1 = [20, NaN, 'abc', null, undefined, true, false, obj, box, window];
console.log(arr1);

console.log(arr1[4]);
console.log(arr1[7]);
```

#### function

function: 函数 保存一段代码在有需要的时候调用

1. 声明: function 函数名(){ // 代码块 }

2. 调用: 函数名();

​      注意: 只声明, 函数没有任何效果

```javascript
function fun1(){
    console.log(1);
}
fun1();
fun1();
fun1();
fun1();
fun1();
fun1();
fun1();
```

### 数据存储位置

基本数据类型存储在栈中，数据比较单一, 数据的容量比较小

复杂数据类型存储在堆中, 数据种类比较多样化，数据的容量相对大

```javascript
/* 
    typeof: 
        返回自身： number  string  boolean undefined  function
        返回object: null object array

        基本数据类型存储在栈中，数据比较单一, 数据的容量比较小
        复杂数据类型存储在堆中, 数据种类比较多样化，数据的容量相对大
*/
console.log(typeof null);
console.log(typeof []);
function a(){
   console.log(1);
}
console.log(typeof a);
```

### 强制转换

#### Number

​        Number(要转换的数据)

​        空字符、空格字符、纯数字字符串、boolean、null

​        转换失败的时候返回NaN

```javascript
console.log(Number('')); // 0
console.log(Number('  ')); // 0
console.log(Number('a')); // NaN
console.log(Number('123')); // 123
console.log(Number('20px')); // NaN

console.log(Number(true)); // 1
console.log(Number(false)); // 0

console.log(Number(null)); // 0
console.log(Number(undefined)); // NaN
```

#### parseInt

​        进制数: 非必传

​        parseInt(要转换的数据, 进制数);

​        从左往右转换每一个字符, 遇到不能转换的就会停止, 如果第一个字母就不能转, 返回NaN

​        返回整型

```javascript
console.log(parseInt('33.3px'));
console.log(parseInt(''));
console.log(parseInt('070', 8));
console.log(parseInt(true));
```

#### parseFloat

​        parseFloat(要转换的数据);

​        从左往右转换每一个字符, 遇到不能转换的就会停止, 如果第一个字母就不能转, 返回NaN

​        返回整型、浮点型

```javascript
console.log(parseFloat('33.3px'));
console.log(parseFloat('33.3.333px'));
```

#### isNaN

判断一个数据 是不是 不是 一个数字

isNaN(要转换的数据)

​        会自动调用Number方法进行转换

​          转换成功（数字）, 返回false

​          转换失败(NaN), 返回true

```javascript
console.log(isNaN('123')); // false
console.log(isNaN('123a')); // true
console.log(isNaN('true')); // 'true'---字符串  Number-NaN  true
console.log(isNaN(true)); // false  
console.log(isNaN(undefined)); // true
```

#### toString

​        数据.toString(进制);

​        进制: 非必传 只对数字有效果

```javascript
var num = 10;
console.log(num.toString());
console.log(typeof num.toString());

var num1 = 70;
console.log(num1.toString(2));

var num2 = NaN;
console.log(num2.toString());
console.log(typeof num2.toString()); // string

var t = true;
console.log(t.toString()); // true

// . 相当于语文 的   t的toString   n的toString
// var n = null;
// console.log(n.toString()); // 报错

var u = undefined;
// console.log(u.toString()); // 报错

var obj = {};
console.log(obj.toString()); // [object Object]   所有对象都会转成这个结果

var arr = [1,2,4];
console.log(arr.toString()); // "1,2,4"
```

#### String

​        强制转换

​        String(要转的数据)

```javascript
console.log(String(null));
console.log(String(undefined));
console.log(String({}));
console.log(String([1, 3,2,3]));
```

#### Boolean

boolean: true-真 false-假

语法： Boolean(要转换的数据); true/false

js中的真真假假：

​        假: 0 NaN 空字符 false null undefined

​        真: 除了假的就是真的

```javascript
console.log(Number(true)); // 1
console.log(Boolean(1)); // true
console.log(Boolean(-1)); // true
console.log(Boolean(0)); // false
console.log(Boolean(NaN)); // false

console.log(Boolean('')); // false
console.log(Boolean(' ')); // true

console.log(Boolean(null)); // false
console.log(Boolean(undefined)); // false

console.log({});
console.log(Boolean({}));
```

### 运算符

1. 算术运算符: + - * / % ++ --

2. 赋值运算符: = += -= *= /= %=

3. 比较运算符: > >= < <= ==(相等) ===(全等) !=(不等) !==(不全等)

4. 逻辑运算符: &&(与) ||(或) !(非，取反)

5. 三目运算符: 条件 ? 条件成立的时候执行的代码 : 条件不成立的时候执行的代码

```javascript
//  算术
console.log(10 + 20);  // 30
console.log(10 % 3);  //  1
console.log(10 % 5);  //  0
// ++ 自加, 在自身的基础上+1, 可以写在变量前 也可以在变量后
var a = 30;
a++;
console.log(a); // 31
++a;
console.log(a); // 32

// ++和其他代码一起在一行的时候, ++在前, 先自加在执行其他代码; ++在后, 先执行其他代码，在自加
var b = 10;
console.log(++b); // ++b;  console.log(b);  11
console.log(b); // 11

var c = 10;
console.log(c++); // console.log(c);  10     c++;
console.log(c); // 11

// --和其他代码一起在一行的时候, --在前, 先自减在执行其他代码; --在后, 先执行其他代码，在自减
var d = 33;
console.log(--d); // --d;  console.log(d);  32

var e = 22;
console.log(e--); // console.log(e);  22   e--;
console.log(e); // 21


// 把一个值给到一个变量上
var  b = 30;
console.log(b);

// 每一次都加10  都是基于当前值得基础上改变
var s = 10;
s += 10; // s = s + 10
console.log(s);

// %=
var mn = 100;
mn %= 33; // mn = mn % 33;
console.log(mn); // 1


// 比较运算符: > >= < <= ==(相等) ===(全等) !=(不等) !==(不全等)
// 比较运算符运行结果只有: true  false
console.log(1 > 2); // false
console.log(1 < 2); // true
console.log(2 >= 2); // true

// ==相等: 只比较数值 
// ===全等: 既比较数值，也比较数据类型
console.log(1 == 1); // true
console.log('1' == 1); // true
console.log('1' === 1); // 数值都是1  字符串 数值  不相等  false

// != : 只比较数值
// !==: 既比较数值 也要比较数据类型  
console.log('1' != 1); // false
console.log('1' !== 1); // 数值相等  数据类型不相等  true

console.log(3>2>1);

// 逻辑运算符: &&(与) ||(或) !(非 取反)
// &&: 两边各自有一个条件, 两边条件都为true 则返回true   如果有一个false, 返回false
console.log(1 > 2 && 2 < 3); // false && true   false
// 3 > 2   true > 1
console.log(3>2>1);

// ||: 两边各自有一个条件, 两边条件都为false 则返回false   如果有一个true, 返回true
console.log(1 > 2 || 2 < 3); // false || true  true

// !: 结果都会布尔值
console.log(!true); // 不是true   false
console.log(!''); //   !false    true

// 三目运算符: 条件 ? 条件成立的时候执行的代码 : 条件不成立的时候执行的代码
// 简单的判断
// 注意: 三目运算符中不允许出现分号
// 如果1>2  弹出1  否则弹出2
1 > 2 ? alert(1) : alert(2);
// 1 > 2 ? alert(1); : alert(2);  报错

```

### 隐式转换

隐式转换： 

​        发生在算术运算符中的 + - * / % ++ --

规则:

1. 数值之间的计算正常计算.

2. 有字符串的加法, 转成字符串之后做拼接

3. 没有字符串的加法以及其他运算中，都尽可能转成数值之后在计算(Number)

4. 如果有数组或对象, 先调用自身的toString方法，转成字符串之后，在参照上述规则进行计算

```javascript
console.log(10 + 20); // 30
console.log(10 - 20); // -10
console.log(0 * 1); // 0

console.log('' + 123); // '123'
console.log('a' + NaN); // aNaN 
console.log('1' + true); // 1true
console.log('1' + null); // 1null
console.log('1' + undefined); // 1undefined


console.log('a' - '1'); // NaN - 1   NaN
console.log(true * 10); // 1 * 10   10
console.log(null / 30); // 0 / 30  0
console.log(true + false); // 1 + 0   1

console.log(true + {}); // true + '[object Object]'   true[object Object]
console.log(true - {}); // true - '[object Object]'   1 - NaN    NaN
console.log(false + []); // false + ''      false
console.log(false - []); // false - ''   0 - 0  0
console.log(null * [2]); //  null * '2'  0 * 2   0
console.log(null * [2,3]); // null * '2,3'   0 * NaN  NaN
```

# 流程控制语句

将代码按照规定的流程来进行执行的语句

## 分类

1. 顺序语句： 从上到下执行的顺序

2. 条件/分支语句: if if else switch

3. 循环语句: 让代码执行固定的次数的语句

​          for while do while

4. 其他语句: break continue

## 条件语句

### if

语法:

​        if(条件){

​          // 条件为真的时候, 执行的代码

​        }

简写: if(条件) 条件为真的时候, 执行的代码

​        只能控制条件后面的第一条代码

```javascript
var today = '星期三';
if(today == '星期五'){ 
    // '星期三' == '星期五'  false   
    // '星期五' == '星期五'  true
    alert('明天休息');
}

if(true){
    alert(1);
}

// 简写模式
var money = 10;
if(money == 100){
    alert('吃零食');
    alert('吃火锅');
}

if(money == 100) 
alert('吃零食');
alert('吃火锅');
```

### if else

语法:

​        if(条件){

​          // 条件为真的时候, 执行的代码

​        } else {

​          // 条件为假的时候执行的代码

​        }

```javascript
// 100  火锅零食  否则 面包
var money = 10;
if(money == 100){
    alert('吃火锅');
    alert('吃零食');
} else {
    alert('吃面包');
}
```

### if else嵌套

语法： 

​      if(条件){

​        // 条件为真的时候执行的代码

​      } else if(条件1){

​        // 条件1为真的时候执行的代码

​      } else {

​        // 以上条件均不满足的时候，执行的代码

​      }

```javascript
// 90  A  80  B  70  C 60 D  60下 E
var core = 58;
if (core >= 90) {
    console.log('A');
} else if (core >= 80) {
    console.log('B');
} else if (core >= 70) {
    console.log('C');
} else if (core >= 60) {
    console.log('D');
} else {
    console.log('E');

}
```

### switch

语法:

​        switch(条件/变量){

​          case 结果1:

​            符合结果1的时候执行的代码;

​            break;

​          case 结果2:

​            符合结果2的时候执行的代码;

​            break;

​          case 结果3:

​            符合结果4的时候执行的代码;

​            break;  

​          default:

​            以上结果都不符合的时候执行的代码;

​            break;

​        }

**switch: 更适用于条件和结果比较单一的时候**

**break: 防止穿透**

**如果不加break, 当switch匹配到一个符合的结果的时候，后面的结果都不匹配，直接执行后面所有的代码**

```javascript
var c = '-';
switch (c) {
    case '+':
        console.log(20 + 30);
        break;
    case '-':
        console.log(20 - 30);
        break;
    case '*':
        console.log(20 * 30);
        break;
    case '/':
        console.log(20 / 30);
        break;
    default: 
        alert('当前运算符错误');
        break;
}
```

## 循环语句

1. 通过id获取 document.getElementById('id')

2. 通过标签名获取: 

   ​        document/父元素.getElementsByTagName('标签名');

### 标签获取元素

document/父元素.getElementsByTagName('标签名');

1. 通过标签名获取到的是集合, 类数组, 有长度有下标

​      长度： length

​      下标： 从左到右从0开始的数字

2. 指定下标的元素: 集合[下标]

​      **注意: 哪怕只获取到一个元素，也是在集合中存放的**

```javascript
var lis = document.getElementsByTagName('li');
console.log(lis); // HTMLCollection(10)   HTML集合  元素的集合  [li, li, li, li, li, li, li, li, li, li]
console.log(lis.length);
console.log(lis[4]);

var uls = document.getElementsByTagName('ul');
console.log(uls[0]); // HTMLCollection  集合

// 如果父元素只有一个的时候  直接获取到指定下标的元素
var ul = document.getElementsByTagName('ul')[0];
console.log(ul);        

// 只想获取第一个ul中的li
var lis1 = uls[0].getElementsByTagName('li');
console.log(lis1);
```

### 类名获取元素

document/父元素.getElementsByClassName('类名');

1. 通过标签名获取到的是集合, 类数组, 有长度有下标

​      长度： length

​      下标： 从左到右从0开始的数字

2. 指定下标的元素: 集合[下标]

​      **注意: 哪怕只获取到一个元素，也是在集合中存放的**

```javascript
// 通过box的元素
var boxes = document.getElementsByClassName('box');
console.log(boxes);

// 第二个ul中的box
console.log(uls[1]);
var box1 = uls[1].getElementsByClassName('box');
console.log(box1); // [li.box]
```

### 各种获取元素方式的区别

1. id:

   直接获取到元素  直接去操作元素 只能通过document获取

   静态性(先获取，在添加元素，拿不到)

2. tagName/className:

   获取到的是集合 必须通过下标获取到元素之后才能操作 既可以是document也可是父元素

   动态性(先获取, 后添加元素, 也能拿到)

```javascript
// var eight = document.getElementById('eight');
// console.log(eight);

// var boxes = document.getElementsByClassName('box');
// console.log(boxes); // [li.box]

// eight.style.background = 'red';
// boxes[0].style.background = 'red';

var ul = document.getElementsByTagName('ul')[0];
console.log(ul);

var ten = document.getElementById('ten');
// 给ul中添加一个id为ten的li
ul.innerHTML = ul.innerHTML + '<li id="ten">这是第十个id</li>';
console.log(ten); // null


var box1 = document.getElementsByClassName('box1');
ul.innerHTML = ul.innerHTML + '<li class="box1">这是class</li>';
console.log(box1); // [li.box1]
```

## 循环

### for

#### 语法

for：让循环体执行指定的次数

for(表达式一; 表达式二; 表达式三){

​        循环体

}

for(初始化变量; 循环条件; 变量更新){

​        循环体

}

#### 说明

​      初始化变量: var 变量名 = 值;

​      循环条件: 符合那个条件，循环会执行

​      变量更新: ++ --

```javascript
for(var i = 1; i <= 100; i++){
    console.log(i);
}
```

#### 执行步骤

1. 初始化变量: var i = 1;

2. 循环条件: i <= 5;

3. 循环体: console.log(i);

4. 变量更新: i++;

​        2342342

```javascript
for(var i = 1; i <= 5; i++){
    console.log(i);
}

// 错误示范
// for(var i = 1; i >= 1; i++){
//     console.log(i);
// }
```

#### 注意

1. 执行时间: for循环在页面加载完成的一瞬间执行完成
2. 注意: 必须要有循环结束的可用条件 没有结束就会形成死循环

#### 断点调试

浏览器右键--检查---source--文件--双击--具体的行前面点一下--刷新---小点点蓝---刷新

### for的变异

1. 语法

   初始化变量;

   for(;循环条件;){

   ​        循环体;

   }

   **注意： 两个分号不能省略**

   ```javascript
   // 1-5    起始值1
   var i = 1;
   for(;i<=5;){
       console.log(i);
       i++;
   }
   ```

### for in

for循环可以遍历数字、集合 但是不能遍历对象

遍历对象用for in

语法:

​        for(var 变量名 in 数据){

​             循环体

​        }

属性名：变量名

属性值: 数据[变量名]

```javascript
var obj = {
    'name': '彭于晏',
    'height': 180,
    'age': 33
};
for(var k in obj){
    console.log(k, obj[k]);
}
```

### while

while语法：

初始化变量;

while(循环条件){

​          循环体;

​          变量更新;

}

```javascript
// 1-5  while
// var i = 1;
// while(i<=5){
//     console.log(i);
//     i++;
// }
```

### dowhile

初始化变量;

do{

​          循环体;

​          变量更新;

}while(循环条件);

```javascript
// do while
// var j = 1;
// do{
//     console.log(j);
//     j++;
// }while(j<=5);
```

### 区别

第一次循环条件就不符合: while一次都不会执行， dowhile会执行一次

```javascript
var i = 6;
while(i<=5){
    console.log(i);
    i++;
}

var j = 6;
do{
    console.log(j);
    j++;
}while(j<=5);
```

### break与continue

​      break: 防止穿透; 终止循环;

​      continue: 中止本轮循环，下次循环继续

```javascript
for(var i = 0; i < 5; i++){
    // 如果i等于2, 终止/中止循环
    if(i == 2){
        // break; // 后面代码和循环都不走   0 1
        continue; // 中止本轮循环  本次循环后面的代码不走  0 1 3 4
    }
    console.log(i);
}
```

# this

## this的概念

​      this: 这个 指代词  谁用就代表谁

​      this存在于函数里面或者函数外面 

​      this存在于页面的任何位置 

## 页面的理解

​      html-->document 虽然是整个页面的父元素

​      祖宗---> window 整个浏览器窗口对象

​      script标签下 范围 全局作用域

​      声明的变量和函数 属于window的一个属性和方法

​      变量---属性

​      函数---方法

​      如果变量和属性直接挂在window上的话 会省略window

```javascript
var a = 20;
console.log(window);
console.log(window.a);
console.log(a);
function am(){
    console.log(1);
}
console.log(window.am);
window.am();
```

## this的指向

1. 全局this: window

   ```javascript
   console.log(this); // window
   ```

2. 普通函数this: window

   ```javascript
   function am(){
       console.log(1);
       console.log(this, '1----'); // window  谁用就是谁
   }
   
   console.log(window.am);
   window.am();
   ```

3. 点击事件中 this指向谁 ---> 事件的触发源 点谁就是谁

   ```javascript
   var lis = document.getElementsByTagName('li');
   console.log(lis); // [li, li, li, li, li]
   console.log(lis[0]);
   // 添加点击事件
   lis[0].onclick = function(){
       // alert(1);
       console.log(this);
   }
   ```

4. 对象的方法: this指向对象本身

   ```javascript
   // 对象的方法中
   var obj = {
       'name': '彭于晏',
       'tip': function(){
           console.log(this);
       }
   };
   console.log(obj);
   console.log(obj.tip); // 对象.属性名
   obj.tip(); // 对象的方法: this指向对象本身
   ```

## this的应用

1. 当在事件中得不到正确下标的时候, 得不到元素的时候  this

   ```javascript
   /* 
       点击每一个li, 让这个li的背景色变红
   */
   // 1. 获取元素
   var lis = document.getElementsByTagName('li');
   console.log(lis);
   // 每一个
   for(var i = 0; i < lis.length; i++){
       console.log(lis[i]); // 获取li 
       // 添加事件
       lis[i].onclick = function(){
           // 让这个li的背景色变红
           console.log(i); // 9  for循环在页面加载的一瞬间就执行完成了, i就变成了了结束条件 9 
           console.log(lis[i]); // undefined
           // 当在事件中得不到正确下标的时候,  得不到元素的时候   this
           console.log(this);
           this.style.background = 'red';
       }
   }
   ```

2. 利用this作为父元素获取子元素

   ```javascript
   /* 
       滑入每一个li, 将li中的p标签显示出来
   */
   // 1. 获取元素
   var lis = document.getElementsByTagName('li');
   console.log(lis);
   // 每一个
   for(var i = 0; i < lis.length; i++){
       // 添加划上事件
       lis[i].onmouseenter = function(){
           console.log(lis[i]); // 对应的li
           console.log(this);
           // 通过父元素来获取子元素
           var p = this.getElementsByTagName('p')[0];
           console.log(p);
           p.style.display = 'block';
       }
   
       // 滑下事件
       lis[i].onmouseleave = function(){
           console.log(lis[i]); // 对应的li
           console.log(this);
           // 通过父元素来获取子元素
           var p = this.getElementsByTagName('p')[0];
           console.log(p);
           p.style.display = 'none';
       }
   }
   ```

## 自定义属性

1. 属性: 写在起始标签上的除了起始标签名以外的都是属性

​    id src class style 固有属性

​    自己规定的名字和属性值 自定义属性

2. 自定义属性操作与固有属性操作一致： 获取： 元素.属性名 元素['属性名'] 设置: 元素.属性名 = 值

3. **点和[]中方式不能直接获取写在标签上的自定义属性**

4. **js设置的自定义属性，在标签上看不到，但是可以正常的获取和设置**

```javascript
var div = document.getElementsByTagName('div')[0];
console.log(div);
console.log(div.tx); // undefined
console.log(div['tx']); // undefined

div.ex = 1;
console.log(div.ex); // 1
```

### 自定义属性的应用

1. 在for循环中给每一个元素都加一个开关，利用自定义属性添加
2. 在点击事件中判断 自己的开关  自定义属性来做判断

```javascript
/* 
    点击每一个div, 如果当前高是100px 变成300  如果高是300px  变成100px
*/
// 1. 获取元素
var divs = document.getElementsByTagName('div');
console.log(divs);
// 不知道当前是什么状态, 假设状态
var tag = 1;  // 1--- 100   2----300
// 用一个开关控制多个div    
// 每一个
for(var i = 0; i < divs.length; i++){
    console.log(divs[i]); // 获取每一个div

    // 给每一个元素都加一个开关  自定义属性
    divs[i].tag1 = 1; // 1---100   2---300

    // 加事件
    divs[i].onclick = function(){
        // 输出tag 
        console.log(this, this.tag1);
        // // 判断 自己的开关  自定义属性来做判断
        if(this.tag1 == 1){
            this.style.height = '300px';
            this.tag1 = 2;
        } else {
            this.style.height = '100px';
            this.tag1 = 1;
        }
    }
}
```

## 自定义索引

有几个按钮，就有几条数据 关系： 按钮和数据 下标 是一一对应的

自定义索引:

​        将自定义属性的值 存储成下标 自定义索引

​    1. for循环中 元素.属性名 = i;

    2. 获取自定义索引: 事件中: this.index就可以获取到自定义索引

### 例子一

```javascript
var arr = [
    "HTML", "CSS", "javascript"
];
var btns = document.getElementsByTagName('button');
console.log(btns); // [button, button, button]
// 给每一个按钮添加点击事件
for(var i = 0; i < btns.length; i++){
    console.log(i); // for循环的时候, i可以正确的值
    // 将自定义属性的值 存储成下标  自定义索引
    btns[i].index = i;


    btns[i].onclick = function(){
        // 获取数组中对应的数据 只能通过下标来获取
        // console.log(i);
        // 获取自定义索引  自定义属性
        console.log(this.index);
        // 从数组中取值
        console.log(arr[this.index]);
        alert(arr[this.index]);
    }
}
```

### 例子二

**无法知道上一次操作的情况下, 利用排他思维实现效果**  

**先清空所有的样式  再给指定的这一个按钮加上样式**

```javascript
/* 
    点击每一个按钮, 切换body的背景颜色， 从数组中去颜色  这一个按钮的背景色变成黑色  其他不变
    按钮和数据之间的关系: 下标是一一对应的
*/
var arr = ['yellow', 'red', 'pink'];
// 1. 获取元素
var btns = document.getElementsByTagName('button');
console.log(btns); // [button, button, button]
// 点击每一个按钮
for(var i = 0; i < btns.length; i++){
    // 拿到每一个按钮
    console.log(btns[i]);
    // 存储自定义索引
    btns[i].index = i;
    // 点击事件
    btns[i].onclick = function(){
        // 获取对应的数组中的数据  数据通过下标获取  
        // 获取按钮的下标
        // console.log(i); // 得不到正确  用自定义索引
        // 获取自定义索引
        console.log(this.index);
        // 获取对应的下标的数据
        console.log(arr[this.index]);
        document.body.style.background = arr[this.index];

        // 无法知道上一次操作的情况下  
        // 先清空所有的样式  再给指定的这一个按钮加上样式
        
        // 排他
        // 1. 清空所有样式
        for(var j = 0; j < btns.length; j++){
            btns[j].style.background = '';
        }

        // 2. 这一个按钮的背景色变成黑色
        this.style.background = 'green';
    }
}
```

### 例子三

```javascript
/*  选项卡效果
    1. 布局
    2. js
*/
/* 
    点击每一个按钮, 将内容切换成对应的, 按钮背景色改变 字体也改变
*/
// 1. 获取元素  按钮  内容
// 有父元素的情况下用父元素来获取
var box = document.getElementById('box');
console.log(box);
var btns = box.getElementsByTagName('button');
var divs = box.getElementsByTagName('div');
console.log(btns, divs);
// 2. 给每一个按钮添加点击事件
for(var i = 0; i < btns.length; i++){
    // 存索引
    btns[i].index = i;
    // 加事件
    btns[i].onclick = function(){
        // 切换到对应的内容 通过下标设置显示
        // 内容的下标  和 按钮下标  一一对应
        // 按钮的下标 用自定义索引
        // 取索引
        console.log(this.index);

        // 只显示一个 不知道之前是什么操作  排他

        // 1. 清空所有的类名
        for(var j = 0; j < divs.length; j++){
            divs[j].className = '';
            btns[j].className = '';
        }

        // 展示对应的内容盒子
        divs[this.index].className = 'active';
        // 按钮也要显示对应的样式
        this.className = 'active';
    }
}
```

# 函数

## 函数概念

函数: 是被事件驱动或当他被调用的时候执行的代码块

​        用来保存一段代码在有需要的时候被调用

## 函数声明方式

### 函数声明

1. 声明函数 function 函数名(){ // 代码块 }

2. 调用函数: 函数名();

```javascript
function s(){
    console.log(1);
}
s();
```

### 表达式声明

1. 声明函数 var 变量名 = function(){ // 代码块}

2. 调用函数: 变量名();

```javascript
var su = function(){
    console.log(2);
}
su();
```

## 使用场景

1. 有目的性的函数

   ```javascript
   function sum(){
       // 存和
       var s = 0;
       // 1-100中的每一个数字的和
       for(var i = 1; i <= 100; i++){
           s += i;
       }
       console.log(s); // 5050
   }
   sum();
   ```

2. 事件处理函数 

   ```javascript
   document.onclick = function(){
       alert(1);
   }
   ```

3. 对象的方法

   ```javascript
   var obj = {
       'name': '彭于晏',
       'tip': function(){
           console.log('挣100w');
       }
   };
   obj.tip();
   ```

4. 封装复用

   目的: 让页面代码更少 将同样的重复性的代码 放在一个函数中在调用

   函数封装: 

   + 新建一个空函数

   + 分析重复代码，将重复代码粘贴到函数中

   + 源代码的位置上调用函数 看是否正常执行

   ```javascript
   // 1. 获取元素 右箭头  img  div
   var right = document.getElementById('right');
   var img = document.getElementById('img');
   var sz = document.getElementById('sz');
   var dm = document.getElementById('dm');
   console.log(right, img, sz, dm);
   // 图片名字没有规律的时候
   var arr = ['./img/11.jpg', './img/22.jpg', './img/33.jpg', './img/44.jpg'];
   // 不知道是第几张图的时候  假设存一下
   var n = 0; // 数组下标从0开始
   // 2. 加事件  点击右箭头
   right.onclick = function () {
       //  切换图片  1 ---> 2  下标  0 --- 1
   
       move();
   
   }
   
   /* 
       左箭头： 点击左键头, 切换图片  4--3--2--1---4
   */
   var left = document.getElementById('left');
   console.log(left);
   // 2. 添加事件
   left.onclick = function () {
       // n  4--3---2
       // n--; // 减一   --- 》 减2
       n -= 2;
       console.log(n);
       move(); // 加一 
   }
   
   /*  目的: 让页面代码更少 将同样的重复性的代码  放在一个函数中在调用
       函数封装: 
           1. 新建一个空函数
           2. 分析重复代码，将重复代码粘贴到函数中
           3. 源代码的位置上调用函数  看是否正常执行
   */
   function move() {
       n++;
       console.log(n);
       // 如果n是-1的时候回到3
       if (n == -1) {
           n = 3;
       }
       // 当n变成4的时候回到第一张
       if (n == 4) {
           n = 0;
       }
       // 获取对应的图片地址
       console.log(arr[n]);
       // 渲染img的src
       img.src = arr[n];
       // 更新文本内容 元素.innerHTML = 值  计数从1开始  字符串的时候 加法会拼接
       sz.innerHTML = '' + (n + 1) + '/4';
       dm.innerHTML = '动漫' + (n + 1);
   }
   ```

## 函数的参数

什么时候用参数：

​	当函数中出现不确定的项的时候，就将它抽成参数

函数参数的分类:

1. 形参: 形式参数, 用来做占位的参数, 类似变量, 写在function后面的()

​        作用: 接收实参传递过来的数据

2. 实参: 实际的参数, 实际的数据, 传给形参的数据, 写在函数调用()

3. arguments: 实参的集合, 确定不了有多少个参数的时候

### 单个参数

```javascript
function sum(a){ // a---形参
    console.log(a); // 10
}
sum(10); // 10----实参


// 计算10 + 20   10 + 40  10 + 100  10 + 1000
function s(a){
    console.log(10 + a); // 不确定的项
}
s(20);
s(40);
s(100);
```

### 多个参数

多个形参去接受多个实参传递过来的数据, 用,隔开

```javascript
function s(a, b){
    console.log(b + a); // 不确定的项
}
s(20, 30);
s(40, 33);
s(100, 10);
s(87, 44);
```

### arguments

arguments: 实参的集合, 确定不了有多少个参数的时候

```javascript
function sum() {
    // 确定不了有多少个参数的时候，干脆一个都不写
    // 每个函数中都有一个实参的集合: arguments
    console.log(arguments);
    var s = 0;
    // 将集合中的每一个数据都加起来
    for(var i = 0; i < arguments.length; i++){
        console.log(arguments[i]);
        s += arguments[i];
    }
    console.log(s);
}
sum();
sum(33, 45, 67);
sum(1, 4, 5, 2, 78);
```

## 参数的类型

参数的数据类型: **可以是一切数据类型**

​      基础数据类型: number string boolean null undefined

​        **一般不用null\undefined作为实参**

​      复杂数据类型: object array function

```javascript
function typeN(a){
    console.log(a, typeof a);
}

var num = 20;
typeN(num); // number

var str = '1234';
typeN(str);

var bool = true;
typeN(bool);

var n = null;
typeN(n);

var un = undefined;
typeN(un);

var obj = {
    'name': '彭于晏'
};
typeN(obj);

var arr = [1,2,3,4,5];
typeN(arr);

function a(){
    console.log(1);
}
typeN(a);
```

## 函数的问题

1. 函数名重复 后面的函数就会覆盖前面的

2. 形参多于实参:从左往右依次赋值给每一个形参, 剩下的形参就会是undefined

   实参多于形参:从左往右依次赋值给每一个形参, 多余的实参不能通过形参获取

```javascript
/* 
    1. 函数名重复  后面的函数就会覆盖前面的
*/
function sum() {
    console.log(1);
}
function sum() {
    console.log(2);
}
sum(); // 2

/* 
    2. 形参多于实参:从左往右依次赋值给每一个形参, 剩下的形参就会是undefined
      实参多于形参:从左往右依次赋值给每一个形参, 多余的实参不能通过形参获取
*/
function s(a, b, c) {
    console.log(a, b, c);
}
s(10);
s(20, 30, 40, 50);
```

## document.write与innerHTML

都可以识别标签

document.write(内容):

​          只能操作body

​          window.onload中使用的时候 会覆盖页面原有的内容

​          不会覆盖自身添加的内容

innerHTML:

​          操作所有的闭合标签

​          会覆盖原标签中所有的内容

```javascript
window.onload = function () {
    /*  都可以识别标签
        document.write(内容):
            只能操作body
            window.onload中使用的时候  会覆盖页面原有的内容
            不会覆盖自身添加的内容


        innerHTML:
            操作所有的闭合标签
            会覆盖原标签中所有的内容

    */
    document.write(111);
    document.write(2222);


    document.body.innerHTML = '1234567';

    document.write('123<br>456');
    document.body.innerHTML = '<i>1234567</i>';

}
```

## 作用域

1. 概念

   作用：读 写

   域: 区域 范围

2. 作用域: 变量和函数可以被读写的范围  由函数来进行划分 叫做: 函数作用域

   + 全局作用域: script标签下的就是全局

     var声明的变量叫做全局变量

     function声明的函数叫做全局函数

     **全局变量和全局函数可以在整个作用域的任何位置被读取被写入**

   + 局部作用域: 函数{}中的区域就是局部作用域

     var声明的变量叫做局部变量

     function声明的函数叫做局部函数

     **局部变量和局部函数只作用于当前的局部作用域中, 但凡出了{} 就会被销毁**

```javascript
var a = 20;  // 全局变量
function sum(){ // 全局函数
    // 局部作用域
    console.log(a); // 全局的a
}
sum(); // 全局的sum


function s(){
    // 局部作用域
    var num = 30;
    console.log(num); // 局部变量的num

    function m(){
        console.log(1);
    }
    m();
}
s();

// console.log(num); // num is not defined  num未定义   报错
// m(); // 报错： m is not defined  m未定义
```

## 作用域链

作用域链: js中的一种查找方式, 决定了变量和函数向上查找的方式

​      先在自身作用域范围中查找变量和函数，如果找到就直接返回，如果找不到往上一级作用域查找，如果一直找到全局作用域都没有，就会报错

```javascript
var a = 20;
function sum(){
    console.log(a); // 20
    // console.log(c);
}
sum();


var b = 30;
function s(){
    var b = 21;
    console.log(b); // 21
}
s();
```

## 变量提升/预解析

js的解析器在执行js代码的时候，会按照一定的顺序来执行

1. 找 var function, 将var声明的变量，声明提前, 但是不赋值; 将function声明的函数整个存储在内存中;

   2. 逐行解析(从上到下)

在第一步中，找var的过程中，只声明，遇到 = += -= *= 赋值运算符的时候 才会赋值

​      function只存函数

```javascript
var a = 20;
sum();
function sum() {
    console.log(1);
}
/*
    var a;
    function sum(){
        console.log(1);
    }

    a = 20;
    sum();
*/
```

### 例子一

```javascript
// console.log(a);
// var a = 3;
// console.log(typeof a);
// function a() {
//     alert('1');
// }
// a();
// var a = 4;
// console.log(a);
// a();
// function a() {
//     alert(5);
// };
// a();
// console.log(a);

// ---------解析步骤--------------
// 变量重复命名   后面的覆盖前面的  预解析
var a;
var a;
function a() {
    alert('1');
}
function a() {
    alert(5);
};
console.log(a); // 47行的函数a
a = 3;
console.log(typeof a); // number
// a(); // 报错  
a = 4;
console.log(a); // 4
// a(); // 报错
// a(); // 报错 
console.log(a); // 4
```

### 例子二

```javascript
// console.log(a);
// console.log(d);
// var a = 3;

// var d = function a() {
//     alert('1');
// };
// console.log(a);
// console.log(d);
// a();

// ------------解析过程----------- 
var a;
var d;
console.log(a); // 36的a
console.log(d); // undefined
a = 3;
d = function a(){
    alert('1');
}
console.log(a); // 3
console.log(d); //  函数44
a(); // a是3  不能被调用
```

### 例子三

```javascript
function fn(a) { // 形参  a === var a
    console.log(a);
    var a = 3;
    console.log(a);

    // ----解析过程-----
    // var a; // 形参声明的时候  var a就执行了
    // console.log(a); // undefined
    // a = 3;
    // console.log(a); // 3
}

fn();
// ------解析过程------
/* 
    函数调用时候, 执行函数内部的代码，代码执行的作用域是局部作用域
    执行环境改变的时候，会重新执行预解析并且执行代码
*/
```

### 例子四

```javascript
function fn(a) { // 形参  a === var a
    console.log(a);
    var a = 3;
    console.log(a);

    // ----解析过程-----
    // var a; // 形参声明的时候  var a就执行了
    // a = 2; // 实参赋值给形参
    // console.log(a); // 2
    // a = 3;
    // console.log(a); // 3
}

fn(2);
// ------解析过程------
/* 
    函数调用时候, 执行函数内部的代码，代码执行的作用域是局部作用域
    执行环境改变的时候，会重新执行预解析并且执行代码

    实参的赋值在声明完形参之后  var
*/
```

### 例子五

```javascript
var a = 4;
function fn(b) {
    console.log(a);
    var a = 3;
    console.log(a);
};

fn();
console.log(a);

// -----解析过程-----
/* 
    函数调用时候, 执行函数内部的代码，代码执行的作用域是局部作用域
    执行环境改变的时候，会重新执行预解析并且执行代码

    实参的赋值在声明完形参之后  var
*/
// var a;
// function fn(b) {
//     console.log(a);
//     var a = 3;
//     console.log(a);
// };
// a = 4;
// fn();
// /* 
//     var b;
//     var a;  局部变量
//     console.log(a);  undefined
//     a = 3;
//     console.log(a); 3
// */
// console.log(a); // 全局变量  4
```

### 例子六

```javascript
var a = 4;
function fn(b) {
    console.log(a);
    a = 3;
    console.log(a);
};

fn();
console.log(a);

// -----解析过程-----
/* 
    函数调用时候, 执行函数内部的代码，代码执行的作用域是局部作用域
    执行环境改变的时候，会重新执行预解析并且执行代码

    实参的赋值在声明完形参之后  var
*/
// var a;
// function fn(b) {
//     console.log(a);
//     a = 3;
//     console.log(a);
// };
// a = 4;
// fn();
// /* 
//     var b;
//     console.log(a); 全局变量  4
//     a = 3; 
//     console.log(a); 全局变量  3
// */
// console.log(a); // 全局变量  3
```

### 例子七

```javascript
var a = 4;
function fn(a) {
    console.log(a);
    a = 5;

};

fn(a);
console.log(a);

// ----解析过程-----
// var a;
// function fn(a) {
//     console.log(a);
//     a = 5;
// };
// a = 4;
// fn(a); // 全局变量a  a=4
// /*
//     fn(4);

//     var a;  函数内有var a  a就是局部变量
//     a = 4;  实参赋值给形参
//     console.log(a); 4
//     a = 5;


// */
// console.log(a); // 全局a  4
```

### 例子八

```javascript
function fn(a) {
    var s = a;
    s.name = '优就业';
};

var json = {
    name: '小u'
};

fn(json);
console.log(json);

// ----- 解析过程----
// var json;
// function fn(a) {
//     var s = a;
//     s.name = '优就业';
// };

// json = {
//     'name': '小u'
// };
// fn(json); // 小u
// /* 
//     var a;
//     var s;
//     a = {小u};
//     s = a; {小u}
//     s.name = '优就业'
// */
// console.log(json); // 有就业
```

## 函数返回值

### 函数的返回值:

​        每个函数被调用以后, 都会有一个返回结果, 这个返回结果就是函数返回值

​        **var 变量 = 函数名();**

​        在未设置返回值的时候，默认返回undefined

设置返回值：

​          **return 值;**

**使用场景**：

​        函数里面的值, 要在函数外面用到的时候, 需要将这个值设置成返回值

```javascript
function sum(){
    alert(1);
}
var u = sum();
console.log(u); // undefined

function s(){
    return 30;
}
var m = s();
console.log(m); // 30
```

```javascript
var m = sum(1000);
console.log(m);

function sum(num) {
    // 有一个变量存和
    var s1 = 0;
    // 判断每一个数字是不是奇数
    for (var i = 1; i <= num; i++) {
        // 判断是不是奇数  2n + 1  对2取余  如果余数是1  当前就是奇数
        if (i % 2 == 1) {
            // console.log(i);
            s1 += i;
        }
    }
    console.log(s1);
    return s1;
}
// console.log(s1); // 报错
```

### return

**return作用：**

​        \1. 设置返回值

​        \2. 结束代码  在函数中，只要遇到了return 后面所有的代码都不在执行 直接结束

**return返回多个值:**

​        \1. return和,设置多个返回值的时候, 将最后一个数据返回回来

​        \2. 用object、array设置返回，array中多个数据, 无法明确的值具体的代表谁 

​          建议object, 可以明确知道每个数据代表什么含义

```javascript
var m = sum(1000);
console.log(m); // 数组  对象
function sum(num) {
    // 有一个变量存和
    var s1 = 0;
    // 判断每一个数字是不是奇数
    for (var i = 1; i <= num; i++) {
        // 判断是不是奇数  2n + 1  对2取余  如果余数是1  当前就是奇数
        if (i % 2 == 1) {
            // console.log(i);
            s1 += i;
        }
    }
    // return s1,i;  // 函数遇到return  结束之星
    // console.log(s1); // 不执行

    // return [s1, num, i];

    return {
        'sum': s1,
        'num': num,
        'i': i
    }
}
// console.log(s1); // 报错
```

## 获取非行间样式

ie678: 元素.currentStyle.属性名

标准(chrome/ff/ie9): getComputedStyle(元素).属性名 

```javascript
// chrome
// console.log(getComputedStyle(div).width); // 200px  ie8及以下: 属性“getComputedStyle”的值为 null、未定义或不是 Function 对象
// 全局函数 window
console.log(window.getComputedStyle); // ie8: undefined
console.log(div.currentStyle); // 标准： undefined
// console.log(div.currentStyle.width); // 200px  chrome: Cannot read property 'width' of undefined

// 加判断  判断当前是什么浏览器
if(div.currentStyle){ // 真的
    // ie
    console.log(div.currentStyle.width);
    console.log(div.currentStyle.color);
} else {
    // 标准
    console.log(getComputedStyle(div).width);
    console.log(getComputedStyle(div).color);
}
```

## 封装步骤

1. 创建一个空函数

2. 重复代码/目标代码放入

3. 原位置调用

4. 抽取参数 从上到下一行行抽取可变的数据为参数

5. 传参调用 把谁抽出来 就把谁传进去

6. 设置返回值 将函数内要在函数外用的数据返回出去

7. 接收返回值

## 封装非行间样式

```javascript
var w = getStyle(div, 'width');
console.log(w);

var c = getStyle(div, 'color');
console.log(c);


var s = getStyle(span, 'fontSize');
console.log(s);
/* 
    1. 创建一个空函数
    2. 重复代码/目标代码放入
    3. 原位置调用
    4. 抽取参数  从上到下一行行抽取可变的数据为参数
    5. 传参调用  把谁抽出来 就把谁传进去
    6. 设置返回值  将函数内要在函数外用的数据返回出去
    7. 接收返回值
*/
function getStyle(ele, attr) {
    // ele: 元素
    // attr: 属性

    // 加判断  判断当前是什么浏览器
    if (ele.currentStyle) { // 真的
        // ie
        return ele.currentStyle[attr];
    } else {
        // 标准
        return getComputedStyle(ele)[attr];
    }
}
```

## 使用

```html
<!-- 1. 引入公用js文件 -->
<script src="./ujiuye.js"></script>
<script>
    // 获取元素
    var div = document.getElementsByTagName('div')[0];

    var bg = getStyle(div, 'backgroundColor');
    console.log(bg);

    console.log(getStyle(div, 'backgroundColor'));
</script>
```

# 定时器

定时器: 让一段代码延迟一段时间或者每隔多长时间执行一次

## 分类

1. 延迟定时器: setTimeout(函数, 时间) 时间单位: ms

2. 间隔定时器: setInterval(函数, 时间) 单位: ms

## 延迟定时器

延迟定时器: setTimeout(函数, 时间) 时间单位: ms

​          setTimeout(函数名, 时间) 时间单位: ms

只会执行一次

使用场景： 一次性广告 关不掉的广告

遇到： 等待多长时间执行什么

```javascript
setTimeout(function(){
    console.log(1);
}, 3000);
```

```javascript
// 1. 获取元素
var img = document.getElementsByTagName('img')[0];
// 2. 等待页面3秒后  延迟定时器
setTimeout(s, 3000); // 函数名后面不加()
function s(){
    img.style.display = 'inline-block';
}
```

## 间隔定时器

间隔定时器： setInterval(函数, 时间) 时间单位： ms

​        每隔一段时间就让函数调用一次 

每隔 不间断 

应用: 轮播图 计数器 定时器 倒计时

```javascript
// 1---10  每隔1s
var n = 1;
setInterval(function(){
    console.log(n);
    n++;
}, 1000);
```

## 清除定时器

定时器一旦开启不会自动清除 需要手动清除

​    setTimeout--- >clearTimeout(timeId)

​    setInterval--- >clearInterval(timeId)

定时器开启后(定时器开始后)，会返回一个标识，这个标识是整个页面中唯一的

​    var 变量 = setInterval/setTimeout();

变量就是唯一标识

```javascript
var n = 10;
var timer = setInterval(function () {
    console.log(n);
    n--;
    // 倒计时不存在你负数
    if (n < 0) {
        n = 0;
        // 清除定时器
        clearInterval(timer);
    }
    // 写到页面中
    document.body.innerHTML = n;
}, 1000);
console.log(timer, '标识');

var t = setTimeout(s, 3000); // 函数名后面不加()
function s(){
    console.log(10);
}
console.log(t, '标识1');
```

## 注意

1. clear与return不一样，clear只清除定时器，不会阻断后续代码， 后续代码继续执行

2. 每个定时器都会有唯一标识, 一次可以开多个定时器

# Math

```javascript
console.log(Math); // 对象
console.log(Math.PI); // π
console.log(Math.floor(3.9999999)); // 向下取整  舍掉小数  3
console.log(Math.ceil(3.00000000001)); // 向上取整  只要有js识别的小数 4
// console.log(Math.ceil(3.000000000000000000000000001));
// console.log(3.000000000000000000000000001);
console.log(Math.abs(-10)); // 绝对值
console.log(Math.round(4.455555)); // 四舍五入
console.log(Math.round(4.555555)); // 四舍五入
console.log(Math.pow(2, 10)); // 幂次方  1024
console.log(Math.pow(3, 2)); // 幂次方  9
console.log(Math.sqrt(9)); // 开根号    3
console.log(Math.sqrt(8)); // 开根号  2.8284271247461903
console.log(Math.max(30,2,3,4,1,3));  // 求一组数中的最大值
console.log(Math.min(30,2,3,4,1,3));  // 求一组数中的最小值
// 随机数 Math.random()
```

## 随机数

​        Math.random() 0-1之间的随机数

​        Math.random() * 数 0-数之间的随机数 不包括0 和 数

​        Math.randon() * (y - x) + x  x代表小的数值 y代表大数值 不包含x、y

```javascript
for(var i = 1; i < 6; i++){
    // console.log(Math.random());
    // console.log(Math.random() * 10);
    console.log(Math.random() * (30 - 20) + 20);
}
```

# 时间对象

## 对象的分类

1. 原生对象: Number\String\Boolean\Object\Array\Function\Date\RegExp\Error 三基础三复杂三其他

2. 全局对象: window

3. 宿主对象: DOM BOM

4. 内置对象: Global(全局 window, document) Math

## 创建时间对象

var date = new Date(); // 当前时间对象

var 变量名 = new Date(未来时间格式);

```javascript
// 1. 创建时间对象
var date = new Date();  // 当前时间对象
console.log(date); // Tue Dec 01 2020 10:26:29 GMT+0800 (中国标准时间)
console.log(typeof date); // object
```

```javascript
var fur = new Date(2020, 11, 12, 0, 0, 0); // 年, 月, 日, 时, 分, 秒    月份是数字需要用0-11代表1-12月
var fur = new Date(2020, 11, 12); 

var fur = new Date('2020-12-12 0:0:0'); // '年,月,日 时:分:秒';  // 字符串的时候  月份不需要减1
var fur = new Date('2020$12$12 23:32:23');
// -连字符可以换成一切英文字符中的特殊符号
console.log(fur);
```



## 获取特定格式时间

```javascript
console.log(date.toString()); // Tue Dec 01 2020 10:26:29 GMT+0800 (中国标准时间)
console.log(typeof date.toString()); // string

console.log(date.toLocaleDateString()); // 2020/12/01
console.log(date.toLocaleTimeString()); // 上午10:29:21
console.log(date.toDateString()); // Tue Dec 01 2020
console.log(date.toTimeString()); // 10:30:09 GMT+0800 (中国标准时间)
```

## 获取单个时间

```javascript
// 创建时间
var date = new Date();
console.log(date);

console.log(date.getFullYear()); // 年
console.log(date.getMonth() + 1); // 月  0-11数字 表示1--12月
console.log(date.getDate()); // 日
console.log(date.getDay()); // 星期  日---六  0---6

var week = ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六'];

console.log(week[date.getDay()]); // 星期二

console.log(date.getHours()); // 小时  10
console.log(date.getMinutes()); // 分钟
console.log(date.getSeconds()); // 秒

// 毫秒  从1970-1-1 到现在的毫秒数   1s == 1000ms   时间戳
console.log(date.getTime()); // 毫秒  时间戳
```

## 设置/创建时间

```javascript
/* 
    1. 创建未来时间
    var 变量名 = new Date(未来时间格式);
*/
var fur = new Date(2020, 11, 12, 0, 0, 0); // 年, 月, 日, 时, 分, 秒    月份是数字需要用0-11代表1-12月
var fur = new Date(2020, 11, 12); 

var fur = new Date('2020-12-12 0:0:0'); // '年,月,日 时:分:秒';  // 字符串的时候  月份不需要减1
var fur = new Date('2020$12$12 23:32:23');
// -连字符可以换成一切英文字符中的特殊符号
console.log(fur);

// 2. 单独设置某个时间  年 月  日  时  分  秒  毫秒
var cur = new Date();
// 所有get方法都有set方法 除了星期
cur.setFullYear(2022);

cur.setMonth(2); // 月份是数字需要用0-11代表1-12月
cur.setDate(28);

cur.setHours(13);
cur.setMinutes(0);
cur.setSeconds(0);

// 毫秒直接表示一个完整的时间
cur.setTime(1578654345678);
console.log(cur);
```

## 计算倒计时

```javascript
/*  双十二
    倒计时:  当前时间   未来时间
    差值 = 未来时间 - 当前时间

    1. 未来时间  当前时间
*/


auto();

// 页面每隔1s更新一次
setInterval(auto, 1000);
function auto() {
    var cur = new Date();
    console.log(cur);
    var fur = new Date(2020, 11, 12, 0, 0, 0);
    console.log(fur);

    // 时间差 = 未来时间的毫秒数 - 现在时间的毫秒数;
    var cha = fur.getTime() - cur.getTime();
    console.log(cha); // 900540033

    // 1s = 1000ms   1m = 60s   1h = 60m   1d = 24h
    // 秒
    var s = parseInt(cha / 1000 % 60);
    console.log(s);

    // 分  
    var m = parseInt(cha / 1000 / 60 % 60);
    console.log(m);

    // 小时
    var h = parseInt(cha / 1000 / 60 / 60 % 24);
    console.log(h);

    // 天
    var d = parseInt(cha / 1000 / 60 / 60 / 24);
    console.log(d);
    // 页面中显示倒计时
    document.body.innerHTML = '现在距离双12还剩：' + add0(d) + '天' + add0(h) + '小时' + add0(m) + '分' + add0(s) + '秒';
}
```

# moment

moment.js 处理时间的时间库

## 下载

​      百度: momentjs cdn

​      Moment.js 是一个 JavaScript 日期处理类库，用于解析、检验、操作、以及显示日期。

​      https://www.bootcdn.cn/moment.js/

​      https://momentjs.bootcss.com/

## 分类

​      moment.js: 未压缩 学习

​      moment.min.js: 压缩 开发

## 使用注意

​      所有的单个数字必须要有前导0

​      符号不能用中文字符

## 创建时间

```javascript
/* 1. 创建时间 */
var date = moment(); // 没有参数的时候，创建的当前时间 
var date = moment('2005-08-11 14:22:22'); // 字符串
var date = moment({
    year: 2003,
    month: 4,  // 5
    day: 22,
    hour: 23,
    minute: 21,
    second: 10,
    millisecond: 999   // 毫秒
});
console.log(date);
```

## 格式化时间

​      YYYY年

​      MM 月

​      DD 日

​      d  星期

​      HH 小时

​      mm 分钟

​      ss 秒

​      X  只含秒的时间戳

```javascript
// 格式化时间
console.log(date.format('YYYY-MM-DD HH:mm:ss'));
console.log(date.format('YYYY年MM月DD日 HH:mm:ss'));

console.log(date.format('YYYY')); // 年份
console.log(date.format('MM')); // 带有前导0的月份
console.log(date.format('DD')); // 带有前导0的日期
console.log(date.format('d')); //  0 - 6  代表  周日到周六 
console.log(date.format('HH')); // 带有前导0的小时
console.log(date.format('mm')); // 带有前导0的分钟
console.log(date.format('ss')); // 带有前导0的秒
console.log(date.valueOf()); // 毫秒  1053616870999
console.log(date.format('X')); // 只含有秒的时间戳 1053616870
```

## 设置/获取

```javascript
var date = moment();
console.log(date.format('YYYY-MM-DD HH:mm:ss'));
// 获取/设置
console.log(date.year()); // 获取年

date.year(2012);
date.set('year', 2022); // '属性名', '属性值'
date.set({
    year: 2020
});

console.log(date.format('YYYY-MM-DD HH:mm:ss'));

//-------有类似用法
console.log(date.month());
console.log(date.date());
console.log(date.hour());
console.log(date.minute());
console.log(date.second());
console.log(date.day()); // 星期  0--6  日  六  2   

console.log(date.daysInMonth()); // 日期所在月份的天数
console.log(date.week()); // 一年中的第几周
console.log(date.dayOfYear()); // 一年中的第几天
console.log(date.quarter()); // 一年中的第几个季度
console.log(date.isLeapYear()); // 是否是闰年

console.log(date.toDate()); // moment对象--->时间对象   Tue Dec 01 2020 15:28:57 GMT+0800 (中国标准时间)
```

# String

## 概念

string: 字符串  被成对的单双引号包裹的就是字符串

## 创建

1. 字面量创建: var 变量 = '字符';
2. 强制转换: var 变量 = String(数据);
3. 构造函数/实例创建: var 变量 = new String(数据);

**区别: 1.2创建的是字符串类型  3创建的是对象类型**

```javascript
var str = '123456a';
console.log(str);
console.log(typeof str); // string


var str1 = String(true);
console.log(str1);
console.log(typeof str1); // string

var str2 = new String(false);
console.log(str2); // {"false"}
console.log(typeof str2); // object
```

## 长度

length: 字符串.length 长度

下标: 从左往右从0开始的数字

```javascript
var str3 = '最近，生活在四川甘孜州理塘县的藏族小伙丁真，因为一条不到10秒的视频意外走红网络，不仅被当地聘为旅游大使，更引发了各地文旅机构助推热潮。通过丁真这个窗口让更多人了解到四川乃至全国的景点，网友纷纷表示“这才是网红最好的打开方式”。今晚，我们就从这个藏族小伙聊起。互联网为每个人提供了展现自我的舞台，因为一句话、一个表情、一个动作而走红的不在少数，但像丁真这样引发如此大规模的网络热潮，甚至收获了外交部发言人打call的，却也罕见。有人说丁真的走红，源自于其超高的颜值和帅气的外表，也有人说丁真身上的淳朴和纯真格外打动人。事实上，这些只是让他具备了网红的潜质。真正让他成为“顶级流量”的，是他对家乡、对生活的热爱，让人们感受到逆境中成长的自强不息力量，是镜头中的雪山、白云、藏族服饰等元素，展现了一个丰富多彩而又立体的中国，唤醒了人们对诗和远方的向往，是在他走红之后依然保持的纯真本色，让人们看到一颗赤子之心。';
console.log(str3.length); // 
```

## 指定下标的字符

charAt: 字符串.charAt(下标)

[]: 字符串[下标]

```javascript
console.log(str3.charAt(51));
console.log(str3[51]);
```

## 指定下标的字符的ASCII值

charCodeAt: 字符串.charCodeAt(下标);

​        0----48 9---57

​        A----65 Z---90

​        a----97 z---122

```javascript
console.log(str3.charCodeAt(51));
```

## 字符串比较

字符串的比较: 从左往右，依次比较每一个字符的ASCII值, 如果比较出来大小, 就结束

```javascript
console.log('100000000000' < '2'); // true
console.log('100' < '1'); // false  48 < 0
```

## 查找

### indexOf

1. 语法: indexOf: 字符串.indexOf('匹配的字符', 起始下标);

   起始下标可传可不传

2. 查找规则:

   查找字符在字符串中出现的第一次的位置，从左往右依次匹配，找到就返回下标，找不到返回-1

   起始下标表示要从这个下标的位置开始从左往右依次查找

   ```java
   var str = 'abcdefabcdef';
   console.log(str.indexOf('a')); // 0
   console.log(str.indexOf('g')); // -1
   
   console.log(str.indexOf('a', 3)); // 6
   ```

### lastIndexOf

1. 语法规则: lastIndexOf: 字符串.lastIndexOf('匹配的字符', 起始下标);

   ​      起始下标可传可不传

2. 查找规则

   查找字符在字符串中出现的第一次的位置，从右往左依次匹配, 找到就返回下标，找不到返回-1

   ​      起始下标表示要从这个下标的位置开始从右往左依次查找

```javascript
console.log(str.lastIndexOf('a')); // 6
console.log(str.lastIndexOf('a', 4)); // 0
```

## 截取

### substring

substring: 字符串.substring(起始下标, 结束下标);

​        不传参: 截取返回整个字符串

​        传一个参数: 从起始下标开始截取到字符串的结束为止 包含起始下标的字符

​        传两个参数：

​          起始下标<结束下标: 从起始下标开始截取到结束下标为止, 包含起始下标的字符 不包含结束下标的字符

​          起始下标>结束下标: 互换位置 然后截取

​          如果其中一个是负数: 负数变成0， 参考上述规则

```javascript
var str = 'ABCDEFGHIJK';
console.log(str.substring());
console.log(str.substring(3)); // DEFGHIJK
console.log(str.substring(3, 6)); // DEF 
console.log(str.substring(6, 3)); // DEF 
console.log(str.substring(3, -4)); // 0-3  ABC
```

### slice

slice: 字符串.slice(起始下标, 结束下标);

​        不传参: 截取返回整个字符串

​        传一个参数: 从起始下标开始截取到字符串的结束为止 包含起始下标的字符

​        传两个参数：

​          起始下标<结束下标: 从起始下标开始截取到结束下标为止, 包含起始下标的字符 不包含结束下标的字符

​          起始下标>结束下标: 返回空字符串

​          如果其中一个是负数(结束): 表示字符从右向左有几个不要 

```javascript
console.log(str.slice());
console.log(str.slice(3)); // DEFGHIJK
console.log(str.slice(3, 6)); // DEF
console.log(str.slice(6, 3)); // 空
console.log(str.slice(3, -3)); // DEFGH
```

### substr

substr: 字符串.substr(起始下标, 截取的长度)

​        不传参: 截取返回整个字符串

​        传一个参数: 从起始下标开始截取到字符串的结束为止 包含起始下标的字符

​        传两个参数: 从起始下标开始截取几位

```javascript
console.log(str.substr());
console.log(str.substr(3)); // DEFGHIJK
console.log(str.substr(3, 6)); // 从下标3开始截取6个字符   DEFGHI
```

## 大小写转换

​      大写: 字符串.toUpperCase();

​      小写: 字符串.toLowerCase();

​      应用: 不区分大小写验证码

```javascript
var str = 'ASDFGHJasdfghj';
console.log(str);
console.log(str.toUpperCase());
console.log(str.toLowerCase());
```

## 替换

replace: 将内容替换成新字符

​        str.replace('要替换的内容'/正则, '新字符'/函数);

​        一次只能替换一个字符

```javascript
var str = 'abcabc';
console.log(str.replace('a', '***')); // ***bcabc
```

## 分割

​      将字符串按照分割符进行分割

​      字符串.split('分割符'); 

​      分割符可以是一切字符

​      将字符串分割成数组返回

数组拼接方法:

​        join: 数组.join('连接符');

​        连接符默认是,

​        连接符可以是一切字符 包括标签

​        将数组组成字符串之后再返回

```javascript
var str = '12341234';
console.log(str.split('1'));
console.log(str.split('1').join('****'));
console.log(str.split('1').join('<br>'));

var s = str.split('1').join('<b>123</b>');
document.body.innerHTML = s;
```

## trim

trim: 去除字符串左右空格

​      字符串.trim();

```javascript
var str = '     123  121       ';
console.log(str);
console.log(str.trim());
```

# 数组

## 概念

数组概念: 用来存储不定数量不定类型的数据的容器

## 声明

### 字面量

字面量: var 变量 = [数据,数据,...];

```javascript
var arr = [1,2,3,4];
console.log(arr);
```

### 构造函数/实例

var 变量 = new Array(数据); 

​          数据: 两个及以上: 数组中的每一个项

​          如果就一项并且是数字: 数组的长度 数组中就有几个empty(undefined)

```javascript
var arr1 = new Array(1,2, 'a', true);
console.log(arr1);
var arr2 = new Array(4);
console.log(arr2);
console.log(arr2.length);
```

## 长度

length: 数组.length 数组的长度

```javascript
console.log(arr2.length);

arr2.length = 10; // 通过改变长度可以改变数组中的项

console.log(arr2);

arr.length = 2;
console.log(arr); // 通过长度删掉的数据 找不回来
```

## 元素和索引

元素: 数组中的每一个值 项

索引: 数组中每一个值得下标

```javascript
console.log(arr2[3]);
console.log(arr[0]);
```

## 栈方法

​        push: 向数组的末尾添加一项或者是多项 返回数组的长度

​        pop: 从数组的末尾删除一项，返回被删除的项

​        unshift: 向数组的开头添加一项或者是多项 返回数组的长度

​        shift: 从数组的开头删除一项，返回被删除的项

**会改变原数组**

```javascript
var b = [1,2,4];
var arr = ['a', 'b', 1, 2, 'c', 4];
var len = arr.push(3, b, 4, 6);
console.log(arr);
console.log(len);

var del = arr.pop();
console.log(arr);
console.log(del);

var len1 = arr.unshift(10, 9, 8);
console.log(arr);
console.log(len1);

var del1 = arr.shift();
console.log(arr);
console.log(del1);
```

## splice

### 语法

splice: 万能的数组方法

​      语法: 数组.splice(起始下标, 删除的项的个数, 项1, 项2,...,项n);

​      添加: 数组.splice(起始下标, 0, 项1, 项2,...,项n);

​      删除: 数组.splice(起始下标, 删除的项的个数);

​      修改: 数组.splice(起始下标, 删除的个数, 项1, ... ,项n)

​        删除几个, 添加几个

返回值: 返回被删除的项 组成一个数组返回

```javascript
var arr = [0,1,2,3,4];
// 小乔
arr.splice(2, 0, '小乔', '大乔');
console.log(arr); // [0, 1, "小乔", "大乔", 2, 3, 4]

arr.splice(4, 3);
console.log(arr); // [0, 1, "小乔", "大乔"]

var arr1 = arr.splice(0, 2, '吕布', '貂蝉');
console.log(arr); // ["吕布", "貂蝉", "小乔", "大乔"]

console.log(arr1);
```

### 去重

```javascript
var arr = [1,2,3,3,4,4,5,4,4,1,2,1,1,2333334,51,2,243,1];
console.log(arr);
/* 
    拿第一项(0)和后面的每一项(1)进行对比，如果有重复的就把后面重复的那一项给删除掉
    拿第二项(1)和后面的每一项(2)进行对比，如果有重复的就把后面重复的那一项给删除掉
    拿第三项(2)和后面的每一项(3)进行对比，如果有重复的就把后面重复的那一项给删除掉
    ....
    拿最后项和后面的每一项进行对比，如果有重复的就把后面重复的那一项给删除掉
*/
for(var i = 0; i < arr.length; i++){
    // 后面的每一项
    for(var j = i + 1; j < arr.length; j++){
        console.log(arr[i] , arr[j]);
        if(arr[i] == arr[j]){
            // 后面重复的那一项(j)给删除掉
            arr.splice(j, 1);
            // 本轮循环需要多一次
            j--;
        }
    }
}
console.log(arr);
```

## 算法

### 选择排序算法

选择排序:

​        拿一项出来，和后面的每一项进行对比，如果后面的项小于前面的, 互换位置

过程: 

​        拿第一项(0)和后面的每一项(1)进行对比，如果前面的项大于后面的项，互换位置

​        拿第二项(1)和后面的每一项(2)进行对比，如果前面的项大于后面的项，互换位置

​        拿第三项(2)和后面的每一项(3)进行对比，如果前面的项大于后面的项，互换位置

​        ....

​        拿最后项和后面的每一项进行对比，如果前面的项大于后面的项，互换位置

```javascript
var arr = [1, 3, 1, 4, 2, 5, 6, 3232, 1,32];

for(var i = 0; i < arr.length; i++){
    // 后面的每一项
    for(var j = i + 1; j < arr.length; j++){
        console.log(arr[i], arr[j]);
        // 如果前面的项大于后面的项，互换位置
        if(arr[i] > arr[j]){
            // 中间项
            var temp = arr[i];
            arr[i] = arr[j];
            arr[j] = temp;
        }
    }
}
console.log(arr);
```

### 冒泡算法排序

​        用相邻的两项比较，如果前面的比后面的大，互换位置

​        数组有多少个长度 走多少遍

```javascript
var arr = [3, 1, 2, 4, 6, 1, 7];

for (var i = 0; i < arr.length; i++){
    // 相邻的两项比较  0  1  2  3  4
    for(var j = 0; j < arr.length - i; j++){
        // 相邻
        console.log(arr[j], arr[j+1]);
        if(arr[j] > arr[j+1]){
            // 互换位置
            var temp = arr[j];
            arr[j] = arr[j+1];
            arr[j+1] = temp;
        }
    }
}
console.log(arr);
```

## sort

sort: 数组.sort();

​      默认按照字符串的编码进行排序

数组.sort(参数);

​		参数必须是函数  函数有两个形参

​		第一个形参 - 第二个形参  按照从小到大排序

​		第二个形参 - 第一个形参  按照从大到小的顺序进行排序

```javascript
var arr = [3, 4, 5, 1, 2, 5, 6];
arr.sort();
console.log(arr); // [1, 2, 3, 4, 5, 5, 6]

var arr = [32, 23, 1, 32, 23, 4, 6, 8, 54, 32];
// arr.sort();
// console.log(arr); // [1, 23, 23, 32, 32, 32, 54]

// 参数必须是函数  函数有两个形参
arr.sort(function (a, b) {
    // return a - b; // 第一形参-第二个形参  默认按照从小到大排序
    return b - a; // 第二个形参 - 第一个形参  按照从大到小的顺序进行排序
});
console.log(arr);
```

## 数组方法

### join

join: 将数组的每一项用连接符连接起来，返回字符串 默认以,链接

​    连接符可以是一切字符

```javascript
var arr = [1,2,3,45,6];
console.log(arr.join());
console.log(arr.join('-'));
```

### concat

concat: 将多个数组或者项拼接到一个数组中 数组.concat(项, 项1, ....);

​    返回拼接以后的数组

​    不会改变原数组

```javascript
var arr1 = [4,5,6];
console.log(arr.concat(arr1));
console.log(arr, arr1);
```

### reverse

reverse: 将数组进行翻转 数组.reverse();

​    会改变原数组

    ```javascript

arr.reverse();
console.log(arr);
arr.reverse();
console.log(arr);
    ```

### indexOf/lastIndexOf

indexOf/lastIndexOf: 查找，与字符串的方法使用完全一致 

要查找的项与数组中的项全等(===)的时候 才能找到

如果找到返回对应的项的下标, 如果找不到返回-1

```javascript
var arr = [1,2,3,5,6];
console.log(arr.indexOf(1)); // 0
console.log(arr.indexOf('1')); // -1
console.log(arr.lastIndexOf(6)); // 4
```

### slice

slice: 截取 数组中只有这一个 

slice: 数组.slice();

与字符串是完全一致的规则

**截取规则:** 

+ 一个都不传  返回所有
+ 传一个参数, 从当前的起始下标截取到最后
+ 传两个参数, 从当前的起始下标截取到结束下标  包含起始下标  不包含结束下标
+ 如果起始下标>结束下标  直接返回空
+ 当结束下标为负数的时候, 表示后面有几项是不要的

```javascript
console.log(arr.slice()); // 一个都不传  返回所有
console.log(arr.slice(3)); // 5 6 传一个参数, 从当前的起始下标截取到最后
console.log(arr.slice(3, 4)); //  5  传两个参数, 从当前的起始下标截取到结束下标  包含起始下标  不包含结束下标
console.log(arr.slice(6, 4)); // 空数组  如果起始下标>结束下标  直接返回空
console.log(arr.slice(1, -1)); // 2 3 5 当结束下标为负数的时候, 表示后面有几项是不要的
```

## 迭代方法

1. every: 对数组的每一项进行一个判断, 如果每一项都符合这个判断条件, 返回结果就是true, 有一个是false就是false

​          全真为真 一假为假 &&

​          数组.every(function(value, index, array){});

​          3个形参名字不固定

​          index: 下标

​          value: 项

​          array: 数组本身

​          没有设置返回值，默认返回undefined

```javascript
var arr = [1, 2, 3, 4];
var m = arr.every(function (v, i, a) {
    console.log(i, v, a);
    // return v > 0; 
    return v > 3;
});
console.log(m);
```

2. some: 对数组的每一项进行一个判断, 如果有一项符合这个判断条件, 返回结果就是true, 所有是false就是false

​          全假为假 一真为真 ||

​          数组.some(function(value, index, array){});

```javascript
var n = arr.some(function(v, i, a){
    console.log(i, v, a);
    // return v > 0;
    return v > 3;
});
console.log(n);
```

3. filter: 挑选符合条件的数据组成一个新的数组返回, 过滤数据

   ```javascript
   var mn = arr.filter(function(v, i, a){
       console.log(i, v, a);
       // return v > 2;
       return v > 0;
   });
   console.log(mn);
   ```

4. map: 返回一个新数组  将返回值组成一个新数组返回

   ```javascript
   var ab = arr.map(function(v, i){
       console.log(v, i);
       // return 1;
       return v * v * v;
   });
   console.log(ab);
   ```

5. forEach: 就是一个简单的循环 没有返回值 for 数组

   ```javascript
   var l = arr.forEach(function(v, i){
       console.log(v, i);
       // v = i + 1;  不会影响原数组
       // arr[i] = v * v;
       return 20;
   });
   console.log(arr);
   console.log(l);
   ```

## 算法

### 快速排序

1. 先找到中间下标

2. 找到中间下标的项存储

3. 并且在原数组中删除

4. 声明两个空数组用来存储比中间小的和比中间项大的值

5. 遍历数组中的每一项，如果值比中间项小, 放在left, 如果值比中间大或者相等, 放在right

6. 左右两边数组重复上述操作

7. 将左边数组和中间项以及右边数组连接起来 concat

```javascript
var arr = [2, 3, 5, 21, 54, 12, 43];

function qs(shuzu) {
    // 函数结束的条件
    if (shuzu.length <= 0) {
        return shuzu;
    }
    // 1. 先找到中间下标
    var num = Math.floor(shuzu.length / 2);
    console.log(num);
    // 2. 先找到中间下标的项存储
    var val = shuzu[num];
    console.log(val);
    // 3. 并且在原数组中删除
    shuzu.splice(num, 1);
    console.log(shuzu);
    // 4. 声明空数组
    var left = [], right = [];
    // 5. 遍历
    for (var i = 0; i < shuzu.length; i++) {
        if (shuzu[i] < val) {
            left.push(shuzu[i]);
        } else {
            right.push(shuzu[i]);
        }
    }
    return qs(left).concat(val, qs(right));
}

var a = qs(arr);
console.log(a);
```

## 中文排序

中文排序: 数据.localseCompare(数据1, 语言);

​        结合sort对数据进行排序

​        zh: 中文  en: 英文

中文: b 从z到a排序  a 从a到z

```javascript
// 中文: b  从z到a排序   a  从a到z
var a = '张三';
var b = '李四';
console.log(a.localeCompare(b, 'zh'));
console.log(b.localeCompare(a, 'zh'));

var arr = [
    { name: '武丽昕', num: 78 },
    { name: '汤文博', num: 38 },
    { name: '卢文博', num: 58 },
    { name: '邓钧键', num: 97 },
    { name: '刘继昂', num: 56 },
    { name: '栗军安', num: 78 },
    { name: '屈晓月', num: 98 },
    { name: '付秋萍', num: 79 }
];

arr.sort(function(a, b){
    console.log(a, b);
    // 按照名字进行排序 
    // a-b从小到大  b-a 从大到小
    // 中文: b从z到a排序   a   从a到z
    // return b.name.localeCompare(a.name, 'zh');
    return a.name.localeCompare(b.name, 'zh');
});
console.log(arr);
```

# DOM

## 介绍

DOM: Document Object Model 文档对象模型

DOM是W3C规定的可以操作页面的标准接口

浏览器渲染页面 生成DOM树

​                    html

​      head                 body

 meta  title        a  div  p  em

​                            text href src

## 获取子节点

1. children 非标准属性 标准浏览器中获取到所有的标签节点  ie678 标签节点和注释节点
2. childNodes 标准属性 标准浏览器中 所有的子节点(标签+换行) ie678 标签节点

3. 语法: 元素.children 元素.childNodes

```javascript
var ul = document.getElementsByTagName('ul')[0];
console.log(ul.children); // HTMLCollection
console.log(ul.childNodes); // NodeList
```

## 节点属性

​        节点名称: nodeName: 每一个标签名都是大写 A LI DIV

​        节点类型: nodeType: 1-12的数字  1--标签 2---属性 3---内容

​        节点内容: nodeValue: 只有text(文本)才有内容

```javascript
// for(var i = 0; i < ul.children.length; i++){
//     console.log(ul.children[i]);
//     console.log(ul.children[i].nodeName); // LI
//     console.log(ul.children[i].nodeType); // 8  3  1
//     console.log(ul.children[i].nodeValue); //  null 
// }

for(var i = 0; i < ul.childNodes.length; i++){
    console.log(ul.childNodes[i]);
    console.log(ul.childNodes[i].nodeName); // LI
    console.log(ul.childNodes[i].nodeType); // 
    console.log(ul.childNodes[i].nodeValue); // 标签没有内容  文本节点才有内容
    if(ul.childNodes[i].nodeType == 1){
        // 判断节点是标签节点的时候
        console.log(ul.childNodes[i].childNodes); // 获取标签节点中的所有的子节点
        console.log(ul.childNodes[i].childNodes[0]); // 获取标签节点中文本节点
        console.log(ul.childNodes[i].childNodes[0].nodeValue); // 获取标签节点中文本节点的内容
    }
}
```

## 父节点

1. 获取直接父节点: 元素.parentNode

2. 具有定位属性的父节点: 元素.offsetParent 如果没有具有定位属性的父元素 得到的就是body

```javascript
// 获取第三个li
var li = document.getElementsByTagName('li')[2];
console.log(li);
/* 
获取父节点：
    1. 获取直接父节点: 元素.parentNode
    2. 具有定位属性的父节点: 元素.offsetParent  如果没有具有定位属性的父元素  得到的就是body
*/
console.log(li.parentNode);
console.log(li.offsetParent);
```

## 获取其他节点

### 第一个子节点

第一个子节点: 

​        父节点.firstChild: ie8 标签节点  标准: 换行

​        父节点.firstElementChild: ie8 undefined 标准: 标签节点

换行解决的方式:

 1. 删掉换行

 2. **兼容**: 一个属性有，一个属性没有(undefined false null..)

    将没有的放在||前面 将有的放在||后面

    父节点.firstElementChild || 父节点.firstChild

```javascript
console.log(ul.firstChild, ul.firstElementChild);
console.log(ul.firstElementChild || ul.firstChild);
```

### 最后一个子节点

​        父节点.lastChild: ie8 标签节点  标准: 换行

​        父节点.lastElementChild: ie8 undefined 标准: 标签节点

**兼容**: 父节点.lastElementChild || 父节点.lastChild

```javascript
console.log(ul.lastChild, ul.lastElementChild);
console.log(ul.lastElementChild || ul.lastChild);
```

### 上一个兄弟节点

上一个兄弟节点: 

​          节点.previousSibling: ie8 标签节点  标准: 换行

​          节点.previousElementSibling: ie8 undefined 标准: 标签节点

**兼容**: 节点.previousElementSibling || 节点.previousSibling

```javascript
console.log(li.previousSibling, li.previousElementSibling);
console.log(li.previousElementSibling || li.previousSibling);
```

### 下一个兄弟节点

下一个兄弟节点:

​        节点.nextSibling: ie8 标签节点  标准: 换行

​        节点.nextElementSibling: ie8 undefined 标准: 标签节点

**兼容**: 节点.nextElementSibling || 节点.nextSibling

```javascript
console.log(li.nextSibling, li.nextElementSibling);
console.log(li.nextElementSibling || li.nextSibling);
```

## 创建节点

1. 创建标签节点: document.createElement('标签名')

2. 创建文本节点: document.createTextNode('内容')

3. 文本节点添加到标签节点中: 父节点.appendChild(子节点);

4. 标签节点添加到父元素中: 父节点.appendChild(子节点);

```javascript
var ul = document.getElementsByTagName('ul')[0];
var li = document.createElement('li');
console.log(li);
var txt = document.createTextNode('00001');
console.log(txt);
li.appendChild(txt);
console.log(li);
ul.appendChild(li);
```

## 追加节点

### 将子节点追加到父节点中(最后):

父节点.appendChild(子节点);

​      **如果追加一个已经存在与页面中元素, 反生物理位移(换位置);**

```javascript
var ul = document.getElementsByTagName('ul')[0];
var li = document.createElement('li');
console.log(li);
var txt = document.createTextNode('00001');
console.log(txt);
li.appendChild(txt);
console.log(li);
ul.appendChild(li);

var ul1 = document.getElementsByTagName('ul')[1];
ul1.appendChild(li);
```

### 插入到某个元素之前

父节点.inserBefore(新节点, 参考节点);

```javascript
var li1 = document.createElement('li');
// 设置内容：
li1.innerHTML = '1234';
ul1.insertBefore(li1, li);
```

## 移除节点

1. 移除自身: 节点.remove(); 会将自身及其中所有的子节点删掉
2. 移除子节点: 节点.removeChild(子节点); 会移除子节点及其中所有的节点

```javascript
ul1.removeChild(li1);
ul.remove();
```

## 替换节点

替换子节点: 父节点.replaceChild(新节点, 参考节点);

```javascript
var li2 = document.createElement('li');
li2.innerHTML = '<b>12345</b>';
ul1.replaceChild(li2, li);
```

## 克隆节点

克隆: 节点.cloneNode(boolean);

​          true: 克隆节点和其中的内容

​          false/不传: 只克隆节点

​        返回克隆好的节点, 需要再次追加到父元素中才能在页面中看到

```javascript
// var ul2 = ul1.cloneNode();
// var ul2 = ul1.cloneNode(false);
var ul2 = ul1.cloneNode(true);
console.log(ul2);
document.body.appendChild(ul2);
```

## 获取元素新方式

ie8+:

document.querySelector('css选择器') 获取到的是符合选择器的第一个元素

document.querySelectorAll('css选择器') 获取到的是符合选择器的所有的元素的集合

与id一样的特性，静态性, 获取的时候页面中有，就能拿到， 获取的时候没有, 拿不到

```javascript
var txt = document.querySelector('#txt');
console.log(txt);

var boxes = document.querySelectorAll('.box');
console.log(boxes); // NodeList

// 获取类名为box和a
var boxa = document.querySelectorAll('.box.a');
console.log(boxa);

// 获取类名为a何id为txt
// 组合选择器
var all = document.querySelectorAll('.a,#txt');
console.log(all);

var li = document.createElement('li');
li.innerHTML = '12345';
li.className = 'aaaa';

var aa = document.querySelector('.aaaa');
var ul = document.querySelector('ul');

console.log(aa); // 获取新加的节点  null
ul.appendChild(li);
console.log(aa); // null
```

## 操作属性

1. 获取属性: 元素.属性名 元素['属性名']

   ```javascript
   console.log(box.id);
   console.log(box.className);
   ```

2. 设置属性: 元素.属性名 = 值; 元素['属性名'] = 值;

   ```javascript
   box.id = 'oBox';
   box.className = 'oTxt';
   ```

**注意: 1.2 获取不到写在标签身上的自定义属性 操作自定义属性**

3. 获取属性: 元素.getAttribute('属性名'); 类名直接写class

   ```javascript
   console.log(box.getAttribute('class')); // oTxt
   console.log(box.getAttribute('tag')); // 1
   ```

4. 设置属性: 元素.setAttribute('属性名', '属性值');

   ```javascript
   box.setAttribute('class', 'a b');
   box.setAttribute('a1', true);
   ```

5. 移除属性: 元素.removeAttribute('属性名');

   ```javascript
   box.removeAttribute('tag');
   ```

## 快速获取表格元素

```javascript
// 快速获取表格元素
// 1. 先获取table
var table = document.getElementsByTagName('table')[0];
console.log(table);

console.log(table.tHead); // 表格头
console.log(table.tFoot); // 表格脚
console.log(table.tBodies); // 表格体的集合

// 表格中  表格由行组成
console.log(table.rows); // 整个表格中所有的行的集合
// 获取指定的表格体中的行
console.log(table.tBodies[0].rows); // 第一个表格体中所有的行

// 表格中  行是由单元格  只能通过行获取所有的行中单元格
console.log(table.rows[0].cells); // 第一个行的所有的单元格的集合
console.log(table.tBodies[0].rows[0].cells);

console.log(table.cells); // undefined
console.log(table.tBodies[0].cells); // undefined
```

# 表单

## 快速获取表单元素

快速获取表单中的元素: form.name值  

值: form.name值.value

```javascript
// 1. form
var form = document.getElementsByTagName('form')[0];
// 2. 快速获取表单中的元素:  form.name值   
// 值: form.name值.value
console.log(form.user);
console.log(form.user.value);
console.log(form.sex); // RadioNodeList  集合
console.log(form.sex.value); // nan

console.log(form.hobby); // RadioNodeList
// 无法通过form.name值.value的方式获得复选框的选中值

// 如何获取复选框的值
var arr = [];
for(var i = 0; i < form.hobby.length; i++){
    if(form.hobby[i].checked == true){
        arr.push(form.hobby[i].value);
    }
}
console.log(arr);
```

## 表单事件

### onsubmit

当点击按钮触发表单的提交

​          return true: 表单可以被提交

​          return false: 表单不允许提交

**form表单元素**.onsubmit = function(){}

```javascript
var form = document.getElementsByTagName('form')[0];
console.log(form);

// 给提交按钮加上点击事件
console.log(form.sub);
form.sub.onclick = function(){}

form.onsubmit = function(){
    console.log(1);

    // return false;
    // 当姓名和密码有一个没有输入的时候  不允许提交
    if(form.user.value == '' || form.pass.value == ''){
        alert('请填写完整信息');
        return false;
    }
}
```

### onreset

表单.onreset

​          当表单被重置的时候

​          return true: 表单可以被重置

​          return false: 表单不允许被重置

```javascript
// 重置事件
form.onreset = function(){
    // 如果姓名和密码都输入了，重置 否则不重置
    if(form.user.value != '' && form.pass.value != ''){
        return true;
    } else {
        return false;
    }
}
```

### onfocus

表单中的元素.onfocus

当输入框获取焦点的时候 会触发事件

```javascript
form.user.onfocus = function(){
    this.style.background = 'pink';
}
```

### onblur

元素.onblur

当输入框失去焦点的时候 会触发事件

```javascript
form.user.onblur = function(){
    this.style.background = 'green';
}
```

### onchange

元素.onchange

输入框失去焦点并且内容与上一次内容发生改变得时候会触发

```javascript
form.pass.onchange = function(){
    this.style.background = 'orange';
}
```

### oninpu/onpropertychange

元素.oninput/onpropertychange

在输入框中一边输入一边触发

```javascript
// 边输入边触发
// 事件可以连等 表示触发同一个事件处理函数
form.pass.oninput = form.pass.onpropertychange = function(){
    console.log(this.value);
}
```

## 表单方法

表单方法: 

​          重置: 表单.reset();

​          提交: 表单.submit();

表单元素方法:

​          聚焦: 元素.focus();

​          失焦: 元素.blur();

​          自动选择: 元素.select();

```javascript
var divs = document.getElementsByTagName('div');
var form = document.getElementsByTagName('form')[0];
console.log(divs);
// 点击提交div
divs[0].onclick = function(){
    // 如果用户名和密码都输入了就可以提交
    if(form.user.value != '' && form.pass.value != ''){
        form.submit();
    } else {
        console.log('信息不全');
    }
}
// 点击重置
// 如果用户名或者密码输入了  重置
divs[1].onclick = function(){
    if(form.user.value != '' || form.pass.value != ''){
        form.reset();
    } else{
        console.log('无需重置');
    }
}

// 点击聚焦  用户名输入框聚焦
divs[2].onclick = function(){
    form.user.focus();
}

// 等待10s  用户名输入框失去焦点
// setTimeout(function(){
//     console.log(1);
//     form.user.blur();
// }, 10000);


// 等待页面3s  让输入框自动选择
setTimeout(function(){
    // form.user.select();
    form.sex[1].select();
}, 3000);
```

# BOM

## 基础信息

​      BOM: Browser Object Model 浏览器对象模型

​      **核心： window**

​      window是任何浏览器都支持的一个对象

​      \1. js中用来访问浏览器的接口

​      \2. es中Global的window

​      整个页面中所有的全局的变量和全局的函数 都是属于window

​      全局变量: window的一个属性

​      全局函数: window的一个方法

```javascript
console.log(window);
var a = 20;
console.log(a);
console.log(window.a);

function getNum(){
    console.log(a);
}
getNum();
window.getNum();

// alert('123');
window.alert('345');
```

## 系统对话框

1. 警告框: alert('弹出内容');

2. 带有确定取消按钮: confirm(弹出的内容); 

​        具有返回值 true--确定 false--取消

3. 带有输入框的对话框: prompt(提示内容, 默认值); 默认值不传 输入框就是空 

​        具有返回值

​        确定：返回输入框中的内容

​        取消: null

​      给用户加提示或者选择跳转信息

```javascript
// var c = confirm('是否同意协议');
// console.log(c);
// if(c == false){
//     console.log('用户未同意此协议');
// }

// 输入框的对话框
var p = prompt('请输入要在跳转到第几页', 10);
console.log(p);
```

## open与close

### open

打开一个新的页面

**open(地址, 打开方式, 新页面的宽高, 是否替代历史纪录);**

​        打开方式: _self _blank

​        设置新页面宽高: _blank

**返回新页面的window**

```javascript
var span = document.querySelector('span');
var w = null;
span.onclick = function(){
    w = open('http://www.ujiuye.com', '_blank', 'width=200px,height=1000px', true);
    console.log(w);
}
```

```html
<!-- 行内不能省略window -->
<span onclick="window.open('http://www.ujiuye.com')">这又是一个新的页面</span>
```

### close

close(): 不加前缀/window 表示关闭当前页面

也可以关闭其他页面

```javascript
var btn = document.getElementsByTagName('button')[0];
btn.onclick = function(){
    // close();
    // window.close();
    w.close();
}
```

```html
<button>关闭当前页面</button>
<button onclick="window.close()">行内关闭页面</button>
```

## location

```javascript
/* 
    location BOM中最有用的对象之一   
    存的当前窗口的一些信息以及提供一些导航功能 
    location既是window的一个对象属性  document的一个属性
*/
console.log(location);
console.log(location.hash); // 哈希值, 散列  #+后面内容
console.log(location.href); // 完整地址  file:///E:/1026/day10/08%20location.html#123
console.log(location.protocol); // 协议  http  https  file
console.log(location.host); // 服务器名称+端口号  127.0.0.1:5500
console.log(location.hostname); // 服务器名称  127.0.0.1
console.log(location.port); // 端口号  5500
console.log(location.pathname);//  文件地址  /day10/08%20location.html
console.log(location.search); // 搜索内容  ?+内容

// 刷新页面  location.reload();
// 页面跳转  window.location = 地址;   location.href = 地址;
document.onclick = function(){
    // location.reload();
    // window.location = 'http://www.ujiuye.com';
    location.href = 'http://www.baidu.com';
}
```

## history

history: 历史  存储用户的浏览记录
    back: 后退一个页面
    forward: 前进一个页面
    go: 前进 后退 刷新  
        go(数字): 0--刷新   正数---向前前进几个页面   负数---向后后退几个页面

```javascript
/* 
    history: 历史  存储用户的浏览记录
    back: 后退一个页面
    forward: 前进一个页面
    go: 前进 后退 刷新  
        go(数字): 0--刷新   正数---向前前进几个页面   负数---向后后退几个页面
*/
console.log(history);
// 等待3s  向前前进一个页面
setTimeout(function(){
    // history.forward();
    history.forward(1);
},3000);
```

## 三大宽高

### client

可视宽高: client

​		clientWidth/clientHeight: 可视宽/可视高 content + padding

​		clientLeft/clientTop: 左/上边框的宽度

当前可视区域的宽高:

​        document.documentElement.clientHeight/clientWidth

```javascript
var div = document.querySelector('div');
console.log(div);
console.log(div.clientHeight, div.clientWidth);// 215(200 + 10 + 5) 235(200 + 25 + 10)
console.log(div.clientLeft, div.clientTop);

console.log(document.documentElement.clientHeight, document.documentElement.clientWidth);
```

### offset

占位宽高: offset

​        offsetHeight/offsetWidth: 占位高/占位宽 content + padding + border

​        offsetTop: 当前元素距离具有定位属性的父元素的距离, 如果没有定位父元素, 距离body的距离 顶部

​        offsetLeft: 当前元素距离具有定位属性的父元素的距离, 如果没有定位父元素, 距离body的距离 左边

```javascript
console.log(div.offsetHeight, div.offsetWidth); // 235   270
console.log(div.offsetLeft, div.offsetTop);// 5 30
```

### scroll

实际宽高: scroll

​        scrollHeight/scrollWidth: 元素的实际宽高

​        scrollTop/scrollLeft: 元素被滚动的距离

页面的滚动距离：

​        document.documentElement.scrollTop/scrollLeft

​        document.body.scrollTop/scrollLeft  谷歌75以前

兼容:

​        document.documentElement.scrollTop || document.body.scrollTop

```javascript
console.log(div.scrollHeight, div.scrollWidth);

// div.onscroll = function(){
//     console.log(div.scrollTop, div.scrollLeft);
// }

window.onscroll = function(){
    // console.log(document.documentElement.scrollTop, document.body.scrollTop);
    console.log(document.documentElement.scrollTop || document.body.scrollTop);
}
```

### 总结

```javascript
/* 
    client: 可视宽高
        clientWidth/clientHeight: content + padding
    offset: 占位宽高
        offsetHeight/offsetWidth: content + padding + border
        offsetTop/offsetLeft: 距离具有定位属性的父元素的距离
    scroll:
        scrollTop/scrollLeft: 页面/元素被卷去的高度/宽度

    窗口的可视宽高：
        document.documentElement.clientWidth/clientHeight
    页面的滚动距离
        document.documentElement.scrollTop || document.body.scrollTop


    scrollTop/scrollLeft  既可以获取也可以赋值
    其他的只能获取值
*/
```

## 懒加载

懒加载: 页面滚动到哪里 图片就显示到哪里

1. 布局: 1.1 img必须有宽高的占位 1.2 img的地址写在一个自定义属性上

2. js

​        2.1 页面滚动到哪里图片就显示到哪里 图片进入页面的时候显示出来

​        页面滚动距离 + 屏幕的可视高度 >= 元素距离页面顶部的距离

​        2.2 进入页面的时候，需要先显示第一屏

​	    2.3 屏幕尺寸发生改变的时候 显示当前屏幕的图片

```javascript
window.onload = function () {
    /*
        懒加载: 页面滚动到哪里 图片就显示到哪里
        1. 布局: 1.1 img必须有宽高的占位 1.2 img的地址写在一个自定义属性上
        2. js
            2.1 页面滚动到哪里图片就显示到哪里  图片进入页面的时候显示出来
            页面滚动距离 + 屏幕的可视高度 >= 元素距离页面顶部的距离
            2.2 进入页面的时候，需要先显示第一屏
            2.3 屏幕尺寸发生改变的时候  显示当前屏幕的图片
    */
    // 2.1 页面滚动到哪里图片就显示到哪里  图片进入页面的时候显示出来
    // img
    var imgs = document.getElementsByTagName('img');
    console.log(imgs);
    // var st = document.documentElement.scrollTop || document.body.scrollTop;
    // // console.log(st);
    // var ch = document.documentElement.clientHeight;
    // // console.log(ch);
    // // 判断每一张图片与上述规则是否符合
    // for (var i = 0; i < imgs.length; i++) {
    //     if (st + ch >= imgs[i].offsetTop) {
    //         // 将这张图片的地址设置出来
    //         imgs[i].src = imgs[i].getAttribute('nsrc');
    //     }
    // }

    showImg();
    // 滚动
    window.onresize = window.onscroll = function () {
        showImg();
    }

    function showImg() {
        var st = document.documentElement.scrollTop || document.body.scrollTop;
        // console.log(st);
        var ch = document.documentElement.clientHeight;
        // console.log(ch);
        // 判断每一张图片与上述规则是否符合
        console.log(imgs[0].offsetTop);
        // if(st + ch >= imgs[0].offsetTop){
        //     // 将这张图片的地址设置出来
        //     imgs[0].src = imgs[0].getAttribute('nsrc');
        // }
        for (var i = 0; i < imgs.length; i++) {
            if (st + ch >= imgs[i].offsetTop) {
                // 将这张图片的地址设置出来
                imgs[i].src = imgs[i].getAttribute('nsrc');
            }
        }
    }
}
```

## resize

屏幕尺寸变化事件

```javascript
window.onresize = function(){
    console.log(1);
}
```

# 事件对象

## 概念

当事件被触发的时候，浏览器会将相关当前事件的一些信息和鼠标的位置存储在一个对象上，这个对象就是事件对象

全局中: event

低版本ff: 以事件的第一个参数传递进来

```javascript
var div = document.querySelector('div');
div.onclick = function(evs){
    console.log(event); // MouseEvent
    console.log(window.event); // MouseEvent
    console.log(evs);
    // 兼容: 多使用的放在||前面
    var ev = window.event || evs;
    console.log(ev);
}

document.oncontextmenu = function(evs){
    var ev = window.event || evs;
    console.log(ev.type);
    console.log(ev.target || ev.srcElement);
}
```

## 事件对象属性

```javascript
console.log(ev.type); // 事件类型
console.log(ev.target || ev.srcElement); // 事件的触发源  
console.log(ev.target, ev.srcElement); // 事件的触发源  
console.log(ev.clientX, ev.clientY); // 鼠标距离屏幕可视区域的位置(x--left  y---top)
console.log(ev.pageX, ev.pageY); // 鼠标距离页面(body)左上角的位置
console.log(ev.ctrlKey, ev.altKey, ev.shiftKey); // 当事件被触发的时候, 对应的键是否被按下  true--按下  false--没有
```

# 事件绑定

## 绑定

1. 元素.事件 = function(){}

   ​      如果给同一个元素绑定同一个事件 后面的会覆盖前面的

2. 事件绑定：

   + 标准： 元素.addEventListener('事件类型', 事件处理函数, 是否捕获);

     ​        是否捕获： false

   + ie： 元素.attachEvent('on+事件类型', 事件处理函数);

   ```javascript
   function a() {
       console.log(1);
   }
   function b() {
       console.log(this);
   }
   // 点击div  触发 a  b
   // ie8及以下: 对象不支持“addEventListener”属性或方法
   console.log(div.addEventListener);  // ie8: undefined
   // div.addEventListener('click', a, false);
   // div.addEventListener('click', b, false);
   // 判断  当前addEventListener方法是否存在  存在的话就可以调用
   if (div.addEventListener) {
       div.addEventListener('click', a, false);
       div.addEventListener('click', b, false);
   }
   
   // 标准: div.attachEvent is not a function
   console.log(div.attachEvent); // 标准: undefined
   // div.attachEvent('onclick', a);
   // div.attachEvent('onclick', b);
   
   // 判断  
   if (div.attachEvent) {
       // 存在  ie8
       div.attachEvent('onclick', a);
       div.attachEvent('onclick', b);
   }
   ```

## 封装

```javascript
function addEvent(ele, type, fn) {
    // ele: 元素
    // type: 事件类型
    // fn: 绑定的事件处理函数
    if (ele.addEventListener) {
        // 标准
        ele.addEventListener(type, fn, false);
    } else {
        // ie8
        ele.attachEvent('on' + type, fn);
    }
}
```

## 事件机制区别

标准: 

​        \1. 事件类型不加on

​        \2. 标准有捕获

​        \3. this指向触发源

​        \4. 正序/顺序执行

ie:

​        \1. 事件类型加on

​        \2. ie没有捕获

​        \3. this指向window

​        \4. 倒序执行

# 事件取消

## 取消

1. 元素.事件  元素.事件 = null;
2. 元素.addEventListener  元素.removeEventListener('事件类型', 事件处理函数, 是否捕获)
3. 元素.attachEvent     元素.detachEvent('on+事件类型', 事件处理函数)

```javascript
// ie8:  对象不支持“removeEventListener”属性或方法
if(div.removeEventListener){
    div.removeEventListener('click', a, false);
}
// 标准： div.detachEvent is not a function
if(div.detachEvent){
    div.detachEvent('onclick', a);
}
```

## 封装

```javascript
removeEvent(div, 'click', a);
function removeEvent(ele, type, fn) {
    // ele: 元素
    // type: 事件类型
    // fn: 事件处理函数
    // 判断
    if (ele.detachEvent) {
        // ie8
        ele.detachEvent('on' + type, fn);
    } else {
        // 标准
        ele.removeEventListener(type, fn, false);
    }
}
```

# 事件流

事件流: 当事件发生, 事件在父子节点之间的固定的传递过程就是事件流

​        捕获阶段: 事件从window开始往子元素一层层传递

​        确定目标阶段: 确定事件触发目标

​        冒泡阶段: 事件源开始处理事件， 处理完成后，事件会依次从子节点往父节点传递，直到window为止

​        每一个经过的元素都会接受到当前的事件 会触发自己身上的同类型事件

事件类型: 

​        捕获型事件(标准) 冒泡型事件(默认 标准 ie)

```javascript
var divs = document.getElementsByTagName('div');
function a(){
    console.log(getComputedStyle(this).backgroundColor);
}
// 元素.事件  冒泡型事件
// divs[0].onclick = a; // a后面不加()
// divs[1].onclick = a; // a后面不加()
// divs[2].onclick = a; // a后面不加()
// divs[3].onclick = a; // a后面不加()

// 标准浏览器的事件绑定
// divs[0].addEventListener('click', a, false); // 是否捕获： true--捕获型事件   false--冒泡型事件
// divs[1].addEventListener('click', a, false); // 是否捕获： true--捕获型事件   false--冒泡型事件
// divs[2].addEventListener('click', a, false); // 是否捕获： true--捕获型事件   false--冒泡型事件
// divs[3].addEventListener('click', a, false); // 是否捕获： true--捕获型事件   false--冒泡型事件

// divs[0].addEventListener('click', a, true); // 是否捕获： true--捕获型事件   false--冒泡型事件
// divs[1].addEventListener('click', a, true); // 是否捕获： true--捕获型事件   false--冒泡型事件
// divs[2].addEventListener('click', a, true); // 是否捕获： true--捕获型事件   false--冒泡型事件
// divs[3].addEventListener('click', a, true); // 是否捕获： true--捕获型事件   false--冒泡型事件
```

# 阻止冒泡

由于冒泡产生的问题 阻止冒泡解决

依赖于事件对象

​      标准: ev.stopPropagation();

​      ie: ev.cancelBubble = true;

一个是方法 一个是属性 需要做兼容 **判断方法是否存在:**

​      **ev.stopPropagation ? ev.stopPropagation() : ev.cancelBubble = true;**

不想让哪一个事件冒泡，就在那一个元素的事件上阻止

```javascript
// 点击按钮  让div显示出来
// 1. 获取元素
var btn = document.querySelector('button');
var div = document.querySelector('div');
console.log(btn, div);
// 2. 添加事件
btn.onclick = function(evs){
    var ev = window.event || evs;
    // ev.stopPropagation(); // ie8: 对象不支持“stopPropagation”属性或方法
    // ev.cancelBubble = true;
    console.log(ev.stopPropagation); // 标准: function   ie: undefined
    ev.stopPropagation ? ev.stopPropagation() : ev.cancelBubble = true;

    console.log(1);
    div.style.display = 'block';
}
// 给页面添加点击事件
document.onclick = function(){
    div.style.display = 'none';
}
```

# 阻止默认事件

1. 元素.事件    return false;

2. addEventListener ev.preventDefault();

3. attachEvent    ev.returnValue = false;

4. 兼容: 

   ​        ev.preventDefault ? ev.preventDefault() : ev.returnValue = false;

5. 使用常景:

   + 阻止冒泡:

     ​        如果不想子元素触发父元素的事件

   + 阻止默认事件：

     ​        取消浏览器自带的默认行为

   + 两者可以同时出现

```javascript
// document.oncontextmenu = function(){
//     return false;
// }

document.addEventListener('contextmenu', function(evs){
    var ev = window.event || evs;
    // ev.preventDefault();
    ev.preventDefault ? ev.preventDefault() : ev.returnValue = false;

});

// document.attachEvent('oncontextmenu', function (evs) {
//     var ev = window.event || evs;
//     // ev.preventDefault(); // ie8: 对象不支持“preventDefault”属性或方法
//     // ev.returnValue = false;
//     ev.preventDefault ? ev.preventDefault() : ev.returnValue = false;
// });
```

# 键盘事件

## 事件类型

onkeydown: 按键按下的时候

onkeyup: 按键抬起的时候

onkeypress: 按键按下的时候 

```javascript
document.onkeydown = function (evs) {
    //    console.log(1);
    var ev = window.event || evs;

    // console.log(ev.key); // 可以得到具体的按键  ie: undefined
    // console.log(ev.keyCode); // 具体的按键的编码 ASCII
    // console.log(ev.ctrlKey, ev.shiftKey, ev.altKey); // 对应的按键是否被按下  true--按下  false---没有

    // 复制： ctrl + c  输出 复制
    // if(ev.ctrlKey == true && ev.keyCode == 67){
    //     console.log('复制');
    // }

    console.log(ev.keyCode);
}

document.onkeypress = function (evs) {
    var ev = window.event || evs;
    console.log(ev.keyCode, 'press');
}

document.onkeyup = function(){
    console.log(2);
}
```

## down和press的区别

1. onkeydown: 所有键  不区分大小写 大写的编码   shift + 1 ===> 49
2. onkeypress: 非特殊键 区分大小写 对应的大小写编码 shift + 1 ===> 33

# 滚轮事件

## 滚动

ie+chrome: 元素.onmousewheel

 ff: firefox 

​        事件监听: DOMMouseScroll

```javascript
// document.onmousewheel = function () {
//     console.log('滚了');
// }

// if(document.addEventListener){
//     document.addEventListener('DOMMouseScroll', function(){
//         console.log('滚了');
//     });
// }

function a (){
    console.log('滚远了');
}
document.onmousewheel = a;
if(document.addEventListener){
    document.addEventListener('DOMMouseScroll', a);
}
```

## 滚动方向判断

1. ie chrome: wheelDelta  120  150

​          120/150 上

​          -120/-150 下

​        ff: undefined

2. ff: detail 3 

​          -3  上

​          +3  下

```javascript
function a (evs){
    var ev = window.event || evs;
    // console.log(ev.wheelDelta);
    // console.log(ev.detail);
    // 不知道当前是向上还是向下 假设
    var tag = '上';

    // 判断wheelDelta 是否存在
    if(ev.wheelDelta){
        // ie chrome
        // console.log(ev.wheelDelta);
        // if(ev.wheelDelta > 0){
        //     tag = '上';
        // } else {
        //     tag = '下';
        // }
        tag = ev.wheelDelta > 0 ? '上' : '下';
    } else {
        // ff
        // console.log(ev.detail);
        tag = ev.detail > 0 ? '下' : '上';
    }
    console.log(tag);
}
document.onmousewheel = a;
if(document.addEventListener){
    document.addEventListener('DOMMouseScroll', a);
}
```

# 事件委托

**事件委托**： 事件代理, 将子节点要做的事情交给父元素来做

**原理**: 将原来要给子元素添加的事件, 加给父元素, 事件中通过 target || srcElement 找到对应的子节点, 子节点处理具体的操作

**优点**: 避免使用for  后续加进来的元素也有同样的事件处理

**使用**: 如果子节点有统一的事件(每一个li都加点击事件 每一个li都输出元素)

```javascript
ul.onclick = function(evs){
    var ev = window.event || evs;
    // console.log(ev.target || ev.srcElement);
    var tar = ev.target || ev.srcElement;
    tar.style.background = 'red';
}

// 创建节点
var li = document.createElement('li');
li.innerHTML = '12345';
// 追加进去
ul.appendChild(li);
```

## 回调函数

当一个动作执行完成之后还要继续执行的函数就是回调函数

# 面向对象

## 概念

面向对象: 是一种 **编程思想** 

面向对象: 注重的是**结果** 对象

面向过程: 注重的是**过程** 每一步

面向对象概念: 

​        使用一个模板创建出来一系列的对象 利用对象中的方法和属性实现当前的需求

​        找对象 找得到对象 用对象 找不到 创建对象

**类**：模板 将一系列的动作或属性包含在一个对象中 

​        es5没有类的概念

​        可以将具象化的过程抽象成一个对象中的一个属性或方法(抽象化)

**实例**：通过模板创建出来的对象

## 特征

1. 封装: 可以把一些参数根据传输数据的不同 体现不同的效果 可以划分属性和函数的使用范围

2. 继承: 从公用的函数或者是对象上接受一些共同的方法和属性

3. 多态: 根据的参数的不同 体现的结果是不同的 

​          \+ number + number  'abc' + num 拼接

## 对象的组成:

1. 方法: 动态性 行为

2. 属性: 静态的 描述性

## 创建对象

### 字面量

var 变量名 = {};

缺点: 只适用于单个对象的创建

```javascript
var obj = {
    name: '胡歌',
    height: 188,
    tip: function(){
        console.log('长得帅');
    }
}
console.log(obj);
```

### 实例创建

​      var 变量名 = new Object();

​      缺点: 代码冗余 不直观

```javascript
// 创建对象        
var obj = new Object();
// 添加属性和方法
obj.name = '胡歌';
obj.height = 188;
obj.tip = function(){
    console.log('非常帅');
}
console.log(obj);
```

### 工厂模式

缺点: 识别不清

```javascript
var obj1 = createObj('胡歌', 188);
var obj2 = createObj('王俊凯', 187);
console.log(obj1, obj2);
console.log(typeof obj1);

// 对象 instancof 函数名    检验对象是否由后面的函数创建
console.log(obj1 instanceof createObj); // false--不是

function createObj(name, height) {
    // 创建对象
    var obj = new Object();
    // 添加属性和方法
    obj.name = name;
    obj.height = height;
    obj.tip = function () {
        console.log('非常帅');
    }
    // 返回对象
    return obj;
}
```

对象 instancof 函数名  检验对象是否由后面的函数创建

```javascript
var arr = new Array();
console.log(arr instanceof Array);

// 对象 instancof 函数名    检验对象是否由后面的函数创建
console.log(obj1 instanceof createObj); // false--不是
```

### 构造函数创建

#### 过程

1. 函数名首字母大写（普通函数区分）

2. 把方法和属性添加给this

3. 用new来调用, 不用new和普通函数没有区别

#### new的时候

1. 创建一个空对象

2. 将构造函数的this指向空对象

3. 给this添加属性和方法

4. 隐式返回对象

#### 缺点:

​        同一个方法会在内存中存储很多次 内存浪费

```javascript
function CreateObj(name, height){
    // 创建对象
    // var obj = new Object();
    console.log(this);
    // 添加属性和方法
    this.name = name;
    this.height = height;
    this.tip = function () {
        console.log('非常帅');
    }
    // 设置返回值
    // console.log(obj);
    // return obj;
}

// 实例化对象
var obj = new CreateObj('胡歌', 188);
console.log(obj);
var obj1 = new CreateObj('蔡徐坤',177);
console.log(obj1);
console.log(obj instanceof CreateObj); // true

// 判断一个方法/函数是否在内存中是同一个  ==  true--是同一个  false--不是同一个
console.log(obj.tip == obj1.tip); // false
```

### 原型创建

#### 原型

原型对象: 在函数上

原型属性: 就是原型(对象的) 存储的最顶层的共享的方法和属性  从原型对象上继承来的

通过改变原型对象上的方法和属性 可以将这个方法和属性共享给所有由这个原型创建的对象

```javascript
var arr = [1,2,3,5];
var arr1 = [4,5,6,7,8];

// push 
arr.push(9);
arr1.push(9);
console.log(arr, arr1);

// 原型: 
// 原型对象: 函数  
console.log(Array.prototype)


// 原型属性: 就是原型(对象的)  存储的最顶层的共享的方法和属性   从原型对象上继承来的
console.log(arr.__proto__);

console.log(arr.__proto__ == Array.prototype);

Array.prototype.push = function(){
    console.log('赵某某以一己之力是成都再次战备');
}
console.log(Array.prototype);

arr.push(10);

// 通过改变原型对象上的方法和属性  可以将这个方法和属性共享给所有由这个原型创建的对象
```

#### 原型创建

原型创建缺点: 不能传参

```javascript
// 1. 构造函数
function CreateObj(){};

// 2. 给原型对象添加属性和方法(共享所有的创建的对象)
CreateObj.prototype.name = '胡歌';
CreateObj.prototype.height = 188;
CreateObj.prototype.tip = function(){
    console.log('非常帅');
}

// 3. 实例化对象
var obj = new CreateObj();
console.log(obj);
console.log(obj.name);
obj.tip();

var obj1 = new CreateObj();
obj1.tip();
console.log(obj1.name);

console.log(obj.tip == obj1.tip); // true

// 解决构造函数的问题
// 原型创建缺点: 不能传参
```

### 混合创建

混合创建 构造函数 + 原型

```javascript
// 1. 构造函数(可变的 属性 方法)
function CreateObj(name, height){
    this.name = name;
    this.height = height;
};

// 2. 给原型对象添加属性和方法(不变的属性和方法)
CreateObj.prototype.tip = function(){
    console.log('非常帅');
}

// 3. 实例化对象
var obj = new CreateObj('胡歌', 188);
var obj1 = new CreateObj('蔡徐坤', 150);
console.log(obj, obj1);

obj.tip();
obj1.tip();

console.log(obj.tip == obj1.tip); // true
```

### 动态混合创建

判断要加给原型的方法或者属性是否存在 如果存在 不重复添加 不存在 需要添加

```javascript
// 1. 构造函数(可变的 属性 方法)
function CreateObj(name, height) {
    this.name = name;
    this.height = height;

    // 判断：判断要加给原型的方法或者属性是否存在 如果存在 不重复添加  不存在 需要添加
    console.log('调用对象' + this.name);
    // if (typeof (this.tip) == 'function') {
    //     // 不添加
    //     console.log('不添加');
    // } else {
    //     console.log('添加');
    //     // 2. 给原型对象添加属性和方法(不变的属性和方法)
    //     CreateObj.prototype.tip = function () {
    //         console.log('非常帅');
    //     }
    // }

    if (typeof (this.tip) != 'function') {
        CreateObj.prototype.tip = function () {
            console.log('非常帅');
        }
    }
};



// 3. 实例化对象
var obj = new CreateObj('胡歌', 188);
var obj1 = new CreateObj('蔡徐坤', 150);

console.log(obj, obj1);

obj.tip();
obj1.tip();
```

## 命名空间

命名空间: 将页面中要使用的变量划分成每一块的对象来存储

```javascript
var page = {
    nav: {},
    arr: [1,2,3,4]
}

page.nav.img = 'leftNav';
page.nav.center = {};
page.nav.center.baby = '宝贝';
page.nav.center.arr = ['施华洛世奇', '潮流四件套', '时尚女鞋'];

console.log(page.nav.center.arr);
console.log(page.arr);
```

## 改变this指向

作用: 更改this的指向

call: 函数.call(this的新指向, 参数1, 参数二, ..., 参数n);

apply: 函数.call(this的新指向, [参数1, 参数二, ..., 参数n]);

```javascript
var obj = {
    'name': '胡歌',
    'age': 38,
    'sayname': function () {
        console.log(this.name);
    },
    'jishu': function (a, b) {
        console.log(this, a + b);
    }
}

var obj1 = {
    'name': '张三丰'
}

obj.sayname(); // 胡歌
obj.sayname.call(obj1); // sayname: this-->obj1   this.name --- > 张三丰
obj.jishu(100, 200);
obj.jishu.call(obj1, 500, 600);

obj.jishu.apply(obj1, [50, 60]);
obj.jishu.apply(1, [50, 60]);
obj.jishu.apply(document.body, [50, 60]);
```

## 面向对象的继承

**继承:** 

​        父类构造函数(基类)

​        子类构造函数(派生类)

**分类**

​      \1. 原型链继承

​      \2. 对象冒充继承 子类构造函数冒充父类行使父类构造函数的权限

​      \3. 组合继承

​      \4. 寄生式组合继承

### 原型链继承

```javascript
// 1. 父类构造函数
function Student(){
    this.tip = function(){
        console.log('good good study, day day up, no game');
    }
}
Student.prototype.play = function(){
    console.log('相当可以');
}

// 2. 子类构造函数
function Small(name, age){
    this.name = name;
    this.age = age;
}

// 3. 子类构造函数的原型对象(prototype) = 父类构造函数的实例化对象
Small.prototype = new Student();

// 4. 实例化对象
var obj = new Small();
console.log(obj);
```

### 对象冒充继承

对象冒充继承 this的指向 原本父类构造函数的this变成子类构造函数创建出来的对象

```javascript
// 1. 父类构造函数
function Student(name, age) {
    this.name = name;
    this.age = age;
    this.arr = [1, 2, 3, 4, 5];
    this.tip = function () {
        console.log('好好学习天天向上')
    }
}

Student.prototype.play = function () {
    conosle.log('have fun');
}

// 2. 子类构造函数
function Small(name, age) {
    // 3. 调用父类构造函数  改变this指向为当前子类构造函数的this
    console.log(this); // Small创建的对象
    Student.call(this, name, age);

    this.game = function () {
        cosnole.log('峡谷精英');
    }
}

var obj = new Small('张三', 18);
var obj1 = new Small('张三1', 18);
console.log(obj);
console.log(obj.a);

console.log(obj.arr, obj1.arr);
obj.arr.push(888);
console.log(obj.arr, obj1.arr);

// 缺点： 无法继承父类构造函数的原型对象上的方法和属性
```

### 组合继承

```javascript
// 组成继承: 原型链继承(不变的 属性 方法) + 对象冒充继承(可变的 属性 方法)
// 1. 父类构造函数
function Student(name, age) {
    this.name = name;
    this.age = age;
    this.arr = [1, 2, 3, 4, 5];
    this.tip = function () {
        console.log('好好学习天天向上')
    }
}

Student.prototype.play = function () {
    conosle.log('have fun');
}

// 2. 子类构造函数
function Small(name, age) {
    // 3. 调用父类构造函数  改变this指向为当前子类构造函数的this
    Student.call(this, name, age);

    this.game = function () {
        cosnole.log('峡谷精英');
    }
}

// 4. 子类构造函数的原型对象 = 父类构造函数的实例化对象
Small.prototype = new Student();

var obj = new Small('张三', 18);
var obj1 = new Small('张三1', 18);
console.log(obj);

console.log(obj.a);

console.log(obj.arr, obj1.arr);
obj.arr.push(888);
console.log(obj.arr, obj1.arr);

console.log(obj.__proto__.constructor);
```

# 正则

## 概念

正则: 就是利用事先定义好的特殊的含义的字符组合起来的规则字符串

正则: RegExp

作用: 用来检索和替换字符串

## 创建

### 字面量创建

 var 变量 = /zifu/修饰符;

```javascript
var reg = /web/;
console.log(reg);
console.log(typeof reg); // object
console.log(reg.constructor);
```

### 构造函数

var 变量 = new RegExp('规则字符串', '修饰符');

```javascript
var reg1 = new RegExp('web', '');
console.log(reg1);
```

### 修饰符

i: ignore case 忽略大小写

g: global 全局(整个字符串)

```javascript
var reg = /web/ig;
console.log(reg);
console.log(typeof reg); // object
console.log(reg.constructor);

var reg1 = new RegExp('web', 'g');
console.log(reg1);
```

## 字符串方法

1. split: 字符串.split('分割符'/正则);

   ```javascript
   var reg = /Web/;
   // var reg = /WWW/;
   // var reg = /\d/; // \d   0-9
   console.log(reg);
   
   // 13个 split replace search match
   var str = 'web123web123web456Web';
   
   // split: 字符串.split('分割符'/正则);
   console.log(str.split(reg));
   ```

2. replace: 字符串.replace('替换的字符'/正则, 新字符/函数);

   替换的字符: 一次只能替换一个

   正则: 替换所有

   ```javascript
   console.log(str.replace(reg, '******'));
   ```

3. search(indexOf): 字符串.search(正则); 返回下标 找不大返回-1

   ```javascript
   console.log(str.search(reg));
   ```

4. match: 字符串.match(正则) 返回匹配到的项  

   ["web", "web", "web", "Web"] 

   ["Web", index: 18, input: "web123web123web456Web", groups: undefined]

   如果匹配不到返回null

   ```javascript
   console.log(str.match(reg));
   ```

## 正则方法

1. test

   检验字符串是否有符合正则规范的字符 正则.test(字符串) 

   返回结果true---有符合  false---没有符合

   如果没有加g, 每一次匹配都从0开始

   加了g, 每一次匹配从上一次匹配到的结果项的下一位开始匹配 如果找到最后，返回false，下一次会再从0开始

   ```javascript
   // 正在开始校验的下标  RegExp.lastIndex
   // 1. 检验字符串是否有符合正则规范的字符  正则.test(字符串) 
   // 返回结果true---有符合   false---没有符合
   var reg = /web/;
   console.log(reg.lastIndex); // 0
   console.log(reg.test(str)); // true
   // g: 全局 如果没有加g, 每一次匹配都从0开始
   console.log(reg.lastIndex);
   console.log(reg.test(str));
   
   // g: 加了g, 每一次匹配从上一次匹配到的结果项的下一位开始匹配 如果找到最后，返回false，下一次会再从0开始
   var reg = /web/g;
   console.log(reg.lastIndex); // 0
   console.log(reg.test(str)); // true
   console.log(reg.lastIndex); // 3
   console.log(reg.test(str)); // true
   console.log(reg.lastIndex); // 9
   console.log(reg.test(str)); // true
   console.log(reg.lastIndex); // 15
   console.log(reg.test(str)); // false
   console.log(reg.lastIndex); // 0
   console.log(reg.test(str)); // true
   ```

2. exec

   exec: 返回数组, 项 下标 字符串

   返回匹配到的结果

   正则.exec(字符串);

   ["day", index: 17, input: "good good study, day day up", groups: undefined]

   如果没有加g, 每一次匹配都从0开始,加了g, 每一次匹配从上一次匹配到的结果项的下一位开始匹配 如果找到最后，返回false，下一次会再从0开始

   ```javascript
   var str = 'good good study, day day up';
   var reg = /day/;
   console.log(reg.lastIndex); // 0
   console.log(reg.exec(str));
   console.log(reg.lastIndex); // 0
   
   var reg = /day/g;
   console.log(reg.lastIndex); // 0
   console.log(reg.exec(str));
   console.log(reg.lastIndex); // 20
   console.log(reg.exec(str));
   console.log(reg.lastIndex); 
   console.log(reg.exec(str)); // null
   console.log(reg.lastIndex); // 0
   console.log(reg.exec(str));
   ```

## 元字符

1. . 除换行以外的任意字符

   ```javascript
   var str = '\nabc';
   console.log(str);
   // var reg = /./;
   var reg = /.../;
   console.log(reg.exec(str)); // a
   ```

2. []: 字符集, 写的是任意你想匹配的字符 字符集中的任何一个字符

   [^]: 字符集 不匹配字符集中的任何一个字符

   [0-9] [a-z] [A-Z] [A-Za-z]

   任何字符不需要加（空格 , \ |）隔开 不加引号

   ```javascript
   var str = '0!/web123';
   // var reg = /[!/web]/;
   var reg = /[0-9a-zA-Z]/;
   console.log(reg.exec(str));
   
   var reg = /[^0-9a-zA-Z]/;
   console.log(reg.exec(str)); // !
   ```

3. \d: 匹配0-9  \D: 不匹配数字

   ```javascript
   var str = 'web123';
   var reg1 = /\d/;
   console.log(reg1.exec(str)); // 1
   var reg2 = /\D/;
   console.log(reg2.exec(str)); // w
   ```

4. \w: 匹配数字、字母、_ \W: 不匹配数字、字母、_

   ```javascript
   var str = '_!123web';
   var reg = /\w/;
   console.log(reg.exec(str)); // _
   var reg = /\W/;
   console.log(reg.exec(str)); // !
   ```

5. \s: 匹配空格 \S: 匹配非空格

   ```javascript
   var str = 'he is sleeping';
   var reg = /\s/;
   console.log(reg.exec(str)); // 2
   var reg = /\S/;
   console.log(reg.exec(str)); // h
   ```

6. \b: 匹配单词边界 \B: 匹配非单词边界

   一个单词有2个边界 一个字母有2个边界

   ```javascript
   var str = 'you are a beautiful girl';
   var reg = /\ba\b/; // a两边都是边界 空格  匹配a  a的两边都是边界
   console.log(reg.exec(str)); // 8
   var reg = /a\B/; // 匹配a  右边不是边界的a
   console.log(reg.exec(str)); // 4
   var reg = /\Ba\B/; // 匹配 a  左右都不是边界的a
   console.log(reg.exec(str));
   ```

7. ^a: 字符串以a为开头 a$: 整个字符串以a为结尾

   ```javascript
   var str = 'today is a fun day';
   // var reg = /^a/; // 以a为开头的字符串
   var reg = /^t/;
   console.log(reg.exec(str));
   
   // var reg = /a$/; // 以a为结尾的字符串
   var reg = /y$/; // 以y为结尾的字符串
   console.log(reg.exec(str)); 
   ```

## 量词

1. a?: 表示有1个或者0个a 从左往右匹配第一个字符

   ```javascript
   var str = 'web123';
   var str = '1web123';
   var reg = /\d?/;
   console.log(reg.exec(str));
   ```

2. a*: 表示匹配0个或者连续多个a 从左往右匹配第一个字符 如果匹配到，尽可能多的去匹配

   ```javascript
   var str = 'web123456';
   var str = '123456web345';
   var reg = /\d*/;
   console.log(reg.exec(str));
   ```

3. a+: 表示尽可能多的匹配多个a 

   ```javascript
   var str = 'web1234567';
   var reg = /\d+/;
   console.log(reg.exec(str));
   ```

4. a{n,m}: 至少匹配n次最多匹配m次

   a{n}: 只匹配n次

   a{n,}: 至少匹配n次

   注意: 不要加空格

   尽可能多的去匹配

   ```javascript
   var str = 'web1234567890123456';
   var reg = /\d{3,7}/;
   console.log(reg.exec(str));
   var reg = /\d{6}/;
   console.log(reg.exec(str));
   var reg = /\d{1,}/;
   console.log(reg.exec(str));
   ```

## 特殊

1. |: 或 a|b 匹配a或者b

   ```javascript
   var str = 'web0123webabc'; 
   var reg = /web1|weba/;
   console.log(reg.exec(str));
   ```

2. (): 分组 表示匹配括号中的一项 

   ()优先计算

   ```javascript
   var reg = /web(\d|a)/; // 匹配web后面是1或者是a的web拼接字符(web1   weba)
   var reg = /web(\d|a)(\d|b)/; // 匹配web后面是1或者是a的web拼接字符(web1   weba)   (web+数字 weba)后面跟上数字或者b
   console.log(reg.exec(str));
   // $1  $2拿到的就是正则中()最终匹配的字符的结果
   console.log(RegExp.$1); // 表示获取第一个小括号中匹配到的结果 0
   console.log(RegExp.$2); // 
   ```

3. (?!.....): 不能是前面这个括号中的正则

   ```javascript
   // 设置密码： 字母和数字的组合  6-18位
   var str = 'abc1234456';
   // 不能是纯数字 ^\d{6,18}$
   // var str = '123456789';
   
   // 不能是纯字母    先写纯字母的正则  
   // var regs = /^[a-zA-Z]{6,18}$/;
   // var str = '123456789a';
   
   var str = 'qwertyuiop1';
   var reg = /(?!^[a-zA-Z]{6,18}$)(?!^\d{6,18}$)^[0-9A-Za-z]{6,18}$/;
   
   console.log(reg.exec(str));
   ```

## 匿名函数

### 函数分类

1. 普通函数

   ```javascript
   function fn(){
       console.log(1);
   }
   fn();
   ```

2. 表达式函数

   ```javascript
   var fn1 = function(){
       console.log(2);
   }
   fn1();
   ```

3. 构造函数

   ```javascript
   function Fn(){
       this.name = '张三';
   }
   console.log(new Fn());
   ```

4. 事件处理函数

   ```javascript
   document.onclick = function(){
       alert(1);
   }
   
   function a(){
       alert(2);
   }
   document.onclick = a;
   ```

5. 匿名函数

   ```javascript
   // function (){
   //     console.log(4);
   // }
   ```

### 立即执行函数

#### 概念

没有名字的报错的函数 给它加上()把报错部分转换成表达式

函数的调用 函数()

优点:

1. 当函数只执行一次 进入页面、事件触发 

2. 刚加入新团队开发js代码 保证js完整的加入页面 不会占用函数名 

3. 优美

```javascript
// 没有名字的报错的函数  给它加上()把报错部分转换成表达式
(function () {
    console.log(1);
});
// 函数的调用 函数()

(function () {
    console.log(1);
})();

(function () {
    console.log(2);
}());
```

#### 特点

1. 匿名函数有形参有实参

   形参: function后面的()

   实参: 调用的()

   ```javascript
   (function (a, b) {
       console.log(a, b);
   })(10, 20);
   ```

2. 有返回值

   设置返回值: return 值;

   接收返回值: var 变量 = 函数(); 

   ```javascript
   var s = (function (a, b) {
       return a + b;
   })(10, 20);
   console.log(s);
   ```

# 闭包

## 概念

闭包: 可以读取其他函数内部变量的函数, 函数里面套函数, 内部函数访问外部函数的变量。

本质上，将函数内外连接起来的桥梁。

特点: 闭包中的变量类似于全局变量, 会一直存储在内存中，不会被销毁

解决的问题: for循环中全局i的问题 模拟私有变量

```javascript
function a(){ // 外部
    var s = 10;
    return function b(){ // 内部
        s++;
        console.log(s);
    }
}

var mn = a();
console.log(mn); // 函数b
mn(); // 11 s++; log(s);   
mn(); // 12
```

## 作用

### 解决全局i

```javascript
// 点击每一个li  输出下标
// 因为for执行的速度非常快 一瞬间  
var lis = document.getElementsByTagName('li');
console.log(lis);
for(var i = 0; i < lis.length; i++){
    // console.log(i);
    // 1. 匿名函数
    // 2. 将全局i 作为实参传递到匿名函数中
    (function (s){ // 形参  只在自己的局部作用域中起作用
        console.log(s);
        lis[s].onclick = function(){
            console.log(s);
        }
    })(i);
    // lis[i].onclick = function(){
    //     console.log(i); // 10
    // }
}
```

### 模拟私有变量

```javascript
// 1. 空函数  接收数据
function Fn(value){
    this.value = value;
    var that = this;
    // 需要特定的方法进行值得修改
    this.fun = {
        'setValue': function(v){
            console.log(this);
            that.value = v;
        },
        'getValue': function(){
            console.log(that.value);
        }
    }
}
var obj = new Fn('胡歌');
console.log(obj);
obj.fun.setValue('吴亦凡');

console.log(obj);
obj.fun.getValue();


// 普通函数
function fn(v){ // 外部函数
    var value = v;
    return {
        'setValue': function(v){ // 内部函数
            value = v;
        },
        'getValue': function(){ // 内部函数
            console.log(value);
        }
    }
}

var obj1 = fn('胡歌'); // 出生了一个人  名字叫胡歌
console.log(obj1); // 对象
obj1.getValue();
obj1.setValue('张三'); // 改名叫 张三
obj1.getValue(); // 张三


var obj2 = fn('张三'); // 又出生了一个人 名字叫张三
obj2.getValue(); // 张三

console.log(obj1 == obj2); // false
```

# AJAX

## 概念

ajax: 是一种快速创建动态交互网页的技术

​      在不刷新全页面的情况下更新部分数据

ajax: Asynchronous Javascript and xml

​         异步   javascript 和 xml

通过和后台服务器进行少量的数据数据交互 页面更新

用于： 访问数据 动态请求

​      购物车 新闻刷新 热点更新 全页面数据

## 请求

1. 异步: 不需要等待当前请求返回数据再执行后续的代码
2. 同步: 必须等待请求返回数据以后才能去执行后续代码

## 报错信息

```html
Access to XMLHttpRequest at 'file:///E:/1026/day15/a.txt' from origin 'null' has been blocked by CORS policy: Cross origin requests are only supported for protocol schemes: http, data, chrome, chrome-extension, chrome-untrusted, https.
检查文件的打开方式:
    ajax请求服务器的方式打开
    vscode: Live Sever
```

## readyState

​        0: 创建了ajax对象

​        1: 建立了链接

​        2: 发送了请求

​        3: 后台接收到了请求

​        4: 后台开始处理请求，处理完成后返回了响应包

## status

​        1XX: 信息

​        2XX: 请求成功 200 

​        3XX: 重定向 304

​        4XX: 网页有错误 400 404 403 401 405 

​        5XX: 服务器有错误 500 501 504

## get

1. 创建ajax对象
2. 建立连接 ajax对象.open('请求方式', '请求地址' + ? +'参数', 是否异步)  
3. 发送请求
4. 监听请求的状态
5. 监听后台处理完成的请求
6. 获取数据

```javascript
// 1. 创建ajax对象
var ajax = new XMLHttpRequest();
console.log(ajax);


// 2. 建立连接 ajax对象.open('请求方式', '请求地址' + ? +'参数', 是否异步)  
// 请求方式: get  post
// 请求地址: 本地地址 线上接口
// 是否异步: true---异步  false--同步
// 参数: key=value&&key=value
ajax.open('get', './a.txt?a=1&b=2', true);
console.log(ajax);


// 3. 发送请求
ajax.send();
console.log(ajax);

// 4. 监听请求的状态
// 请求状态改变事件
ajax.onreadystatechange = function(){
    console.log(ajax.readyState); // ajax的请求状态
    // 5. 监听后台处理完成的请求
    if(ajax.readyState == 4 && ajax.status == 200){
        // 6. 获取数据
        console.log(ajax.response);
    }
}
```

##  post

1. 创建ajax对象
2. 建立连接: open('请求方式', 请求地址, 是否异步)
3. 设置请求头
4. 发送请求 send(请求参数);
5. 监听请求的状态改变
6. 监听请求状态和返回值

```javascript
// 1. 创建ajax对象
var ajax = new XMLHttpRequest();

// 2. 建立连接: open('请求方式', 请求地址, 是否异步)
ajax.open('post', 'a.txt', true);

// 3. 设置请求头
ajax.setRequestHeader('Content-type', 'application/x-www-form-urlencoded;charset=utf-8;');

// 4. 发送请求 send(请求参数);
ajax.send('a=1&&b=2');

// 5. 监听请求的状态改变
ajax.onreadystatechange = function(){
    // 6. 监听请求状态
    if(ajax.readyState == 4 && ajax.status == 200){
        console.log(ajax.response);
    }
}


/* 
    Content-type:
        application/x-www-form-urlencoded:  默认  表单
        text/plain: 文本
        mulitipart/form-data: 文件


    vscode 不支持 post请求  405

    wampsever 
*/
```

## 封装

```javascript
function ajax(type, url, data, fn) {
    // type: 请求方式  
    // url: 请求地址
    // data: 请求数据
    // fn: 请求成功以后的回调函数

    // 1. 创建ajax对象
    var ajax = new XMLHttpRequest();
    if (type == 'post') {
        // 2. 建立连接: open('请求方式', 请求地址, 是否异步)
        ajax.open(type, url, true);

        // 3. 设置请求头
        ajax.setRequestHeader('Content-type', 'application/x-www-form-urlencoded;charset=utf-8;');

        // 4. 发送请求 send(请求参数);
        ajax.send(data);
    } else {
        ajax.open(type, url+ '?' + data, true);
        // 3. 发送请求
        ajax.send();
    }

    // 5. 监听请求的状态改变
    ajax.onreadystatechange = function () {
        // 6. 监听请求状态
        if (ajax.readyState == 4 && ajax.status == 200) {
            // console.log(ajax.response);
            // 设置返回值  拿不到结果
            // return ajax.response;

            // 等待后台返回数据之后 才能输出结果 回调函数
            // 把请求返回的数据作为实参传递给回调函数
            fn(ajax.response);
        }
    }
}
```

# 移动端

## 移动端介绍

1. 可用pc端事件 但是不建议用

2. 由于模拟器时好时坏, 为了避免元素.on事件方式有可能出现不能够用, 使用addEventListener来进行添加

## 事件分类

1. 手指按下的时候，触发的事件: touchstart

2. 手指抬起的时候，触发的事件: touchend

3. 手指移动的时候, 触发的事件: touchmove  只要手指在元素内按下 可以再全屏幕

```javascript
var div = document.getElementsByTagName('div')[0];
// div.onclick = function(){
//     console.log(1);
// }

// div.addEventListener('click', function(){
//     console.log(2);
// });

div.addEventListener('touchstart', function(){
    console.log(3);
});

div.addEventListener('touchend', function(){
    console.log(4);
});

div.addEventListener('touchmove', function(){
    console.log(5);
});
```

## 移动端问题

1. 为了监控用户是双击还是单击 所以pc端的事件有300ms的延迟

   ```javascript
   var div = document.getElementsByTagName('div')[0];
   // div.onclick = function(){
   //     console.log(1);
   // }
   
   div.addEventListener('click', function(){
       console.log(2);
   });
   
   div.addEventListener('touchstart', function(){
       console.log(3);
   });
   ```

2. 在移动端中 如果300ms内, 上层元素触发了点击事件 下层元素本身也是有的, 上层元素隐藏的话, 事件会漂移到下层元素上

   ```javascript
   var div = document.getElementsByTagName('div')[0];
   // div.onclick = function(){
   //     console.log(1);
   // }
   
   // div.addEventListener('click', function(){
   //     console.log(2);
   // });
   
   div.addEventListener('touchstart', function(){
       console.log(3);
       div.style.display = 'none';
   });
   ```

## 事件对象的属性

```javascript
var div = document.getElementsByTagName('div')[0];
div.addEventListener('touchstart', function(evs){
    var ev = window.event || evs;
    console.log(ev);
    // console.log(ev.touches); // 当前屏幕上所有的手指列表
    // console.log(ev.targetTouches); // 当前触发元素上的所有的手指列表
    // console.log(ev.changedTouches); // 触发了事件的手指列表  常用

    // 每一个手指又是一个对象
    var touch = ev.changedTouches[0];
    console.log(touch);
    console.log(touch.identifier); // 手指id
    console.log(touch.target); // 触发源
    console.log(touch.screenX, touch.screenY); // 手指按下的时候距离屏幕左上角的距离  74  212
    console.log(touch.clientX, touch.clientY); // 手指按下的时候距离屏幕可视区域的左上角的距离
    console.log(touch.pageX, touch.pageY); // 手指按下的时候距离页面左上角的距离
    console.log(touch.rotationAngle); // 旋转的距离
    console.log(touch.force); // 手指按下的压力
    console.log(touch.radiusX, touch.radiusY); // 手指的半径
});
```

# touch

## 介绍

​      touch.js: 百度云clouda

​      下载: https://www.bootcdn.cn/touchjs/

​      专门为移动端设计使用, ie8 webkit

​      压缩版本: touch.min.js 容量更小 工作

​      未压缩版本: touch.js 格式清晰 学习

## touch.on

1. 给元素添加事件

   touch.on('选择器', '事件', 回调函数)

   ​        选择器: 一切css中的选择器 #id  .class tagName  ,  父 子  父>子

   ​        事件: 可以写多个 多个事件之间用空格分开

   ​        回调函数: 事件触发的时候执行的函数

   ```javascript
   touch.on('div', 'tap  doubletap hold', function(ev){
       console.log(1);
   });
   ```

2. 事件委托

   touch.on('父类选择器', '事件', '子类选择器', 回调函数)

   ```javascript
   touch.on('div', 'tap', 'p,li', function(){
       console.log(this);
   });
   ```

## 事件对象属性

```javascript
touch.on('div', 'tap swipe', 'p,li', function(ev){
    ev.startRotate(); // 开始旋转
    console.log(ev); // CustomEvent 事件对象
    // console.log(ev.originEvent); // 原生事件对象
    // console.log(ev.type); // 事件类型
    // console.log(ev.target, ev.srcElement); // 触发源
    // console.log(ev.position); // 鼠标的位置
    // console.log(ev.direction); // 滑动方向
    // console.log(ev.distanceX, ev.distanceY); // 滑动的距离
    // console.log(ev.rotation); // 旋转角度
    // console.log(ev.fingersCount); // 手指数量
    // console.log(ev.distance); // 移动的距离
    console.log(ev.duration); // 时长   touchstart  到 touchend 
});
```

## 事件分类

单击: tap

双击: doubletap

长按: hold

滑动:

​        swipe 

​        swiping

​        swipestart

​        swipeend

​        swipeleft

​        swiperight

​        swipeup

​        swipedown

拖拽类:

​        drag

​        dragstart

​        dragend

旋转类:

​        rotate

​        rotateleft

​        rotateright

```javascript
// touch.on('div', 'tap doubletap hold swipe swiping swipestart swipeend swipeleft swiperight swipeup swipedown drag dragstart dragend rotate rotateleft rotateright', function(ev){
//     console.log(ev.type);
//     // console.log(ev.x, ev.y);
// });

touch.on('img', 'touchstart', function(ev){
    // console.log(ev.type);
    ev.startRotate();  // 想要触发旋转事件, 监听手指开始事件 在其中调用startRotate
    // console.log(ev.x, ev.y);
});

touch.on('img', 'rotate rotateleft rotateright', function(ev){
    console.log(ev.type);
    // console.log(ev.x, ev.y);
});
```

# JQuery

## 基础介绍

1. 介绍: jQuery 是一个高效、精简并且功能丰富的 JavaScript 工具库。它提供的 API 易于使用且兼容众多浏览器，这让诸如 HTML 文档遍历和操作、事件处理、动画和 Ajax 操作更加简单

2. 理念: 写得少 做得多 write less, do more

3. 百度下载地址: 

   ​        cdn: https://www.bootcdn.cn/jquery/

   ​        官网: https://jquery.com/

4. 使用版本: 

   ​        jquery.js: 未压缩版本  学习

   ​        jquery.min.js: 压缩版本 工作

5. 引入方式： 

   ​        \1. 引入本地文件: 常用

   ​        \2. 引入cdn文件: 不常用

   ```html
   <!-- <script src="https://cdn.bootcdn.net/ajax/libs/jquery/3.5.1/jquery.js"></script> -->
   <script src="js/jquery.js"></script>
   ```

6. 最新版本： 

   ​        3.5.1

   ​        2XX 3XX都不是兼容IE678  

   ​        1XX 兼容IE678

7. 优点:

   ​        \1. 写得少 做得多

   ​        \2. 强大的选择器

   ​        \3. 轻量级

   ​        \4. DOM文档

   ​        \5. 动画

   ​        \6. 隐式迭代

   ​        \7. 链式操作

   ​        \8. ajax操作

   ​        \9. 开源 免费 源代码释放

   ​        \10. ....其他

8. 文档: 

   ​        https://jquery.cuishifeng.cn/

## $与jQuery的关系

$和jQuery是同一个东西

```javascript
console.log(jQuery);
console.log(window.jQuery);
console.log(window.$);
console.log($);
console.log(window.jQuery == $);
```

## 等待页面加载

window.onload 一个页面只能写一个 如果写多个,后面的会覆盖前面的 不能简写 执行时机(等待页面和资源)

 ready 一个页面可以写多个 叠加执行 可以简写 执行时机(DOM结构加载完成后)

```javascript
// 1. 原生等待页面及资源加载
window.onload = function(){
    console.log(1);
}
window.onload = function(){
    console.log(2);
}

// 2. jquery 等待页面加载
// 2.1 $(document).ready(function(){})
$(document).ready(function(){
    console.log(3);
});
// 2.2 $().ready(函数);
$().ready(function(){
    console.log(4);
});
// 2.3 $(function(){});
$(function(){
    console.log(5);
});
```

## jquery对象和js对象的互转

1. js对象转成jq对象

   js转成jq对象  $(js对象)

   ```javascript
   window.onload = function(){
       // 1. 获取元素
       var li = document.getElementsByTagName('li');
       console.log(li); // HTMLCollection
       // 通过原生获取元素方式得到的元素   可以使用js中的方法
   
   
       // js转成jq对象  $(js对象)
       console.log($(li)); // jQuery.fn.init
       console.log($(li[0])); // jQuery.fn.init
   }
   ```

2. jQuery对象 转成js对象

   + jq对象[下标]
   + jq对象.get(下标)

   ```javascript
   $(function(){
       var li = $('li'); // $('选择器')
       console.log(li); // jQuery.fn.init
       // 通过jq方法得到的元素叫做jquery对象  可以使用jq的方法 
   
       // jQuery对象 转成js对象  jq对象[下标]
       console.log(li[0]); // <li>0001</li>   具体的标签 也是js对象
       console.log(li.get(0)); // jq对象.get(下标)   具体下标代表的js对象
   });
   ```

## 选择器

### 基本选择器

```javascript
console.log($('li')); // 标签选择器
console.log($('.a')); // 类名选择器
console.log($('#five')); // id名选择器
console.log($('.a,#five')); // 基本选择器
```

### 层级选择器

```javascript
// jq元素.css('属性名', '属性值')
// jq除非语法错误  否则不报错
// js对象用了jq方法  某些必传参数写错了
console.log($('ul li').css('background', 'red'));
console.log($('ul > li').css('background', 'yellow'));
console.log($('.box + div').css('background', 'blue'));
console.log($('.box ~ div').css('background-color', 'green'));
```

### 过滤选择器

#### 基本过滤选择器

```javascript
$('ul li:first').css('background', 'red'); // 第一个元素
$('ul li:last').css('background', 'red'); // 最后一个元素
$('ul li:not(.box)').css('background', 'green'); // 类名不为box的li的元素
$('ul li:even').css('background', 'red'); // 索引为偶数的li的元素
$('ul li:odd').css('background', 'blue'); // 索引为奇数的li的元素
$('ul li:eq(5)').css('background', 'yellow'); // 获取索引为5的元素
$('ul li:lt(5)').css('background', 'pink'); // 索引小于5的元素
$('ul li:gt(5)').css('background', 'skyblue'); // 索引大于5的元素
```

#### 内容过滤选择器

```javascript
$('li:contains(6)').css('background', 'red'); // 文本中包含某个文字的
$('li:has(span)').css('background', 'blue'); // 标签中有span
$('li:parent').css('background', 'orange'); // li中有内容  文字  标签
$('li:empty').css('background', 'blue'); // li中为空的
```

#### 可见性过滤选择器

```javascript
// 不可见: input type="hidden"  display:none
console.log($('li:visible'));
console.log($('li:hidden'));

console.log($('body *:hidden'));
console.log($('body *:visible'));
```

#### 属性过滤选择器

```javascript
$('li[tag]').css('background', 'red'); // 获取有tag属性的li
$('li[tag=123]').css('background', 'green'); // tag属性值为123的li
$('li[tag!=123]').css('background', 'blue'); // tag属性值不为123的li

$('li[title^=a]').css('background', 'yellow'); // title属性以a为开头
$('li[title$=a]').css('background', 'orange'); // title属性以a为结尾
$('li[title*=a]').css('background', 'skyblue'); // title中有a这个字符的
```

#### 子元素过滤选择器

```javascript
$('ul li:nth-child(1)').css('background', 'red'); // nth-child选中第几个
$('ul :nth-child(1)').css('background', 'blue'); // nth-child选中第几个
$('ul :nth-child(even)').css('background', 'pink'); // nth-child选中偶数
$('ul :nth-child(odd)').css('background', 'orange'); // nth-child选中奇数
$('ul :nth-child(3n+1)').css('background', 'blue'); // 表达式  1  3   7  

$('ul :first-child').css('background', 'purple');
$('ul :last-child').css('background', 'purple');
```

#### 表单属性过滤选择器

```javascript
console.log($('input:enabled')); // 获取可用的输入框
console.log($('input:disabled')); // 获取不可用的输入框

console.log($(':checkbox:checked')); // 获取选中的复选框
console.log($(':radio:checked')); // 获取选中的单选框

console.log($('select :selected')); // 获取选中的下拉列表的项
```

#### 表单元素过滤选择器

```javascript
console.log($(':input')); // 获取所有的表单
console.log($(':text')); // 获取所有的输入框
console.log($(':radio')); // 单选按钮
console.log($(':checkbox')); // 复选按钮
console.log($(':button')); // 按钮
console.log($(':reset')); // 重置按钮
console.log($(':submit')); // 重置按钮
console.log($(':image')); // 上传图片
console.log($(':file')); // 上传文件 
```

## 节点遍历

### 子节点

```javascript
// 下面所有的方法均可以接受一个选择器作为过滤条件
// 1. 子节点
console.log($('ul').children());
console.log($('ul').children('li'));
console.log($('ul').children('li:odd'));

// 2. 上一个兄弟节点
$('.box').prev().css('background', 'red'); // 获取上一个
$('.box').prevAll().css('background', 'blue'); // 获取前面所有的
$('.box').prevAll('a').css('background', 'black'); // 获取前面所有的

// 3. 下一个兄弟节点
$('.box').next().css('background', 'orange'); // 获取下一个
$('.box').nextAll().css('background', 'green'); // 获取下面所有的

// 4. 获取所有的兄弟节点
$('.box').siblings().css('background', 'pink'); // 获取所有的兄弟节点
```

### 父节点

```javascript
// 获取父节点
console.log($('.box').parent()); // 直接父节点
console.log($('.box').parents()); // 获取所有的父节点  html
console.log($('.box').parents('ul')); // 可以接收选择器作为接收条件
```

### 过滤

```javascript
// 过滤节点：find filter not
$('ul').find('.box').css('background', 'pink'); // 找到ul后 再去找ul中类名为box的元素
$('li').filter('.box').css('background', 'orange'); // 找到li  在li中过滤出有类名.box的元素
$('li').not('.box').css('background', 'blue'); // 找到li  在li中过滤出没有类名.box的元素
```

## 取赋值

取赋值一体化: 取值 设置值 用同一个方法

​     	 取值: 只获取符合选择器条件的第一个元素的值

​     	 赋值: 遍历赋值(隐式迭代)

## 操作属性

### attr

​        jq对象.attr('属性名')  获取

​        jq对象.attr('属性名', '属性值') 设置 只适用于单个属性的设置

​        jq对象.attr({

​       	   '属性名': 属性值,

​       	   '属性名1': 属性值1,

​        });  适合批量设置多个属性

​        既可以操作固有属性 也可以操作自定义属性

​        jq对象.removeAttr('属性名');

```javascript
console.log($('.box').attr('class'));
console.log($('.box').attr('id'));
console.log($('.box').attr('tag'));

$('.box').attr('id', 'a45678');
$('.box').attr('tag', 'weekDay');

$('li').attr({
    'name': 'isLi',
    'age': 20
});

$('li').attr('name', '');
$('li').removeAttr('name');
```

### prop

​        语法跟attr完全一致 使用有限制

​        \1. 只添加属性名就起作用的时候(固有属性) 

​        \2. 属性值只有true、false  checked disabled selected

​        jq对象.prop('属性名')  获取

​        jq对象.prop('属性名', '属性值') 设置 只适用于单个属性的设置

​        jq对象.prop({

​        	  '属性名': 属性值,

​         	 '属性名1': 属性值1,

​        });  适合批量设置多个属性

​        可以操作固有属性 

​        jq对象.removeProp('属性名');

```javascript
console.log($(':checkbox'));
console.log($(':checkbox').prop('checked'));
// $(':checkbox').prop('checked', true);
$(':checkbox').prop({
    'name': 'check',
    'value': '复选框',
    'tag': '123',
    // 'checked': true
});

// console.log($(':checkbox').removeProp('checked'));
$(':checkbox').attr('checked', true);
$(':checkbox').attr('checked', false);
```

### 链式调用

链式调用原理: jq方法在被调用之后, 将当前方法操作的对象或者操作以后的对象返回回来

## 操作类名

### addClass

添加类名 jq对象.addClass('类名1 类名2')

```javascript
// $('div').addClass('active');
// $('div').addClass('active bg');
// console.log($('div').addClass('active').addClass('bg'));
```

### removeClass

移除类名: jq对象.removeClass('类名 类名1')

```javascript
// $('div').removeClass('active bg');
```

### toggleClass

添加移除类名 jq对象.toggleClass('类名')

有类名的话 就移除  如果没有类名 就添加类名

```javascript
$('div').toggleClass('active');
```

### hasClass

是否具有某个类名: jq对象.hasClass('类名')  

有 返回true 如果没有 返回false

```javascript
console.log($('div').hasClass('active'));
```

### is

是否具有某个选择器或状态: jq对象.is('.类名') ()里面写的是选择器

有 返回true 如果没有 返回false

```javascript
console.log($('div').is('.active'));
```

## 操作样式

1. jq对象.css('属性名') 获取对应的值

2. jq对象.css('属性名', '属性值') 设置 只设置单个样式属性

3. jq对象.css({ '属性名': 属性值,'属性名1': 属性值1 }) 设置

**注意:**

属性名: 可以加引号 也可以不加 如果不加的话 - 需要转成驼峰命名法 如果加引号 不需要转驼峰 建议加引号

属性值:

​        带单位 '30px'

​        数值  300  默认添加px

​        表达式 '+=40' -= *=  /=

```javascript
console.log($('div').css('width'));
console.log($('div').css('width', 300));
console.log($('div').css({
    'width': 500,
    'height': '300px',
    // fontSize: 30
    // 'font-size': 30
    'font-size': '+=20'
}));
$('button').click(function(){
    $('div').css({
        'font-size': '+=10',
    });
})
```

## 操作内容

### text

text(): 类似于innerText

​        \1. 取值: jq对象.text(); 获取到所有符合条件的元素的内容

​        \2. 设置: jq对象.text('内容'); 后面的会覆盖前面的 遍历设置 

```javascript
console.log($('div').text());

// $('div').text('这是我写的新内容');
```

### html

html(): 类似于innerHTML

​        \1. 取值: jq对象.html(); 获取符合条件的元素的第一个的内容

​        \2. 设置: jq对象.html('内容'); 后面的会覆盖前面的 遍历设置 

​        可以识别标签

```javascript
console.log($('div').html());
console.log($('div').html('<i>这是我写的新内容</i>'));
$('p').text('<i>这是我写的新内容</i>');
```

### val

val(): 类似于value

​        \1. 取值: jq对象.val(); 获取符合条件的元素的第一个的内容

​        \2. 设置: jq对象.val('内容'); 后面的会覆盖前面的 遍历设置 

```javascript
console.log($('input').val());
$(':text').val('新内容');

console.log($(':radio:checked').val());

$(':radio').val(['男']); // value上的值

console.log($(':checkbox').val());


$(':checkbox').val(['LOL', 'CS']);

console.log($('#city').val());

$('#city').val('nj');
// $('#city').val('nj ');


console.log($('#mul').val());
console.log($('#mul').val(['bj', 'nj']));
```

## BOM

### 三大宽高

1. 宽: width height

2. 可视: clientWidth

3. 占位: offsetWidth

4. 滚去的高度: scrollTop

```javascript
console.log($('div').width(), $('div').height()); // 宽 高  内容
console.log($('div').innerWidth(), $('div').innerHeight()); // 可视宽  可视高  content + padding
console.log($('div').outerWidth(), $('div').outerHeight()); // 占位宽、高 content + padding + border
// 有一个参数  布尔值: true--content + padding + border +margin  false/不传---content + padding + border
console.log($('div').outerWidth(true), $('div').outerHeight(true));

// 取赋值一体化 
// jq对象.width(数值)
$('div').width(500);
// jq对象.innerWidth(数值)   padding不会改变  变得是具体的内容宽高
$('div').innerWidth(500); // content + padding = 500  
// jq对象.outerWidth(数值, 是否包含margin)  true--表示包含   false/不传--表示不包含
$('div').outerWidth(500); // content + padding + border = 500   
$('div').outerWidth(500, true); // content + padding + border + margin = 500 
```

### 元素位置

当前元素距离具有定位属性父元素的距离

```javascript
console.log($('div').offset());
console.log($('div').offset().top);
```

### 滚动高度

```javascript
$(window).scroll(function(){
    console.log($(this).scrollTop())
    console.log($(this).scrollLeft())
});
```

## DOM

### 创建节点

$('html片段')

```javascript
var li = $('<li>这是一个新标签</i>');
console.log(li);
```

### 追加节点

```javascript
/* 
    1. 追加到父节点的末尾

*/
// $('ul').append(li); // 父节点.append(子节点)
// li.appendTo('ul'); // 子节点.appendTo('父节点选择器')
// 如果是一次性批量的往父元素中添加
// li.appendTo('ul:eq(0)');
// li.appendTo('ul:eq(1)');
// 分开步骤追加同一个节点到不同的父节点中  会发生物理位移

/* 
    2. 追加到父节点的开头
    prepend
    prependTo
*/
// $('ul').prepend(li); // 父节点.prepend(子节点)
// li.prependTo('ul'); // 子节点.prependTo(父节点)

/* 
    3. 追加某个参考元素之前
    before  insertBefore
*/
// $('.box').before(li); // 参考节点.before(新节点)
// li.insertBefore('.box'); // 新节点.insetBefore('选择器')

/* 
    4. 追加到某个参考元素之后
    after  insetAfter
*/
// $('.box').after(li); // 参考节点.after(新节点)
li.insertAfter('.box'); // 新节点.insertAfter('选择器')
```

### 删除节点

1. detach: 删除当前元素, 返回被删除的元素, 可以保留之前元素的行为

2. remove: 删除当前元素, 返回被删除的元素, 不能保留之前元素的行为

3. empty: 清空当前元素(删除当前元素的所有子元素)

```javascript
$('ul li').click(function(){
    $(this).css('background', 'red');
});


// :eq(0)   jq对象.eq(下标)   得到的都是jq对象
$('button:eq(0)').click(function(){
    var li = $('ul li').eq(0).detach();
    console.log(li);
    setTimeout(function(){
        $('ul').append(li);
    }, 2000);
});

$('button:eq(1)').click(function(){
    var li = $('ul li').eq(0).remove();
    console.log(li);
    setTimeout(function(){
        $('ul').append(li);
    }, 2000);
});


$('button:eq(2)').click(function(){
    $('ul').empty();
});
```

### 克隆节点

jq对象.clone(布尔值) 返回克隆的节点 页面不存在 需要追加到页面中才能看到

不传/false 表示不克隆行为  true 表示克隆行为

```javascript
$('ul li').click(function(){
    console.log(this);
});

// jq对象.clone(布尔值)  返回克隆的节点  页面不存在 需要追加到页面中才能看到
// 不传/false  表示不克隆行为   true  表示克隆行为
$('button').click(function(){
    // var li = $('ul li').eq(0).clone();
    var li = $('ul li').eq(0).clone(true);
    $('ul').append(li);
});
```

### 替换节点

replaceAll: 新节点.replaceAll('选择器')

replaceWith: $('参考节点').replaceWith(新节点)

```javascript
var li = $('<p>这是非法嵌套</p>');
// $('li').replaceWith(li); 
li.replaceAll('li');
```

### 包裹节点

```javascript
// 链式调用原理： jq方法操作的对象或者是操作以后的对象返回回来
// 1. jq对象.wrap('标签')  jq对象的外面包裹一层标签
$('span').wrap('<div></div>');

// 2. jq对象.wrapInner('标签');  jq对象的里面包裹一层标签
$('span').wrapInner('<i>12345</i>');

// 3. jq对象.wrapAll('标签')  jq对象包裹在一个标签中
var b = $('span').wrapAll('<p></p>');

// 4. jq对象.unwrap(); jq对象删除以及父节点  删到body截止
var a = $('span').unwrap().unwrap().unwrap().unwrap();
console.log(a, b);
```

## 事件对象

```javascript
/* 
    事件对象： 事件处理函数的第一个参数
*/
$('div').click(function(ev){
    console.log(ev); // jQuery.Event
    console.log(ev.originalEvent); // 原生事件对象
    console.log(ev.type); // 事件类型
    console.log(ev.target); // 触发源
    console.log(ev.delegateTarget); // 事件的绑定对象
    console.log(ev.which); // 与keyCode基本一致，比keyCode强大  保留鼠标的左中右  123
    console.log(ev.screenX, ev.screenY); // 鼠标距离屏幕左上角
    console.log(ev.pageX, ev.pageY); // 鼠标距离页面左上角
    console.log(ev.offsetX, ev.offsetY); // 鼠标距离div的左上角的距离
    console.log(ev.ctrlKey, ev.shiftKey, ev.altKey); // 事件触发的时候  对应的键是否被按下
    console.log(ev.clientX, ev.clientY); // 鼠标相对于屏幕左上角可视区域的距离

    // 阻止冒泡
    ev.stopPropagation();
    // 阻止默认行为
    ev.preventDefault();
    // 阻止冒泡 + 阻止默认事件
    return false;
    // 一般写在函数的最后
});
$(document).contextmenu(function(){
    // return false;
});
```

## 事件绑定

### on

1. 给同一个元素绑定同一事件不同的事件处理函数

   ```javascript
   function a(){
       console.log(1);
   }
   function b(ev){
       console.log(ev.type);
   }
   // 1. jq对象.on('事件类型', 事件处理函数)
   $('div').on('click', a);
   $('div').on('click', b);
   ```

2. 给同一元素的不同事件添加同一处理函数

   jq对象.on('事件类型 事件类型1 事件类型2', 事件处理函数)

   ```javascript
   $('div').on('click dblclick mouseenter mouseleave contextmenu', b);
   ```

3. 给同一个元素的不同事件添加对应的事件处理函数

   jq对象.on({ 属性名: 函数}) 属性名---事件类型

   ```javascript
   $('div').on({
       'click': b,
       'mouseenter': a,
       'mouseleave': function(){
           console.log(2);
       },
       // 'click': a // 如果属性名相同  后面的覆盖前面的
   });
   ```

4. 绑定自定义事件

   自定义事件

   ```javascript
   $('div').on('abc', function(){
       console.log('哈哈哈哈哈');
   });
   // 手动触发: jq对象.trigger(自定义事件类型)
   setTimeout(function(){
       $('div').trigger('abc'); // 手动触发自定义事件
   }, 3000);
   ```

5. 实现事件委托 元素可以发生在未来

   事件委托： jq对象.on(事件类型, 选择器, 事件处理函数)

   ```javascript
   $('div').on('click', 'p', function(){
       console.log($(this).text());
   });
   $('div').append('<p>12345</p>');
   ```

### 命名空间

```javascript
/* 
    jq对象.on();
    jquery1.7版本以上 delegate  bind  live
*/
// function a(){
//     console.log(1);
// }
// function b(ev){
//     console.log(ev.type);
// }

$('div').on('click.a', function(){
    console.log(2);
});

$('div').on('mouseover.a', function(){
    console.log(4);
});
```

### off

事件取消： jq对象.off(事件类型, 处理函数的名字);

​      事件处理函数的名字可写可不写

```javascript
/* 
    jq对象.on();
    jquery1.7版本以上 delegate  bind  live
*/
function a(){
    console.log(1);
}
function b(ev){
    console.log(ev.type);
}

$('div').on('click.a', function(){
    console.log(2);
});

$('div').on('mouseover.a', function(){
    console.log(4);
});

$('div').on('click', a);
$('div').on('click', b);

/* 
    事件取消： jq对象.off(事件类型, 处理函数的名字);
    事件处理函数的名字可写可不写
*/
// $('div').off('click', a);
// $('div').off('click.a');
// $('div').off('click');
$('div').on('click', function (){
    console.log(333);
});

// 无法取消事件
// $('div').off('click', function(){
//     console.log(333);
// });
$('div').off('click');
```

### one

one: on用法完全一致

区别: one一次性事件

```javascript
// $('div').one('click', function(){
//     console.log(1);
// });


// 用on模拟one事件
$('div').on('click', function(){
    console.log(1);
    // 解绑事件
    $(this).off('click');
});
```

### 合成事件

语法： jq对象.hover();

​      参数是一个函数：滑入滑出事件都触发这个函数

​      参数是两个函数: 滑入函数 和 滑出函数

```javascript
// $('div').hover(function(ev){
//     console.log(ev.type);
// });

$('div').hover(function(ev){
    $(this).html('这是enter');
    $(this).css('background', 'blue');
}, function(){
    $(this).html('这是leave');
    $(this).css('background', 'green');
});
```

## 遍历

### $.each

$.each(数据, 函数) 

​      函数有两个形参 第一个形参是索引/属性名 第二个形参具体的值

```javascript
// 1. 遍历集合
$.each($('li'), function(i, v){
    // console.log(i, v);
    $(v).css('background', 'red');
    // console.log(this); // 当前的元素
    // console.log(this == v);
});


// 2. 遍历数组
var arr = ['a', 'b', 'c', 'd', 'e'];
$.each(arr, function(i, v){
    // console.log(i, v);
    // console.log(this); // 当前的值
    // console.log(v == this);
});

// 3. 遍历对象
var obj = {
    name: '彭于晏',
    height: 188,
    age: 18
};
$.each(obj, function(k, v){
    console.log(k, v);
});
```

### $().each

$().each(函数)

​      函数有两个形参 第一个形参是索引 第二个形参具体的值

​      不能遍历对象

```javascript
// 1. 遍历集合
$('li').each(function (i, v) {
    // console.log(i, v);
    console.log(this);
});

// 2. 数组
var arr = ['a', '1', 2, 3, 4, 5];
$(arr).each(function(i,v){
    console.log(i, v);
});
```

## extend

### 浅拷贝

浅拷贝: 只比较属性名，如果属性名重复，用后面的覆盖前面的

返回拼接数据以后的dest

工具: $.extend(dest, src, src); 

```javascript
var obj = {
    name: '张艺兴',
    height: 198,
    age: 33
};

var obj1 = {
    age: 18,
    tip: '挣钱'
}

// 工具: $.extend(dest, src, src);  

// 浅拷贝: 只比较属性名，如果属性名重复，用后面的覆盖前面的
// 返回拼接数据以后的dest
// var objnew = $.extend(obj, obj1);
// console.log(obj);
// console.log(objnew);
// console.log(objnew == obj);

// 会改变dest里数据  可以使用以下方法
// $.extend({}, src, src1...)
// var objnew1 = $.extend({}, obj, obj1);
// console.log(objnew1);
// console.log(obj);
```

### 深拷贝

深拷贝: $.extend(true, dest, src, src)

原理: 将$.extend的第一个参数设置成true的时候就是深拷贝。过程: 先看属性名是否重复，不重复就把属性名和属性值拷贝进来，如果属性名重复, 有一个属性值不是对象的时候，就用后面的覆盖前面的，如果都是对象，就会对比子属性, 重复上述过程.

```javascript
var a = {
    name: 1,
    age:{
        n: 30,
        l: 18
    },
    height: 188,
    xl: 8
};

var b = {
    name: 2,
    age: {
        n: 31,
        look: 19
    }
}

var o = $.extend(true, {}, a, b);
console.log(o);
```





















