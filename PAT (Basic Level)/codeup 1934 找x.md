# 【codeup 1934】找x

## 题意概述

输入一个数n，在接下来一行中输入n个数，用数组保存，在下一行中输入一个数x，输出x在数组中的下标,若找不到则输出-1。

## 输入输出格式

输入n，数组a存n个数，以及x。

## 数据规模

maxn=200

## 算法设计

遍历数组，寻找使得a[k]=x，k即为answer。

## C++代码

```cpp
#include<cstdio>
const int maxn=200;
int main(){
  int n,x;
  int a[maxn]={0};
  while(scanf("%d",&n)!=EOF){
  for(int i=0;i<n;i++)
    scanf("%d",&a[i]);
  scanf("%d",&x);
  /*
  int k;
  for(k=0;k<n;k++){
    if(a[k]==x){
      printf("%d\n",k);
      break;
    }
  }
  if(k==n)
    printf("-1\n");
  */
  int k=-1;
  for(int i=0;i<n;i++)
    if(a[i]==x){
      k=i;
      break;
    }
  printf("%d\n",k);
  }
  return 0;
}
```
