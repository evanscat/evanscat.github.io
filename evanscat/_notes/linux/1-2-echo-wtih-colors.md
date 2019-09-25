---
title: echo
mathjax: true
permalink: /notes/linux/echo
key: notes-linux-echo
---

## echo with colors in terminals

```tex
1 设置粗体
2 设置一半亮度(模拟彩色显示器的颜色)
4 设置下划线(模拟彩色显示器的颜色)
5 设置闪烁
7 设置反向图象
8 消隐 
22 设置一般密度
24 关闭下划线
25 关闭闪烁
27 关闭反向图象
// 字体颜范围(前景颜色):30~39
30:黑 
31:红 
32:绿 
33:黄 
34:蓝色 
35:紫色 
36:深绿 
37:白色 
38:在缺省的前景颜色上设置下划线
39:在缺省的前景颜色上关闭下划线
// 字背景颜色范围(背景颜色):40~49 
40:黑 
41:深红 
42:绿 
43:黄色 
44:蓝色 
45:紫色 
46:深绿 
47:白色 
nA 光标上移n行 
nB 光标下移n行 
nC 光标右移n行 
nD 光标左移n行 
y;xH设置光标位置 
2J 清屏 
K 清除从光标到行尾的内容 
s 保存光标位置 
u 恢复光标位置 
?25l 隐藏光标 
?25h 显示光标
```

例子

```shell
echo -e "\033[47;30;5m david use echo say \033[0m Hello World \n" 
```

```latex
作用:
42->背景色为白色，
30->字体为黑色，
5->字体闪烁，
0->关闭所有属性
输出字符 “david use echo say”，然后重新设置屏幕到缺省设置，输出字符 “Hello World”后颜色回复正常
```

```shell
echo -e "\033[0m none \033[0m"
echo -e "\033[30m black \033[0m"
echo -e "\033[1;30m dark_gray \033[0m"
echo -e "\033[0;34m blue \033[0m"
echo -e "\033[1;34m light_blue \033[0m"
echo -e "\033[0;32m green \033[0m"
echo -e "\033[1;32m light_green \033[0m"
echo -e "\033[0;36m cyan \033[0m"
echo -e "\033[1;36m light_cyan \033[0m"

echo -e "\033[0;31m red \033[0m"
echo -e "\033[1;31m light_red \033[0m"
echo -e "\033[0;35m purple \033[0m"
echo -e "\033[1;35m light_purple \033[0m"
echo -e "\033[0;33m brown \033[0m"
echo -e "\033[1;33m yellow \033[0m"
echo -e "\033[0;37m light_gray \033[0m"
echo -e "\033[1;37m white \033[0m"
echo -e "\033[0m none \033[0m"
echo -e "\033[0m none \033[0m"
echo -e "\033[0m none \033[0m"
echo -e "\033[0m none \033[0m"
echo -e "\033[0m none \033[0m"

echo -e "\033[40;37m 黑底白字 \033[0m"
echo -e "\033[41;30m 红底黑字 \033[0m"
echo -e "\033[42;34m 绿底蓝字 \033[0m"
echo -e "\033[43;34m 黄底蓝字 \033[0m"
echo -e "\033[44;30m 蓝底黑字 \033[0m"
echo -e "\033[45;30m 紫底黑字 \033[0m"
echo -e "\033[46;30m 天蓝底黑字 \033[0m"
echo -e "\033[47;34m 白底蓝字 \033[0m"
echo -e "\033[4;31m 下划线红字 \033[0m"
echo -e "\033[5;31m 红字在闪烁 \033[0m"
echo -e "\033[8m 消隐 \033[0m "
```

![img](http://i1.fuimg.com/699855/056a6ebabb26b780.jpg)

```shell
RED_COLOR='\E[1;31m'  
YELOW_COLOR='\E[1;33m' 
BLUE_COLOR='\E[1;34m'  
RESET='\E[0m'

#需要使用echo -e
echo -e  "${RED_COLOR}===david say red color===${RESET}"
echo -e  "${YELOW_COLOR}===david say yelow color===${RESET}"
echo -e  "${BLUE_COLOR}===david say green color===${RESET}"
```

![img](http://i1.fuimg.com/699855/056a6ebabb26b780.jpg)

[原链接](https://blog.csdn.net/david_dai_1108/article/details/70478826)
