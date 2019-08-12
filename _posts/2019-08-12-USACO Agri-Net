---
layout: post
title: "USACO-Agri-Net"
date: 2019-8-12
excerpt: "Kruskal"
tags: [USACO]
comments: true
---

## 蒟蒻日常

### 因为不会将kruskal转成链式前向星向灌水区的dalao提问的日常

### 我太菜了

### %%%前缀自动机·宋(真dalao)

## 题目描述
### 约翰已经给他的农场安排了一条高速的网络线路，他想把这条线路共享给其他农场。为了用最小的消费，他想铺设最短的光纤去连接所有的农场。
### 你将得到一份各农场之间连接费用的列表，你必须找出能连接所有农场并所用光纤最短的方案。每两个农场间的距离不会超过100000

## 输入格式
### 第一行： 农场的个数，N（3<=N<=100）。
### 第二行..结尾: 后来的行包含了一个N*N的矩阵,表示每个农场之间的距离。理论上，他们是N行，每行由N个用空格分隔的数组成，实际上，他们限制在80个字符，因此，某些行会紧接着另一些行。当然，对角线将会是0，因为不会有线路从第i个农场到它本身。

## 输出格式
### 只有一个输出，其中包含连接到每个农场的光纤的最小长度。

### 在评论区的dalao的调教下终于~~改邪归正~~

### 我太蒟了

```cpp
#include <bits/stdc++.h>
#define maxn 200001
using namespace std;
struct node{
	int u,v,c,nxt;
}e[maxn];
int n,fa[maxn],ans;
inline int find(int u){
	if (fa[u] == u) return u;
	else return fa[u] = find(fa[u]);
}
bool cmp(node a,node b){
	return a.c < b.c;
}
int main(){
	cin >> n;int m = 0,k;
	for (int i = 1;i <= n;++i)
		for (int j = 1;j <= n;++j){
		cin >> k;
		if(i > j){
			m++;
			e[m].u = i;
			e[m].v = j;
			e[m].c = k;
		}
	}
	for (int i = 1;i <= n;++i)fa[i] = i;
	sort (e+1,e+m+1,cmp);
	for (int i = 1;i <= m;++i){
		int x = e[i].u,y = e[i].v;
		int fax = find(x),fay = find(y);
		if (fax == fay)continue;
		fa[fax] = fay;
		ans += e[i].c;
	}
	cout << ans;
}
```
