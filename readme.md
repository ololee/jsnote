### 0x01:常量

``` js
const Num=100;
```

### 0x02:变量

与Python一样是自动变量

``` js
var score=0.0;
```

### 0x03:命名规范

```
0x01:常量名 字母全部大写，可以有下划线
0x02:变量名 小写字母开头，单词首字母大写
```

### 0x04:注释

```
单行注释 //
多行注释or块注释 /**/
```

### 0x05:数据类型

```
0x01:数值类型
0x02:布尔类型
0x03:字符串类型
0x04:对象类型 var currentDay=new Date()
0x05:数组类型 var array=new Array(10);
```

### 0x06:数据类型字面量

|         数据         |       类型       |
| :------------------: | :--------------: |
|         1234         |       整数       |
|       3.14159        |      浮点数      |
|    “hello world”     |      字符串      |
|         true         |       bool       |
| {height:10,width:20} |       对象       |
|  [1,2,3,4,5,6,7,8]   |       数组       |
|         null         | 对象空(不存在的) |

### 0x07:数据类型转换

|          转换类型          |          方法           |
| :------------------------: | :---------------------: |
|      转换成字符串类型      |       toString()        |
| 转换成二\八\十六进制字符串 |    toString(2\8\16)     |
|         转换成数字         | parseInt(""),parseFloat |
|            bool            |     Boolean(value)      |
|           number           |      Number(value)      |
|           String           |      String(value)      |

### 0x08:运算符

| 一元运算 | 说明 |
| :------: | :--: |
|    -     | 取反 |
|    ++    | 自增 |
|    --    | 自减 |

| 二元运算 | 说明 |
| :------: | :--: |
|    +     |  加  |
|    -     |  减  |
|    *     |  乘  |
|    /     |  除  |
|    %     | 取余 |

| 算数赋值运算符 |     说明     |
| :------------: | :----------: |
| +=,-=,*=,/=,%= | 先算数再赋值 |

| 关系运算符 |    说明    |
| :--------: | :--------: |
|     ==     |    等于    |
| <,>,>=,<=  |            |
|    ===     |  严格等于  |
|    !==     | 严格不等于 |

| 逻辑运算符 | 说明 |
| :--------: | :--: |
|     &      |  与  |
|     \|     |  或  |
|     !      |  非  |
|     ^      | 异或 |
|     &&     |  且  |
|    \|\|    |  或  |

| 位运算符 |    说明    |
| :------: | :--------: |
|    ~     |    位反    |
|    &     |    位与    |
|    \|    |    位或    |
|    ^     |   位异或   |
|   \>>    |    右移    |
|   \>>>   | 无符号右移 |
|    <<    |    左移    |

| 其他运算符 |         说明         |
| :--------: | :------------------: |
|     ?:     | 三元运算符，比较返回 |
|     []     |      下标运算符      |
| instanceof |  对象类型判断运算符  |

### 0x09：函数

```js
function 函数名(参数列表)
{
    语句;
    [return 返回值;]
}
```

### 0x0a:嵌套函数

```js
function A()
{
    function B()
    {
    }
}
```

### 0x0b:返回函数

```js
function B()
{
    return 'b'
}
function C()
{
    return 'c'
}
function A(type)
{
    var returnfunc;
    switch(type)
    {
        case 'b':returnfunc=B;break;
        case 'c':returnfunc=C;break;
    }
    return returnfunc;
}
var a=A('b');
a();
```

### 0x0c:面向对象

```js
0x01:使用字面量创建对象
   var Person={
       name:'a',
       age:18,
       description:function()
       {
           var rs=this.name+"'s age is"+this.age;
           return rs;
       }
   }
   var p=Person;
   p.descrition();
0x02:使用Object.create()函数创建对象
var p=Object.create({
       name:'a',
       age:18,
       description:function()
       {
           var rs=this.name+"'s age is"+this.age;
           return rs;
       }
    });
或者
var p=Object.create(Person);
p.age=19;
p.description();
0x03:使用函数对象
function Student(name,age)
{
    this.name=name;
    this.age=age;
    this.description=function()
    {
          var rs=this.name+"'s age is"+this.age;
           return rs;
    }
}
var p1=new Student('olo',18);
var p2=new Student('lee',19);
p1.description()
p2.description()
```

### 0x0d:常用的js内部对象

```js
0x01:Object对象
0x02:String对象
function print(str)
{
    console.log(str);
}
var str=new String("ololee,o");
print(str.toString());
print(str.length);
print(str.toUpperCase());
print(str.charAt(2));
print(str.indexOf('o'));
print(str.indexOf('o',3));
print(str.lastIndexOf('o'));
print(str.substring(3,7));
print(str.split(','))
0x03:Math对象
function print(str)
{
    console.log(str);
}
print(Math.PI);
print(Math.SQRT2);
print(Math.random());
print(Math.min(4,5,90));
print(Math.max(55,17));
print(Math.pow(2,3));
print(Math.sqrt(9));
0x04:Date对象
function print(str)
{
    console.log(str);
}
var d=new Date();
print(d.toString());
d=new Date("2008 08 08");
print(d.toString());
print(d.getFullYear());/**/
print(d.getYear());/*当年减去1900*/
print(d.getMonth());//当月-1月
print(d.getDay());//当年的当天的星期几
```

### 0x0e:原型 prototype

```js
每一个javascript对象都是从原型继承而来的;
调用对象的prototype属性获得该原型对象；
function print(str)
{
    console.log(str);
}
function People(name,age) {
    this.name=name;
    this.age=age;
    this.description=function () {
        print(this.name+"'s age is "+this.age);
    }
}
People.prototype.stunum=function (num) {
    this.num=num;
    this.printStunum=function () {
        print(this.name+"'s stunum is "+this.num);
    }
}
var x=new People('ololee',18);
x.description();
x.stunum(100001);
x.printStunum();
在原函数上加了一个新的变量，再加上了一个新的函数
```
