---
layout: post
title: " UVA10474 Where is the Marble? "
date: 2019-8-11
excerpt: "Find + Sort"
tags: [UVA,sort]
comments: true
---

# 前排高调官宣

# 不得不说这个题是我第一个A掉的UVA题，~~这题好水~~

## 前排嘲讽前缀自动机'宋各种WA

## 题目描述

### Raju and Meena love to play with Marbles. They have got a lot of marbles with numbers written on them. At the beginning, Raju would place the marbles one after another in ascending order of the numbers written on them. Then Meena would ask Raju to find the first marble with a certain number. She would count 1...2...3. Raju gets one point for correct answer, and Meena gets the point if Raju fails. After some fixed number of trials the game ends and the player with maximum points wins. Today it’s your chance to play as Raju. Being the smart kid, you’d be taking the favor of a computer. But don’t underestimate Meena, she had written a program to keep track how much time you’re taking to give all the answers. So now you have to write a program,which will help you in your role as Raju.

## Input

### There can be multiple test cases. Total no of test cases is less than 65. Each test case consists begins with 2 integers: N the number of marbles and Q the number of queries Mina would make. The next N lines would contain the numbers written on the N marbles. These marble numbers will not come in any particular order. Following Q lines will have Q queries. Be assured, none of the input numbers are greater than 10000 and none of them are negative. Input is terminated by a test case where N = 0 and Q = 0.

## Output
### For each test case output the serial number of the case. For each of the queries, print one line of output. The format of this line will depend upon whether or not the query number is written upon any of the marbles. The two different formats are described 

### below:

### • ‘x found at y’, if the first marble with number x was found at position y. Positions are numbered 1, 2, . . . , N.

### • ‘x not found’, if the marble with number x is not present.

## ~~以上自己去百度翻译~~

## 代码很简单

	```
	#include <bits/stdc++.h>
	#define maxn 10001
	using namespace std;
	int a[maxn],n,q,sum;
	inline int find(int x){
		for (int j = 1;j <= n;++j){
			if (x == a[j])return j;
		}
		return 0;
	}
	void init(){
		sum++;
		cout <<"CASE# " <<sum <<":"<<endl;
		for (int i = 1;i <= n;++i)cin >> a[i];
		sort (a+1,a+n+1);
		for (int i = 1;i <= q;++i){
			int x;
			cin >> x;
			if(!find(x))cout << x << " not found"<<endl;
			else cout << x << " found at " << find(x)<<endl;
		}
	}
	int main(){
		while(1){
			cin >> n >> q;
			if (n == 0 && q == 0)return 0;
			else init();
		}	
	}
```
