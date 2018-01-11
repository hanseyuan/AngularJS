### AngularJS 是一个 JavaScript 框架
AngularJS 是一个 JavaScript 框架。它是一个以 JavaScript 编写的库。

AngularJS 是以一个 JavaScript 文件形式发布的，可通过 script 标签添加到网页中：

    <script src="http://cdn.static.runoob.com/libs/angular.js/1.4.6/angular.min.js"></script>

### AngularJS 扩展了 HTML
AngularJS 通过 ng-directives 扩展了 HTML。

ng-app 指令定义一个 AngularJS 应用程序。

ng-model 指令把元素值（比如输入域的值）绑定到应用程序。

ng-bind 指令把应用程序数据绑定到 HTML 视图。

    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="utf-8">
    </head>
    <body>
        <div ng-app="">
             <p>名字 : <input type="text" ng-model="name"></p>
             <h1>Hello {{name}}</h1>
        </div>
        <script src="http://cdn.static.runoob.com/libs/angular.js/1.4.6/angular.min.js"></script>
    </body>
    </html>

实例讲解：

    1. 当网页加载完毕，AngularJS 自动开启。
    2. ng-app 指令告诉 AngularJS，<div>元素是 AngularJS 应用程序 的"所有者"。
    3. ng-model 指令把输入域的值绑定到应用程序变量 name。
    4. ng-bind 指令把应用程序变量 name 绑定到某个段落的 innerHTML。

AngularJS 使得开发现代的单一页面应用程序（SPAs：Single Page Applications）变得更加容易。

- AngularJS 把应用程序数据绑定到 HTML 元素。
- AngularJS 可以克隆和重复 HTML 元素。
- AngularJS 可以隐藏和显示 HTML 元素。
- AngularJS 可以在 HTML 元素"背后"添加代码。
- AngularJS 支持输入验证。



### AngularJS 表达式
AngularJS 表达式写在双大括号内：{{ expression }}。

AngularJS 表达式把数据绑定到 HTML，这与 ng-bind 指令有异曲同工之妙。

AngularJS 将在表达式书写的位置"输出"数据。

AngularJS 表达式 很像 JavaScript 表达式：它们可以包含文字、运算符和变量。

实例 {{ 5 + 5 }} 或 {{ firstName + " " + lastName }}


##### AngularJS 表达式 与 JavaScript 表达式
    类似于 JavaScript 表达式，AngularJS 表达式可以包含字母，操作符，变量。
    与 JavaScript 表达式不同，AngularJS 表达式可以写在 HTML 中。
    与 JavaScript 表达式不同，AngularJS 表达式不支持条件判断，循环及异常。
    与 JavaScript 表达式不同，AngularJS 表达式支持过滤器。

### AngularJS 应用
AngularJS 模块（Module） 定义了 AngularJS 应用。

AngularJS 控制器（Controller） 用于控制 AngularJS 应用。

ng-app指令定义了应用, ng-controller 定义了控制器。

### AngularJS 指令
AngularJS 通过被称为 指令 的新属性来扩展 HTML。

AngularJS 通过内置的指令来为应用添加功能。

AngularJS 允许你自定义指令。

    AngularJS 指令是扩展的 HTML 属性，带有前缀 ng-。
    
    ng-app 指令初始化一个 AngularJS 应用程序。
    
    ng-init 指令初始化应用程序数据。
    
    ng-model 指令把元素值（比如输入域的值）绑定到应用程序。
    
##### 数据绑定
AngularJS 中的数据绑定，同步了 AngularJS 表达式与 AngularJS 数据。

{{ firstName }} 是通过 ng-model="firstName" 进行同步。

    <div ng-app="myApp1">
        <h2>价格计算器</h2>
        数量: <input type="text" ng-model="count">
        单价: <input type="text" ng-model="price">
        <br>
        总价: {{count * price}}
    </div>
##### 重复 HTML 元素
ng-repeat 指令会重复一个 HTML 元素：
##### ng-app 指令
ng-app 指令定义了 AngularJS 应用程序的 根元素。

ng-app 指令在网页加载完毕时会自动引导（自动初始化）应用程序。

##### ng-init 指令
ng-init 指令为 AngularJS 应用程序定义了 初始值。

通常情况下，不使用 ng-init。您将使用一个控制器或模块来代替它。

稍后您将学习更多有关控制器和模块的知识。

#### ng-model 指令
ng-model 指令 绑定 HTML 元素 到应用程序数据。

ng-model 指令也可以：

     为应用程序数据提供类型验证（number、email、required）。
    为应用程序数据提供状态（invalid、dirty、touched、error）。
    为 HTML 元素提供 CSS 类。
    绑定 HTML 元素到 HTML 表单。
ng-repeat 指令
    
    ng-repeat 指令对于集合中（数组中）的每个项会 克隆一次 HTML 元素。 
    
### 创建自定义的指令
你可以使用 .directive 函数来添加自定义的指令。

要调用自定义指令，HTML 元素上需要添加自定义指令名。

使用驼峰法来命名一个指令， runoobDirective, 但在使用它时需要以 - 分割, runoob-directive:

        <div ng-app="myApp">
        <!--元素名-->
        <!--<runoob-directive></runoob-directive>-->
        <!--属性-->
        <!--<div runoob-directive></div>-->
        <!--类名-->
        <div class="runoob-directive"></div>
        <!--注释-->
        <!--directive:runoob-directive-->
    </div>
    <script>
        var app=angular.module("myApp",[]);
        app.directive("runoobDirective",function(){
            return{
                restrict : "C",
                template:"<h1>自定义指令</h1>"
            }

        })
    </script>
    
可以通过以下方式来调用指令：

 -  元素名
 -  属性
 -  类名
 -  注释

> 限制使用

你可以限制你的指令只能通过特定的方式来调用。

通过添加 restrict 属性,并设置值为 "A",来设置指令只能通过属性的方式来调用:

        restrict: " "
        E 作为元素名使用
        A 作为属性使用
        C 作为类名使用
        M 作为注释使用
    restrict 默认值为 EA, 即可以通过元素名和属性名来调用指令。

### AngularJS Scope(作用域)
