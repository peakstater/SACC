# misc

## BUUCTF  小明的保险箱

题目链接：https://buuoj.cn/challenges#小明的保险箱

![ 2024-11-23 214418.png](https://s2.loli.net/2024/11/23/oLDtGYkqSJEPn57.png)

题目附件为一张图片，使用binwalk工具可以分离出一个rar压缩包

![ 2024-11-23 214818.png](https://s2.loli.net/2024/11/23/Q8YC2e4mUdvnEkW.png)

打开压缩包显示需要密码，根据题目提示得知密码为四位数字

使用ARCHPR暴力破解

![ 2024-11-23 214249.png](https://s2.loli.net/2024/11/23/8QJ1rIjhTUEsgfV.png)

解压压缩包，得到txt文本，里面就是flag

flag{75a3d68bf071ee188c418ea6cf0bb043}

## BUUCTF  剑龙

解压题目附件，得到三个文件

> pwd.txt
>
> hh.jpg
>
> O_O

使用file命令，发现O_O为pyc文件，手动添加后缀

![屏幕截图 2024-11-30 161558.png](https://s2.loli.net/2024/11/30/FSaIXDQH5AOxCe3.png)

打开pwd.txt，显示一堆颜文字表情，显然是AAencode加密的特点

解密后得到密码：welcom3!

![屏幕截图 2024-11-30 162355.png](https://s2.loli.net/2024/11/30/LfzOXbnF69Utijr.png)

hh.jpg是steghide隐写，用密码解密得到一段密文

![屏幕截图 2024-11-30 164320.png](https://s2.loli.net/2024/11/30/5GnYTDL1diaPZ7C.png)

查看hh.jpg的属性，发现一段密钥

![屏幕截图 2024-11-30 162540.png](https://s2.loli.net/2024/11/30/4imRkgVb5yMUQXz.png)

用密钥解密，得到原文，提示为stegosaurus隐写

![屏幕截图 2024-11-30 164852.png](https://s2.loli.net/2024/11/30/5d1sOrEbtwHMK7p.png)

使用stegosaurus工具得到flag：flag{3teg0Sauru3_!1}

## BUUCTF  鸡你太美

题目链接：https://buuoj.cn/challenges#鸡你太美

解压附件，得到两张GIF，其中篮球.gif可以打开，篮球副本.gif不能打开

用010打开篮球副本，发现文件头不是gif文件头

添加上gif文件头47 49 46 38后可以打开

![ 2024-11-23 220828.png](https://s2.loli.net/2024/11/23/mxEdIy4GMHe6Na3.png)

得到flag{zhi-yin-you-are-beautiful}

提示错误，-换成_

答案为：flag{zhi_yin_you_are_beautiful}

## 菜狗杯  flag一分为二

解压题目附件，得到一张png图片

将图片拖入tweakpng，显示crc校验错误，说明高度可能被修改

![ 2024-11-22 212428.png](https://s2.loli.net/2024/11/22/t1b4Izha58oTJXp.png)

用010editor打开图片，高度的值为700，将其修改为1200

![ 2024-11-22 215931.png](https://s2.loli.net/2024/11/22/48Duysv3ifrNHk9.png)

再打开图片，右下角可见半段flag：SecondP@rTMikumiku~}

![ 2024-11-22 215831.png](https://s2.loli.net/2024/11/22/zVFn7WEfKchYLMS.png)

使用盲水印工具解析，得到另一段flag：ctfshow{FirstP@RT

![ 2024-11-22 220125.png](https://s2.loli.net/2024/11/22/9NTytM8ZSIYc5XD.png)

合并得到答案：ctfshow{FirstP@RTSecondP@rTMikumiku~}

## 菜狗杯  我吐了你随意

打开题目附件，为一个文本文件；O宽隐写.txt

根据文本名提示为0宽度隐写，使用工具解析文本内容即可

flag为：ctfshow{OP_is_for_Over_Power}

![ 2024-11-30 205130.png](https://s2.loli.net/2024/11/30/ZuYPAIkspbwdfKJ.png)

## 菜狗杯  迷之栅栏

解压题目附件，得到两个png文件

> 找不同1.png
>
> 找不同2.png

因此打开010editor，选择工具--比较文件

![ 2024-11-30 205949.png](https://s2.loli.net/2024/11/30/zdYxD7OXMrj8ln9.png)

得到有差异的文本为：

cfhwfaab2cb4af5a5820}

tso{06071f997b5bdd1a

隔空插入得到flag：ctfshow{f0a6a0b721cfb949a7fb55ab5d8d210a}

## 菜狗杯  黑丝白丝还有什么丝

题目链接是一个抖音视频，轮播了

白黑黑白白白白黑黑白黑黑黑黑黑黑黑黑白白白白白白黑黑黑黑黑黑黑白黑白白黑白黑白白白黑黑白丝的图片

根据题目提示：莫丝密码。可知除了黑丝白丝之外还有摩丝

![ 2024-11-22 222743.png](https://s2.loli.net/2024/11/22/d8u2BFqWL65aAbm.png)

可知白丝对应.，黑丝对应-

仔细观察视频，发现有时两张图片之间使用渐变转场，对应空格

因此得到摩斯密码：**.-- ....- -. - - ----- -... ...-- -- --- .-. . -.-. ..- - .**

解码得到：w4ntt0b3morecute

加上前后缀：ctfshow{w4ntt0b3morecute}

## 菜狗杯  打不开的图片

解压题目附件，得到一个png图片，打开显示不支持此文件格式

使用010editor打开，该文件以**77 B0 B2 B9**开头

而png的文件头为**89 50 4E 47**

加上文件头，图片仍然无法查看

使用计算器发现，在16进制中

> 77+89=100
>
> B0+50=100
>
> B2+4E=100
>
> B9+47=100

将77 B0 B2 B9替换为89 50 4E 47仍无法打开

考虑将所有16进制字节每两位取100的余数

得到含有flag的图片

![bbf5a9393e45470cb4c5b9c99d496549.png](https://s2.loli.net/2024/11/22/oq8ROKaJQkVFyXf.png)

提取文字得到flag：

ctfshow{84a3ca656e6d01e25bcb7e5f415491fa}

## 菜狗杯  你会异或吗

根据题目提示，使用010打开png图片，选择工具--十六进制运算--二进制异或

将操作数设置为0x50

打开图片，提取文字得到flag：ctfshow{030d0f5073ab4681d30866d1fdf10ab1}

## 西瓜杯  二维码拼图

打开题目靶场，获得一张拆散的二维码

![.png](https://s2.loli.net/2024/11/22/l7VaukWMFDS6pOg.png)

使用ps拼接

![ 2024-11-22 204947.png](https://s2.loli.net/2024/11/22/XRkpiqxrYvme1Lf.png)

微信扫描二维码得到flag：

ctfshow{769f5211-bad2-49de-84ac-712527cf2e4a}

