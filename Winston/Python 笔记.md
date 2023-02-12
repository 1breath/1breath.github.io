### _Str字符串_ 

#### _字符串函数
_ord()_ 将字符串转换为整数表示
_chr()_ 编码转换为字符串
_len()_ 函数计算str中包含多少字符串，或字节数
len(b'str_x')
len(b' \ xe4\xb8\xd6\x97') byte,
len('中文'.encode('utf-8')), 输入后显示结果为“6”

#### _字符串表示_ 
以Unicode表示的str，用encode()方法可以将字符串编码成指定bytes,

#### _字符串格式化_
格式化方式与C语言一致，即用 _%_ 实现.
##### _%_ 是运算符，表示字符串替换。
_%d_ ：整数    如：%02d, 意指整数补零且位数为2，％2d，不补零，整数为2。
_%f_  ：浮点数 如：%.nf，n为指定小数的位数，如3
_%s_  ：字符串
_%x_  ：十六进行整数
##### 采用format()方法，用传入的参数依次替代字符串内占位符{0}、{1}......
'Hell0, {0}, 你的聪明指数是{1:.1f}%'.format('丁涛'，144.324)



### _dict字典_
dict,　即dictionary的缩写，其它语言或称之为map，使用“健－值（key-val）＂存储，也就是“索引－正文”的方式存储，查找速度极快。

一个key只能对应一个value，任何改变都会改变原有的数据存储关系。同一个key，多次放入value（相同或不同），只会保留后面的值。

创建字典或把数据放入字典
一、初始化指定
d={'key1':value1, 'key2':value2, 'key3':value3,...'keyn':valuen}
二、Key放入
['key']=value 

dict报错：key不存在，字典报错
避免dict报错的方法：
一、通过in判断key是否存在
‘key' in d
二、通过dict提供的方法get()
d.get('key')
如果key不存在，可以返回Python的交互环境不显示结果的None
自己指定value
d.get('key', value)

删除key
用pop(key)方法：d.pop('key')，删除key，该key对应的value也从dict中删除

dict的特点
查找与插入速度极快，不受key数量多寡的影响；需要占用内存，内存浪费
和list比，dict是以空间换效率的方法

key与value之间的对应关系，dict通过hash算法来确定，首先key需要不可变，字符串、整数不可变变量可作为key，list可变，不能用作key.

### _set_ 













一组不重复key的集合，但不存储value.
创建set，需要提供一个list作为输入集合
name_set=set([x1,x2,x3])

list中的重复元素会被自动过滤掉

通过 _add(key)_ 的方法，可以添加元素到 set 中，重复添加同一元素，无效果。
s.add(key_x)
通过 _remove(key)_ 的方法可以删除元素
s.remove(key_x)

set 可视为无序且无重复元素的集合，故两个set可以进行数学上的集合运算（交、并）？
s1=set([x1,x2,x3])
s2=set([y1,y2,x2])
s1&s2 输出结果为{x2}
s1|s2  输出结果为{x1,x2,x3,y1,y2}

**集合运算类型：子、交、并、超（补）、差、对称
子集：z.issubset(x)
交集：x&y; x.intersection(y)
并集：x|y; x.union(y)
超集：x.issuperset(z)
差集：x-y; x.difference(y)
对称差集：x^y; x.summetric_difference(y)


