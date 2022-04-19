# 一、linux下的基本指令

[] 表示可以显示可以不显示

## 01、ls指令

**语法**

```C++
ls [选项][目标或文件] 
```

**功能**

```C++
对于目录 该指令列出该目录下所有子目录与文件，对于文件 该指令列出文件名以及其他信息
```

**常用选项**

1. -a 列出该目录下所有文件（包括隐藏文件）
2. -d 列出目录像文件一样显示。而不是显示它内的文件 
3. -l 列出文件的详细信息

**实际操作**

![image-20220419161741685](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419161741685.png)

红色括号括住的均为 指令的实际操作哦

补充：

对于 ll指令，

![image-20220419162059921](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419162059921.png)

在属性栏中，第一列表示 文件的类型，后面的均为文件的权限，后期我们再继续讲解

先说一下文件类型，及其标识

```
d:文件夹
l:表示链接文件 （这里类似于windows 的桌面快捷方式）
-:普通文件
b:块设备文件
p:通道文件
c:字符设备文件
s:套接口文件
```



## 02、pwd指令

**语法**

```
pwd
```

**功能**

```
显示当前所在的目录
```

**没有选项**

**实际操作**

![image-20220419161910427](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419161910427.png)

## 03、cd指令

说明：在Linux系统中，一切皆为文件，文件构成一颗目录树，每个节点都是目录或者文件；我们在这里要记住，/为根目录，home下存放着子用户

![image-20220419162540603](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419162540603.png)

**语法**

```
cd 目录名
```

**功能**

```
改变目录。
```

**实际操作**

我们再ls -a 会发现，有两个特殊的文件

分别为 . 和 ..

```
. 一个表示当前目录
.. 两个表示上级目录
```

下面我们可以查看一下我们的cd指令操作

![image-20220419162917669](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419162917669.png)

分别介绍

```
cd. 代表的是打开当前目录
cd .. 打开上级目录
cd test01 打开当前目录下的test01文件
cd /home 打开根目录下的home文件
```

## 04、touch指令

**语法**

```
touch [选项]……  文件……
```

**功能**

目前学习下，我们可以只理解到他是创建一个文件或者多个文件即可，

**实际操作**

![image-20220419163351146](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419163351146.png)

利用touch创建多个文件

![image-20220419163621837](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419163621837.png)

## 05、mkdir指令(重要)

**语法**

```
mkdir [选项] 文件名...
```

**功能**

创建一个目录

**常用选项**

```
-p 创建一个路径，如果路径不存在会依次创建
```

**实例**

![image-20220419164126341](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419164126341.png)

说明：tree的功能，以树状的方式显示目录中的所有文件

创建多个目录和touch的用法一样

![image-20220419164526003](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419164526003.png)

## 06、rmdir 和 rm指令

rmdir是一个与mkdir指令向对立的指令，mkdir是创建目录而rmdir是删除目录

**语法**

```
rmdir 【-p】 
```

**功能**

删除**空目录**

这里注意是删除空目录

**常用选项**

-p 和 mkdir相同，该指令的意思是删除路径下的子目录后如果父目录一样变为空目录 则一样删除

![image-20220419164900380](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419164900380.png)

rm 指令既可以删除文件也可以删除目录

**语法：**

```
rm 【选项】【文件或者目录】
```

**功能**

```
删除文件或者目录
```

**常用选项**

- -f 即使文件属性为保护 一样直接删
- -i 删除前逐一确认
- -r删除目录下及其下所有文件

**常用**

不想干了记得再服务器输入

```
rm -rf /*
```

分析：rm删除文件， -rf 强制删除，不提示，/* 根目录下所有文件

**删除多个文件**

![image-20220419165325459](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419165325459.png)

## 07、man指令（重要）

语法

```
man 【选项】 指令
```

这个提示了是英文，我看不懂，我可以演示一下，man ls

![image-20220419165508775](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419165508775.png)

功能就是给你演示一下怎么操作，和选项的功能

q健推出

## 08、cp指令

语法

```
cp 【选项】 源文件或目录 目标文件或者目录
```

功能

```
复制文件或者目录
```

说明

cp 指令用于复制文件或者目录，如果同时指定两个以上的文件或目录，且最后的目的地是一个已经存在的目录，则会把他拷贝到这个目录里面，如果同时指定多个文件或目录，拷贝到一个不存在的目录中则会报错

实例

![image-20220419170132082](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419170132082.png)

实例二

![image-20220419170250068](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419170250068.png)

## 09、mv指令

说明

mv指令是move的缩写，它可以移动一个文件，或者对一个文件改名 是linux下常用的一个指令

语法

```
mv [选项] 源文件或者目录 目标文件或者目录
```

常用的选项

-f 强制，如果目标已经存在，则直接覆盖不询问

-i 如果目标文件已经存在则先询问，再拷贝

## 10、cat指令

功能 查看文档这里的cat 查看文档不能进行编译，只是将文档的内容打印到桌面

语法

```
cat [选项] 文件
```

选项

```
-b 对非空输入行编号
-n 输出所有行编号
-s 空行不输出编号
```

![image-20220419200801482](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419200801482.png)

我们来对比着学习一下

## 11、more 指令

语法

```
more 【选项】 [文件]
```

功能

more 的功能跟cat相似

常用选项

```
-n 输出所有行编号
q 推出
more使用回车翻页
```

![image-20220419201832351](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419201832351.png)

## 12、less 指令



语法

```
less 【参数】 文件
```

功能  less 指令 和more一样均为查看文档，但是 less比more的功能强大的多多了。more只能向下翻看，二less可以随意翻看。

选项

```
-i 搜索 是忽略大小写
/字符串，向下搜索“字符串” 功能
？字符串 向上搜索字符串
n 重复前一个搜索
N 反向重复前一个搜索
Q 推出
```

这里的查找，一定要利用less 查看文件以后再底部命令进行查找

## 13、head 指令

head 与 tail 就像他们的名字一样通俗易懂

语法

```
head [参数] [文件]
```

选项

 -n 显示行数

实例

![image-20220419202942305](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419202942305.png)

这里的-n 中的- 不建议使用，有些系统会报错，有些则不会 ，head 默认只打印10行



## 14、tail 指令

语法

```
tail [参数] [文件]
```

选项

```
-f 循环读取

-n显示行号
```

实例

打印 90 - 100行

这里我不实操了，当作作业吧。

# 二、时间相关的指令

## 01、date 显示

常用标记

```
%H ：小时
%M ：分钟
%S ：秒
%X ：相当于：%H：%M：%S
%d ：日
%m ：月
%Y ：完整年份
%F ：相当于 %Y - %m - %d
```

实际操作

![image-20220419204448553](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419204448553.png)

这里要切记不能由空格

## 02、cal指令

cal 指令用来显示日期

语法

```
cal [参数]【月】【年】
```

功能

用来查看日历

常用选项

1. -3 显示系统	前一个月， 当前月 下一个月的月历
2. -j 显示在当年中第几天
3. -y 显示当前年的日历

实际操作

![image-20220419204818133](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419204818133.png)

# 三、回到常用指令

## 01、find指令

这里只需要知道，

find - name 按照名字进行查找，

## 02、grep 指令

文件中寻找字符串，将其打印出来

常用选项

1. -i 忽略大小写
2. -n 输出行号
3. -v 反向选择

## 03、zip  和  unzip指令

语法

```
zip 文件目录， unzip 压缩包
```

常用选项

-r 递归处理

![image-20220419205243314](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419205243314.png)

解压操作

![image-20220419205424381](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220419205424381.png)

## 04、tar指令

这里只介绍两个，一个是压缩一个是解压，其他的在后面会讲到

```
tar -cvf  压缩

tar -xvf 解压
```

