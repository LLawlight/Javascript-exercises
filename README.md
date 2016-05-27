# 各大互联网公司JavaScript笔试面试题

原文出处：[http://www.cnblogs.com/coco1s/p/4029708.html](http://www.cnblogs.com/coco1s/p/4029708.html)   
部分略有错误，稍作修改。

## 初级Javascript：[(参考答案)](https://github.com/Clark-Zhao/Javascript-exercises/blob/master/%E5%88%9D%E7%BA%A7JavaScript%E7%AD%94%E6%A1%88.md)

#### 1.JavaScript是一门什么样的语言，它有哪些特点？

#### 2.JavaScript的数据类型都有什么？

**如何判断某变量是否为数组数据类型？**

#### 3.已知ID的Input输入框，希望获取这个输入框的输入值，怎么做？(不使用第三方框架)

#### 4.希望获取到页面中所有的checkbox怎么做？(不使用第三方框架)

#### 5.设置一个已知ID的DIV的html内容为xxxx，字体颜色设置为黑色(不使用第三方框架)


#### 6.当一个DOM节点被点击时候，我们希望能够执行一个函数，应该怎么做？

#### 7.什么是Ajax和JSON，它们的优缺点。

#### 8.看下列代码输出为何？解释原因。

    var a;
    alert(typeof a);
    alert(b);

####  9.看下列代码,输出什么？解释原因。

    var a = null;
    alert(typeof a);

#### 10.看下列代码,输出什么？解释原因。

    var undefined;
    undefined == null;
    1 == true;
    2 == true;
    0 == false;
    0 == '';
    NaN == NaN;
    [] == false;
    [] == ![];

**看下面的代码，输出什么，foo的值为什么？**

    var foo = "11"+2-"1";
    console.log(foo);

####  11.看代码给答案。

    var a = new Object();
    a.value = 1;
    b = a;
    b.value = 2;
    alert(a.value);

#### 12.已知数组var stringArray = [“This”, “is”, “Baidu”, “Campus”]，Alert出”This is Baidu Campus”。

**已知有字符串foo=”get-element-by-id”,写一个function将其转化成驼峰表示法”getElementById”。**

#### 13.var numberArray = [3,6,2,4,1,5];

1. 实现对该数组的倒排，输出[5,1,4,2,6,3]   
1. 实现对该数组的降序排列，输出[6,5,4,3,2,1]

#### 14.输出今天的日期，以YYYY-MM-DD的方式，比如今天是2014年9月26日，则输出2014-09-26

#### 15.将字符串“&lt;tr&gt;&lt;td&gt;{$id}&lt;/td&gt;&lt;td&gt;{$name}&lt;/td&gt;&lt;/tr&gt;”中的{$id}替换成10，{$name}替换成Tony。（使用正则表达式）

#### 16.为了保证页面输出安全，我们经常需要对一些特殊的字符进行转义，请写一个函数escapeHtml，将<, >, &, \进行转义

#### 17.foo = foo||bar ，这行代码是什么意思？为什么要这样写？

#### 18.看下列代码，将会输出什么?(变量声明提升)

    var foo = 1;
    function(){
    	console.log(foo);
    	var foo = 2;
    	console.log(foo);
    }

#### 19.用js实现随机选取10–100之间的10个数字，存入一个数组，并排序。

#### 20.把两个数组合并，并删除第二个元素。

#### 21.怎样添加、移除、移动、复制、创建和查找节点

#### 22.有这样一个URL：`http://item.taobao.com/item.htm?a=1&b=2&c=&d=xxx&e`，请写一段JS程序提取URL中的各个GET参数(参数名和参数个数不确定)，将其按key-value形式返回到一个json结构中，如{a:’1′, b:’2′, c:”, d:’xxx’, e:undefined}。

#### 23.正则表达式构造函数var reg=new RegExp(“xxx”)与正则表达字面量var reg=//有什么不同？匹配邮箱的正则表达式？

#### 24.看下面代码，给出输出结果。

    for(var i=1;i<=3;i++){
      setTimeout(function(){
      console.log(i);
      },0);  
    };

**如何让上述代码输出1 2 3？**

#### 25.写一个function，清除字符串前后的空格。（兼容所有浏览器）

#### 26.Javascript中callee和caller的作用？

**如果一对兔子每月生一对兔子；一对新生兔，从第三个月起就开始生兔子；假定每对兔子都是一雌一雄，试问一对兔子，第n个月能繁殖成多少对兔子？（使用callee完成）**