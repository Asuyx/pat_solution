# 【codeup 1928】日期差值

## 题意概述

两行日期，形式YYYYMMDD，求日期差值，若日期连续则为两天。

## 输入输出格式

输入两行日期YYYYMMDD。
输出日期差值。

## 数据规模

无

## 算法设计

令date1，date2存储两个日期，使date1<date2;(做判断，大于则交换。)
y1,y2,m1,m2,d1,d2存储年月日。
思路是这样的：d1++，若d1等于当前月份天数+1，则m1++，d1置1；若m1==13，year1++，直到y1==y2&&m1==m2&&d1==d2；
里面循环加个ans变量记录叠加天数，即是答案。

## C++代码

```cpp
#include<cstdio>
//利用二维数组存储平闰年的月份天数。
int month[13][2]={{0,0},{31,31},{28,29},{31,31},{30,30},{31,31},
{30,30},{31,31},{31,31},{30,30},{31,31},{30,30},{31,31}};
bool isleap(int year){ //bool而不是boolen
	return ((year%4==0&&year%100!=0)||year%400==0);
}
int main(){
	int date1,date2;
	int y1,y2,m1,m2,d1,d2;
	while(scanf("%d%d",&date1,&date2)!=EOF){
		if(date1>date2){
			int temp=date1;
			date1=date2;
			date2=temp;
		}
		y1=date1/10000;
		m1=date1/100%100;
		d1=date1%100;
		y2=date2/10000;
		m2=date2/100%100;
		d2=date2%100;
		int ans=1;
		while(y1<y2||m1<m2||d1<d2){
			d1++;
			if(d1==month[m1][isleap(y1)]+1){
				d1=1;
				m1++;
			}
			if(m1==13){
				y1++;
				m1=1;
			}
			ans++;
		}
		printf("%d\n",ans);
	}
	return 0;
}
```
