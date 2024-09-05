### python标识符

```
开头是下划线，字母表中的字母。
其他部分可以是字母，数字，下划线。
大小写敏感。
```

### 行间缩进

​	python不使用{}表示代码块，而是同一代码块包含相同的缩进空格数。

### 基本数据类型

```
数值类型：整数，浮点数，复数
字节类型：字符串，字节串
组合类型：集合，元组，列表，字典
```

### 数据类型

集合{}， 元组()，列表[]，字典{key:value,key:value}





# 字符串

##### 定义：

由0个或多个字符组成的有序字符序列，用一对单引号或一对双引号表示

```
'单引号'
"双引号"
```

##### 序号

![img](https://img-blog.csdnimg.cn/20210414102222410.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDk0MDQ4OA==,size_16,color_FFFFFF,t_70)

##### 使用

```
使用[]获取一个或多个字符
s[N]通过序号获取单个字符
s[M,N]获取M到N(不包含)的字串
s[M,N,K]根据步长对字符串进行切片
s[::-1]对字符串进行逆序
M缺少表示开头，N缺失表示结尾
```

##### 字符串处理函数

```python
len(x) //返回字符串的函数
str(x) //返回x的字符串形式
hex(x)或oct(x) //	整数x的十六进制或八进制小写形式字符串
chr(x) //x为Unicode编码，返回其对应的字符
ord(x) //x为字符，返回其对应的Unicode编码
```



##### 字符串处理方法

```python
str.lower() //返回字符串的小写副本
str.upper() //返回字符串的大写副本
str.split(sep=None) //返回列表，由str根据sep //分割的部分组成
str.count(sub) //返回sub再str中出现的次数
str.replace(old,new) //返回str的副本，old字串被替换未new
str.center(width,[fillchar]) //字符串根据width居中，fillchar可选
str.strip(chars) //从str去掉其左侧和右侧chars列出的字符
str.join(iter) //在iter变量除最后一个元素外每个元素后增加一个str
str.title() //首字母大写
```

格式化输出

```python
name=input()
# 方法1
print('I am {} '.format(name))

# 方法2：位置一一对应
print('I am {0}'.format(name))

# 方法3:参数
print('I am {A}'.format(A=name))

# 方法4:文本用 %s 占位符
print('I am %s'%name)


小数指定位数
a = float(input())

print(f'{a:.2f}')
print('%.2f' % a)
print('{:.2f}'.format(a))
```



### 集合

用大括号{}表示，元素之间使用逗号分隔，空集合用{}或set()函数

##### 特点

```
无序，元素间没有顺序
元素不能相同
非一致性，元素类型可以不同
无索引，不能对某个元素定点索引，可以便利或获取随机元素
```

##### 集合操作符

```
S | T 并集
S & T 交集
S - T 差集
S ^ T 补集
S <= T 或S < T返回True或False，判断S和T的子集关系
S >= T同理
```

##### 集合常用的方法

```python
S.add(x) //如果x不在S中，将x加入S
S.discard(x) //移除S中x元素，如果x不在S，不报错
S.remove(x) //移除S中x元素，若x不在S中，产生keyError异常
S.clear() //清除S中的所有元素
S.pop() //随机返回S中的一个元素，更新S，所S为空，产生keyError异常
S.copy()//返回集合S的一个副本
len(s) //返回集合S中元素个数
x in S //判断x是否在S中
x in not S //判断x是否不在S中
set(x) //将其他类型变量x转变为集合类型，也可以用于数据去重
```

### 列表

序列类型的一种，元素间的有序组合，类型不限，创建后可以随时被修改

列表使用中括号[]表示，元素间用逗号分隔，括号不可省略

列表可以将多个数据有序地组织在一起，更方便调用

<u>**数据类型不需要一致**</u>

常用函数（列表）

```
len(list) //返回元素个数
max(list) //返回元素最大值
min(list) //返回元素最小值
list(seq) //将元组转化为列表
id(list) //返回列表的内存地址
```

常用方法

```
list.append('baidu') //	追加"baidu"元素
list.insert(1,'baidu') //在列表第一个位置插入“baidu”元素
list.index(x) //返回列表中第一个值为x的元素的索引
list.remove(v)	 //从列表中移除第一次找到的值v
list.pop([i])	//从列表中指定位置删除元素。并将其返回。
list.reverse()	//	倒排列表中的元素
list.count(X)	//	计数，返回x在列表中出现的次数
list.sort(key = None, reverse = False)	//对列表中的元素进行适当排序， reverse = True为降序， reverse = False为升序（默认）
del list[2]	 //删除列表第三个元素
del list  //删除列表
```

### 字典

常用方法

```
d.keys()  返回一个列表，列表包含字典的所有键的信息
d.values()		返回一个列表，列表包含字典的所有值的信息
d.items()  	返回一个列表，列表元素为字典的键和值构成的元组
d.len(d)	返回字典的长度，即字典元素的数目
d.str(d)	输出字典可打印的字符串
d.copy()	复制一个字典
d.zip()		合并列表组成字典
d.update()		将一个字典的元素添加到另一个字典中
d.clear()	删除字典中全部的键值对，使之变为空字典
del d[k]	删除字典d中键k对应的值
k in d		判断键k是否在字典d中
len(d)	返回字典的个数
```











