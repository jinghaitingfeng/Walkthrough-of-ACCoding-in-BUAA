# E6-士谔书院2017级程设基础训练第六次练习赛

# `A` 韩信点兵

时间限制：1000ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

汉高祖刘邦曾问大将韩信：“你看我能带多少兵？”

韩信斜了刘邦一眼说：“你顶多能带十万兵吧！”

汉高祖心中有三分不悦，心想：你竟敢小看我！“那你呢？”

韩信傲气十足地说：“我呀，当然是多多益善啰！”

刘邦心中又添了三分不高兴，勉强说：“将军如此大才，我很佩服。现在，我有一个小小的问题向将军请教，凭将军的大才，答起来一定不费吹灰之力的。”

韩信满不在乎地说：“可以可以。”

刘邦狡黠地一笑，传令叫来一小队士兵隔墙站队，刘邦发令：“每 aa 个人站成一排。”队站好后，小队长进来报告：“最后一排只有 xx 个人。”

刘邦又传令：“每 bb 个人站成一排。”小队长报告：“最后一排只有 yy 个人。”

刘邦再传令：“每 cc 个人站成一排。”小队长报告：“最后一排只有 zz 个人。”

刘邦转脸问韩信：“敢问将军，这队士兵最少有多少人？”假如你就是韩信，请快速算出结果。

## 输入

第一行，空格间隔的两个整数 a,xa,x。

第二行，空格间隔的两个整数 b,yb,y。

第三行，空格间隔的两个整数 c,zc,z。

1≤a,b,c≤100,1≤x<a,1≤y<b,1≤z<c1≤a,b,c≤100,1≤x<a,1≤y<b,1≤z<c。

数据保证**有解**。

## 输出

一个整数，表示满足条件的非 11 的最少人数

## 输入样例

```
5 3
7 2
9 5
```

## 输出样例

```
23
```

## 思路

本题数值范围非常小，所以暴力解法是可以的，只要从2开始枚举，直到取模完全符合上述条件即可

**正解是采用数论的中国剩余定理，但是需要注意如果答案是1，则还要加上3个数的最小公倍数**

# `B` 狐狸捉兔子

时间限制：1000ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

围绕着山底有 1010 个洞，狐狸要吃兔子，兔子说：“可以，但必须找到我，我就藏身于这十个洞中，你从 1010 号洞出发，先到 11 号洞找，第二次隔 11 个洞找，第三次隔 22 个洞找，以后如此类推，次数不限。”

但狐狸从早到晚进进出出了 10001000 次，仍没有找到兔子。请问兔子究竟藏在哪个洞里？输出兔子可能藏的山洞的编号。

## 输入

无

## 输出

输出兔子可能藏的洞，如果有多个，用空格分隔输出。

如果不存在这样的洞，输出 `"NIE"`（不含引号，注意大小写）。

## 输入样例

无

## 输出样例

无

## 思路

枚举即可，直接输出答案也行

# `C` 马鞍数

时间限制：1000ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

求一个 n×nn×n 矩阵中的马鞍数。马鞍数的特点是在它所在的行，它的值严格最小。在它所在的列，它的值严格最大。

## 输入

第一行一个整数 n(2≤n≤300)n(2≤n≤300)。

接下来 nn 行，每行 nn 个空格隔开的整数（均在 `int` 范围内），表示矩阵。

## 输出

如果不存在马鞍数，那么输出 `"NIE"`（不含引号，注意大小写）。

如果存在，那么输出三个空格隔开的正整数 x,y,vx,y,v，分别表示马鞍数所在行、列（从 11 开始编号），和其数值。

很容易证明马鞍数要么不存在，要么存在仅一个。

## 输入样例

```
3
1 4 8
6 7 9
5 1 3
```

## 输出样例

```
2 1 6
```

## 思路

枚举即可

# `D` 约瑟夫问题

时间限制：1000ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

设有 nn 个人围坐在一个圆桌周围，编号顺序从 11 到 nn。现从第 ss 个人开始报数，数到 mm 的人出列，然后从出列的**下一个人**重新开始报数，数到 mm 的人又出列。如此重复直到所有的人全部出列为止。

对于任意给定的 n,sn,s 和 mm，输出按出列次序得到的 nn 个人员的编号。

## 输入

三个空格间隔的整数 n,s,mn,s,m。1≤n,m≤102,1≤s≤n1≤n,m≤102,1≤s≤n。

## 输出

输出 nn 行，表示 nn 个人的出列序列。

## 输入样例

```
3 1 2
```

## 输出样例

```
2
1
3
```

## 思路

模拟即可

不过约瑟夫问题拥有更为高效的解法，读者可以自行查询

# `E` 蛇形矩阵

时间限制：1000ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

输入一个整数 nn，在 n×nn×n 的方阵里填入数字 1,2,3,...,n×n1,2,3,...,n×n 使之构成蛇形。

## 输入

一个正整数 nn。1≤n≤201≤n≤20。

## 输出

输出 nn 行，每行用空格隔开的 nn 个整数。

所有输出构成一个蛇形矩阵，最小元素在右上角，其余数字依次顺时针排列，具体要求见样例。

## 输入样例

```
4
```

## 输出样例

```
10 11 12 1
9 16 13 2
8 15 14 3
7 6 5 4
```

## 思路

本题主要是需要一个比较好的写法，直接利用转向即可

# `F` 子序列

时间限制：1000ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

给出两个数字序列 AA 和 BB，判断 BB 是否是 AA 的子序列。

是输出 `"TAK"`，不是输出 `"NIE"`（不含引号，注意大小写）。

我们设序列 A,BA,B 的长度分别为 n,mn,m，序列 BB 是 AA 的子序列，**当且仅当**存在下标序列 1≤i1<i2<⋯<im≤n1≤i1<i2<⋯<im≤n，满足对 ∀j∈[1,m]∀j∈[1,m]，有 Aij=BjAij=Bj。

## 输入

第一行两个空格隔开的整数 n,mn,m，分别表示序列 A,BA,B 的长度。1≤n,m≤1051≤n,m≤105。

第二行 nn 个空格隔开的整数，表示序列 AA。

第三行 mm 个空格隔开的整数，表示序列 BB。

序列中的数均在 `int` 范围内。

## 输出

见题目描述。

## 输入样例

```
7 4
1 2 3 2 1 2 1
1 2 1 1
```

## 输出样例

```
TAK
```

## 样例解释

**1** 2 3 **2** **1** 2 **1**

1 2 1 1

## 思路

没啥好说，直接遍历

