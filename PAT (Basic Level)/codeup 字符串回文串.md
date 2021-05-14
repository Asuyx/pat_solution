# 【codeup 字符串回文串】

## 题意概述

输入一行字符串，若是回文串则输出YES，否则输出NO。

## 输入输出格式

输入一行字符串

判断后输出YES或者NO

## 数据规模

字符串长度不超过255.

## 算法设计

用字符数组ch[256]来存储字符串，只需遍历一半字符串长度，len=strlen(ch),遍历len/2即可。
同时判断前一半与后一半字符是否相同，即i与len-1-i。

## C++代码

```cpp
#include<cstdio>
#include<cstring>
int main(){
	char ch[256];
	int i;
	while(scanf("%s",ch)!=EOF){
	int len=strlen(ch);
	for(i=0;i<len/2;i++)
		if(ch[i]!=ch[len-i-1])
			break;
	if(i==len/2)
		printf("YES");
	else
		printf("NO");
    }	
	return 0;
	
}
```
