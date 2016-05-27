## 初级Javascript：

#### 1.JavaScript是一门什么样的语言，它有哪些特点？

**没有标准答案。**   

我的答案：   
JavaScript是一门强大的编程语言，是一种专为与网页交互而设计的脚本语言，是一种动态类型、弱类型、基于原型的语言。   

特点：   

1. 脚本语言。JavaScript是一种解释型的脚本语言,C、C++等语言先编译后执行,而JavaScript是在程序的运行过程中逐行进行解释。   
1. 基于对象。JavaScript是一种基于对象的脚本语言,它不仅可以创建对象,也能使用现有的对象。   
1. 简单。JavaScript语言中采用的是弱类型的变量类型,对使用的数据类型未做出严格的要求,是基于Java基本语句和控制的脚本语言,其设计简单紧凑。   
1. 动态性。JavaScript是一种采用事件驱动的脚本语言,它不需要经过Web服务器就可以对用户的输入做出响应。在访问一个网页时,鼠标在网页中进行鼠标点击或上下移、窗口移动等操作JavaScript都可直接对这些事件给出相应的响应。   
1. 跨平台性。JavaScript脚本语言不依赖于操作系统,仅需要浏览器的支持。因此一个JavaScript脚本在编写后可以带到任意机器上使用,前提上机器上的浏览器支 持JavaScript脚本语言,目前JavaScript已被大多数的浏览器所支持。

#### 2.JavaScript的数据类型都有什么？

- 基本数据类型：Number、String、Boolean、Null、Undefined   
- 复杂数据类型：Object（Function、Array、Date、RegExp）


**如何判断某变量是否为数组数据类型？**

    if (typeof Array.isArray === "undefined"){
    	Array.isArray = function(arg){
    		return Object.prototype.toString.call(arg)==="[object Array]";
    	}
    }


#### 3.已知ID的Input输入框，希望获取这个输入框的输入值，怎么做？(不使用第三方框架)

    document.getElementById(ID).value;

#### 4.希望获取到页面中所有的checkbox怎么做？(不使用第三方框架)

    var inputs = document.getElementsByTagName("input"),
    	arr = [],
		len = inputs.length;
    while (len--){
    	if(inputs[len].type == "checkbox"){
    		arr.push(inputs[i]);
    	}
    }

#### 5.设置一个已知ID的DIV的html内容为xxxx，字体颜色设置为黑色(不使用第三方框架)

	var oDiv = document.getElementById(ID);
    oDiv.innerHTML = "xxxx";
    oDiv.getElementById(ID).style.color = "black";

#### 6.当一个DOM节点被点击时候，我们希望能够执行一个函数，应该怎么做？

先获取到这个DOM节点，然后绑定onclick事件。比如`myDOM.onclick = fn`或者`myDOM.addEventListener("click",fn);`   

或者直接在HTML中绑定`<div onclick = "fn()"></div>`

#### 7.什么是Ajax和JSON，它们的优缺点。

Ajax是异步JavaScript和XML，用于在Web页面中实现异步数据交互。

优点：

- 可以使得页面不重载全部内容的情况下加载局部内容，降低数据传输量
- 避免用户不断刷新或者跳转页面，提高用户体验   

缺点：

- 对搜索引擎不友好
- 要实现ajax下的前后退功能成本较大
- 可能造成请求数的增加
- 跨域问题限制   

JSON是一种轻量级的数据交换格式，ECMA的一个子集

优点：轻量级、易于人的阅读和编写，便于机器（JavaScript）解析，支持复合数据类型（数组、对象、字符串、数字）


#### 8.看下列代码输出为何？解释原因。

    var a;
    alert(typeof a); //undefined
    alert(b); //报错

变量a是被声明的，只是没有赋值，所以值为undefined。而b未被声明，所以不存在。


####  9.看下列代码,输出什么？解释原因。

    var a = null;
    alert(typeof a); //object

null是一个空指针对象，所以类型是object。

#### 10.看下列代码,输出什么？解释原因。

    var undefined;
    undefined == null; //true
    1 == true; //true
    2 == true; //false
    0 == false; //true
    0 == ''; // true
    NaN == NaN; //false
    [] == false; //true
    [] == ![]; //true

- undefined与null在if语句中会被自动转为false，相等运算符直接报告两者相等。（如果是全等的话结果为false）
- 数字和布尔值进行比较会把布尔值变为数字，true为1，false为0。
- 0为假即false，空值或者空格也为false。
- NaN和任何值都不相等。
- []被当作数组处理，空数组转换为0，所以等于false。
- ![]想做将数组转换为布尔值的运算，[]为一个数组对象，所以![]为false。


**看下面的代码，输出什么，foo的值为什么？**

    var foo = "11"+2-"1";
    console.log(foo); //111

 先做"11"+2运算，当一个为字符串一个为数字时，将数字转换为字符串，所以字符串拼接为"112"。当两个数据都是字符串时，+以外的运算会先把字符串转换为数字，即112-1=111,foo类型为Number。如果是+运算，则为"112"+"1"="1121"，foo类型为String。

####  11.看代码给答案。

    var a = new Object();
    a.value = 1;
    b = a;
    b.value = 2;
    alert(a.value); //2

a,b都指向同一个对象，所以b修改了value值，a的value值也变了。

#### 12.已知数组var stringArray = ["This", "is", "Baidu", "Campus"]，Alert出"This is Baidu Campus"。

stringArray.join(" ");

**已知有字符串foo=“get-element-by-id”,写一个function将其转化成驼峰表示法“getElementById”。**

    var fooArr = foo.split("-");
    var newFoo = fooArr[0];
    for(var i=1;i<fooArr.length;i++){
    	newFoo += fooArr[i].charAt(0).toUpperCase()+fooArr[i].slice(1);
    }
    return newFoo;

#### 13.var numberArray = [3,6,2,4,1,5];

1. 实现对该数组的倒排，输出[5,1,4,2,6,3]   

    `numberArray.reverse();`

1. 实现对该数组的降序排列，输出[6,5,4,3,2,1]

    ```
	numberArray.sort(function(a,b){
    	return b-a;
    });
	```

#### 14.输出今天的日期，以YYYY-MM-DD的方式，比如今天是2014年9月26日，则输出2014-09-26

    var date = new Date();
    var year = date.getFullYear();
    var month = date.getMonth()+1;
    var nowDate = date.getDate();
    if(month<10){month = "0" + month;}
    if(nowDate<10){nowDate = "0" + nowDate;}
    var today = year + "-" + month + "-" + nowDate;

#### 15.将字符串“&lt;tr&gt;&lt;td&gt;{$id}&lt;/td&gt;&lt;td&gt;{$name}&lt;/td&gt;&lt;/tr&gt;”中的{$id}替换成10，{$name}替换成Tony。（使用正则表达式）

    var str = "<tr><td>{$id}</td><td>{$name}</td></tr>";
    str.replace(/\{\$id\}/,"10").replace(/\{\$name\}/,"Tony");

#### 16.为了保证页面输出安全，我们经常需要对一些特殊的字符进行转义，请写一个函数escapeHtml，将<, >, &, \进行转义

    function escapeHTML(str){
    	return str.replace(/[<>&"]/g,function(match){
    		switch(match){
    			case "<":
    			return "\<";
    			case ">":
    			return "\>";
    			case "&":
    			return "\&";
    			case "\"":
    			return "\"";
    		}
    	});
    }

#### 17.foo = foo||bar ，这行代码是什么意思？为什么要这样写？

如果foo不为假则使用原来的值，没有值则把bar的值付给foo。

#### 18.看下列代码，将会输出什么?(变量声明提升)

    var foo = 1;
    function(){
    	console.log(foo); //undefined
    	var foo = 2;
    	console.log(foo); //2
    }

函数声明和变量声明会被隐式地提升到当前作用域的顶部，但是不会提升赋值部分。相当于：

    var foo = 1;
    function(){
		var foo;
    	console.log(foo); //undefined
    	foo = 2;
    	console.log(foo); //2
    }

#### 19.用js实现随机选取10–100之间的10个数字，存入一个数组，并排序。

    var arr = [];
    for(var i=0;i<10;i++){
    	arr.push(Math.random()*0.9*100+10);
    }
	arr.sort(function(a,b){return a-b;});

#### 20.把两个数组合并，并删除第二个元素。

    var arr1 = [1,2,3];
    var arr2 = ["a","b","c"];
    var newArr = arr1.contant(arr2);
    newArr.splice(1,1);

#### 21.怎样添加、移除、移动、复制、创建和查找节点

- appendChild() //添加
- reomveChild() //移除
- insertBefore() //移动
- cloneNode() //复制
- createElement();createTextNode();createDocumentFragment //复制
- getElementById();getElementsByTagName();getElementsByClassName();getElementsByName() //查找

#### 22.有这样一个URL：`http://item.taobao.com/item.htm?a=1&b=2&c=&d=xxx&e`，请写一段JS程序提取URL中的各个GET参数(参数名和参数个数不确定)，将其按key-value形式返回到一个json结构中，如{a:’1′, b:’2′, c:”, d:’xxx’, e:undefined}。

    var url = "http://item.taobao.com/item.htm?a=1&b=2&c=&d=xxx&e";
    var gets = url.split("?")[1];
    var getsArr = gets.split("&");
    var obj = {};
    for(var i=0;i<getsArr.length;i++){
    	obj[getsArr[i].split("=")[0]] = getsArr[i].split("=")[1];
    }
    return obj;

#### 23.正则表达式构造函数var reg=new RegExp(“xxx”)与正则表达字面量var reg=//有什么不同？匹配邮箱的正则表达式？

当使用RegExp()构造函数的时候，不仅需要转义引号（即\"表示"），并且还需要双反斜杠（即\\表示一个\）。   

    /^([A-Za-z0-9-_])+@([A-Za-z0-9]+.)+([a-z])+$/

#### 24.看下面代码，给出输出结果。

    for(var i=1;i<=3;i++){
      setTimeout(function(){
      console.log(i); //4 //4 //4
      },0);  
    };

Javascript事件处理器在线程空闲之前不会运行。

**如何让上述代码输出1 2 3？**

    for(var i=1;i<=3;i++){
      setTimeout((function(i){
      console.log(i);
      })(i),0);  //立即执行函数
    };

#### 25.写一个function，清除字符串前后的空格。（兼容所有浏览器）

    if(!String.prototype.trim){
    	String.prototype.trim = function(){
    		return this.replace(/^\s+/,"").replace(/\s+$/,"");
    	}
    }

#### 26.Javascript中callee和caller的作用？

**如果一对兔子每月生一对兔子；一对新生兔，从第三个月起就开始生兔子；假定每对兔子都是一雌一雄，试问一对兔子，第n个月能繁殖成多少对兔子？（使用callee完成）**

    var result = [];
    function fn(n){
    	if(n==1){
    		return 1;
    	}else if(n==2){
    		return 1;
    	}else{
    		result[n] = arguments.callee(n-2)+arguments.callee(n-1);
    		return result[n];
    	}
    }