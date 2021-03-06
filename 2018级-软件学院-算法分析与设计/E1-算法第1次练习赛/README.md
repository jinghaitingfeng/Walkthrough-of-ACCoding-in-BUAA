# E1-算法第1次练习赛

# 妙妙趣排序

时间限制: 1000 ms 内存限制: 65536 kb

总通过人数: 136 总提交人数: 167

## 题面

本题中：

一个即将排好序的序列定义为：将这个序列去除至多一个值后，新序列是严格递增的。

一个过滤器[u,v]定义为：一个序列a经过过滤器[u,v]后，𝑎𝑢=𝑚𝑖𝑛(𝑎𝑢,𝑎𝑣)au=min(au,av),𝑎𝑣=𝑚𝑎𝑥(𝑎𝑢,𝑎𝑣)av=max(au,av)，其他值不变。

妙妙趣排序器由k个过滤器组成，一个序列的妙妙趣排序需要依次经过排序器的k个过滤器。

那么请问，1~n的全排列中，有几个序列经过给定的妙妙趣排序后可以变成即将排好序的序列。

## 输入

第一行一个正整数t表示数据组数(0<𝑡<1000<t<100)

接下来t组数据

每组数据第一行两个整数n，k (2≤𝑛≤50,0≤𝑘≤102≤n≤50,0≤k≤10)

每组数据接下来k行，每行两个整数u,v，表示一个过滤器(1≤𝑢<𝑣≤𝑛1≤u<v≤n)

## 输出

每组数据输出一行，一个整数

## 输入样例

```
4
4 0
4 1
1 2
4 3
1 2
2 3
1 2
4 6
1 2
2 3
1 2
3 4
2 3
1 2
```

## 输出样例

```
10
14
24
24
```

## 思路

**这道题基本上能看出是一个DFS回溯+剪枝的问题，除此之外应该别无其他做法了**

**首先需要知道即将排好的序列是什么——那很显然是已经排好的序列+所有有1个错位的序列**

**不难推出，所有即将排好的序列，其个数不会超过n^2，但是在生成所有序列的时候需要做到不重不漏，这个需要稍微注意一下**

**然后接下来我们需要从所有即将排好的序列往回进行回溯，所有的dfs回溯也就是O(2^k)的，主要就是保证如何不重不漏的搜索以及对错误情况进行剪枝**

**首先搜索的分支不难，经过这个过滤器之后的序列有两种可能，即依旧不变和两者交换了，只要顺着这两个分支搜索，肯定是能保证不重复不漏的**

**剪枝的情况主要是，一旦出现了经过这个过滤器之后的序列，两个数是逆序的，那么很明显就是非法序列，需要减掉**

**顺带注意一下corner case，当k=0的时候，答案就是所有即将排好的序列的个数**

