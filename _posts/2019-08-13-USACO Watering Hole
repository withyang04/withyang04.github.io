---
layout: post
title: "USACO Watering Hole"
date: 2019-08-13
excerpt: "Orz and Kruskal"
tags: [USACO]
comments: true
---
### QAQ 上午考试的题

### 正解是Kruskal

### 昨天刚练了~~(今天就WA了)~~

### 窝 汰 蔡 了

## 题目描述
### Farmer John has decided to bring water to his N (1 <= N <= 300) pastures which are conveniently numbered 1..N. He may bring water to a pasture either by building a well in that pasture or connecting the pasture via a pipe to another pasture which already has water.
### Digging a well in pasture i costs W_i (1 <= W_i <= 100,000).
### Connecting pastures i and j with a pipe costs P_ij (1 <= P_ij <= 100,000; P_ij = P_ji; P_ii=0).
### Determine the minimum amount Farmer John will have to pay to water all of his pastures.

## 输入格式
### 第1 行为一个整数n。第2 到n+1 行每行一个整数，从上到下分别为W_1 到W_n。第n+2 到2n+1 行为一个矩阵，表示需要的经费（P_ij）。

## 输出格式
### 只有一行，为一个整数，表示所需要的钱数。

### 数组开小见祖宗QAQQAQQAQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQAQ

```cpp
#include <bits/stdc++.h>
using namespace std;
const int maxn = 310000;
struct node{
	int u,v,c,nxt;
}e[maxn];
int n,ans,a,w[maxn],head[maxn],cnt = 0;
int fa[maxn];
inline void add_edge(int u,int v,int c){
	e[++cnt].u = u;
	e[cnt].v = v;
	e[cnt].c = c;
	e[cnt].nxt = head[u];
	head[u] = cnt;
}
inline int find(int u){
	if (fa[u] == u)return u;
	else return fa[u] = find(fa[u]);
}
void Kruskal(){
	for (int i = 0;i <= cnt;++i){
		int fax = find (e[i].u),fay = find (e[i].v);
		if (fax == fay)continue;
		fa[fax] =fay;
		ans += e[i].c;
	}
}
bool cmp (node a,node b){
	return a.c < b.c;
}
int main(){
	cin >> n;
	for (int i = 1;i <= n;++i){
	cin >> w[i];
	add_edge(i,0,w[i]);
	add_edge(0,i,w[i]);
	}
	for (int i = 1;i <= n;++i)
		for (int j = 1;j <= n;++j){
			cin >> a;
			if (i > j)
				add_edge(i,j,a);
		}
	for (int i = 1;i <= n;++i)fa[i] = i;
	sort (e,e+cnt+1,cmp);
	Kruskal();
	cout << ans;
	return 0;
}
```
