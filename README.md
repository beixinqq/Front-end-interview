# Front-end-interview
`学会发散思维 分析总结！`
***
###HTML+CSS经典面试题
1. display:none和visibility:hidden的区别？
* CSS中 link 和@import 的区别是？
* position的absolute与fixed共同点与不同点
* 介绍一下CSS的盒子模型
* CSS 选择符有哪些？哪些属性可以继承？优先级算法如何计算？ CSS3新增伪类有那些？
* 列出display的值，说明他们的作用。position的值， relative和absolute分别是相对于谁进行定位的？
* CSS3有哪些新特性？
* 为什么要初始化CSS样式。
* 对BFC规范的理解
* 解释下 CSS sprites，以及你要如何在页面或网站中使用它。
* 说说你对语义化的理解？
* Doctype作用? 严格模式与混杂模式如何区分？它们有何意义?
* HTML与XHTML——二者有什么区别
* html常见兼容性问题？
* 解释下浮动和它的工作原理？清除浮动的技巧
```css
body, h1, h2, h3, h4, h5, h6, hr, p, blockquote, dl, dt, dd, ul, ol, li, pre, form, fieldset, legend, button, input, textarea, th, td { margin:0; padding:0; }
body, button, input, select, textarea { font:12px/1.5tahoma, arial, \5b8b\4f53; }
h1, h2, h3, h4, h5, h6{ font-size:100%; }
address, cite, dfn, em, var { font-style:normal; }
code, kbd, pre, samp { font-family:couriernew, courier, monospace; }
small{ font-size:12px; }
ul, ol { list-style:none; }
a { text-decoration:none; }
a:hover { text-decoration:underline; }
sup { vertical-align:text-top; }
sub{ vertical-align:text-bottom; }
legend { color:#000; }
fieldset, img { border:0; }
button, input, select, textarea { font-size:100%; }
table { border-collapse:collapse; border-spacing:0; } 
```
***

###javascript经典面试题
1. 请你谈谈Cookie的弊端
* 简单说一下浏览器本地存储是怎样的
* web storage和cookie的区别
* 组合/聚合复用原则
* “迪米特”法则
* 单一职责原则

###javascript变态题
```js
(function(){
    return typeof arguments;//"object"
})();
```
```js
var f = function g(){ return 23; };
typeof g();//报错
```
```js
(function(x){
    delete x;
    return x;//1
})(1);
```
```js
var y = 1, x = y = typeof x;
x;//"undefined"
```
```js
(function f(f){
    return typeof f();//"number"
})(function(){ return 1; });
```

```js
var foo = {
    bar: function() { return this.baz; },
    baz: 1
};

(function(){
    return typeof arguments[0]();//"undefined"
})(foo.bar);
```
```js
var foo = {
    bar: function(){ return this.baz; },
    baz: 1
}
typeof (f = foo.bar)();//"undefined"
```
```js
var foo = {
    bar: function(){ return this.baz; },
    baz: 1
}
typeof (f = foo.bar)();//"undefined"
```
```js
var f = (function f(){ return '1'; }, function g(){ return 2; })();
typeof f;//"number"
```
```js
var x = 1;
if (function f(){}) {
    x += typeof f;
}
x;//"1undefined"
```
```js
var x = [typeof x, typeof y][1];
typeof typeof x;//"string"
```
```js
(function(foo){
    return typeof foo.bar;//"undefined"
})({ foo: { bar: 1 } });
```
```js
(function f(){
    function f(){ return 1; }
    return f();//2
    function f(){ return 2; }
})();
```
```js
(function f(){
    function f(){ return 1; }
    return f();//2
    function f(){ return 2; }
})();
```
```js
function f(){ return f; }
new f() instanceof f;//false
```
```js
with (function(x, undefined){}) length;//2
```
```js
var x = 1;
var y = 0;
var z = 0;
function add(n){n=n+1;}
y = add(x);
function add(n){n=n+3;}
z = add(x);
```