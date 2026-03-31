---
​---
title : Notes on Diffusion-Reaction Equations
author : Longxiao
​---
---

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
\lambda ^ 2 -c \lambda + 1 = 0
$$
$\Delta = c^2 - 4 \geq 0$, $\lambda = \frac{- c \pm \sqrt{c^2 - 4}}{2} > 0$ , is a stable node



For $(0,1)$
$$
\lambda ^ 2 -c \lambda - 1 = 0
$$
$\Delta = c^2 + 4 \geq 0$, $\lambda = \frac{- c \pm \sqrt{c^2 + 4}}{2}$ , is a saddle.

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

let$a=0.5$ to make it symmetric.


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
$\Delta = c^2 + 4a >0$
$$
\lambda^2-c\lambda-a=0
$$
$(0,0)$ is a saddle

$\Delta = c^2 + 4(1-a)>0$ $(1,0)$ is a saddle

$\Delta = c^2 - 4a(1-a)>0$ $(a,0)$is a stable node.

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

！ 对每个物种分别考虑！关键是a

# Two species






$$
\partial_t N_1 = \nabla^2_x N_1 + r N_1(1 - a N_1 - b N_2)\\
\partial_t N_2 = \nabla^2_x N_2 + r N_2(1 - a N_2 - b N_1)\\
$$

let $u = N_1+N_2$, $v=N_1-N_2$
$$
\partial_t u = \nabla^2_x u + r u - r a (N_1^2 + N_2^2) - 2 r b N_1 N_2\\
\partial_t v = \nabla^2_x v + r v - r a (N_1^2 - N_2^2)\\
$$

Notice the fact that $u^2 + v^2 = 2(N_1^2 + N_2^2)$, $u^2- v^2 = 4 N_1N_2$, $uv = N_1^2 - N_2^2$.
$$
\partial_t u = \nabla^2_x u + r u - \frac{1}{2} r a (u^2 + v^2) - \frac{1}{2} r b (u^2-v^2)\\
\partial_t v = \nabla^2_x v + r v - r a u v = \nabla^2_x v + r v ( 1 - a u)\\
$$
