  

# 定积分的计算

## 通过定义的方法来计算

>**定积分的定义为**：设闭区间$[a,b]$上有$n-1$个点，依次为
>$$
>a=x_0<x_1<x_2<\cdots<x_{n-1}<x_n<b
>$$
>他们把$[a,b]$分成n个小区间$\Delta_i=[x_{i-1},x_i],i=1,2,\cdots,n$.这些闭子区间构成对区间$[a,b]$的一种分割，记为
>$$
>T=\{x_0,x_1,\cdots,x_n\}或\{\Delta_1,\Delta_2,\cdots,\Delta_n\}
>$$
>小区间$\Delta_i$的长度为$\Delta_i=x_i-x_{i-1}$,并记
>$$
>||T|| = \displaystyle \max_{1\le i\le n}\{\Delta_i\}
>$$
>称为分割T的模.
>
>***
>
>设$f$是定义在$[a,b]$上的一个函数，对于$[a,b]$的一个分割$T$，任取点$\xi_i\in\Delta_i,i=1,2,\cdots,n,$并做和式
>$$
>\sum_{i=1}^nf(\xi_i)\Delta_i
>$$
>
>称此和式为函数$f$在$[a,b]$上的一个**积分和**，也称**黎曼和**.
>
>***
>
>如果这个黎曼和在$||T||\to0$的时无限接近某个数，即$\exist J,\forall \varepsilon>0,\exist\delta>0$，对于$\forall T$，只要$||T||<\delta$,就有
>$$
>|\sum_{i=1}^nf(\xi_i)\Delta_i-J|<\varepsilon
>$$
>则称函数$f$在区间$[a,b]$上**可积**或**黎曼可积**；数$J$称为$f$在$[a,b]$上的**定积分**或**黎曼积分**，记作
>$$
>J=\int_a^bf(x)dx.
>$$
>其中，$f$称为**被积函数**，$x$称为**积分变量**，$[a,b]$被称为积分区间，a、b分别称为这个积分的上限和下限.

***

==也就是说，要求一个连续函数在某个区间上的定积分，只需要求一个极限。==

***

**例1：**求在区间$[0,1]$上，以抛物线$y=x^2$为曲边的曲边三角形的面积.

​	**解：**因为函数$y=x^2$在区间$[0,1]$连续，所以面积为
$$
S=\int_0^1x^2dx=\lim_{T\to0}\xi_i\Delta_{x_i}.
$$
为求得此极限，我们将$T$进行特殊分割，即等份分割：
$$
T=\{0,\frac1n,\frac2n,\cdots,\frac{n-1}n,1\},||T||=\frac1n
$$
并取$\xi_i=\frac{i-1}n\in[\frac{i-1}n,\frac in],i=1,2,\cdots,n.$则有
$$
S=\lim_{n\to\infty}\sum_{i=1}^n\left(\frac{i-1}n\right)^2\frac1n=\lim_{n\to\infty}\frac1{n^3}\sum_{i=1}^n\left(i-1\right)^2
$$

$$
=\lim_{n\to\infty}\frac{(n-1)n(2n-1)}{6n^3}=\frac13.
$$



## 通过几何方法来计算

>对于在区间$[a,b]$上连续的函数$f(x)$，当$f(x)\ge0，x\in[a,b]$时，定积分$\int^b_af(x)dx$的几何意义就是曲线$f(x)，x=a,x=b,x$轴所围成的曲边梯形的面积；当$f(x)\le0，x\in[a,b]$时，定积分$\int^b_af(x)dx$的几何意义就是位于x轴下方曲边梯形的相反数，不妨称之为“负面积”；对于一般有正有负的$f(x)$而言，定积分的值则是曲线$y=f(x)$在==x轴上方部分==的所有曲边梯形的面积**减去**在==x轴下方部分==所有曲边梯形面积的差值，简称“上减下”。

***

**例1：**求$\int_0^{2\pi} sinxdx$

​	**解：**$f(x)=sinx$在$[0,\pi]$的面积和在$[\pi,2\pi]$的面积相等，并且在$[0,\pi]$上$f(x)\ge0$，在$[\pi,2\pi]$上$f(x)\le0$，所以$\int_0^{2\pi} sinxdx = 0$

***

**例2：**求$\int_{-1}^1\sqrt{1-x^2}dx$

​	**解：**$f(x)=\sqrt{1-x^2}$在$[-1,1]$的图像是半个圆，而且都在x轴上方，所以面积为$S=\frac1  2\pi\times1^2=\frac12\pi$，所以$\int_{-1}^1\sqrt{1-x^2}dx=\frac12\pi$



## 特殊函数的定积分

**奇函数在区间$[-a,a]$上的定积分为0**

**偶函数在区间$[-a,a]$上的定积分是在区间$[0,a]$或在区间$[-a,0]$上定积分的二倍**

**例1：**求$I=\int_{-\pi}^{\pi}\sin x dx$

​	**解：**$f(x)=\sin x$是奇函数

​		所以$I=0$

**例2：**求$I= \int _{-\pi}^{\pi}\cos x dx$

​	**解：**$f(x)=\cos x$是偶函数

​		$I=\int_{-\pi}^{\pi}\cos x dx = 2\int_0^{\pi}\cos x dx = 2 \sin x \bigg|_0^{\pi}=0$

## 通过牛顿-莱布尼兹(Newton-Leibniz)公式来计算

>**定理：**若函数$f$在$[a,b]$上连续，并且存在原函数$F$，即$F'(x)=f(x),x\in[a,b]$，则$f$在$[a,b]$上可积，且
>$$
>\int_a^bf(x)dx=F(b)-F(a)
>$$
>上式称为**牛顿-莱布尼兹公式**，它也常写成
>$$
>\int_a^bf(x)dx=F(x)\bigg|^b_a.
>$$

通过牛莱公式我们可以很简单的求出某些初等函数在某个区间上的定积分

**例1：**求下列定积分

(1)$\int_a^bx^ndx$ (n为正整数)

(2)$\int_a^be^xdx$

(3)$\int_a^b\frac{dx}{x^2}$   ( $0<a<b$ )

(4)$\int_0^\pi \sin x dx$

(5)$\int_0^2x\sqrt{4-x^2}dx$



**解**

​	(1)$\int_a^bx^ndx=\frac{x^{n+1}}{n+1} \bigg|_a^b=\frac1{n+1}\left(b^{n+1}-a^{n+1}\right).$

​	(2)$\int_a^be^xdx=e^x \bigg|_a^b=e^b-e^a.$

​	(3)$\int_a^b\frac{dx}{x^2}=-\frac1x\bigg|_a^b=\frac1a-\frac1b.$

​	(4)$\int_0^\pi \sin x dx=-\cos x \bigg|_0^\pi=2.$

​	(5)先用不定积分法求出$f(x)=x\sqrt{4-x^2}$的一个原函数，再完成定积分的计算：
$$
\int x\sqrt{4-x^2}dx=-\frac12\int\sqrt{4-x^2}d\left(4-x^2\right)
$$

$$
=-\frac13\sqrt{\left(4-x^2\right)^3}+C
$$

$$
\int_0^2x\sqrt{4-x^2}=-\frac13\sqrt{\left(4-x^2\right)^3}\bigg|_0^2=\frac83.
$$

## 通过含参量积分来间接计算定积分

**例：**求$I=\int_0^1\frac{\ln (1+x)}{1+x^2}dx$

​	**解：**考虑含参量积分
$$
\phi(\alpha)=\int_0^1\frac{\ln{(1+\alpha x)}}{1+x^2}dx
$$
​	显然$\phi(0)=0,\phi(1)=I$，且$f(x)=\frac{\ln{(1+\alpha x)}}{1+x^2}$ 和$f'(x)$在$R=[0,1]\times[0,1]$上连续
$$
\phi'(\alpha)=\int_0^1\frac x{(1+x^2)(1+\alpha x)}dx
$$
​	因为
$$
\frac x{(1+x^2)(1+\alpha x)}=\frac1{1+\alpha^2}\left(\frac{a+x}{1+x^2}-\frac\alpha{1+\alpha x}\right),
$$
​	所以
$$
\phi'(\alpha)=\frac1{1+\alpha^2}\left(\int_0^1\frac\alpha{1+x^2}dx+\int_0^1\frac x{1+x^2}dx-\int_0^1\frac\alpha{1+\alpha x}dx\right)
$$

$$
=\frac1{1+\alpha^2}\left[\alpha\arctan x\bigg|_0^1+\frac12\ln (1+x^2)\bigg|_0^1-\ln (1+\alpha x)\bigg|_0^1\right]
$$

$$
=\frac1{1+\alpha^2}\left[\alpha \cdot \frac\pi4+\frac12 \ln 2 - \ln (1+\alpha) \right]
$$

因此
$$
\int_0^1 \phi'(\alpha)d\alpha=\int_0^1\frac1{1+\alpha^2}\left[\frac \pi4 \alpha + \frac 1 2 - \ln (1 + \alpha) \right]d\alpha
$$

$$
=\frac \pi 8 \ln (1+\alpha^2)\bigg|_0^1 + \frac 1 2 \ln2 \arctan\alpha \bigg|_0^1-\phi(1)
$$

$$
=\frac \pi 8 \ln 2 + \frac \pi 8 \ln 2 - \phi(1)
$$

$$
=\frac \pi 4 \ln 2 - \phi(1)
$$

另一方面
$$
\int_0^1\phi'(\alpha)d\alpha=\phi(1)-\phi(0)=\phi(1)
$$
所以$I=\phi(1)=\frac \pi 8 \ln 2$



