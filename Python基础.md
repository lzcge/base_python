﻿﻿# *python基础知识*

```apl
@File    ：python基础知识
@Author  ：lizhencai
@Date    ：2022年11月
@Description :自学python基础知识笔记记录，内容来源@《疯狂Python讲义》/ 李刚编著.-北京：电子工业出版社，2019.1
```



# 1、python简介

## 1.1、python的特点

- python是一种面向对象、解释型、弱类型的脚本语言。

 - python具有跨平台的特征，只要为平台提供相应的python解释器，python就可以在该平台上运行。
 - python程序相对java、c++等编译型语言运行效率要慢。
 - 源代码加密困难，python直接运行源程序，对源代码加密比较困难。

## 1.2、python程序注意事项

 - 编写python程序不要使用写字板，word等文档编辑器。他们是有格式的编辑器，会包含一些隐藏格式字符。
 - Windows不区分大小写，windows上的python代码程序路径可以不区分大小写，但是Mac OS和Linux中区分大小写，因此程序中要注意大小写。





# 2、变量和简单类型

## 2.1、变量

python是一门弱类型语言，弱类型语言包含两方面含义：

①所有变量无需声明即可使用，对从未使用过的变量赋值就是声明了该变量。

②变量的数据类型可以随时改变，同一个变量可以一会是数值型，一会是字符串型。

## 2.2、单行注释和多行注释

> **单行注释：**使用#号
>
> **多行注释：**三个单引号或者三个双引号括起来

## 2.3、查看变量类型

使用type()函数查看变量类型

```python
a = 5
type(a)
<class 'int'>

a = 'hello'
type(a)
<class 'str'>
```



## 2.4、print输出函数

1、print()默认以空格隔开多个变量，如果希望更改默认分隔符，可通过sep参数进行设置。

```python
user_name = 'lsi'
user_age = 8
print('名字：',user_name,'年龄：',user_age)
名字： lsi 年龄： 8

print('名字：',user_name,'年龄：',user_age,sep='|')
名字：|lsi|年龄：|8
```

2、默认情况下，print()函数输出后总会换行，因为print()函数的end参数默认为'\n'，如果希望不换行，则重设end参数即可。

```python
print(40,end="")
```



## 2.5、变量命名规则

1、可以由字母、数字、下划线组成，其中不能数字开头

2、不能是python的关键字，但可以包含关键字

3、不能包含空格



## 2.6、※字符串

### 2.6.1、字符串和转义字符

python中的字符串要求使用单引号或者双引号括起来。本身无任何区别，但如果字符串内容本身包含了单引号或者双引号，需要进行如下特殊处理：

①使用不同的引号将字符括起来。

②使用转义字符'\'对引号进行转义。



### 2.6.2、拼接字符串

①两个字符串紧挨着写，就会自动拼接。

```python
s1 = "hello," 'lisi'
print(s1)
hello,lisi
```

②使用加号"+"进行拼接。

```python
s1 = "hello," 'lisi'
print(s1)
hello,lisi
s2 = 'hhhh'
print(s1+s2)
hello,lisihhhh
```



### 2.6.3、字符串转换

str()和repr()函数都可以将数值转换成字符串，区别是：str是python内置函数(和int、float一样)，repr只是一个函数



### 2.6.4、字符串输入

input()函数用于向用户生成一条提示，然后获取用户输入内容。**返回字符串**：将用户输入内容转换成字符串。



### 2.6.5、原始字符串

原始字符串不会把反斜线'\'当成转义字符，使字符串原样输出，原始字符串以'r'开头。

```python
s3 = r'G:\public\sodes'
print(s3)
G:\public\sodes
```

### 2.6.6、字符串格式化

python使用‘%’对各种类型的数据进行格式化输出。

常用转换说明符：

| 转换说明符 | 说明                                 |
| :--------- | :----------------------------------- |
| d,i        | 转换带符号的十进制形式的整数         |
| f,F        | 转换为十进制形式的浮点数             |
| r          | 使用repr()将变量或表达式转换为字符串 |
| s          | 使用str()将变量或表达式转换为字符串  |

- 可以使用上面的说明符指定转换后的最小宽度。

- -：指左对齐
- +：数值总要带符号（整数带+，负数带-）
- 0：表示不补充空格，而是补充0

```python
num = -28
print('num is: %d' % num)
num is: -28

print('num is: %6d' % num)
#指定最小宽度为6，自动在前面补充三个空格
num is:    -28
    
num2 = 30
print('num2 is:%06d' % num2)
num2 is:000030   
print('num2 is:%+06d' % num2)
num2 is:+00030 
print('num2 is:%-06d' % num2)
num2 is:30 
    
my_value = 3.001415926535
print('my value is: %8.3f' % my_value)
my value is:    3.001
print('my value is: %.4f' % my_value)
my value is: 3.0014
```



### 2.6.7、序列相关方法

①python字符串直接使用方括号[]中的索引获取对应字符，第一个字符索引为0；也可从后面开始计算索引，最后一个也可以是-1。

②python字符串支持**in**运算符判断是否包含某个子串。

③**len()**函数获取字符串长度。



### 2.6.8、大小写相关方法

①**title()：**将每个单词的首字母转换为大写。

②**lower()：**将整个字符串转换为小写。

③**upper()：**将整个字符串转换为大写。



### 2.6.9、删除空白

①**strip()：**删除字符串中的前后空格。

②**lstrip()：**删除字符串左边的空格。

③**rstrip()：**删除字符串右边的空格。

<font color='red'>※注意：python中的str是不可变的，这三个方法是返回字符串的副本，并没有改变字符串本身</font>

```python
s = ' this is a puppy '

print(s.lstrip())
this is a puppy 

print(s.rstrip())
 this is a puppy

print(s.strip())
this is a puppy

print(s)
 this is a puppy 
```



### 2.6.10、查找、替换相关方法

①**startwith()：**判断字符串是否以指定子串开头。

②**endwith()：**判断字符串是否以指定子串结尾。

③**find()：**查找指定子串在字符串中出现的位置，<font color='red'>如果没有找到，返回-1</font>。

④**index()：**查找指定子串在字符串中出现的位置，<font color='red'>如果没有找到，引发ValueError错误</font>。

⑤**replace()：**使用指定字符串替换字符串中的目标子串。

⑥**translate()：**使用指定的翻译映射表对字符串执行替换。



### 2.6.11、分割、连接方法

①**split()：**将字符串按指定分割符分割成多个短语。

②**join()：**将多个短语连接成字符串。<font color='red'>必须是多个短语，如果只有一个短语则原样输出</font>。

```python
s = 'lisi is a good boy'
print(s.split(' '))
['lisi', 'is', 'a', 'good', 'boy']

mylist = s.split(' ')
print('/'.join(mylist))
lisi/is/a/good/boy

mylist = ['hhh']
print('/'.join(mylist))
hhh
```



## 2.7、运算符



### 2.7.1、算术运算符

①**“+”**：加

> 除用于加法运算外，还可以作为字符串的连接运算符

②**“-”**：减

> 除用于减法运算外，还可以作为求负运算符

③**“*”**：乘

> 除用于乘法运算外，还可以作为字符串连接运算符，表示N个字符串连接起来

```python
s2 = 'hello,'
print(s2*5)
hello,hello,hello,hello,hello,
```

④**“/或者//”**：除

> - **"/"**普通除法，**结果与数学计算相同，除不尽产生小数**
> - **"//"**整除，结果保留整数

⑤**“%”**：求余运算符

> **支持对浮点数求余**。求余结果不一定总是整数

⑥******：乘方运算符，使用它也可以进行开放运算

```python
print('5的二次方：', 5**2)
5的二次方： 25
print('5的三次方：', 5**3)
5的三次方： 125
print('4开平方：', 4**0.5)
4开平方： 2.0
print('27的开三次方：', 27**(1/3))
27的开三次方： 3.0
```



### 2.7.2、索引运算符

索引运算符就是方括号，在括号中可以用单个索引值，也可以使用索引范围，还可指定步长

```python
a = 'dfdfdffgg'
#获取索引2到8的子串，步长3
print(a[2:8:3])
df
```



### 2.7.3、比较运算符

| >      | 大于                                                 |
| ------ | ---------------------------------------------------- |
| >=     |                                                      |
| <      |                                                      |
| <=     |                                                      |
| ==     | 比较值是否相等                                       |
| !=     |                                                      |
| is     | 比较两个对象的所指向的地址值是否相等                 |
| is not | 判断两个变量所引用的对象是否不相等，比较的内存地址值 |

<font color='red'>※注意：==与is的区别</font>。



### 2.7.4、三目运算符

格式：

```python
True_statement if expression else False_statement
```

```python
a = 5
b = 3
st = "a>b" if a>b else "a<b"
print(st)
a>b
```





# 3、列表、元组和字典

## 3.1、列表和元组异同比较

- **相同点**

  列表和元组都按顺序保存元素，列表和元组都可通过索引访问元素。

- **不同点：**

  **①元组不可修改，列表可修改**

  ②常见列表用方括号，创建元组用圆括号



## 3.2、列表和元组的通用方法

1. **通过索引使用元素**
2. **子序列（切片）**

```python
[start:end:step]
```

```python
假设存在列表或者元组players：
1、players[0:3]   #0~3不包含3，左闭右开
2、players[1:4]   #1~4不包含4，左闭右开
3、players[:4]    #从列表开头开始
4、players[2:]    #到列表结尾
5、players[-3:]   #输出最后三个

b_tuple = (1,2,3,4,5,6,7,8,9)
print(b_tuple[2:8:2])  #以步长为2取索引2到8之间的数，不包含8。
(3, 5, 7)  
```



3. **加法**

拼接成一个更大的列表或元组。但是列表只能和列表相加，元组只能和元组相加



4. **乘法**

把它们包含的元素重复N次

```python
c_list = [1,2]
print(c_list*3)
[1, 2, 1, 2, 1, 2]
```



5. **in和not in运算**

判断列表或元组是否包含某元素



6. **长度、最大值和最小值**

len()、max()、min()

使用max()和min()函数时，要求列表或者元组必须是相同类型且可以比较大小的。如果都是字符串，依次比较每个字符的ASCII码值，先比较第一个字符，若相同就比较第二个字符，依次类推。（26个小写字母的ASCII码值为97~122。26个大写字母的ASCII码为65~90）



7. **序列封包和序列解包**

①程序把多个值赋给一个变量时，python会自动将多个值封装成元组。称为序列封包

```python
xyz = 1,2,3
print(xyz)
(1, 2, 3)
```

②程序允许将序列（元组或者列表）直接赋值给多个变量，序列中的各个元素依次赋值给每个变量，要求序列元素个数与变量个数相同。称为序列解包

```python
x,y,z = xyz
print(x,y,z)
1 2 3
```

**通过序列封包和序列解包可实现多变量赋值**

```python
x,y,z = 4,5,6
#先封包，再解包过程
print(x,y,z)
4 5 6

```



## 3.3、使用列表

### 3.3.1、列表创建

- []
- list()：可用于将元组、区间（range）对象转换为列表。与之对应也可使用tuple()函数将列表、区间（range）转换为元组

```python
#创建1~10的偶数列表，并求和
#range(2,11,2) 表示2~11，已2的阶梯向后创建
ranges = list(range(2,11,2))
print(ranges)
[2, 4, 6, 8, 10]
```



### 3.3.2、增加列表元素

- append()方法：把参数追加到列表后面，<font color='red'>如果追加参数为列表、元组时，会嵌套追加</font>
- extend()方法：把参数追加到列表后面，<font color='red'>如果追加参数为列表、元组时，不会嵌套追加，只追加列表中的元素，extend 接受的参数总是一个序列（不能只是一个数）</font>
- insert()方法：在列表中某个索引位置追加元素

```python
a_list = [1,2,3]
b_list = ['a','b','c']
a_list.append(4)
print(a_list)
[1, 2, 3, 4]

#append()嵌套追加
a_list = [1,2,3]
b_list = ['a','b','c']
a_list.append(b_list)
print(a_list)
[1, 2, 3, ['a', 'b', 'c']]

#extend()非嵌套追加，只追加元素
a_list = [1,2,3]
b_list = ['a','b','c']
a_list.extend(b_list)
print(a_list)
[1, 2, 3, 'a', 'b', 'c']

#insert()中间追加
a_list = [1,2,3]
a_list.insert(1,4)
print(a_list)
[1, 4, 2, 3]
```



### 3.3.3、删除列表元素

- del：根据索引删除，可删除一个，可删除一段。eg：del a_list[2]、del a_list[1:3]、del a_list[1:5:2]

- remove()：删除列表中第一个找到的元素。eg：c_list.remove(30)

- clear()：清空列表所有元素。eg：d_list.clear()



### 3.3.4、修改列表元素

直接对列表元素重新赋值



### 3.3.5、列表其它常用方法

- count()：统计列表中某个元素出现的次数
- index()：某个元素在列表中首次出现的位置
- pop()：实现元素出栈功能
- reverse()：将列表元素反向存放
- sort()：列表元素排序



### 3.3.6、遍历列表

```python
# for循环遍历遍历列表
magicians=['alice','david','carolina']
for magician in magicians:
    print(magician)
    
# range（1,10）表示1~10不包含10，左闭右开
for ran in range(1,10):
    print(ran)

#可获取列表list的元素序号  
for i, val in enumerate(list):
    print ("序号：%s   值：%s" % (i + 1, val))
```

<font color='red'>注意：如果遍历列表过程中需要删除列表，则通过遍历拷贝的List，操作原始的List的方式，不能遍历原始列表过程中对原始列表元素进行删除</font>





### 3.3.7、列表复制



**①直接赋值：其实就是对象的引用（别名）**

b = a: 赋值引用，a 和 b 都指向同一个对象。

**②浅拷贝(copy())：拷贝父对象，不会拷贝对象的内部的子对象**

b = a.copy(): 浅拷贝, a 和 b 是一个独立的对象，但他们的子对象还是指向统一对象（是引用）。

**③深拷贝(copy.deepcopy())： copy 模块的 deepcopy 方法，完全拷贝了父对象及其子对象**

b = copy.deepcopy(a): 深度拷贝, a 和 b 完全拷贝了父对象及其子对象，两者是完全独立的。



### 3.3.8、列表生成式

```python
>>> [x * x for x in range(1, 11)]
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

>>> [x * x for x in range(1, 11) if x % 2 == 0]
[4, 16, 36, 64, 100]

>>> [m + n for m in 'ABC' for n in 'XYZ']
['AX', 'AY', 'AZ', 'BX', 'BY', 'BZ', 'CX', 'CY', 'CZ']
```

if  else

**if在for循环后面时 跟在`for`后面的`if`是一个筛选条件，不能带`else`**

```python
>>> [x for x in range(1, 11) if x % 2 == 0]
[2, 4, 6, 8, 10]
```

**if在for前面时，需要带上else。`for`前面的表达式`x if x % 2 == 0 else -x`才能根据`x`计算出确定的结果**

```python
>>> [x if x % 2 == 0 else -x for x in range(1, 11)]
[-1, 2, -3, 4, -5, 6, -7, 8, -9, 10]
```





## 3.4、使用字典

### 3.4.1、创建字典

- {key:value}
- dict()

```python
#字典定义
user = {
    'name':'zhangsan',
    'sex':'男',
    'age':20,
    'wight':130
}
dict2 = dict()

dict3 = dict(username='lisan',age=30)
print(dict3)
{'username': 'lisan', 'age': 30}
```



### 3.4.2、字典值获取

- user[key]获取

- 通过get()获取

  **区别：当指定的键不存在时通过user[key]获取会报错，通过get()方法获取可以指定键不存在时的返回值进而避免报错**





### 3.4.3、常用方法

- clear()：清空字典中的所有key-value对
- get()：根据key来获取value
- update()：可使用一个字典所包含的key-value对来更新已有的字典
- items()：获取字典中的所有key-value对
- keys()：获取字典中的所有key
- values()：获取字典中的所有value
- pop()：获取指定key对应的value，并删除这个key-value对
- popitem()：随机弹出字典中的一个key-value对
- fromkeys()：使用给定的多个key创建字典，这些key对应的value默认为None

```python
a_dict = dict.fromkeys([1,2])
print(a_dict)
{1: None, 2: None}
```



### 3.4.4、字典遍历

```python
#遍历所有键值对
for key, value in user.items():
    print(key+" : "+value)
#遍历所有键
for key in user.keys():
    print(key)
#遍历所有值
for value in user.values():
    print(value)
```



## 3.5、集合（set）

集合的定义：用{}

```java
languages = {'python','c','java'}
```



## 3.6、集合、列表、元组、字典的区别

> **定义：** 列表[]，元组()，字典{'key':'value'}，集合{}
> **特性：** <font color='red'>列表可修改可重复，元组不可修改可重复，集合可修改不可重复</font>







# 4、流程控制

## 4.1、if判断

```java
age = 12
if age<14:
    print("your admission cost is $0")
elif age<18:
    print("your admission cost is $25")
else:
    print("your admission cost is $40")
```
 **判断一个元素是否包含在一个列表中**

```java
names = ['a','b','c']
name  = 'a'
if name in names:
    print("in")
if name not in names:
    print("not in")
```



## 4.2、while

```python
while i<10:
    print(i)
    i += 1
```



## 4.3、for

```python
# for循环遍历遍历列表
magicians=['alice','david','carolina']
for magician in magicians:
    print(magician)
    
# range（1,10）表示1~10不包含10，左闭右开
for ran in range(1,10):
    print(ran)

#可获取列表list的元素序号  
for i, val in enumerate(list):
    print ("序号：%s   值：%s" % (i + 1, val))
```



## 4.4、break、continue、return

①break：结束循环

②continue：跳过本次循环，执行下一次循环

③return：结束该函数或者方法，直接返回，循环也随之结束






# 5、函数
## 5.1、函数基础

①函数声明使用def、return返回的值既可以是变量也可以是表达式

```python
def my_max(x,y):
    return x if x>y else y
```

②※可返回多个值，返回的多个值自动封装成元组





## 5.2、函数的参数



### 5.2.1、形参和实参

- 形参：函数体中的形式参数
- 实参：实际传入函数的参数



### 5.2.2、位置参数

**按照形参位置传入的参数**,传入参数时，按照函数定义的指定的顺序传入参数值

```python
def girth(width,height):
    print('width:',width)
    print('height:',height)
    return 2*(width+height)

if __name__ == '__main__':
    print(girth(2, 3))

width: 2
height: 3
10
```



### 5.2.3、关键字参数

**根据参数名来传入参数，无需遵守形参顺序**

<font color='red'>注：如果调用函数时混合使用位置参数和关键字参数，关键字参数必须放在位置参数后面</font>

```python
def girth(width,height):
    print('width:',width)
    print('height:',height)
    return 2*(width+height)

if __name__ == '__main__':
    print(girth(2, height=3))
```



### 5.2.4、参数默认值

定义函数时，为参数指定默认值，调用时可省略传入该参数

```python
def power(x, n=2):
    s = 1
    while n > 0:
        n = n - 1
        s = s * x
    return s
    
power(5)
```

如上：n=2就是默认参数

<font color='red'>注：必选参数在前，默认参数必须在参数列表最后</font>



### 5.2.5、※可变参数

<font color='red'>Python 利用*args **kwargs 灵活传递参数</font>

####  5.2.5.1、一个*号

**收集可变长度的普通参数，多个参数值当元组传入**

```python
def calc(*numbers):
    sum = 0
    for n in numbers:
        sum = sum + n * n
    return sum

calc(1, 2, 3)
```

如上：*numbers为可变参数，<font color='red'>①可接收0和任意个参数，②可位于任意位置，当后面有普通位置参数时，因为可变参数可接收个数不同的参数值，所以后面的参数在传参时必须使用关键字参数形式进行传参。③一个函数最多一个该参数</font>

<font color='red'>注：参数`numbers`接收到的是一个tuple</font>，如果已经有一个list或者tuple，要调用一个可变参数怎么办？，可使用如下方法

```python
>>> nums = [1, 2, 3]
>>> calc(*nums)
```

`*nums`表示把`nums`这个list的所有元素作为可变参数传进去

#### 5.2.5.2、两个*号

**收集可变长度的关键字参数，会将这种关键字参数收集成字典**

> 根据参数名来传入参数，无需遵守形参顺序

```python
def person(name, age, **kw):
    print('name:', name, 'age:', age, 'other:', kw)
    
>>> person('Jack', 24, city='Beijing',job='Engineer')
```

<font color='red'>注：kw将获得一个dict，注意kw获得的dict是一份拷贝，对kw的改动不会影响到函数外的</font>




### 5.2.6、参数组合

```python
def f1(a, b, c=0, *args, **kw):
    print('a =', a, 'b =', b, 'c =', c, 'args =', args, 'kw =', kw)

```

```python
def person(name, age, sex = '男' , *cars, **kw):
    print('name:', name, 'age:', age, 'sex:',sex)
    print('cars:',cars)
    print('kw:',kw)

if __name__ == '__main__':
    person('张三',24,'女','car1','car2','car3',语文=90,数学=92)
    
name: 张三 age: 24 sex: 女
cars: ('car1', 'car2', 'car3')
kw: {'语文': 90, '数学': 92}
```

<font color='red'>注意:参数定义的顺序必须是：位置参数、默认参数、可变参数</font>



### 5.2.7、※函数的参数传递机制

①python中函数的参数传递机制都是“值传递”。所谓值传递，就是将实际参数值的副本传入函数，而参数本身不会受到任何影响。

<font color='red'>②如果参数本身是一个可变对象（如：列表、字典），此时虽然python采用的是值传递，但是复制传递的是它们的引用变量的值（一个指针，保存了对象的内存地址值），并未复制列表、字典本身的数据，因此参数本身数据会被改变。</font>



### 5.2.8、变量作用域

- 局部变量：在函数中定义的变量，包括参数
- 全局变量：在函数外面、全局范围内定义的变量





# 6、类和对象

python支持面向对象的三大特征：封装、继承、多态

## 6.1、类和对象

### 6.1.1、定义类

- python类名必须是由一个或多个有意义的单词组成，每个单词首字母大写，其他字母全部小写，单词与单词之间不要任何分隔符（**驼峰命名法**）

- 类定义使用**class**关键字

- python类包含两个成员：

  **①变量：** **类变量属于类本身**，可在任何地方为已有的类增加变量；通过del删除已有类的类变量。（python可动态增加或者删除类变量和方法）

  **②方法**：类中定义的方法默认为实例方法（所谓实例方法就是第一个参数会绑定到方法的调用者上-self参数）。类中含有一个特殊的实例方法：`__init__`构造方法，如果开发者未定义构造方法，python会自动为该类定义一个只含self参数的默认构造方法。

```python
class Student:
    def __init__(self,name,age,gender,phone,address,email):
        self.name = name
        self.age = age
        self.gender = gender
        self.phone = phone
        self.address = address
        self.email = email

    def eat(self,food):
        print("%s eat %s" % (self.name,food))
    def drink(self,drink):
        print("%s drink %s " % (self.name,drink))
    def play(self,toy):
        print("%s play %s " % (self.name, toy))
    def sleep(self):
        print("%s 正在sleep" % self.name)


if __name__ == '__main__':
    student = Student("zhangsan",24,2,15215079130,"天西路44号","45454@gmail.com")
    student.eat("零食")
```



### 6.1.2、对象的动态性

由于python是动态语言，程序可以为对象动态增加实例变量或者方法。增加只要为它的新变量赋值即可；也可以使用del语句动态删除。

```python
#有一个实例对象P
p.skills = ['programming','swimming']
print(p.skills)
del p.name
print(p.name)
```



### 6.1.3、实例方法和自动绑定self

self参数出现位置不同，含义不同：

- 在构造方法中：引用该构造方法正在初始化的对象
- 在普通实例方法中：调用该方法的对象

**注意：同一个对象需要在一个方法中调用另一个方法时，不可以省略self**

```python
class Dog:
    def jump(self):
        print('跳')
    def run(self):
        self.jump()  #self调用
        print('叫')
```



## 6.2、方法



### 6.2.1、类方法和静态方法



1. python的类方法和静态方法都推荐通过类来调用（也可以使用对象来调用）。类方法和静态方法的区别就是：**python会自动绑定类方法的第一个参数（参数名建议：cls）会自动绑定到类本身；静态方法不会自动绑定**

2. **使用@classmethod修饰类方法，@staticmethod修饰静态方法**

```python
class Bird:
    # classmethod修饰的方法是类方法
    @classmethod
    def fly (cls):
        print('类方法fly: ', cls)
    # staticmethod修饰的方法是静态方法
    @staticmethod
    def info (p):
        print('静态方法info: ', p)
# 调用类方法，Bird类会自动绑定到第一个参数
Bird.fly()  
# 调用静态方法，不会自动绑定，因此程序必须手动绑定第一个参数
Bird.info('crazyit')

# 创建Bird对象
b = Bird()
# 使用对象调用fly()类方法，其实依然还是使用类调用，
# 因此第一个参数依然被自动绑定到Bird类
b.fly()  #
# 使用对象调用info()静态方法，其实依然还是使用类调用，
# 因此程序必须为第一个参数执行绑定
b.info('fkit')
```



### 6.2.2、@函数修饰器

1. **函数修饰器的作用：被修饰函数总是被替换为@符号所引用的函数的返回值**，举例说明：

```python
def funA(fn):
    print('A')
    fn() # 执行传入的fn参数
    return 'fkit'
'''
下面装饰效果相当于：funA(funB)，
funB将会替换（装饰）成该语句的返回值；
由于funA()函数返回fkit，因此funB就是fkit
'''
@funA
def funB():
    print('B')
print(funB) # fkit

A
B
fkit
```

上面使用@funA修饰了funB()，完成以下两步：

①将funB作为funA的参数，相当于：funA(funB)

②将funB替换成步骤①执行的返回结果，funA返回'fkit'，因此funB就不再是函数



2. **函数修饰器的实际运用：**

可以在被修饰函数的前面添加一些额外的处理逻辑（比如权限检查），也可以在被修饰函数的后面添加一些额外的处理逻辑（如：记录日志），这种改变不需要修改被修饰函数的代码，只要增加一行修饰即可。

```python
def auth(fn):
    def auth_fn(*args): 
        # 用一条语句模拟执行权限检查
        print("----模拟执行权限检查----")
        # 回调要装饰的目标函数
        fn(*args)
    return auth_fn
@auth
def test(a, b):
    print("执行test函数,参数a: %s, 参数b: %s" % (a, b))
# 调用test()函数,其实是调用装饰后返回的auth_fn函数
test(20, 15)
```



## 6.3、隐藏和封装

1. **封装：**指将对象的信息封装隐藏在对象内部，不允许外部程序直接访问，而是通过类提供的方法实现对内部信息的访问

2. python中没有提供真正的隐藏机制，所以python类定义的所有成员默认都是公开的；如果希望将某些成员隐藏起来，可以让该成员的名字以双下划线开头即可（这是python提供的一种小技巧），但是也可以绕过去。

```python
class User :
    def __hide(self):
        print('示范隐藏的hide方法')
    def getname(self):
        return self.__name
    def setname(self, name):
        if len(name) < 3 or len(name) > 8:
            raise ValueError('用户名长度必须在3～8之间')
        self.__name = name
    name = property(getname, setname)
    def setage(self, age):
        if age < 18 or age > 70:
            raise ValueError('用户名年龄必须在18在70之间')
        self.__age = age
    def getage(self):
        return self.__age
    age = property(getage, setage)
# 创建User对象
u = User()
# 对name属性赋值，实际上调用setname()方法
#u.name = 'fk' # 引发 ValueError: 用户名长度必须在3～8之间
# u.name = 'fkit'
# u.age = 25
```



## 6.4、类的继承

### 6.4.1、继承语法

- python的继承是多继承，可以继承多个父类，父类用括号括起来。**尽量不要使用多继承**
- 如果未指明类的父类，默认继承object类
- 父类包含的范围比子类范围大，父类派生出子类

```python
class SubClass(SuperClass1,SuperClass2,SuperClass3....):
    #具体定义
```

### 6.4.2、关于多继承

- 非必要不使用多继承，容易导致代码混乱，可读性降低，不易排查问题
- 如果多个父类中含有同名的方法，按照括号类的前后顺序执行，后面的不执行

### 6.4.3、方法重写与调用

- 子类重写父类方法后，总会执行子类中重写后的方法，不会默认执行父类中被重写的方法
- 子类重写父类方法后，想要执行父类中被重写的方法，可以采用类名调用的方式，但注意要手动绑定self参数。eg：BaseClass.foo(self)。如果是构造方法，可以使用super()来调用父类的构造方法：`super().__init__()`



## 6.5、多态

**所谓多态就是，同样的方法，由于调用对象的不同会呈现出不同的行为**

```python
class Bird:
    def move(self, field):
        print('鸟在%s上自由地飞翔' % field)
class Dog:
    def move(self, field):
        print('狗在%s里飞快的奔跑' % field)
# x变量被赋值为Bird对象
x = Bird()
# 调用x变量的move()方法
x.move('天空')
# x变量被赋值为Dog对象
x = Dog()
# 调用x变量的move()方法
x.move('草地')
```

### 6.5.1、检查类型

- **issubclass(cls,class_or_tuple)：**检查cls是否为后一个类或者元组包含多个类中任意类的**子类**
- **isinstance(obj,class_or_tuple)：**检查obj是否为后一个类或者元组包含多个类中任意类的**对象**





# 7、异常处理

## 7.1、异常处理机制

### 7.1.1、异常捕获和定义

1. python中的异常处理依赖**try、except、else、finally、raise**五个关键字

- try：里面放置可能引发异常的代码
- except：后面对应的是异常类型和一个代码块，用于表明该except块处理这种类型的代码块
- else：在多个except后放一个else块，表明程序不出现异常时还要执行else块
- finally：用于回收try中的物理资源，finally中的总被执行
- raise：用于引发一个实际的异常，可单独作为语句使用，引发一个具体的异常



2. python中所有异常类都从BaseException派生而来，BaseException的主要子类是Exception，不管是系统异常还是用户自定义的异常都应该继承Exception



### 7.1.2、常见异常

| IndexError      | 索引异常，输入参数不够，或者索引异常时引发该异常 |
| :-------------- | ------------------------------------------------ |
| ValueError      | 数值错误，输入参数不是数字而是字母引发该异常     |
| ArithmeticError | 除0导致的异常                                    |



### 7.1.3、else块

当try块没有异常时，程序执行else块。感觉是多余的语法，但else块绝对不是多余语法。放在else中的代码所引发的异常不会被except捕获，但如果希望某段代码的异常能向外传播（不被except捕获），那么就应该将这段代码放到else中，这就体现出else的作用。

```python
def else_test():
    s = input('请输入除数:')
    result = 20 / int(s)
    print('20除以%s的结果是: %g' % (s , result))
def right_main():
    try:
        print('try块的代码，没有异常')
    except:
        print('程序出现异常')
    else:
        # 将else_test放在else块中
        else_test()
def wrong_main():
    try:
        print('try块的代码，没有异常')
        # 将else_test放在try块代码的后面
        else_test()
    except:
        print('程序出现异常')
wrong_main()
right_main()
```



### 7.1.4、finally--回收资源

```python
    try:
        fis = open("a.txt")
    except OSError as e:
        print(e.strerror)
        # return语句强制方法返回
#        return        # ①
        os._exit(1)     # ②
    finally:
        # 关闭磁盘文件，回收资源
        if fis is not None:
            try:
                # 关闭资源
                fis.close()
            except OSError as ioe:
                print(ioe.strerror)
        print("执行finally块里的资源回收!")
```

**注意：**

①不能在finally中使用return和raise，这会使其失效。

②使用`sys.exit()`方法退出程序不能阻止finally块的执行，因为sys.exit()方法本身就是通过引发SystemExit异常来退出程序。需要使用`os._exit(1)`来退出python解释器，停止finally的执行。

**ps：python 中 os._exit()， sys.exit()， exit() 的区别：**

> 1. sys.exit(n) 退出程序引发SystemExit异常, 可以捕获异常执行些清理工作. n默认值为0, 表示正常退出. 其他都是非正常退出. 还可以sys.exit("sorry, goodbye!"。一般主程序中使用此退出.
> 2. os._exit(n), 直接退出, 不抛异常, 不执行相关清理工作. 常用在子进程的退出.
>
> 3. exit()/quit(), 跑出SystemExit异常. 一般在交互式shell中退出时使用.
>
> **综上，sys.exit()的退出比较优雅，调用后会引发SystemExit异常，可以捕获此异常做清理工作。os._exit()直接将python解释器退出，余下的语句不会执行。**
>
> 一般情况下使用sys.exit()即可，一般在fork出来的子进程中使用os._exit()
>
> **一般来说os._exit() 用于在线程中退出**
>
> **sys.exit() 用于在主线程中退出。**



### 7.1.5、raise-引发异常

1.**常用的三种用法：**

①单独一个raise，默认引发RuntimeError异常

②raise 后跟一个异常类。引发指定异常类的实例

③raise后跟一个异常对象，引发指定的异常对象、



**2.实际常用场景**

**实际中raise常和except结合使用，常见场景：**

首先，应用后台需要通过日志来记录异常发生的详细情况；其次，应用还需要根据异常向用户传达某种提示信息。这种情况下需要except和raise结合使用。

```python
class AuctionException(Exception): pass
class AuctionTest:
    def bid(self, bid_price):
        d = 0.0
        try:
            d = float(bid_price)
        except Exception as e:
            # 此处只是简单地打印异常信息
            print("转换出异常：", e)
            # 再次引当前激活的异常
            raise
        if self.init_price > d:
            raise AuctionException("竞拍价比起拍价低，不允许竞拍！")
        initPrice = d
```



# 8、类的特殊方法

## 8.1、常见特殊方法

**①重写`__repr__`方法**

打印对象时，描述默认时“类名+object at +内存地址”，无法清晰的自我描述（对开发者不直观），所以需要清晰的返回该类的描述时就重写该方法





# 9、模块和包

## 9.1、模块

### 9.1.1、※导入模块

**1.导入模块的方法：**

**①import 模块名1[as 别名1],模块名2[as 别名2]...(导入整个模块，使用时需要添加模块名或者别名前缀)**

**②from 模块名 import 成员名1[as 别名1], 成员名2[as 别名2]...(导入模块中指定成员，使用时不需任何前缀，直接使用成员名或者别名)**



### 9.1.2、定义模块

- 模块就是python程序，只要导入模块就包含模块中的所有变量、方法等

- 模块文件的文件名就是它的模块名，eg：module.py的模块名就是module



### 9.1.3、加载模块

两种加载方式：

①使用环境变量。系统变量中添加

②将模块放到默认的模块加载路径下。默认在**python安装路径下的lib\site-packages路径下**



## 9.2、包

### 9.2.1、定义

什么是包？从物理和逻辑两方面来看：

①物理上看：就是一个文件夹，包含多个模块和一个`__init__.py`文件

②逻辑上看：包的本质也是模块





# 10、文件I/O

## 10.1、os.path操作目录

| 操作                           | 代码                                                         |
| ------------------------------ | ------------------------------------------------------------ |
| **获取绝对路径**               | **os.path.abspath("abc.txt")         #G:\publish\codes\12\abc.txt** |
| 获取共同前缀名                 | os.path.commonprerfix(['/usr/lib','/usr/local/lib'])      #/usr/l |
| **获取共同路径**               | **os.path.commonpath(['/usr/lib','/usr/local/lib'])          #\usr** |
| **获取目录**                   | **os.path.dirname('abc/xyz/readme.txt')             #abc/xyz** |
| **判断指定path是否存在**       | **os.path.exists(path)       #False或者True**                |
| 获取文件大小                   | os.path.getsize(path)                                        |
| **判断是否为文件**             | **os.path.isfile(path)**                                     |
| **判断是否为目录**             | **os.path.isdir(path)**                                      |
| 判断是否为同一个文件           | os.path.samefile(path1,path2)                                |
| **将目录和文件名合成一个路径** | **os.path.join('root','test','runoob.txt')         # root/test/runoob.txt** |
| 分割文件名与路径               | os.path.split('/root/runoob.txt')     # ('/root', 'runoob.txt') |
| 返回文件名                     | os.path.basename('/root/runoob.txt')      #runoob.txt        |

更多方法参见：

https://www.runoob.com/python/python-os-path.html



**常见用法：**

```python
#获得当前文件所在的路径（绝对路径）
current_path  = os.path.abspath(__file__)

# 获取当前文件的父目录
os.path.abspath(os.path.dirname(current_path) + os.path.sep + ".")

# 获取当前目录的父目录的父目录
os.path.abspath(os.path.dirname(current_path) + os.path.sep + "..")
```



## 10.2、fnmatch处理文件名匹配

- ‘*’： 匹配任意个任意字符
- '?' ：匹配一个任意字符
- [字符序列]：匹配括号中字符序列的任意字符
- [!字符序列]：匹配不在括号中字符序列的任意字符



**①fnmatch.fnmatch(filename,pattern)** :判断指定文件名是否匹配指定的pattern

```python
if fnmatch.fnmatch(file,"*_test.py")
```

**②fnmatch.fnmatchcase(filename,pattern)** :判断指定文件名是否匹配指定的pattern，**区分大小写**

**③fnmatch.filter(names,pattern)**  : 对names列表进行过滤，返回names中符合pattern匹配的组成的集合



## 10.3、打开文件

### 10.3.1、open（）函数

open()函数：

```python
file = open(file_name[,mode][,buffering][,encoding])
```

- file.closed：文件是否已经关闭
- file.mode：返回文件访问模式
- file.name：返回文件名称



### 10.3.2、with语句

```phthon
with open('phones.txt',mode='w+',buffering=True,encoding='UTF-8') as f:
     f.readlines()
```

<font color='red'>注意：with和直接使用open打开文件的区别在于：使用with打开文件后会自动帮我们关闭文件，如果使用open()函数，则需要我们手动关闭文件资源</font>



### 10.3.3、文件访问模式（mode）

| 模式 | 意义                                                         |
| ---- | ------------------------------------------------------------ |
| r    | 只读模式                                                     |
| w    | 写模式（清空文件后全新写入）                                 |
| a    | 追加模式（在文件最后进行追加）                               |
| +    | 读写模式，可与其它模式进行组合。如：r+读写，w+读写           |
| b    | 二进制模式，可与其它模式进行组合。如：rb二进制只读，rb+二进制读写 |

**注意：**

①无论是使用w还是w+模式，打开文件时，open函数会立即清空文件原有内容。

②使用r或者r+打开文件时，要求文件本身是存在的。



### 10.3.4、文件缓冲（buffering）

一般建议打开缓冲，打开缓冲后，程度执行输出时，程序会先将数据输出到内存缓冲区，而不用等待外设同步输出，进而提高速度。

缓冲状态：

| 模式     | 状态               |
| -------- | ------------------ |
| 0或False | 不带缓冲           |
| 1或True  | 带缓冲             |
| >1       | 带指定大小的缓冲区 |
| <0       | 使用默认缓冲区大小 |



## 10.4、读取文件

### 10.4.1、按字节或字符读取

按字节或者字符读取 取决于文件访问模式是否为b模式：

- b模式：每次读取一个字节
- 非b模式：每次读取一个字符

### 10.4.2、按行读取

- readline()

- readlines()

### 10.4.3、fileinput读取多个输入流

- fileinput.input(files=None,inplace)：该函数中的files参数用于指定多个文件输入流

```python
for line in fileinput.input(files=('info.txt','test.txt'))
	print(line)
    
with fileinput.input(files=list(file_list),openhook=fileinput.hook_encoded('utf-8', '')) as f:
        for line in f:
            print(line)
```



## 10.5、写文件

**使用w、w+、a、a+模式写文件**

- write(str或者bytes)：输出字符串或字节串
- writelines(可迭代对象)：输出多个字符串或多个字节串

**文件指针：**

- seek()：把文件指针移到指定位置，常见用法：

```python
#清空打开文件的已有内容
file = open((os.getcwd()+r'\doc\my.txt'),mode='a+',buffering=True,encoding='UTF-8')
#把文件指针移动到文件开头
file.seek(0)
#截取 清空文件内容
file.truncate()
```

- tell()：判断文件指针位置



## 10.6、os模块常用函数

| 函数                 | 作用                                     |
| -------------------- | ---------------------------------------- |
| **os.getcwd()**      | **获取当前目录**                         |
| os.chdir(path)       | 改变当前目录                             |
| **os.listdir(path)** | **返回path对应目录下的所有文件和子目录** |
| os.mkdir(path)       | 创建对应目录                             |
| os.rmdir(path)       | 删除path对应的空目录                     |
| os.removedirs(path)  | 递归删除目录                             |
| os.linesep           | 当前平台的换行                           |

**更多函数用法 参见：**

https://www.runoob.com/python/os-file-methods.html
