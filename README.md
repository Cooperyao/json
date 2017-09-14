# json
## 9/14/2017
* stringify()和parse()区别
### parse()
#### parse用于从一个字符串中解析出json对象,如
var str = '{"name":"huangxiaojian","age":"23"}'
结果：
JSON.parse(str)

Object

age: "23"
name: "huangxiaojian"
__proto__: Object
注意：单引号写在{}外，每个属性名都必须用双引号，否则会抛出异常。

### stringify()
#### stringify()用于从一个对象解析出字符串，如

var a = {a:1,b:2}   <br>
结果：   <br>
JSON.stringify(a)

"{"a":1,"b":2}"

3、json.stringify语法实例讲解
语法： 
　　JSON.stringify(value [, replacer] [, space])    <br>
  
value：是必选字段。就是你输入的对象，比如数组，类等。    <br>
replacer：这个是可选的。它又分为2种方式，一种是数组，第二种是方法。    <br>
　　情况一：replacer为数组时，通过后面的实验可以知道，它是和第一个参数value有关系的。一般来说，系列化后的结果是通过键值对来进行表示的。所以，如果此时第二个参数的值在第一个存在，那么就以第二个参数的值做key，第一个参数的值为value进行表示，如果不存在，就忽略。   <br>

　　情况二：replacer为方法时，那很简单，就是说把系列化后的每一个对象（记住是每一个）传进方法里面进行处理。   <br> 

space：就是用什么来做分隔符的。    <br>
　　1）如果省略的话，那么显示出来的值就没有分隔符，直接输出来 。   <br>
　　2）如果是一个数字的话，那么它就定义缩进几个字符，当然如果大于10 ，则默认为10，因为最大值为10。   <br>
　　3）如果是一些转义字符，比如“\t”，表示回车，那么它每行一个回车。    <br>
　　4）如果仅仅是字符串，就在每行输出值的时候把这些字符串附加上去。当然，最大长度也是10个字符   <br>
