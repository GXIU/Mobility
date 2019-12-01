# Critical regimes driven by recurrent mobility patterns of reaction–diffusion processes in networks

Gómez-Gardeñes, J., Soriano-Paños, D. & Arenas, A. Critical regimes driven by recurrent mobility patterns of reaction–diffusion processes in networks. Nature Phys 14, 391–395 (2018) doi:10.1038/s41567-017-0022-7



本文的目的是做一个一般的微观Markovian模型来描述元人口的反应扩散机制。



## 模型

本文分析的基础是基于$SIS$模型的。染病和痊愈概率分别为$\lambda$和$\mu$。

两个基本假设是：

1. 每个人与一个社区是“相关的”
2. 我们强制让每个主体在访问某处之后回归原位。

给定总结点数$N$，每个点染病人的比例记为$\rho_i(t)$，那么它演化的规律就是：
$$
{\rho }_{i}(t+1)=(1-\mu ){\rho }_{i}(t)+\left(1-{\rho }_{i}(t)\right){\Pi }_{i}(t)\\
{\Pi }_{i}(t)=(1-{p}_{{\rm{d}}}){P}_{i}(t)+{p}_{{\rm{d}}}\sum _{j=1}^{N}\frac{{W}_{ij}}{\sum _{l=1}^{N}{W}_{il}}{P}_{j}(t)\\
{P}_{i}(t)=1-\prod _{j=1}^{N}{\left(1-\lambda {\rho }_{j}(t)\right)}^{{n}_{j\to i}}
$$
其中$\Pi_i(t)$代表未染病的人变成染病状态的概率。$p_d$是移动概率，$W_{ij}$是两个位置的交互比例，$P_i(t)$代表健康的个体在$i$处的比例。$i$处的有效人口记为${n}_{i}^{{\rm{eff}}}={\sum }_{j}{n}_{j\to i}$，其中${n}_{j\to i}={\delta }_{ij}\left(1-{p}_{{\rm{d}}}\right){n}_{i}+{p}_{{\rm{d}}}\frac{{W}_{ji}}{\sum _{l=1}^{N}{W}_{jl}}{n}_{j}$。

## 结果

我们希望导出系统的临界现象作为反应扩散方程的参数的函数。

第一个方程可以化简为$\mu\rho_i^* = (1-\rho_i^*)\Pi_i$。在这个临界点附近，疾病就是局部传播的，$\rho_i^*=\epsilon_i^*\ll 1,\forall i$。这使得这个简化的式子可以写成$\frac{\mu }{\lambda }{\epsilon }_{i}^{* }={({\bf{M}}{\vec{\epsilon }}^{* })}_{i}$。其中${M}_{ij}=\left[{\left(1-{p}_{{\rm{d}}}\right)}^{2}{\delta }_{ij}{n}_{j}+{p}_{{\rm{d}}}\left(1-{p}_{{\rm{d}}}\right){n}_{j}{\left({\bf{R}}+{{\bf{R}}}^{T}\right)}_{ij}+{p}_{{\rm{d}}}^{2}{n}_{j}{\left({\bf{R}}\cdot {{\bf{R}}}^{T}\right)}_{ij}\right]$，其中${R}_{ij}=\frac{{W}_{ij}}{{\sum }_{l=1}^{N}{W}_{il}}$。$M$中的每一个元代表位置$i$的一个人与$j$的所有人之间交互的平均强度。

化简到这个形式之后，就变成了一个特征值问题，即流行阈值$\lambda_c$，也就是保证上式成立的最小的$\lambda$是矩阵$M$的最大特征值的函数，
$$
{\lambda }_{{\rm{c}}}=\frac{\mu }{{\Lambda }_{{\rm{\max }}}({\bf{\text{M}}})}
$$
下面分析一些量之间的关系。



移动性参数$p_d$：不好分析。但是通过对特征值的扰动分析，可以得到特征值的表达式${\lambda }_{i}\approx {n}_{i}+2{p}_{{\rm{d}}}{n}_{i}\left({R}_{ii}-1\right)+{p}_{{\rm{d}}}^{2}\sum _{j\ne i}\frac{{n}_{j}{n}_{i}{\left({R}_{ij}+{R}_{ji}\right)}^{2}}{{n}_{i}-{n}_{j}}$。

根据我们对人口分布的知识，当移动性为$0$的时候，最大的特征值跟最大的人口数$n_\max$完全决定。移动性比较低的时候，上式第二项是负的，第三项是正的。那么临界点的特征就可以由最后两项的关系得到。

上式对于$p_d$是一个二次方程，有最小值
$$
{p}_{{\rm{d}}}^{* }=\frac{1-{R}_{{\rm{max,max}}}}{\sum _{j\ne {\rm{\max }}}\frac{{n}_{j}{\left({R}_{{\rm{\max }},j}+{R}_{j,{\rm{\max }}}\right)}^{2}}{{n}_{{\rm{\max }}}-{n}_{j}}}
$$
说明最大特征值总会随着$p_d$的减小而减小。所以临界点$\lambda_c$会增加。这表明移动性与疾病爆发的反向关系。这是一个很神奇的结果。