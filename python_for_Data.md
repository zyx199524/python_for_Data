```python
tup = 4,5,6
```


```python
tup
```




    (4, 5, 6)




```python
tup = tuple('string')
```


```python
tup
```




    ('s', 't', 'r', 'i', 'n', 'g')




```python
b = ['saw','small','he','foxes','six']

b.sort(key=len)
```


```python
b
```




    ['he', 'saw', 'six', 'small', 'foxes']




```python
import bisect
```


```python
c= [1,2,2,2,2,3,4,7]
```


```python
bisect.bisect(c,2)
```




    5




```python
bisect.bisect(c,5)
```




    7




```python
sorted('horse race')
```




    [' ', 'a', 'c', 'e', 'e', 'h', 'o', 'r', 'r', 's']




```python
a=['a0','a1','a2']
b=['b0','b1','b2','b3']
c=('c0','c1','c2')
d='0123456'
e={'e1':'v1','e2':'v2','e3':'v3'}
```


```python
ab=zip(a,b)
ac=zip(a,c)
ad=zip(a,d)
ae=zip(a,e)
```


```python
list(ab)
```




    [('a0', 'b0'), ('a1', 'b1'), ('a2', 'b2')]




```python
list(ac)
```




    [('a0', 'c0'), ('a1', 'c1'), ('a2', 'c2')]




```python
list(ad)
```




    [('a0', '0'), ('a1', '1'), ('a2', '2')]




```python
list(ae)
```




    [('a0', 'e1'), ('a1', 'e2'), ('a2', 'e3')]




```python
seq1=['a','b','c']
seq2=['e','f','g']
```


```python
for i,(a,b) in enumerate(zip(seq1,seq2)):
    print('{0}:{1},{2}'.format(i,a,b))
```

    0:a,e
    1:b,f
    2:c,g
    


```python
words = ['apple','area','birds','bar','cat','dargon','electricity']
by_letters={}
```


```python
for word in words:
    letter=word[0]
    if letter not in by_letters:
        by_letters[letter]=[word]
    else:
        by_letters[letter].append(word)
```


```python
by_letters
```




    {'a': ['apple', 'area'],
     'b': ['birds', 'bar'],
     'c': ['cat'],
     'd': ['dargon'],
     'e': ['electricity']}




```python
for word in words:
    letter = word[0]
    by_letters.setdefault(letter,[]).append(word)
```


```python
by_letters
```




    {'a': ['apple', 'area'],
     'b': ['birds', 'bar'],
     'c': ['cat'],
     'd': ['dargon'],
     'e': ['electricity']}




```python
from collections import defaultdict
by_letters = defaultdict(list)
for word in words:
    by_letters[word[0]].append(word)
```


```python
by_letters
```




    defaultdict(list,
                {'a': ['apple', 'area'],
                 'b': ['birds', 'bar'],
                 'c': ['cat'],
                 'd': ['dargon'],
                 'e': ['electricity']})




```python
a={1,2,3,4,5}
b={3,4,5,6,7,8}
a.union(b)
```




    {1, 2, 3, 4, 5, 6, 7, 8}




```python
a|b
```




    {1, 2, 3, 4, 5, 6, 7, 8}




```python
a.intersection(b)
```




    {3, 4, 5}




```python
a&b
```




    {3, 4, 5}




```python
some_tuples = [(1,2,3),(4,5,6),(7,8,9)]
flattend = []
```


```python
for tup in some_tuples:
    for x in tup:
        flattend.append(x)
```


```python
flattend
```




    [1, 2, 3, 4, 5, 6, 7, 8, 9]




```python
flattend=[x for tup in some_tuples for x in tup]
flattend
```




    [1, 2, 3, 4, 5, 6, 7, 8, 9]




```python
key_list = [0,1,2]
value_list = ['a','b','c']
```


```python
mapping = {}
for key,value in zip(key_list,value_list):
    mapping[key] = value
mapping
```




    {0: 'a', 1: 'b', 2: 'c'}



mapping_2 = dict(zip(key_list,value_list))


```python
mapping_2 = dict(zip(key_list,value_list))
```


```python
mapping_2
```




    {0: 'a', 1: 'b', 2: 'c'}




```python
{0:'a'}===[(0,'a')]
```


      File "<ipython-input-9-1e6d00a2f36d>", line 1
        {0:'a'}===[(0,'a')]
                 ^
    SyntaxError: invalid syntax
    



```python
a_2 = {0:'a',1:'b',2:'c'}
```


```python
def get_check_key (some_dict,key,default_value):
    value = some_dict.get(key,default_value)
    print(value)
```


```python
get_check_key(a_2,0,'没有')
```

    a
    


```python
get_check_key(a_2,5,'这个真没有')
```

    这个真没有
    


```python
words = ['apple','area','birds','bar','cat','dargon','electricity']
from collections import defaultdict
```


```python
by_letter_6 = defaultdict(list)
```


```python
for word in words:
    by_letter_6[word[0]].append(word)

print(by_letter_6)
```

    defaultdict(<class 'list'>, {'a': ['apple', 'area'], 'b': ['birds', 'bar'], 'c': ['cat'], 'd': ['dargon'], 'e': ['electricity']})
    


```python
{1,2,3,4,5,3,3}
```




    {1, 2, 3, 4, 5}




```python
a={1,2,3,4,5}
b={1,3,5,7,9}
```


```python
a.union(b)
```




    {1, 2, 3, 4, 5, 7, 9}




```python
a|b
```




    {1, 2, 3, 4, 5, 7, 9}




```python
a.intersection(b)
```




    {1, 3, 5}




```python
a&b
```




    {1, 3, 5}




```python
a.difference(b)
```




    {2, 4}




```python
a-b
```




    {2, 4}




```python
a.symmetric_difference(b)#不同时在a和b
```




    {2, 4, 7, 9}




```python
a^b
```




    {2, 4, 7, 9}




```python
c = a.copy()
c.update(b)# c \= b
c
```




    {1, 2, 3, 4, 5, 7, 9}




```python
d = a.copy()
d.intersection_update(b)# d &= b
d
```




    {1, 3, 5}




```python
strings = ['a','bcd','efgh','i']
```


```python
[x.upper() for x in strings if len(x) > 2 ]
```




    ['BCD', 'EFGH']




```python
#字典
loc_mapping = {val:index for index, val in enumerate(strings)}
loc_mapping
```




    {'a': 0, 'bcd': 1, 'efgh': 2, 'i': 3}




```python
#集合推导式
strings = ['a','bcd','efgh','i']
unique_lengths = {len(x) for x in strings}
```


```python
unique_lengths
```




    {1, 3, 4}




```python
#map函数
set(map(len,strings))
```




    {1, 3, 4}




```python
all_data = [['Jonh','Emily','Michael','Mary','Steven'],['Maria','Juan','Javier','Natalia','Pilar']]
```


```python
some_tuples = [(1,2,3),(4,5,6),(7,8,9)]
flattened = [x for a in some_tuples for x in a]
flattened
```




    [1, 2, 3, 4, 5, 6, 7, 8, 9]




```python
flattened_2 = [a+b+c for a,b,c in some_tuples]
flattened_2
```




    [6, 15, 24]




```python
[[x for x in tup]for tup in some_tuples]
```




    [[1, 2, 3], [4, 5, 6], [7, 8, 9]]




```python
#情况1 外部不定义 内部定义
def func():
    a_1= []
    for i in range(5):
        a_1.append(i)
    print(a_1)
```


```python
func()
```

    [0, 1, 2, 3, 4]
    


```python
print(a_1)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-8-52e972c3959f> in <module>
    ----> 1 print(a_1)
    

    NameError: name 'a_1' is not defined



```python
##情况2 外部定义 内部不定义
##函数内部直接对变量操作

a_2=[]
def func():
    for i in range(5):
        a_2.append(i)
    print(a_2)
    print(id(a_2))
```


```python
func()
print(a_2)
print(id(a_2))
```

    [0, 1, 2, 3, 4]
    125058816
    [0, 1, 2, 3, 4]
    125058816
    


```python
#情况3 内外都定义 
a_3=[]
def func():
    a_3 = []
    for i in range(5):
        a_3.append(i)
    print(a_3)
    print(id(a_3))
```


```python
func()
print(a_3)
print(id(a_3))
```

    [0, 1, 2, 3, 4]
    122713856
    []
    114414208
    


```python
# 情况1 +global
def func():
    global a_1_g
    a_1_g = 1
    print(a_1_g)
    print(id(a_1_g))

func()
print(a_1_g)
print(id(a_1_g))
```

    1
    8791042500384
    1
    8791042500384
    


```python
#   strip  删除开头和结尾的空格换行
#   re.sub('[!#?]','',value) 将！或#或？ 替换成空
```

## \d ，0-9的数字
## a*，一个或多个a，a,aa,aaaa都行
## [0-9]，0-9的数字都行
## re: python模块
1.re.match 匹配开头
2.re.search 全文匹配
3.sub 替换删除
4.re.compile 编译正则
5.findall 返回列表
6.finditer 返回迭代器
7.re.split 分割返回列表
8.（？P...）分组匹配
9.符号

1. re.match 匹配开头
功能：匹配开头，如果匹配返回某个值，如果不匹配返回None

通式：re.match(pattern, string, flag=0)，其中

pattern：正则表达式如a，如\d代表0-9的数字

string：要匹配的字符串如abc123

flags：标志位，设置匹配方式，如是否区分大小写等


```python
import re
print(re.match('a','abc123'))

print(re.match('b', 'abc123'))
```

    <re.Match object; span=(0, 1), match='a'>
    None
    


```python
index = re.match('what','whatff i whatfffff')
if index:
    print(index.start()) ## 返回起始位置
    print(index.end()) ## 返回结束位置3+1 = 不匹配的f开始位置4
    print(index.span()) ## 返回（起始，结束）
    print(index.group(0))## 返回字符串
```

    0
    4
    (0, 4)
    what
    


```python
import re

a = "123abc456"

rgl_exprs = '([0-9]*)([a-z]*)([0-9]*)'

#正则表达式，从左到右，有几个括号，就是几组
#group（0）：如有匹配，返回字符串整体
#group（1）：1开始，0到9的数字，取到1，*再来取到2，*再来取到3，*再来a不能取
#group（2）：a开始，a到z的字母，取到a，*再来取到b，*再来取到c，*再来4不能取
#group（3）：同理
#group（4）：没有定义会报错

print(re.match(rgl_exprs, a).group(0))  
print(re.match(rgl_exprs, a).group(1))  
print(re.match(rgl_exprs, a).group(2))
print(re.match(rgl_exprs, a).group(3)) 
print(re.match(rgl_exprs, a).group(4)) 
```

    123abc456
    123
    abc
    456
    


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-11-1cb412067f1c> in <module>
         16 print(re.match(rgl_exprs, a).group(2))
         17 print(re.match(rgl_exprs, a).group(3))
    ---> 18 print(re.match(rgl_exprs, a).group(4))
    

    IndexError: no such group



```python
import re

a = "123abc456"
rgl_exprs = '([0-9]*)([a-z]*)([0-9]*)'

print(re.match(rgl_exprs, a).lastindex)
```

    3
    

2. re.search 全文匹配
功能：扫描整个字符串，匹配成功，返回第一个匹配成功的对象，否则返回None

通式：re.search(pattern, string, flags=0)


```python
import re

print(re.search('www', 'www.runoob.com').start())
print(re.match('www', 'www.runoob.com').start()) # 与match对比
print(re.search('com', 'www.runoob.com').span())
print(re.match('com', 'www.runoob.com')) # 与match的区别
```

    0
    0
    (11, 14)
    None
    

3. sub 替换删除
功能：substitude缩写，替换匹配项，用空去替换，那就是删除

通式：re.sub(pattern, repl, string, count=0, flags=0)

repl : 替换的字符串，也可为一个函数

count : 模式匹配后替换的最大次数，默认 0 表示替换所有的匹配


```python
import re

s_sub = "123 abc 456 456 456" # string字符串
p_sub = '456' # pattern 匹配的字符串
r_sub = '789' # replace替换的

s_subed = re.sub(p_sub, r_sub, s_sub, count=1, flags=0)
print("count = 1:", s_subed)
# count = 1 匹配后替换一次

s_subed_ed = re.sub(p_sub, r_sub, s_sub, count=0, flags=0)
print("count = 0:", s_subed_ed)
# count = 0 匹配后替换次数不限

print(s_subed_ed)
```

    count = 1: 123 abc 789 456 456
    count = 0: 123 abc 789 789 789
    123 abc 789 789 789
    

其中repl可以为函数

看这个文档里的例子。。


```python
import re
 
# 将匹配的数字乘以 2

def double(matched):
    value = int(matched.group('value'))
    return str(value * 2)
 
s = 'A23G4HFD567'
s_2 = re.sub('(?P<value>\d+)', double, s)

print(s_2)
```

    A46G8HFD1134
    


```python
import re
 
# 将匹配的数字乘以 2
def double(x):
    value = int(x.group())
    return str(value * 2)
 
s = '12'
print(re.sub('\d', double, s))
```

    24
    

4. re.compile 编译正则
功能：编译正则表达式，生成一个pattern，供 match() 和 search() 使用

通式：re.compile(pattern[, flags])


```python
import re

pattern = re.compile(r'\d+') # 1或多个数字

m = pattern.match('one12twothree34four')  # 查找头部，没有匹配
n = pattern.search('one12twothree34four').group(0)

print(m)
print(n)
```

    None
    12
    


```python
m_2 = pattern.match('one12twothree34four', 2, 10) # 从'e'的位置开始匹配，没有匹配

print(m_2)

m_3 = pattern.match('one12twothree34four', 3, 10) # 从'1'的位置开始匹配，正好匹配

print(m_3)  

print(m_3.group())
```

    None
    <re.Match object; span=(3, 5), match='12'>
    12
    

5. findall 返回列表
功能：全字符串找，匹配，并返回一个列表，否则返回空列表。

通式：findall(string[, pos[, endpos]])

string : 待匹配的字符串。

pos : 可选参数，指定字符串的起始位置，默认为 0。

endpos : 可选参数，指定字符串的结束位置，默认为字符串的长度


```python
import re
 
p_findll = re.compile(r'\d+')   # 查找数字
result1 = p_findll.findall('123abc456')
# 找数字，返回一个列表
result2 = p_findll.findall('123abc456', 3, 8)
# 从3位开始，包括a，从8位结束，不包括6
 
print(result1)
print(result2)
```

    ['123', '456']
    ['45']
    

6. finditer 返回迭代器
功能：类似findall，只不过返回迭代器

通式：re.finditer(pattern, string, flags=0)


```python
import re
 
it = re.finditer(r"\d+","123abc456efg789") 

for match in it: 
    print (match.group())
```

    123
    456
    789
    

7. re.split 分割返回列表
功能：按照能够匹配的子串将字符串分割后返回列表、

通式：re.split(pattern, string [, maxsplit=0, flags=0])

maxsplit：分隔次数，maxsplit=1 分隔一次，默认为 0，不限制次数


```python
re.split('\W+', '，runoob, runoob,    runoob.')

# \W非字母数字及下划线
# 也就是字母数字下划线留着
# ，空格不能要，见到分隔
# .也不能要，见到分隔
# 分隔一次，列表里就有一个元素，就有一个，
# 所以开头结尾都有个空
```




    ['', 'runoob', 'runoob', 'runoob', '']



8. (?P...)  分组匹配
功能：分组匹配，一组对应的值

通式：((?P 《key》 \pattern) 得到一组对应的值，key：匹配的字符

使用groupdict函数可以变成字典


```python
import re

s = '1102231990xxxxxxxx'

res = re.search('(?P<province>\d{3})(?P<city>\d{3})(?P<born_year>\d{4})',s)

print(res.groupdict())
```

    {'province': '110', 'city': '223', 'born_year': '1990'}
    


```python
import re
 

def double(matched):
    
    print(matched) ## 匹配的字符属性
    
    v_d = matched.groupdict('key') ## 试一下匹配的字符用groupdict变成字典格式
    print(v_d) ## 说明得到的是一对儿数，如 key：23
    
    value = int(matched.group('key')) ##  匹配的字符用group（’value’）提出value值
    print(value) ## 匹配的字符串'23'
    
    return str(value * 2) ## 返回 23*2=46，将23替换为46
 
s = 'A23G4HFD567'

s_2 = re.sub('(?P<key>\d+)', double, s) 
## 匹配一个以上的数字如23
## 替换为经double函数处理得到的东西
## 要处理的字符串是s

print(s_2)
```

    <re.Match object; span=(1, 3), match='23'>
    {'key': '23'}
    23
    <re.Match object; span=(4, 5), match='4'>
    {'key': '4'}
    4
    <re.Match object; span=(8, 11), match='567'>
    {'key': '567'}
    567
    A46G8HFD1134
    

9. 正则符号、修饰符


```python

import re

list_start_with = ['abcd','abc123','123abc','efgabc','abcdefg']

for value in list_start_with:
    
    index_start_with=re.search('^abc',value)
    if index_start_with:
        print(value)
```

    abcd
    abc123
    abcdefg
    


```python
import re

list_end_with = ['abcd','1abc123','123abc','efgabc','defgabc']

for value in list_end_with:
    
    index_end_with = re.search('abc$',value)
    if index_end_with:
        print(value)
```

    123abc
    efgabc
    defgabc
    


```python
import re

list_any_character = ['abcd','afc','123abc','aec','a1c']

for value in list_any_character:
    
    index_any_character = re.search('a.c',value)
    if index_any_character:
        print(value)
```

    abcd
    afc
    123abc
    aec
    a1c
    


```python
import re

list_alternation = ['abd','afc','123abc','aec','a1c','12345']

for value in list_alternation:
    
    index_alternation = re.search('a|1',value)
    if index_alternation:
        print(value)
```

    abd
    afc
    123abc
    aec
    a1c
    12345
    


```python
import re

list_quantifier = ['abd','abbcfc','123abbbbc','abbec','a1c','12345abbccbb']

for value in list_quantifier:
    
    index_quantifier = re.search('ab{2}c',value)
    if index_quantifier:
        print(value)
```

    abbcfc
    12345abbccbb
    


```python
import re

list_set = ['Alien','alien','aLien','aliEn']

for value in list_set:
    
    index_set = re.search('[Aa][Ll]ien',value)
    if index_set:
        print(value)
```

    Alien
    alien
    aLien
    


```python
import re

list_grouping = ['abcabc','123abcabca','abc123',]

for value in list_grouping:
    
    index_grouping = re.search('(abc){2}',value)
    if index_grouping:
        print(value)
```

    abcabc
    123abcabca
    


```python
# 通配符8 * ：0 or more of previous expression 0个或多个前面的字符，贪婪模式
# 通配符9 +：1 or more of previous expression 1个或多个前面的字符
import re

list_more = ['acd','abbb','123abbbb','123abb123']

print('ab*：')
for value in list_more:
    index_more_1 = re.search('ab*',value)    
    if index_more_1:
        print(value)

print('\nab+：')        
for value in list_more:    
    index_more_2 = re.search('ab+',value)    
    if index_more_2:
        print(value)
```

    ab*：
    acd
    abbb
    123abbbb
    123abb123
    
    ab+：
    abbb
    123abbbb
    123abb123
    


```python
# 通配符10 ？：0 or 1 of previous expression 0个或多个前面的字符
# also forces minimal matching when an expression might match several strings within a search string.
# 非贪婪模式
import re

list_more = ['acd','abbb','123abbbb','123abb123']

print('ab*贪婪模式：')
for value in list_more:
    index_more_1 = re.search('ab*',value)    
    if index_more_1:
        print(index_more_1.group(0))

print('\nab*?非贪婪模式：')        
for value in list_more:    
    index_more_3 = re.search('ab*?',value)    
    if index_more_3:
        print(index_more_3.group(0))        
```

    ab*贪婪模式：
    a
    abbb
    abbbb
    abb
    
    ab*?非贪婪模式：
    a
    a
    a
    a
    


```python
# 通配符11 \：Preceding one of the above, it makes it a literal instead of a special character. 
# 让上面的符号变为简单的字符，而不是特殊的功能符号
# Preceding a special matching character, see below
# 在一个特殊的匹配符号前，之后再说

import re

list_grouping = ['abc?123','abccc']

for value in list_grouping:  
    index_grouping = re.search('abc\?',value)
    if index_grouping:
        print(value)
```

    abc?123
    


```python
#[^aeiou]：

#Matches any single character not in the specified set of characters.

#匹配不在这里的单个字母

#除了a e i o u的其他字母

import re

list_not_in_set = ['abc?123','book','change','aaaa']

for value in list_not_in_set:  
    index_not_in_set = re.search('[^a]',value)
    if index_not_in_set:
        print(index_not_in_set.group(0))
```

    b
    b
    c
    


```python
import re

list_hyphen = ['0ab','1cd','3ab','0de','abc12abc']

for value in list_hyphen:  
    index_hyphen = re.search('[0-2][a-c]',value)
    if index_hyphen:
        print(index_hyphen.group(0))
```

    0a
    1c
    2a
    


```python
import re

list_decimal_digit = ['0ab','1cd','abc','\042','\x12']

for value in list_decimal_digit:  
    index_decimal_digit = re.search('\d',value)
    if index_decimal_digit:
        print(index_decimal_digit.group(0))
```

    0
    1
    


```python
import re

list_decimal_digit_2 = ['0ab','1cd','abc','\040987','\x12']
## \040987  按照贪婪法  分为 \040   9 8 7 

for value in list_decimal_digit_2:
    index_decimal_digit_2 = re.search('\d',value)
    if index_decimal_digit_2:
        print(index_decimal_digit_2.group(0))

## '\040789' 是一个字符串吧
## 按照贪婪法 \040 才是一个有效的转义字符   
## \04不够贪婪  毕竟\040 也有效    
## \0407  贪婪过度  转义的八进制最多只能三位
```

    0
    1
    9
    


```python
import re

list_nondigit = ['0ab','1cd','12']

for value in list_nondigit:  
    index_nondigit = re.search('\D',value)
    if index_nondigit:
        print(index_nondigit.group(0))
```

    a
    c
    


```python
#任何词汇的字符，相当于[a-zA-Z_0-9]
import re

list_any_word = ['abc','123','ABC','!#','*&']

for value in list_any_word:  
    index_any_word = re.search('\w',value)
    if index_any_word:
        print(index_any_word.group(0))
```

    a
    1
    A
    


```python
#非词汇字符，相当于[^a-zA-Z_0-9].

import re

list_any_nonword = ['abc','123','ABC','!#','*&']

for value in list_any_nonword:  
    index_any_nonword = re.search('\W',value)
    if index_any_nonword:
        print(index_any_nonword.group(0))
```

    !
    *
    


```python
#所有的空白字符换页，换行，回车，Tab，纵向Tab

#相当于[\f\n\r\t\v].

import re

list_white_space = ['ab  c','12\n3','A\tBC','!#\f？','*\v&']

for value in list_white_space:  
    index_white_space = re.search('\s',value)
    if index_white_space:
        print(value)
```

    ab  c
    12
    3
    A	BC
    !#？
    *&
    


```python
#所有的非空白字符，相当于[^ \f\n\r\t\v].

import re

list_non_white_space = ['   ','\n','\t','\f','\v','abc\n']

for value in list_non_white_space:  
    index_non_white_space = re.search('\S',value)
    if index_non_white_space:
        print(value)
```

    abc
    
    


```python
import re

line = "Cats are smarter than dogs"

matchObj = re.match( r'(.*) are (.*?) .*', line, re.M|re.I) 
## re.M：多行匹配
## re.I：不考虑大小写

if matchObj:
    
    print("matchObj.group() : ", matchObj.group())
    # 整体匹配的字符串：什么 空格are空格 什么 空格 什么
    print("matchObj.group(1) : ", matchObj.group(1))
    # 从开头C到空格are空格，取group（1）
    print("matchObj.group(2) : ", matchObj.group(2))
    # 从are空格之后，也就是s到空格.*取group（2）
    # 空格.* 是 空格than dogs
    # 所以group（2）= smarter
else:
    print ("No match!!")
```

    matchObj.group() :  Cats are smarter than dogs
    matchObj.group(1) :  Cats
    matchObj.group(2) :  smarter
    


```python
import re

matchObj = re.match( r'(.*?) are (.*?)(.*)d(.*)', "Cats are smarter than dogs")

if matchObj:
    
    print("matchObj.group() : ", matchObj.group())
    print("matchObj.group(1) : ", matchObj.group(1))
    print("matchObj.group(2) : ", matchObj.group(2))
    ## 匹配are空格和group（3）之间的东西
    print("matchObj.group(3) : ", matchObj.group(3))
    ## group（3）匹配are空格are和d之间的东西，即smater than空格
    ## 所以group（2）就是空
    print("matchObj.group(4) : ", matchObj.group(4))
    ## group（4）匹配d之后的，即ogs
```

    matchObj.group() :  Cats are smarter than dogs
    matchObj.group(1) :  Cats
    matchObj.group(2) :  
    matchObj.group(3) :  smarter than 
    matchObj.group(4) :  ogs
    


```python
states = ['   #Alabama?  ', 'FlOrIda', 'south   carolina##', 'West virginia?']
import re

def clean_strings(strings):
    result = []
    for value in strings:
        value = value.strip()  #去空格
        value = re.sub('[!#?]', '', value) #替换sub
        value = value.title()  #大写
        result.append(value)
    return result

clean_strings(states)
```




    ['Alabama', 'Florida', 'South   Carolina', 'West Virginia']




```python
def remove_punctuation(value):
    return re.sub('[!#?]', '', value)
## 先定义一个函数，他的功能就是删除标点
def remove_spacss(value):
    return re.sub(' +',' ',value)
## 一个及以上的空格，替换为一个空格
## 通配符9 +：1 or more of previous expression 1个或多个前面的字符

clean_ops = [str.strip,remove_punctuation,str.title,remove_spacss]
## 定义一个列表，元素为函数！！！
## 除去前后的空格换行，删除标点，变成标题格式

def clean_strings(strings,ops):
    ## 定义函数清洗字符串列表，参数为要清洗的字符串，和实现清洗的函数
    result = []
    ## 空列表，装结果
    for value in strings:
         # 对于字符串列表里的值
        for function in ops:
        # 取出一个函数
            value = function(value)
            # 对值执行函数
        result.append(value)
    return result

clean_strings(states,clean_ops)
```




    ['Alabama', 'Florida', 'South Carolina', 'West Virginia']




```python
for x in map(remove_punctuation, states):
    print(x)
```

       Alabama  
    FlOrIda
    south   carolina
    West virginia
    


```python
ints = [4, 0, 1, 5, 6]
ints_3 = [x * 2 for x in ints]
ints_4 = [x ** 2 for x in ints]

print(ints_3)
print(ints_4)
```

    [8, 0, 2, 10, 12]
    [16, 0, 1, 25, 36]
    


```python
ints_5 = [10, 230, 41, 55, 67]
ints_6 = [x * 2 for x in ints_5]
ints_7 = [x ** 2 for x in ints_5]

print(ints_6)
print(ints_7)
```

    [20, 460, 82, 110, 134]
    [100, 52900, 1681, 3025, 4489]
    


```python
def apply_to_list(some_list, f):
    ## 定义函数
    ## 列表
    ## 函数
    ## 返回经过函数处理的列表值
    return [f(x) for x in some_list]
ints = [4, 0, 1, 5, 6]
ints_2 = apply_to_list(ints, lambda x: x * 2)
## 这里做参数的函数直接用一个lambda定义
print(ints_2)
```

    [8, 0, 2, 10, 12]
    


```python
strings = ['foo', 'card', 'bar', 'aaaa', 'abab']
strings.sort(key=lambda x:len(set(list(x))))
strings
```




    ['aaaa', 'foo', 'abab', 'bar', 'card']



误：list是把strings变成列表，本身就是列表，所以作用不大

正：x是列表的里的元素，比如字符串‘foo’

list把foo变成列表['f','o','o']

set是把列表变为集合，去掉重复元素

len得到set元素的长度

lambda以上三步操作作为一个匿名函数，对x，也就是strings执行

key。。？？？

## 3.2.4.1 list.sort与sorted()用法补充
list.sort
功能：对列表排序，改变原来列表

通式：list.sort(func=None, key=None, reverse=False(or True))

sorted()
功能：对序列排序，不改变原来列表

通式：sorted(iteralable, key=None, reverse=False)

func为了避免混乱返回None？不管了先

key在调用之前，对每个函数进行的函数操作

reverse=False正序，=True反序


```python
student_tuples = [('john', 'A', 15), ('jane', 'B', 12), ('dave', 'B', 10)]

sorted(student_tuples, key=lambda student: student[2])   # sort by age

## 处理对象这个列表，是个可迭代对象
## key对于列表的每个元素进行的函数处理
## 比如('john', 'A', 15)
## lambda，这个函数不def定义了，直接上
## 函数参数student就是这个('john', 'A', 15)
## 做的处理，是提出第二位元素，也就是15
## 处理后返回这个student[2]，15
## 所有元素都经过这个处理之后，变成了，15，12，10
## 再排序10，12，15
## 排出来就应该是dave，jane，john这个顺序
```




    [('dave', 'B', 10), ('jane', 'B', 12), ('john', 'A', 15)]



## Generators 生成器
迭代器协议

迭代器就是一种在上下文中（比如for循环）向Python解释器生成对象的对象


```python
some_dict = {'a': 1, 'b': 2, 'c': 3}
for key in some_dict:
    print(key)
## for这种就让Python解释器尝试生成一个迭代器
```

    a
    b
    c
    


```python
dict_iterator = iter(some_dict)
dict_iterator
```




    <dict_keyiterator at 0x7a9a4f0>




```python
list(dict_iterator)
```




    ['a', 'b', 'c']




```python
dict_iterator_2 = iter(some_dict)
## 所以没办法，只能再定义
tuple(dict_iterator_2)
```




    ('a', 'b', 'c')




```python
some_list = [5, 4, 3, 2, 1]
list_iterator = iter(some_list)
set(list_iterator)
```




    {1, 2, 3, 4, 5}




```python
list_iterator_2 = iter(some_list)
min(list_iterator_2)
```




    1




```python
list_iterator_3 = iter(some_list)
max(list_iterator_3)
```




    5




```python
l = [1, 2, 3]
a = iter(l)
b = iter(l)

print(a)
print(b)

print(list(a))
print(list(b))
print(list(b))
print(b)
## 迭代器只跟自己有关
## 迭代器有一个开始位置和结束位置
```

    <list_iterator object at 0x000000000738A580>
    <list_iterator object at 0x00000000075D4BB0>
    [1, 2, 3]
    [1, 2, 3]
    []
    <list_iterator object at 0x00000000075D4BB0>
    


```python
lst = [1, 2, 3]
for i in iter(lst):
     print(i)
```

    1
    2
    3
    


```python
a = [1, 2, 3]

for x in a:
    print(a.index(x))
```

    0
    1
    2
    


```python
l = [1, 2, 3, 4, 5, 6, 7, 8]

for i in range(0, len(l)):
    print(l[i])
```

    1
    2
    3
    4
    5
    6
    7
    8
    

迭代器的优势

比如要找第4位，索引有点像整个for循环，从0开始，找到4结束

迭代器有点像for循环里的一步，走到第三步，下面就是第四步

索引每次都从0开始数

就因为0数 会有多余的步骤 降低了程序性能

比如有个 100w个元素的list 如果用索引 每次都从0位开始数

不是很浪费时间吗

索引就是记住最开始位置 迭代就是记住了当前操作到的位置


```python
l = [1, 2, 3, 4, 5, 6, 7, 8]
iter_l = iter(l)
next(iter_l)
```




    1




```python
next(iter_l)
```




    2




```python
print(list(iter_l))
```

    [3, 4, 5, 6, 7, 8]
    


```python
def squares(n=10):
    print('Generating squares from 1 to {0}'.format(n ** 2))
    for i in range(1,n+1):
        yield i**2

gen = squares()
gen
```




    <generator object squares at 0x0000000007EFAC10>




```python
for x in gen:
    print(x,end='')
```

    Generating squares from 1 to 100
    149162536496481100

yeild a 相当于return a 只不过return很知足，得到a就结束

yeild得到a之后，继续执行代码，还可以继续得到b c d

a独白：早知道你是这样的yeild，当初啥也不让你得到我


```python
def yield_test_1(n):
    a=n
    yield a
    b=n * 2
    yield b 
    c=n * 3 
    yield c
    d=n * 4 
    yield d
print(yield_test_1(10))
for i in yield_test_1(10):
    print(i)
```

    <generator object yield_test_1 at 0x0000000007D75D60>
    10
    20
    30
    40
    


```python
def yield_test(n):
    for i in range(n):
        yield change(i) 
        ## 功能生成一串鞭炮，每个小鞭儿调用一次change
        ## 并保存，注意保存了
        #print("i = ",i)
    print("end.")

def change(i):
    return i*2

print(yield_test(5)) # 生成了一串鞭炮，change（0），change（1）...change(5)

for i in yield_test(5):#使用for循环点鞭炮
    print(i, "in for")

sum(yield_test(6)) # 用sum点鞭炮
```

    <generator object yield_test at 0x0000000007D754A0>
    0 in for
    2 in for
    4 in for
    6 in for
    8 in for
    end.
    end.
    




    30



3.2.6.1 Generator expresssions 生成器的表达式
列表推导式的[ ]换为( )


```python
gen = (x ** 2 for x in range(100))
gen
```




    <generator object <genexpr> at 0x0000000007D75660>




```python
def _make_gen(): 
    for x in range(100): 
        yield x ** 2 
gen = _make_gen()
sum(x ** 2 for x in range(100))
```




    328350




```python
dict((i,i**2) for i in range(5))
```




    {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}



3.2.6.2 itertools module 模块
还记得groupby吗，以前按周数吧数据分组的时候用过一次

groupby(iterable[，keyfunc分组依据])


```python
from itertools import groupby 

test = [(1, 5), (1, 4), (1, 3), (1, 2), (2, 4), (2, 3), (3, 5)]
temp = groupby(test, key=lambda x: x[0])
## 得到一个迭代器
## x就是一个元组如（1，5）
## key=x[0]根据元组的0位元素分组，1是一组，2一组，3一组
print(temp)
## 得到一组数，分类的标准，分类的结果是个列表1 []
for a, b in temp:
    print(a, list(b))
```

    <itertools.groupby object at 0x00000000081CEBD0>
    1 [(1, 5), (1, 4), (1, 3), (1, 2)]
    2 [(2, 4), (2, 3)]
    3 [(3, 5)]
    


```python
import itertools
first_letter = lambda x: x[0]
names = ['Alan', 'Adam', 'Wes', 'Will', 'Albert', 'Steven']

for letter, names in itertools.groupby(names, first_letter):
    print(letter, list(names)) # names is a generator
```

    A ['Alan', 'Adam']
    W ['Wes', 'Will']
    A ['Albert']
    S ['Steven']
    

其他

combinations (iterable, k) 组合

permutations (iterable, k) 排列

product (*iterables, repeat=1) 多组之间组合


```python
from itertools import combinations
test = combinations([1, 2, 3, 4], 3)
for n in test:
    print(n)
```

    (1, 2, 3)
    (1, 2, 4)
    (1, 3, 4)
    (2, 3, 4)
    


```python
from itertools import permutations
test = permutations([1, 2, 3, 4], 3)
for n in test:
    print(n)
```

    (1, 2, 3)
    (1, 2, 4)
    (1, 3, 2)
    (1, 3, 4)
    (1, 4, 2)
    (1, 4, 3)
    (2, 1, 3)
    (2, 1, 4)
    (2, 3, 1)
    (2, 3, 4)
    (2, 4, 1)
    (2, 4, 3)
    (3, 1, 2)
    (3, 1, 4)
    (3, 2, 1)
    (3, 2, 4)
    (3, 4, 1)
    (3, 4, 2)
    (4, 1, 2)
    (4, 1, 3)
    (4, 2, 1)
    (4, 2, 3)
    (4, 3, 1)
    (4, 3, 2)
    


```python
import itertools
test = itertools.product('abc', 'xy')
for n in test:
    print(n)
```

    ('a', 'x')
    ('a', 'y')
    ('b', 'x')
    ('b', 'y')
    ('c', 'x')
    ('c', 'y')
    

Errors and Exception Handling 错误和异常处理
之前见过，但还是要深化一下

本段主要帮你解决，跟Python表白：

不确定能不能成功怎么办

被拒绝想知道为什么怎么办

被拒绝也不想气氛尴尬怎么办

破天荒成功了怎么办

不管成不成功都想干点啥怎么办


```python
float('1.2345')
float('something')
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-26-6d335c618d25> in <module>
          1 float('1.2345')
    ----> 2 float('something')
    

    ValueError: could not convert string to float: 'something'


1、except 回避所有错误


```python
def attempt_float(x):
    try:
        return float(x)
    except:
        return x

attempt_float('哈哈,我真秀')
```




    '哈哈,我真秀'




```python
def attempt_float_2(x):
    try:
        return float(x)
    except TypeError:
        return x

attempt_float_2((1,2))
```




    (1, 2)




```python
attempt_float_2('蒂花之秀')
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-5-5e96534745e8> in <module>
    ----> 1 attempt_float_2('蒂花之秀')
    

    <ipython-input-4-68dc5d78c1fe> in attempt_float_2(x)
          1 def attempt_float_2(x):
          2     try:
    ----> 3         return float(x)
          4     except TypeError:
          5         return x
    

    ValueError: could not convert string to float: '蒂花之秀'



```python
def attempt_float_3(x):
    try:
        return float(x)
    except (ValueError, TypeError):
        return x

attempt_float_3((1, 2))
```




    (1, 2)




```python
attempt_float_3('造化钟神秀')
```




    '造化钟神秀'




```python
try:
    1/0
except ZeroDivisionError: #指定错误，多个用元祖
    print("Get AError")
except:
    print("exception") #所有报错
else:
    print("else") #try成功执行的
finally:
    print("finally")#成不成功都执行的 
```

    Get AError
    finally
    

else语句的存在必须以except X或者except语句为前提

如果在没有except语句的try block中使用else语句

会引发语法错误

3.3 Files and the Operating System 文件与操作系统

第一步把文件存好，第二步把文件读出来，第三步把文件关上

最后看一眼Python文件读取模式

文件方法或属性

第一步：存文件


```python
# path = 'examples/segismundo.txt'

path = r'D:\anaconda\jupyter_notebook\ch0301.txt'
# r不写会报错
# SyntaxError: (unicode error) 'unicodeescape' codec can't decode bytes in position 2-3: truncated \UXXXXXXXX escape


# f = open(path)
# 直接这么开，会报错
# UnicodeDecodeError: 'gbk' codec can't decode byte 0xff in position 0: illegal multibyte sequence

# f = open(path,encoding='UTF-8')
# encoding = 'UTF-8也会报错'
# UnicodeDecodeError: 'utf-8' codec can't decode byte 0xff in position 0: invalid start byte


f = open(path,encoding='unicode_escape')
# 唯一成功不报错的方法
```


```python
path = r'D:\anaconda\jupyter_notebook\ch0301.txt'
f = open(path,encoding='unicode_escape')
```

默认情况下以只读模式打开，相当于r

生成的f是一个可迭代的东西

就是可以用for循环读出来


```python
for line in f:
    print(line)
```

    ÿþS u e ñ a   e l   r i c o   e n   s u   r i q u e z a , 
    
     
    
     
    
     
    
     q u e   m á s   c u i d a d o s   l e   o f r e c e ; 
    


```python
lines_1 = [line for line in f]
lines_1
```




    []



咦？这个为什么是空？？

呼叫基地请求远程支援

N先生给了个例子

引出了seek()功能


```python
# path = r'D:\jupyter_file'
f_2 = open('ch0301.txt', encoding='unicode_escape')

print('第1次：')
for line in f_2:
    print(line)

print('第2次：\n')
for line in f_2:
    print(line)

print('第3次：')
f_2.seek(0)
for line in f_2:
    print(line)
```

    第1次：
    ÿþS u e ñ a   e l   r i c o   e n   s u   r i q u e z a , 
    
     
    
     
    
     
    
     q u e   m á s   c u i d a d o s   l e   o f r e c e ; 
    第2次：
    
    第3次：
    ÿþS u e ñ a   e l   r i c o   e n   s u   r i q u e z a , 
    
     
    
     
    
     
    
     q u e   m á s   c u i d a d o s   l e   o f r e c e ; 
    

啊，大概是这么回事儿

这个文件存在变量f里

f的读取类似于迭代器

但读完可以用seek（0）恢复到最开始

我先这么理解着


```python
f.seek(0)
lines_2 = [line for line in f]
lines_2
```




    ['ÿþS\x00u\x00e\x00ñ\x00a\x00 \x00e\x00l\x00 \x00r\x00i\x00c\x00o\x00 \x00e\x00n\x00 \x00s\x00u\x00 \x00r\x00i\x00q\x00u\x00e\x00z\x00a\x00,\x00\n',
     '\x00\n',
     '\x00\n',
     '\x00\n',
     '\x00q\x00u\x00e\x00 \x00m\x00á\x00s\x00 \x00c\x00u\x00i\x00d\x00a\x00d\x00o\x00s\x00 \x00l\x00e\x00 \x00o\x00f\x00r\x00e\x00c\x00e\x00;\x00']



场外支援：

我的理解是t作为一个list 是一个整体

把列表元素打印出来

才能编解码看到正常的文字


```python
for x in lines_2:
    print(x)
```

    ÿþS u e ñ a   e l   r i c o   e n   s u   r i q u e z a , 
    
     
    
     
    
     
    
     q u e   m á s   c u i d a d o s   l e   o f r e c e ; 
    

用rstrip去掉line的\n


```python
f.seek(0)
lines_3=[x.rstrip() for x in f]
lines_3
```




    ['ÿþS\x00u\x00e\x00ñ\x00a\x00 \x00e\x00l\x00 \x00r\x00i\x00c\x00o\x00 \x00e\x00n\x00 \x00s\x00u\x00 \x00r\x00i\x00q\x00u\x00e\x00z\x00a\x00,\x00',
     '\x00',
     '\x00',
     '\x00',
     '\x00q\x00u\x00e\x00 \x00m\x00á\x00s\x00 \x00c\x00u\x00i\x00d\x00a\x00d\x00o\x00s\x00 \x00l\x00e\x00 \x00o\x00f\x00r\x00e\x00c\x00e\x00;\x00']




```python
for x in lines_3:
    print(x)
```

    ÿþS u e ñ a   e l   r i c o   e n   s u   r i q u e z a , 
     
     
     
     q u e   m á s   c u i d a d o s   l e   o f r e c e ; 
    

这个文件读取模式，句柄的概念为啥不提前说，这样后面这几个也能理解了

seek()将句柄位置改变到特定字节

read()根据字节数推进文件句柄的位置

tell()句柄当前的位置


```python
f_5 = open(path,encoding='unicode_escape')
t0 = f_5.tell()## 当前句柄位置
print(t0)

r1 = f_5.read(1) ## read往前推一个，读一个
t1 = f_5.tell()

print(r1,t1)

r2 = f_5.read(10) ##read往前推10个字节，读出来
t2 = f_5.tell()
print(r2,t2)

f_5.seek(0)

t3 = f_5.tell()
print(t3)
```

    0
    ÿ 1
    þS u e ñ a 11
    0
    

seek() 只有三个

seek(0)代表从文件开头开始算起

seek(1)代表从当前位置开始算起

seek(2)代表从文件末尾算起。


```python
f.close()
```


```python
f.seek(0)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-37-16754355c5bd> in <module>
    ----> 1 f.seek(0)
    

    ValueError: I/O operation on closed file.



```python
with open(path,encoding='unicode_escape') as f_4:
    lines_4 = [x.rstrip() for x in f_4]
```


```python
f_4.seek(0)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-45-285464532cad> in <module>
    ----> 1 f_4.seek(0)
    

    ValueError: I/O operation on closed file.



```python
for x in lines_4:
    print(x)
```

    ÿþS u e ñ a   e l   r i c o   e n   s u   r i q u e z a , 
     
     
     
     q u e   m á s   c u i d a d o s   l e   o f r e c e ; 
    

检验文件的默认编码


```python
import sys
sys.getdefaultencoding()
```




    'utf-8'



Python文件模式

r 只读

w 只写，创建新文件，覆盖原文件

x 只写，创建新文件，不覆盖原文件，同名报错

a 添加到已存在文件，不存在就创建

r+ 读写

b 二进制模式，跟其他结合使用，rb，wb，xb等

t 文件的文本模式，自动解码为Unicode，可以单独使用，也可以跟其他结合使用，rt，xt等


```python
## 有一个ch0303，文件取出来，放到ch0304

path_2 = r'D:\jupyter_file\ch0303.txt'

with open('ch0304.txt','w') as handle:
    handle.writelines(x for x in open(path_2))
    
with open('ch0304.txt') as f:
    lines = f.readlines()
    
for x in lines:
    print(x.strip())
```

    啊白云
    
    黑土向你道歉
    
    来到你们前
    
    请你睁开眼瞅我多可怜
    

重要的Python方法或属性

read([size]) 将文件数据作为字符串返回，可选参数size控制读取的字节数

readlines([size]) 返回文件中行内容的列表，size参数可选

write(str) 将字符串写入文件

writelines(strings) 将字符串序列写入文件

close() 关闭文件

flush() 将内部I/O缓冲器内容刷新到硬盘

seek(pos) 移动到指定的位置(整数)

tell() 返回当前位置

closed 如果文件已关闭，则为True


```python
import os 
os.remove('ch0304.txt')
```

删除文件


```python

```
