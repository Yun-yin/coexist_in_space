
# Notes on Diffusion-Reaction Equations
author : Longxiao
$$
\frac{\partial u_i}{\partial t} = D_{i} \frac{\partial ^2 u_{i}}{\partial x^2} + f_i(\mathbf{u})
$$


$$
\partial_t u_{i} = D_{i} \nabla_{x}^{2}u_{i} + f_{i}(\mathbf{u})
$$


# One Species (Fisher-KPP Family)

## Fisher-KPP Equation


$$
\frac{\partial u}{\partial t} = D \frac{\partial ^2 u} {\partial x^2} + r u (1-au)
$$
let $u' = au$, $\tau=r a t$, $z = a \sqrt{\frac{r}{D}}x$,


$$
\frac{\partial u'}{\partial \tau} = \frac{\partial ^2 u'} {\partial z^2} +  u' (1-u')
$$
Now we focus on 
$$ {1}
\frac{\partial u}{\partial t} = \frac{\partial ^2 u} {\partial x^2} +  u (1-u)
$$
Assume a traveling wave solution, where the shape of $u(x,t)$ do not change. let $z = x-ct$,
$$
\frac{\mathrm{d}^2 u}{\mathrm{d} z^2} + c \frac{\mathrm{d} u}{\mathrm{d} z} + u(1-u) = 0
$$
$u = 0,1$ are two equilibrium of $f(u) = u (1-u)$.The solution will connect this two state. When $u \rightarrow 0$, assume the approximated solution around here is $u \approx e^{\lambda z}$, thus,
$$
\lambda ^2 + c \lambda + 1 =0
$$
 $\lambda = \frac{- c \pm \sqrt{c^2 - 4}}{2}$.  $u \rightarrow 0$ needs $\lambda <0$, which calls $c \geq 2$.

---

**Fisher's method**

let $p = \frac{\mathrm{d} u}{\mathrm{d} z}$,
$$
\frac{\mathrm{d}p} {\mathrm{d}u} = -c - \frac{u(1-u)}{p}
$$
assume 
$$
\frac{p}{u}|_{u\rightarrow0} = m
$$
then
$$
m = \frac{\mathrm{d}p} {\mathrm{d}u} = -c - \frac{u(1-u)}{p} \approx -c - \frac{1}{m}\\
m^2+cm+1 = 0
$$
has real roots only if $c^2\geq4$, thus $c \geq 2$.

---



Then we show the dynamics of $p\sim u$ on the phase plane, 
$$
\begin{cases}
\dot{u} = p\\
\dot{p} = -cp - u(1-u)
\end{cases}
$$
equilibrium are $(p^*,u^*) = (0,0), (0,1)$.
$$
\mathbf{J} = \begin{pmatrix}
-c & 2u-1\\
1 & 0
\end{pmatrix}
$$

$$
\mathbf{J}|_{(0,0)} = \begin{pmatrix}
-c & -1\\
1 & 0
\end{pmatrix}, 
\mathbf{J}|_{(0,1)} = \begin{pmatrix}
-c & 1\\
1 & 0
\end{pmatrix}
$$

For $(0,0)$
$$
\lambda ^ 2 -(-c) \lambda + 1 = 0
$$
$\Delta = c^2 - 4 \geq 0$, $\lambda = \frac{-c \pm \sqrt{c^2 - 4}}{2} > 0$ , is a stable node



For $(0,1)$
$$
\lambda ^ 2 - (-c) \lambda - 1 = 0
$$
$\Delta = c^2 + 4 \geq 0$, $\lambda = \frac{-c \pm \sqrt{c^2 + 4}}{2}$ , is a saddle.

There is a trajectory connecting these two equilibrium, from (0,0) to  (0,1). Let this curve be $p = \varphi (u)$,  then $\frac{\mathrm{d} u}{\mathrm{d} z}= \varphi (u)$, or $\frac{\mathrm{d} u}{\mathrm{d} x} = \varphi(u)$. Thus,
$$
x - x_{0} = \int_{u_{0}}^{u} \frac{1}{\varphi(u)} \mathrm{d}u
$$
and we will finally get $u(z)$.

As a result, the travelling wave solution for the PDE is the solution of the ODE with boundary condition 
$$
\lim_{z \rightarrow +\infty} u(z) = 0, \lim_{z \rightarrow -\infty} u(z) = 1
$$
To explore the shape, we may use small perturbation method. Assume $c \rightarrow \infty$, and let $\xi = z/c$,
$$
\frac{1}{c^2} \frac{\mathrm{d}^2 u}{\mathrm{d} \xi^2} + \frac{\mathrm{d} u}{\mathrm{d} \xi} + u(1-u) = 0
$$
We may assume the solution is in a form of series,
$$
u(\xi) = u_{0}(\xi) + \frac{1}{c^2}u_{1}(\xi) + \mathcal{O}(\frac{1}{c^4})
$$
then by the power of $c$, 
$$
\frac{\mathrm{d} u_{0}}{\mathrm{d} \xi} + u_{0}(1-u_{0}) = 0\\
\frac{\mathrm{d}^2 u_{0}}{\mathrm{d} \xi^2} + \frac{\mathrm{d} u_{1}}{\mathrm{d} \xi} + u_{1}( 1 - 2 u_{0} ) = 0
$$
If we assume $u(0) = 1/2$, then we also have $u_{0} = 1/2$, $u_{1} = 0$. Then we could solve them,
$$
u_{0} = \frac{1}{1 + e^{z/c}}\\
u_{1} = \frac{e^{z/c}}{\left( 1+ e^{z/c} \right)^2}\ln\left( \frac{4 e^{z/c}}{\left( 1+ e^{z/c} \right)^2} \right)
$$
$u \approx u_{0} + c^{-2} u_{1}$

This approximation fits well even $c = 2$.

## Allen-Cahn Equation 

$$
\frac{\partial u}{\partial t} = \frac{\partial ^2 u} {\partial x^2} +  u (1-u) (u-a)
$$


$$
\frac{\mathrm{d}^2 u}{\mathrm{d} z^2} + c \frac{\mathrm{d} u}{\mathrm{d} z} + u(1-u)(u-a) = 0
$$


$$
\begin{cases}
\dot{u} = p\\
\dot{p} = -cp - u(1-u)(u-a)
\end{cases}
$$

$$
\mathbf{J} = \begin{pmatrix}
-c & 3u^2 - 2(1+a)u +a \\
1 & 0 
\end{pmatrix}
$$

$$
\mathbf{J}|_{(0,0)} = \begin{pmatrix}
-c & a\\
1 & 0 
\end{pmatrix}, 
\mathbf{J}|_{(0,1)} = \begin{pmatrix}
-c & 1-a\\
1 & 0 
\end{pmatrix}
\mathbf{J}|_{(0,a)} = \begin{pmatrix}
-c & a(a - 1) \\
1 & 0 
\end{pmatrix}
$$
At $(0,0)$, $\mathrm{tr}(\mathbf{J})=-c<0$, $\det(\mathbf{J}) = -a<0$ , this node is a saddle. $\Delta = c^2 + 4a >0$

At $(1,0)$, $\mathrm{tr}(\mathbf{J})=-c<0$, $\det(\mathbf{J}) = -(1-a)<0$ , this node is a saddle. $\Delta = c^2 + 4(1-a)>0$ 

At $(a,0)$, $\mathrm{tr}(\mathbf{J})=-c<0$, $\det(\mathbf{J}) = -a(a-1) = a(1-a)>0$ , this node is stable. $\Delta = c^2 - 4a(1-a)$,  $\lambda = \frac{-c \pm \sqrt{c^2 - 4a(1-a)}}{2}$, could be stable node or spiral sink, depends on the value of $\Delta$.

As a result, the travelling wave solution only exist when a certain speed $c$ makes a trajectory connecting $(0,0)$ and $(1,0)$.



Considering the symmetry of $(0,0)$ and $(0,1)$ , we take the condition where $a= 1/2$. In order to have a trajectory connecting two states, $c=0$.

Then we solve the equation
$$
\frac{\mathrm{d}^2 u}{\mathrm{d} z^2} = u(1-u)(a-u)\\
\frac{\mathrm{d}^2 u}{\mathrm{d} z^2} = u^3 -(1+a)u^2 + au\\
\frac{1}{2}\left(\frac{\mathrm{d} u}{\mathrm{d} z}\right)^2 
= \frac{1}{4}u^4 - \frac{1+a}{3}u^3 + \frac{a}{2}u^2\\
2\left(\frac{\mathrm{d} u}{\mathrm{d} z}\right)^2 
= u^2(1-u)^2 \\
$$

$$
\frac{\mathrm{d} u}{\mathrm{d} z} = \frac{\sqrt{2}}{2} u(1-u) \\
\frac{1}{u(1-u)}\mathrm{d} u = \frac{\sqrt{2}}{2}\mathrm{d} z\\
\left(\frac{1}{u} + \frac{1}{1-u}\right)\mathrm{d} u = \frac{\sqrt{2}}{2}\mathrm{d} z\\
\ln{u} - \ln(1-u) = \frac{z}{\sqrt{2}}+C\\
\frac{u}{1-u} = e^{\frac{z}{\sqrt{2}}+C}\\
u = \frac{1}{1+e^{\frac{z}{\sqrt{2}}+C}}\\
u_{0} = 1/2 \Rightarrow C = 0\\
u = \frac{1}{1+e^{\frac{z}{\sqrt{2}}}}
$$


$$
\frac{\mathrm{d}p} {\mathrm{d}u} = -c - \frac{u(1-u)(u-a)}{p}\\
$$



A general way to considering this kind of equation is considering the potential energy.

We start from the ODE
$$
\frac{\mathrm{d}^2 u}{\mathrm{d} z^2} + c \frac{\mathrm{d} u}{\mathrm{d} z} + u(1-u)(u-a) = 0
$$
We hope to define such a function $E(u)$ as the energy of certain density $u$, such that
$$
\frac{\mathrm{d}E(u)}{\mathrm{d}t} \leq 0
$$
That is, $E(u)$ always decline to a lower value. Note here $t$ is just a assumed time for the evolution of $E$, not the time in the former PDE. Here, for example, we could assume $z$ in the equation is $t$. As a result, we try to find a $\frac{\mathrm{d}E}{\mathrm{d}z}$.

Note the following relation holds:
$$
\frac{\mathrm{d}^2 u}{\mathrm{d} z^2} \cdot \frac{\mathrm{d} u}{\mathrm{d} z} = \frac{1}{2}\cdot\frac{\mathrm{d}\left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2}{\mathrm{d}z}
$$


Thus, we multiply the derivative to the ODE:
$$
\left( \frac{\mathrm{d}^2 u}{\mathrm{d} z^2} + c \frac{\mathrm{d} u}{\mathrm{d} z} + u(1-u)(u-a) \right) \cdot \frac{\mathrm{d} u}{\mathrm{d} z}= 0\\
\frac{1}{2}\frac{\mathrm{d}}{\mathrm{d}z}\left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2 + c \left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2 + u(1-u)(u-a) \cdot \frac{\mathrm{d} u}{\mathrm{d} z} = 0
$$
let 
$$
f(u) = u(1-u)(u-a) = \frac{\mathrm{d}W}{\mathrm{d}u}
$$

$$
W(u) = \int u(1-u)(u-a) \mathrm{u} = - \frac{1}{4}u^4 + \frac{1+a}{3} u^3 - \frac{a}{2}u^2
$$

where $W(0) = 0$. $W(1) = \frac{1}{12} - \frac{a}{6}$

then
$$
\frac{1}{2}\frac{\mathrm{d}}{\mathrm{d}z}\left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2 + c \left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2 + u(1-u)(u-a) \frac{\mathrm{d} u}{\mathrm{d} z} = 0\\
\frac{1}{2}\frac{\mathrm{d}}{\mathrm{d}z}\left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2 + c \left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2 + \frac{\mathrm{d}W}{\mathrm{d}u} \cdot \frac{\mathrm{d} u}{\mathrm{d} z} = 0\\
\frac{1}{2}\frac{\mathrm{d}}{\mathrm{d}z}\left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2 + c \left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2 + \frac{\mathrm{d}W}{\mathrm{d} z} = 0
$$

$$
\frac{\mathrm{d}}{\mathrm{d}z} \left( \frac{1}{2}\left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2  + W \right) = - c \left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2 \leq 0
$$



We define 
$$
E(u) = \frac{1}{2}\left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2  + W(u)
$$
integral both side of the former equation
$$
\int_{-\infty}^{+\infty} \frac{\mathrm{d}}{\mathrm{d}z} \left( \frac{1}{2}\left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2  + W \right) \mathrm{d}z = 
\int_{-\infty}^{+\infty} - c \left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2 \mathrm{d}z\\

\left.\left( \frac{1}{2}\left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2  + W \right)\right|_{-\infty}^{+\infty} = 
- c \int_{-\infty}^{+\infty} \left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2 \mathrm{d}z\\
$$
the boundary condition is $\lim_{z \rightarrow +\infty} u(z) = 0, \lim_{z \rightarrow -\infty} u(z) = 1$ , we also assume $\lim_{z \rightarrow +\infty} u'(z) = 0, \lim_{z \rightarrow -\infty} u'(z) = 0$
$$
W(u(+\infty))-W(u(-\infty)) =- c \int_{-\infty}^{+\infty} \left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2 \mathrm{d}z\\
W(1)-W(0) =- c \int_{-\infty}^{+\infty} \left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2 \mathrm{d}z\\
$$

$$
c = \frac{W(0)-W(1)}{\int_{-\infty}^{+\infty} \left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2 \mathrm{d}z}
$$

When $a = \frac{1}{2}$, $W(0)=W(1)$, thus $c=0$. As a result, 
$$
\frac{\mathrm{d}^2 u}{\mathrm{d} z^2} = u(1-u)(0.5-u)
$$

$$
u = \frac{1}{1+e^{\frac{z}{\sqrt{2}}}}
$$

Also,
$$
\frac{\mathrm{d}}{\mathrm{d}z} \left( \frac{1}{2}\left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2  + W \right) = 0
$$
And 
$$
\frac{1}{2}\left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2  + W = 0\\
\frac{\mathrm{d} u}{\mathrm{d} z} = \sqrt{2W(u)} = \frac{\sqrt{2}}{2}u(1-u)
$$


Now for other $a\neq1/2$, we assume the shape of $u(z)$ might be the same. thus $\frac{\mathrm{d} u}{\mathrm{d} z} = \frac{\sqrt{2}}{2}u(1-u)$. put back to $c$,
$$
c = \frac{W(0)-W(1)}{\int_{-\infty}^{+\infty} \left( \frac{\mathrm{d} u}{\mathrm{d} z} \right)^2 \mathrm{d}z} 
=\frac{W(0)-W(1)}{\int_{1}^{0} \left( \frac{\mathrm{d} u}{\mathrm{d} z} \right) \mathrm{d}u} 
=(\frac{a}{6} - \frac{1}{12})\sqrt{2} \frac{1}{\int_{1}^{0} u(1-u) \mathrm{d}z} = \sqrt{2}(\frac{1}{2} - a)
$$




Assume:
$$
\dot{u} = ku(1-u)\\
\ddot{u} = k(1-2u)\cdot \dot{u} = k^2u(1-u)(1-2u)
$$

$$
\ddot{u} + c \dot{u} + u(1-u)(u-a) = 0
$$

$$
k^2u(1-u)(1-2u) + c ku(1-u) + u(1-u)(u-a) = 0\\
k^2 (u-3u^2+2u^3) + ck (u-u^2) -au + (1+a)u^2 -u^3 = 0\\
(2k^2-1)u^3 + (1+a-3k^2-ck)u^2 + (k^2+ck-a)u = 0
$$

we have 
$$
2k^2+1 = 0\\
1+a-3k^2-ck =0\\
k^2+ck-a = 0
$$
thus $k = \frac{\sqrt{2}}{2}$, nothing to do with $a$.

Then
$$
a-\frac{1}{2}-\frac{\sqrt{2}}{2}c = 0\\
\Rightarrow c = \sqrt{2}(a - \frac{1}{2})
$$
holds for any $a$.

# Two species

$$
\frac{\partial N_1}{\mathrm{d}t} = D_{1}\frac{\partial^2 N_1}{\partial x^2} + N_1 \left( r_1 - A_{1,1} N_1 - A_{1,2} N_2 \right)\\ 
\frac{\partial N_2}{\mathrm{d}t} = D_{2}\frac{\partial^2 N_2}{\partial x^2} + N_2 \left( r_2 - A_{2,2} N_2 - A_{2,1} N_1 \right)
$$



## Symmetry

We assume the condition where two species are exactly symmetric. The system could be simplified (as well as rescaled) as


$$
\partial N_{1} = \nabla^2 N_1 + r N_1(1 - N_1 - a N_2)\\
\partial N_{2} = \nabla^2 N_2 + r N_2(1 - N_2 - a N_1)
$$

let $u = N_1+N_2$, $v=N_1-N_2$
$$
\partial u = \nabla^2 u + r u - r (N_1^2 + N_2^2) - 2 r a N_1 N_2\\
\partial v = \nabla^2 v + r v - r (N_1^2 - N_2^2)\\
$$

Notice the fact that $u^2 + v^2 = 2(N_1^2 + N_2^2)$, $u^2- v^2 = 4 N_1N_2$, $uv = N_1^2 - N_2^2$.
$$
\partial_t u = \nabla^2_x u + r u - \frac{1}{2} r (u^2 + v^2) - \frac{1}{2} r a (u^2-v^2)\\
\partial_t v = \nabla^2_x v + r v - r u v = \nabla^2_x v + r v ( 1 - u)
$$
If the system is neutral, then $u = N_{1}+N_{2}$ is a constant (here equals to $1$), both $u$ and $v$ only change by dispersal.

When $a>1$, the system without dispersal is a bistable system, two stable points are $(u^*,v^*) = (1,0),(0,1)$.

Now let us assume that space is still nearly fully occupied, then
$$
u = 1 - \eta
$$
and
$$
\frac{v}{u} = \phi(x)
$$

$$
N_{1} = \frac{u}{2} (1+\phi)\\
N_{2} = \frac{u}{2} (1- \phi)
$$

$$
\partial_t u = \nabla^2_x u + r u - \frac{1+a}{2} r u^2 - \frac{1-a}{2} r v^2\\
$$

we might assume $\partial_t u = 0$ since the total population size is nearly a constant, and $\nabla^2_x u$= 0

since the space is fully occupied. then,
$$
\frac{1+a}{2}u^2 - u + \frac{1-a}{2}v^2 = 0\\
u^2 - \frac{2}{1+a}u + \frac{1-a}{1+a}v^2 = 0
$$
$u = \frac{1\pm\sqrt{1+(a^2-1)v^2}}{1+a}$.


$$
\partial v = \nabla^2 v + r v (1 - \frac{1\pm\sqrt{1+(a^2-1)v^2}}{1+a})
$$


This reaction term also has $3$ root $0,1,-1$, and also nearly the same shape of $kv(1-v)(1+v)$. 

We write the Taylor expansion of $f(v)/rv = (1 - \frac{1+\sqrt{1+(a^2-1)v^2}}{1+a})$
$$
\begin{aligned}
f(v)/rv &= (1 - \frac{1+\sqrt{1+(a^2-1)v^2}}{1+a})\\
&= \frac{a}{1+a} - \frac{1}{1+a} (1+(a^2-1)v^2)^{\frac{1}{2}}\\
&= \frac{a}{1+a} - \frac{1}{1+a} (1+\frac{(a^2-1)v^2}{2} + \mathcal{O}(v^4))\\
&\approx \frac{a-1}{a+1}-\frac{a-1}{2}v^2
\end{aligned}
$$

$$
\partial v = \nabla^2 v + \frac{r(a-1)}{a+1} v (1-\frac{a+1}{2}v^2)\\
\partial v = \nabla^2 v + \frac{(a-1)\sqrt{2(a+1)}}{(a+1^2)}r \sqrt{\frac{a+1}{2}}v (1-\frac{a+1}{2}v^2)
$$

also
$$
f'(v) = rv(1-a)v (1+(a^2-1)v^2)^{-\frac{1}{2}}+r(1 - \frac{1+\sqrt{1+(a^2-1)v^2}}{1+a})\\
=rv(1-a)\sqrt{\frac{1}{\frac{1}{v^2}+(a^2-1)}}+r(1 - \frac{1+\sqrt{1+(a^2-1)v^2}}{1+a})
$$

$$
f'(0) = \frac{(a-1)r}{1+a}
$$

for 
$$
g(v) = rkv(1-v^2)\\
g'(v) = rk(1-3v^2)\\
g'(0) = rk
$$
Thus we could approximately set $f(v)\approx r'v(1-v^2)$, where $r' = r\frac{a-1}{a+1}$

Thus, the shape of the interaction zone is
$$
u = \frac{1}{1+e^{\sqrt{\frac{r'}{2}}z}},r' = r\frac{a-1}{a+1}
$$






！ 对每个物种分别考虑！关键是a
