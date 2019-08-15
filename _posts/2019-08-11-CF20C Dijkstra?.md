---
layout: post
title: "CF20C Dijkstra?"
date: 2019-08-11
excerpt: "Dijkstra"
tags: [CodeForces]
comments: true
---

### 傻雕Linea 各种挂的日常

### 反手一波单向图见了祖宗

### 先是不开long long 紧接着单向图

### 想死QAQ

## 题目大意

## 给出一张图，请输出其中任意一条可行的从点 1 到点 n 的最短路径。

上代码

```cpp
#include <bits/stdc++.h>
#define maxn 1000001
#define ll long long
#define INF 9223372036854775807
using namespace std;
struct Node{ll u,v,c,nex;};Node e[maxn];
struct node{
    ll dis;
    ll pos;
    bool operator <( const node &x )const{return x.dis < dis;}
};
ll n,m,dis[maxn],head[maxn],ans[maxn];
bool vis[maxn];
ll flag,pos[maxn],cnt;
inline ll read(){
    ll x=0; char ch=getchar();
    while(!isdigit(ch)) ch=getchar();
    while(isdigit(ch)) x=(x<<3)+(x<<1)+ch-'0',ch=getchar();
    return x;
}
inline void add(ll u,ll v,ll c){
    cnt++;
    e[cnt].u = u;
    e[cnt].v = v;
    e[cnt].c = c;
    e[cnt].nex = head[u];
    head[u] = cnt;
}
priority_queue <node > q;
void Spfa(){
    for (ll i = 1;i <= n;++i)dis[i] = INF;
    dis[1] = 0;
    q.push((node){0,1});
    while (q.size()){
        node tmp = q.top();
        q.pop();
        ll u = tmp.pos,d = tmp.dis;
        if( vis[u] )continue;
        vis[u] = 1;
        for (ll i = head[u];i;i = e[i].nex){
            ll v = e[i].v;
            if (dis[u] + e[i].c < dis[v]){
    	       dis[v] = dis[u] + e[i].c;
                    q.push( ( node ){dis[v], v} );
                pos[v] = u;
            }
        }
    }
}
int main(){
    ios :: sync_with_stdio(false);
    n = read();m = read();
    for (ll i = 1;i <= m;++i){
        ll u,v,c;
        u = read();v = read();c = read();
        add(u,v,c);
        add(v,u,c);
    }
    Spfa();
    bool flag2=1; //判断能否找到起点 
    for(int i=n;i;i=pos[i]) //到着从终点找回去
    {
        ans[++flag]=i;
        if(i==1) //如果找到起点，更改判断变量 
          flag2=0;
    }

    if(flag2){
        cout<<-1; return 0;
    } //没有找到起点，输出"-1"

    for(int i=flag;i>=1;i--) //因为是倒着找回去的，所以要倒序输出 
      cout<<ans[i]<<" ";
    return 0;
}
```
