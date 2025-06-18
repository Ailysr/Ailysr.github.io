# 刚体飞行器运动方程
本章谈论飞行器的稳定性和操纵性。稳定性，即飞行器在受到外界的瞬时扰动后，自动地恢复到其原来的平衡状态的能力。操纵性指飞行器对驾驶员操纵或舵面指令输入的响应，即从一种飞行状态过渡到另一种飞行状态的能力。
为简化，做一些假设：

* 假设地球为平面大地，忽略地球的曲率和自转；
* 飞行器为刚体，不考虑机体弹性变形和旋转部件的影响；
* 大气为静止的标准大气，不考虑风的影响等。

飞行器作为刚体在空中的运动，一般有六个自由度，相应的有六个动力学方程，其中三个是描述质心的运动，还有三个描述飞行器绕质心的转动。另外，还有 六个运动学方程，用来描述飞行器在空间的位置和姿态的变化。
## 刚体飞行器动力学方程
### 飞行器质心平移的动力学方程
#### 任意动系的质心动力学方程 
利用理论力学的动量定理，在原点为飞行器质心的任意动坐标系$Oxyz$上投影，得到的质心动力学标量方程组如下：
$$
\begin{align}
m(\frac{dV_x}{dt}+V_zw_y-V_yw_z)=F_x \\
m(\frac{dV_y}{dt}+V_xw_z-V_zw_x)=F_y \\
m(\frac{dV_z}{dt}+V_yw_x-V_xw_y)=F_z
\end{align}
$$
式中，$(w_x,w_y,w_z)$是动系相对于惯性系的转动角速度在动系上的投影分量，$(F_x,F_y,F_z)$是作用在飞行器上外力的合力矢量在动系上的投影分量。
#### 航迹轴中的质心动力学方程
找出速度、角速度和合外力矢量在$Ox_ky_kz_k$上的投影，带入任意动系下的质心动力学方程（式1、2、3）中，可以得到


$$
\begin{align}
&m\frac{dV}{dt}=Tcos(\alpha+\varphi)-D-mgsin\gamma \\
&mVcos\gamma \frac{d\chi}{dt}=T[sin(\alpha+\varphi)sin\mu-cos(\alpha+\varphi )sin\beta cos\mu]+C cos\mu +Lsin \mu \\
& -mV\frac{d\gamma}{dt}=T[-sin(\alpha+\varphi)cos\mu-cos(\alpha+\varphi)sin\beta sin\mu]+Csin\mu -L cos\mu +mgcos\gamma
\end{align}
$$


#### 机体轴系中的质心动力学方程

同理可以得到如下方程：


$$
\begin{align}
& m\{\frac{dV_x}{dt}+V_z(\dot{\theta}cos\phi+\dot{\psi}sin\phi cos\theta)-V_y(-\dot{\theta}sin\phi +\dot{\psi}cos\phi cos\theta)\} \\
&=Tcos\varphi-Dcos\alpha cos\beta-Ccos\alpha sin\beta +Lsin\alpha -mgsin\theta \\

& m\{\frac{dV_y}{dt}+V_x(-\dot{\theta}sin\phi +\dot{\psi}cos\phi cos\theta)-V_z(\dot{\phi}-\dot{\psi}sin\theta)\} \\
&=-Dsin\beta +Ccos\beta+mgsin\phi cos\theta  \\

& m\{\frac{dV_z}{dt}+V_y(\dot{\phi}-\dot{\psi}sin\theta)-V_x(\dot{\theta}cos\phi+\dot{\psi}sin\phi cos\theta)\} \\
&=-Tsin\varphi -Dsin\alpha cos\beta  -Csin\alpha sin\beta -Lcos\alpha+mgcos\phi cos\theta
\end{align}
$$


在探讨飞行器大迎角、大机动运动特性的时候，利用气流系中$V$和机体轴系中的$u,v,w$的转换关系$L_{ba}=L(\alpha,\beta)$，即


$$
u=Vcos\alpha cos\beta\\
v=Vsin\beta\\
w=Vsin\alpha cos\beta
$$


相应地得到对时间的导数：


$$
\begin{align}
&\frac{du}{dt}=\frac{dV}{dt}cos\alpha cos\beta -\frac{d\alpha}{dt}V sin\alpha cos\beta -\frac{d\beta}{dt}Vcos\alpha sin\beta\\
&\frac{dv}{dt}=\frac{dV}{dt}sin\beta +\frac{d\beta}{dt}Vcos\beta\\
&\frac{dw}{dt}=\frac{dV}{dt}sin\alpha cos\beta+\frac{d\alpha}{dt}Vcos \alpha cos\beta-\frac{d\beta}{dt}Vsin\alpha \sin\beta
\end{align}
$$


### 飞行器绕质心转动的动力学方程

飞行器的总动量矩可以通过积分得到：


$$
h=\int r\times V \ dm=\int r\ dm\ \times V_o +\int r \ \times (w\times r)\ dm   
$$


当取坐标系原点为质心时，有，


$$
\int r\ dm=0
$$


飞行器的动量矩为：


$$
h=\int r\times (w\times r)\ dm
$$


由


$$
w=w_x i+w_y j+ w_z k\\
r=x i+ y j +z k
$$


带入化简得到：


$$
h_x=w_x I_x -w_y I_{xy} -w_z I_{zx}\\
h_y=w_y I_y -w_x I_{xy} -w_z I_{yz}\\
h_z=w_z I_z -w_x I_{zx} -w_y I_{yz}
$$


其中$I_x,I_y,I_Z,I_{xy},I_{yz},I_{zx}$代表的是惯性积。

#### 固连于飞行器的任意动系中绕质点转动动力学方程
类比加速度$\frac{dV}{dt}$，有动量矩的导数：
$$\frac{dh}{dt}=\frac{\delta h}{\delta t}+w\times h$$
由动量矩定理知，
$$\frac{dh}{dt}=M=\frac{\delta h}{\delta t}+w\times h$$
其中，$\frac{\delta h}{\delta t}$为动系的角速度$w=0$时的动量矩导数，称为动量矩的相对导数，用其投影表示为：
$$\frac{\delta h}{\delta t}=\frac{dh_x}{dt}i+\frac{dh_y}{dt}j+\frac{dh_z}{dt}k$$
而$w\times h$被称为动量矩的转换导数，是由于$w$的存在，动坐标系方向的改变所引起的动量矩变化，可以表示为：
$$
w\times h= 
\left|%也可以使用 \begin{vmatrix}\end{vmatrix}来表示行列式
\begin{matrix}
i & j& k\\
w_x&w_y&w_z\\
h_x&h_y&h_z
\end{matrix}
\right|
$$
带入动量矩导数的式子中，可以得到转动方程的标量形式：
$$
\begin{align}
\frac{dh_x}{dt}+(h_z w_y - h_y w_z)=M_x\\
\frac{dh_y}{dt}+(h_x w_z - h_z w_x)=M_y\\
\frac{dh_z}{dt}+(h_y w_x - h_x w_y)=M_z\\
\end{align}
$$
将$h_x,h_y,h_z$代入，得到飞机绕质心转动的动力学方程：
$$
\begin{align}
I_x \frac{dw_x}{dt}+(I_z-I_y)w_y w_z+I_{yz}(w_z^2-w_y^2)+I_{xy}(w_x w_z-\frac{dw_y}{dt})-I_{zx}(w_x w_y+\frac{dw_z}{dt})=M_x\\
I_y \frac{dw_y}{dt}+(I_x-I_z)w_x w_z+I_{zx}(w_x^2-w_z^2)+I_{yz}(w_x w_y-\frac{dw_z}{dt})-I_{xy}(w_y w_z+\frac{dw_x}{dt})=M_y\\
I_z \frac{dw_z}{dt}+(I_y-I_x)w_x w_y+I_{xy}(w_y^2-w_x^2)+I_{zx}(w_y w_z-\frac{dw_x}{dt})-I_{yz}(w_z w_x+\frac{dw_y}{dt})=M_z
\end{align}
$$
#### 机体轴系中绕质心转动动力学方程
机体系转动角速度在三个机体轴上的投影表示为$[p,q,r]^T$,外力矩在机体系中的投影表示为$[L,M,N]^T$，又因为对于一般的飞行器，$Ox_bz_b$平面通常为对称平面，故$I_{xy}=I_{yz}=0$：
$$
\begin{align}
I_x \frac{dp}{dt}+(I_z-I_y)qr-I_{zx}(pq+\frac{dr}{dt})=L\\
I_y \frac{dq}{dt}+(I_x-I_z)rp+I_{zx}(p^2-r^2)=M\\
I_z \frac{dr}{dt}+(I_y-I_x)pq+I_{zx}(qr-\frac{dp}{dt})=N
\end{align}
$$
特别的，当飞行器为轴对称飞行器时，通常$I_{zx}$也为零，从而：
$$
\begin{align}
I_x \frac{dp}{dt}+(I_z-I_y)qr=L\\
I_y \frac{dq}{dt}+(I_x-I_z)rp=M\\
I_z \frac{dr}{dt}+(I_y-I_x)pq=N
\end{align}
$$
## 刚体飞行器运动学方程
### 飞行器质心运动学方程
若动系在航迹轴系上，得到$[V,\chi,\gamma]$后，利用转换矩阵$L_{gk}$可以得到速度在地面系上的投影$[V_x,V_y,V_z]$，通过对速度进行积分，得到质心位置在空间的变化规律，即运动轨迹。*略*
### 飞行器绕质心转动运动学方程
飞行器在空间的姿态是通过机体轴系相对于地面轴系的三个欧拉角$（\psi,\theta,\phi）$。下面介绍两种建立转动动力学方程的方法。
欧拉角表示法：直接导出欧拉姿态角变化规律的方程；
四元数表示法：简介导出姿态角变化的方程。
#### 欧拉角表示法
从机体系得形成过程可知，$\psi$是由沿着$z_g$轴得角速度$\frac{d\psi}{dt}$形成的；$\theta$是由沿$y^‘$轴的角速度$\frac{d\theta}{dt}$形成的；$\phi$是由沿着 $x_b$轴的角速度$\frac{d\phi}{dt}$形成的，由此可以写出旋转角速度在机体轴上的投影为：
$$
\begin{bmatrix}
p\\q\\r 
\end{bmatrix}=
\begin{bmatrix}
\dot{\phi} \\ 0 \\ 0 
\end{bmatrix}+
\begin{bmatrix}
0 \\ \dot{\theta}cos\phi \\ -\dot{\theta}sin\phi
\end{bmatrix}+
L_{bg}
\begin{bmatrix}
0 \\ 0 \\ \dot{\psi} 
\end{bmatrix}
$$
展开后得到：
$$
\begin{align}
&p=\dot{\phi}-\dot{\psi}sin\theta\\
&q=\dot{\theta}cos\phi +\dot{\psi}sin\phi cos\theta\\
&r=-\dot{\theta}sin\phi +\dot{\psi}cos\phi cos\theta
\end{align}
$$
求解上述方程组得到：
$$
\begin{align}
&\frac{d\phi}{dt}=p+tan\theta\ (q sin\phi+rcos\phi)\\
&\frac{d\theta}{dt}=qcos\phi -r sin\phi\\
&\frac{d\psi}{dt}=\frac{1}{cos\theta}(qsin\phi +r cos\phi)
\end{align}
$$
可以看出，当$\theta=\pm\ \pi/2$时，$\frac{d\phi}{dt}$和$\frac{d\psi}{dt}$会变为无穷大。即，当飞行器进行大机动飞行时，俯仰角$\theta$接近$\pi/2$,方程会出现奇异点，仿真计算或飞行模拟会被迫中断。

为了避免这种奇异的情况，可采用四元数法来描述绕质心转动的运动学方程。

#### 四元数表示法
四元数表示法的原理是，设想同原点的坐标系$S_a$和$S_b$，总能够通过绕某一固定轴$OR$转动一个角度$\sigma$，使得两个坐标系重合。该转轴与空间坐形成三个角度$A,B,C$，于是定义四元数为：
$$
e_0=\cos \frac{\sigma}{2}\\
e_1=\cos A \sin \frac{\sigma}{2}\\
e_2=\cos B \sin \frac{\sigma}{2}\\
e_3=\cos C \sin \frac{\sigma}{2}\\
$$
且，四元数之间还需要满足约束条件：
$$e_0^2+e_1^2+e_2^2+e_3^2=1$$
利用转轴$OR$和坐标轴$S_a$和$S_b$的关系，可以得到坐标系间的转换矩阵：
$$
L_{ba}=
\begin{bmatrix}
e_0^2 +e_1^2 -e_2^2 -e_3^2  & 2(e_1 e_2 +e_0 e_3) & 2(e_1 e_3 -e_0 e_2)\\
2(e_1 e_2 -e_0 e_3) & e_0^2 -e_1^2 +e_2^2 -e_3^2 & 2(e_2 e_3 +e_0 e_1)\\
2(e_0 e_2+e_1 e_3) &2(e_2 e_3 -e_0 e_1) &e_0^2 -e_1^2 -e_2^2 +e_3^2 
\end{bmatrix}
$$
**相关推导**\
假设四元数$v=[s,\bf{v}] $，$q=[\cos \frac{\theta}{2},\sin \frac{\theta}{2} \bf{u}]$，则$v^1=qvq^*$表示的是将$\bf{v}$以$\bf{u}$为旋转轴，旋转$\theta$。
相当于乘以$L(q)$和$R(q^*)$，即
$$
L(q)R(q^*)v=
\begin{bmatrix}
a &-b& -c& d\\
b &a &-d &c\\
c &d &a &-b\\
d &-c &b &a
\end{bmatrix}\cdot
\begin{bmatrix}
a &b &c &d\\
-b&a &-d &c\\
-c&d&a&-b\\
-d&-c&b&a
\end{bmatrix}\cdot
v
$$
化简得，矩阵的外圈除了（1，1）为1，均为0，所以保留剩下的三行三列和$\bf{v}$相乘。从而得到四元数旋转矩阵。

$$
e_0=\cos \left(\frac{\varphi}{2}\right) \cos \left(\frac{\theta}{2}\right) \cos \left(\frac{\psi}{2}\right)+\sin \left(\frac{\varphi}{2}\right) \sin \left(\frac{\theta}{2}\right) \sin \left(\frac{\psi}{2}\right) \\
e_1=\cos \left(\frac{\varphi}{2}\right) \sin \left(\frac{\theta}{2}\right) \cos \left(\frac{\psi}{2}\right)+\sin \left(\frac{\varphi}{2}\right) \cos \left(\frac{\theta}{2}\right) \sin \left(\frac{\psi}{2}\right) \\
e_2=\cos \left(\frac{\varphi}{2}\right) \cos \left(\frac{\theta}{2}\right) \sin \left(\frac{\psi}{2}\right)-\sin \left(\frac{\varphi}{2}\right) \sin \left(\frac{\theta}{2}\right) \cos \left(\frac{\psi}{2}\right) \\
e_3=\sin \left(\frac{\varphi}{2}\right) \cos \left(\frac{\theta}{2}\right) \cos \left(\frac{\psi}{2}\right)-\cos \left(\frac{\varphi}{2}\right) \sin \left(\frac{\theta}{2}\right) \sin \left(\frac{\psi}{2}\right)
$$
又根据，地面系$S_g$和机体系$S_b$的欧拉角转换矩阵
$$
\begin{bmatrix} 
cos\theta cos\psi &sin\theta sin\phi cos\psi-cos\phi sin\psi &sin\theta cos\phi cos\psi+sin\phi sin\psi -sin\phi cos\psi\\
cos\theta sin\psi &sin\theta sin\phi sin\psi+cos\phi cos\psi & sin\theta cos\phi \sin\psi\\
-sin\theta & sin\phi cos\theta & cos\phi cos\theta  
\end{bmatrix}
$$
由对应关系可以得到，
$$
\cos \theta \cos\psi=e_0^2 +e_1^2 -e_2^2 -e_3^2\\
\cos \theta \sin\psi=2(e_1e_2+e_0e_3)\\
-\sin\theta =2(e_1 e_3 -e_0 e_2)\\
\sin\theta \sin \phi \cos\psi-\sin\psi \cos \phi =2(e_1 e_2 -e_0e_3)\\
\sin\theta \sin \phi \sin\psi +\cos \psi \cos\phi =  e_0^2 -e_1^2 +e_2^2 -e_3^2\\
\cos \theta \sin\phi =2(e_2 e_3 +e_0 e_1)\\
\sin\theta \cos \phi \cos\psi +\sin\psi \sin\phi =2(e_0 e_2+e_1 e_3) \\
\sin\theta \cos\phi \sin\psi -\cos \psi \sin\phi=2(e_2 e_3 -e_0 e_1) \\
\cos\theta \cos\phi =e_0^2 -e_1^2 -e_2^2 +e_3^2
$$
通过对四元数对欧拉角的表达式进行求导，得到
$$
\dot{\mathbf{e}}(t)=\left[\begin{array}{l}
\dot{e}_{0}(t) \\
\dot{e}_{1}(t) \\
\dot{e}_{2}(t) \\
\dot{e}_{3}(t)
\end{array}\right]=\frac{1}{2}\left[\begin{array}{cccc}
0 & r(t) & -q(t) & p(t) \\
-r(t) & 0 & p(t) & q(t) \\
q(t) & -p(t) & 0 & r(t) \\
-p(t) & -q(t) & -r(t) & 0
\end{array}\right]_{B}\left[\begin{array}{l}
e_{0}(t) \\
e_{1}(t) \\
e_{2}(t) \\
e_{3}(t)
\end{array}\right]
$$
通过对上述方程积分，得到$e_0(t),e_1(t)\dots$，利用其和欧拉角关系，得到飞行器的俯仰角$\theta$，滚转角$\phi$和偏航角$\psi$
$$
\theta =\arcsin [-(e_1e_3-e_0e_2)]\\
\phi = \arccos [\frac{e_0^2 -e_1^2 -e_2^2 +e_3^2}{\sqrt{1-4(e_1 e_3-e_0e_2)^2}}]\  \text{sgn}[2(e_2 e_3 +e_0 e_1)]\\
\psi = \arccos[\frac{e_0^2 +e_1^2 -e_2^2 -e_3^2}{\sqrt{1-4(e_1 e_3-e_0e_2)^2}}]\  \text{sgn}[2(e_1 e_2 +e_0 e_3)]
$$
用四元数求欧拉角，当$\theta =\pi/2$时，不会出现奇异的情况。

## 刚体飞行器运动方程讨论
### “机体-机体体系”运动方程组
质心运动和绕质心转动运动都在机体轴系上投影的方程组，简称为 **“机体-机体体系运动方程组”**，共由12个方程组成：


$$
\begin{align}

 &m\{\frac{dV_x}{dt}+V_z(\dot{\theta}cos\phi+\dot{\psi}sin\phi cos\theta)-V_y(-\dot{\theta}sin\phi +\dot{\psi}cos\phi cos\theta)\} 
=Tcos\varphi-Dcos\alpha cos\beta-Ccos\alpha sin\beta +Lsin\alpha -mgsin\theta \\

 &m\{\frac{dV_y}{dt}+V_x(-\dot{\theta}sin\phi +\dot{\psi}cos\phi cos\theta)-V_z(\dot{\phi}-\dot{\psi}sin\theta)\} 
=-Dsin\beta +Ccos\beta+mgsin\phi cos\theta  \\

 &m\{\frac{dV_z}{dt}+V_y(\dot{\phi}-\dot{\psi}sin\theta)-V_x(\dot{\theta}cos\phi+\dot{\psi}sin\phi cos\theta)\} 
=-Tsin\varphi -Dsin\alpha cos\beta  -Csin\alpha sin\beta -Lcos\alpha+mgcos\phi cos\theta\\

&I_x \frac{dp}{dt}+(I_z-I_y)qr-I_{zx}(pq+\frac{dr}{dt})=L\\
&I_y \frac{dq}{dt}+(I_x-I_z)rp+I_{zx}(p^2-r^2)=M\\
&I_z \frac{dr}{dt}+(I_y-I_x)pq+I_{zx}(qr-\frac{dp}{dt})=N\\
&\frac{dx_g}{dt}=u cos\theta cos\psi+v(sin\theta sin\phi cos\psi -cos\phi sin\psi)+w(sin\theta cos\phi cos\psi +sin\phi sin\psi)\\
&\frac{dy_g}{dt}=u cos\theta sin\psi+v(sin\theta sin\phi sin\psi +cos\phi cos\psi)+w(sin\theta cos\phi sin\psi -sin\phi cos\psi)\\
&\frac{dz_g}{dt}=-u sin\theta +v sin\phi cos\theta +wcos\phi sin\theta\\
&\frac{d\phi}{dt}=p+tan\theta\ (q sin\phi+rcos\phi)\\
&\frac{d\theta}{dt}=qcos\phi -r sin\phi\\
&\frac{d\psi}{dt}=\frac{1}{cos\theta}(qsin\phi +r cos\phi)
\end{align}
$$



通过对方程及其外力、外力矩的观察分析，方程中未知数有$(u,v,w),(V,\alpha,\beta),(p,q,r),(x_g,y_g,z_g),(\phi,\theta,\psi),(\delta_a,\delta_r,\delta_e,\delta_p)$共计19个。 考虑到前两组参数标配的是同一组速度矢量，去掉3个，仍然有16个未知数，因此为了求解这组方程，还需要给出4个附加关系式。

### "航迹-机体体系"运动方程组
这组方程其质心运动在航迹轴系上投影，绕质心的转动运动在机体轴系上投影，故称为“航迹-机体体系运动方程组”
方程有12个，其未知数有

$(V,\chi,\gamma),(p,q,r),(\alpha,\beta,\mu),(x_g,y_g,z_g),(\phi,\theta,\psi),(\delta_a,\delta_r,\delta_e,\delta_p)$

共计19个。由于引入了两套坐标轴系，其中的8个角度

$(\phi,\theta,\psi,\alpha,\beta,\mu,\chi,\gamma)$

并不是相互独立的，如确定$(\phi,\theta,\psi)$的飞行器的姿态角以及$(\alpha,\beta)$的飞行器相对于气流的关系，则可以确定气流系相对空间的方位$(\mu,\chi,\gamma)$，即其中5个角度是独立变量。
利用转换矩阵的传递性质，有：
$$L_{ba}L_{ak}=L_{bg}L_{gk}$$
可以得到，3个几何关系式，未知数仍然比方程多4个，因此，仍然需要增加4个附加关系才能求解这组方程。


### 飞行力学的几类问题
#### 飞行器本体的稳定性和操纵性

#### 带自动器飞行器的系统稳定性和操纵性
在飞行器上装有飞控系统，操纵机构的运动参数和飞行器的运动参数有关。此时操纵机构的运动规律被称为自动器调节规律，飞行器的状态将有描述自动器动力学方程和飞机动力学方程联立求解。如机体-机体体系运动方程组可以表示为矢量形式：


$$
\begin{equation}
\frac{\mathrm{d} \boldsymbol {x} }{\mathrm{d} t}=\boldsymbol{F(x,\delta)}
\end{equation}
$$


式中，状态变量$\boldsymbol{x}=[u,v,w,p,q,r,\phi,\theta,\psi,x_g,y_g,z_g,]^T$，操纵变量$\boldsymbol{\delta}=[\delta_a,\delta_r,\delta_e,\delta_p]$。\
自动器运动方程组可写为：


$$
\begin{equation}
\frac{\mathrm{d} \boldsymbol {\delta} }{\mathrm{d} t}=\boldsymbol{G(x,\dot{x},\delta,d)}
\end{equation}
$$


式中$\boldsymbol d=[d_a,d_r,d_e,d_p]^T$为操纵指令矢量。当忽略掉系统的惯性、阻尼和非线性因素后，自动器方程组可以简化为：


$$
\begin{equation}
\boldsymbol {\delta}=\boldsymbol{G(x,\dot{x},d)}
\end{equation}
$$


联立式(46)和式(47)或式(48)，可以研究干扰信号和指令信号输入下的动态响应，即系统的稳定性和操纵性

#### 飞行力学逆问题
指，给定飞行器某些运动参数变化规律后，求出其所需的操纵机构运动参数变化规律。这类问题在飞行力学优化问题中时常遇到，如实现最优轨迹或最佳机动来设计舵面的控制规律等。
### 多操纵机构情况
现代飞行器引入推力矢量控制、直接力控制的附加舵面等，操纵量有所增加，为求解方程，需要增加附加关系。
## 运动方程组线性化
上述章节给出的运动方程组是变系数、非线性的方程，一般情况下得不到解析解，只能用数值解法。这样就不容易找出带有普遍意义的一般规律。\
为了方便研究飞行器的稳定性和操纵性，最常利用的是“小扰动”假设，将微分方程线性化，通常称为“小扰动法”。这样就可能用解析法求解，并从中归纳出普遍规律，确定飞行品质标准。

### 小扰动法
#### 基本概念
研究飞行器的稳定性和操纵性问题时，一般把飞行器的运动分为基准运动和扰动运动。\
基准运动是指，在理想条件下，飞行器不受任何外界的干扰，按照规律进行的运动，如定长平飞、定常盘旋等。基准运动参数上标“\*”表示，如$V_*,\alpha_*,\theta_*$等。\
由于各种干扰因素，使得飞行器的运动参数偏离了基准运动参数，因而运动不按预定的规律进行，这种运动被称为扰动运动。受扰运动的参数，不带任何标记，$V,\alpha,\theta$等。\
与基准运动差别甚小的扰动被称为小扰动运动。小扰动简化后的方程可以给出足够满意的结果，原因如下：

* *在大多数的飞行情况下，各主要气动参数的变化与扰动量成线性关系*；
* *飞行中即使遇到相当强烈的扰动，在有限的时间内飞行器的线速度和角速度也往往只有很小的变化量*。

#### 基本假设
**为了便于将线性扰动运动方程组分解为彼此独立的两组，即横向和纵向小扰动方程组，以减少方程的阶次而解析求解**，还需要做出以下假设：

* 飞行器具有对称平面（气动外形和质量分布均对称），且略取机体内转动部件的陀螺力矩效应；
* 在基准运动中，对称平面处于铅锤位置（即$\phi=0$），且运动所在平面与飞行器对称平面相重合（即$\beta=0$）。

在上述条件下，可以推论出：纵向气动力和力矩对横侧参数在其基准运动状态下的导数（$\left. \frac{\partial L}{\partial \beta} \right|_*,\left. \frac{\partial M}{\partial p} \right|_*$）均为零。

#### 线性化方法
飞行器的任意一个运动方程可以表示为下列的一般形式：
$$
f(x_1,x_2,\cdots,x_n)=0
$$
式中，$(x_1,x_2,\cdots,x_n)$可以是运动参数或它们的导数，可以表示为基准运动$x_{i*}$和$\Delta x_i$之和：
$$
x_i=x_{i*}+\Delta x_i
$$
故任意运动方程可以写为：
$$
f(x_{1*}+\Delta x_1,x_{2*}+\Delta x_2,\cdots,x_{n*}+\Delta x_n)=0
$$
在基准点$(x_{1*},x_{2*},\cdots,x_{n*})$处展开泰勒级数，根据小扰动假设，略去二阶以上各阶小量，得到：
$$
f(x_{1*},x_{2*},\cdots,x_{n*})+\left( \frac{\partial f}{\partial x_1}\right)_*\Delta x_1+\left( \frac{\partial f}{\partial x_2}\right)_*\Delta x_2
+\cdots +\left( \frac{\partial f}{\partial x_n}\right)_*\Delta x_n =0
$$
显然，基准运动也满足运动方程，故：
$$
f(x_{1*},x_{2*},\cdots,x_{n*})=0
$$
从而得到：
$$
\left( \frac{\partial f}{\partial x_1}\right)_*\Delta x_1+\left( \frac{\partial f}{\partial x_2}\right)_*\Delta x_2
+\cdots +\left( \frac{\partial f}{\partial x_n}\right)_*\Delta x_n =0
$$
这是由非线性方程简化得到的一个线性化方程，或称线性小扰动方程。方程中，$\Delta x_1,\Delta x_2,\cdots,\Delta x_n$为变量，$\left( \frac{\partial f}{\partial x_1}\right)_*(i=1,2,\cdots,n)$为基准运动状态确定的导数，一般是通过理论和实验的方法已经确定的物理量。\
如果，基准运动是定常运动（运动参数不随时间改变），则上述线性化小扰动方程是常系数的；如果，基准运动非定常，则上述方程为变系数，常采用“系数冻结法”，将其转化为常系数线性微分方程【在基准运动轨迹上，选择特征点--一般为运动参数变化激烈的点】
### 运动方程的线性化
按习惯，研究飞行器的稳定性和操纵性所用的小扰动线性化方程常选用**两种坐标系**的方法，质心运动中的升力和阻力方程在风轴坐标系上建立；而质心运动中侧力方程和绕质心运动中的力矩方程均在机体轴坐标系上建立。
由于在两种坐标系中所得到的俯仰力矩方程相同，因此可以讲，纵向小扰动运动方程是相对于风轴系的，而横侧小扰动运动方程是相对于机体轴系的。
$$
m\frac{\mathrm{d}\Delta V}{\mathrm{d}t}=\Delta T \cos (\alpha_* +\varphi) \cos\beta_* -T_* \sin(\alpha_* +\varphi)\cos\beta_* \Delta\alpha - T_* \cos(\alpha_* +\varphi)\sin\beta_* \Delta\beta -\Delta D -mg \cos \gamma_* \Delta \gamma
$$
利用小扰动假设，其基准状态$\beta_*=0$，带入$\Delta T$ 和$\Delta D$的表达式，得到
$$
\begin{equation}
m\frac{\mathrm{d}\Delta V}{\mathrm{d}t}=(T_V \Delta V +T_H \Delta H +T_{\delta_ p} \Delta \delta_p) \cos (\alpha_* +\varphi)-T_* \sin(\alpha_* +\varphi) \Delta\alpha -(D_V \Delta V +D_H \Delta H +D_{\alpha}\Delta \alpha+D_{\delta _e}\Delta \delta_e)-mg \cos \gamma_* \Delta \gamma 
\end{equation}
$$
同理，得到以下的方程：
$$
\begin{equation}
m V_{*} \frac{\mathrm{d} \Delta \gamma}{\mathrm{d} t}=  \left(T_{V} \Delta V+T_{H} \Delta H+T_{\delta_{\mathrm{p}}} \Delta \delta_{\mathrm{p}}\right) \sin \left(\alpha_{*}+\varphi\right)+T_{*} \cos \left(\alpha_{*}+\varphi\right) \Delta \alpha+ 
 \left(L_{V} \Delta V+L_{H} \Delta H+L_{\alpha} \Delta \alpha+L_{\dot{\alpha}} \Delta \dot{\alpha}+L_{q} \Delta q+L_{\delta_{\mathrm{e}}} \Delta \delta_{\mathrm{e}}\right)+m g \sin \gamma_{*} \Delta \gamma
\end{equation}
$$
$$
\begin{equation}
m V_{*} \frac{\mathrm{d} \Delta \beta}{\mathrm{d} t}+m V_{*} \Delta r-m V_{*} \alpha_{*} \Delta p=  -D * \Delta \beta+\left(C_{\beta} \Delta \beta+C_{p} \Delta p+C_{r} \Delta r+C_{\delta_{\mathrm{r}}} \Delta \delta_{\mathrm{r}}\right)+m g \cos \theta_{*} \Delta \phi
\end{equation}
$$

$$
\begin{equation}
I_x \frac{d\Delta p}{dt} - I_{zx} \frac{d\Delta r}{dt} = L_\beta \Delta \beta + L_p \Delta p + L_r \Delta r + L_{\delta_a} \Delta \delta_a + L_{\delta_r} \Delta \delta_r
\end{equation}
$$
$$
\begin{equation}
I_y \frac{d\Delta q}{dt} = M_V \Delta V + M_H \Delta H + M_\alpha \Delta \alpha + M_{\dot{\alpha}} \Delta \dot{\alpha} + M_q \Delta q + M_{\delta_e} \Delta \delta_e
\end{equation}
$$
$$
\begin{equation}
I_z \frac{d\Delta r}{dt} - I_{zx} \frac{d\Delta p}{dt} = N_\beta \Delta \beta + N_p \Delta p + N_r \Delta r + N_{\delta_\alpha} \Delta \delta_a + N_{\delta_r} \Delta \delta_r
\end{equation}
$$
$$
\begin{equation}
\frac{d\Delta x_g}{dt} = \cos \gamma_* \cdot \Delta V - V_* \sin \gamma_* \cdot \Delta \gamma
\end{equation}
$$
$$
\begin{equation}
\frac{d\Delta y_g}{dt} =V_* \cos \gamma_*  \Delta \chi
\end{equation}
$$
$$
\begin{equation}
\frac{d\Delta z_g}{dt}=-\frac{d\Delta H}{dt}=-\sin \gamma_* \Delta V -V_* \cos\gamma_* \Delta \gamma
\end{equation}
$$
$$
\begin{equation}
\frac{d\Delta \phi}{dt}=\Delta p +\tan \theta_* \Delta r
\end{equation}
$$
$$
\begin{equation}
\frac{d\Delta \theta}{dt}=\Delta q
\end{equation}
$$
$$
\begin{equation}
\frac{d\Delta \psi}{dt}=\frac{1}{\cos\theta_*}\Delta r
\end{equation}
$$
以上是12个运动方程的线性化，下面对3个几何关系进行线性化：
$$
\begin{equation}
\Delta \alpha =\Delta \theta -\Delta \gamma
\end{equation}
$$
$$
\begin{equation}
\Delta \beta=\cos \gamma_* (\Delta \psi -\Delta \chi)+\sin\alpha_* \Delta \phi
\end{equation}
$$
$$
\begin{equation}
\Delta \mu=\tan \gamma_* \Delta \beta+\frac{\cos \theta_*}{\cos\gamma _*}\Delta \phi 
\end{equation}
$$

分析上述得到的线性化方程，可以发现这些方程可以划分为互相独立的两组。\
49-63\
56-70\
方程（49）(50)（53）（55）（57）（59）（61）只包含纵向扰动运动变量，故这些方程组称为纵向小扰动运动方程组。\
方程（51）（52）（54）（56）（58）（60）（62）（63）只包含横侧扰动运动变量，这些方程组称为横侧小扰动运动方程组 

## 纵向小扰动运动方程组
$$
\begin{array}{l}
X_{V}=\left[T_{V} \cos \left(\alpha_{*}+\varphi\right)-D_{V}\right] / m \\
X_{\varepsilon}=\left[-T_{*} \sin \left(\alpha_{*}+\varphi\right)-D_{\alpha}\right] / m \\
X_{H}=\left[T_{H} \cos \left(\alpha_{*}+\varphi\right)-D_{H}\right] / m \\
X_{\delta_{e}}=-D_{\delta_{\mathrm{e}}} / m \\
X_{\delta_{\mathrm{p}}}=T_{\delta_{\mathrm{p}}} \cos \left(\alpha_{*}+\varphi\right) / m \\
Z_{V}=\left[T_{V} \sin \left(\alpha_{*}+\varphi\right)+L_{V}\right] / m V \\
Z_{\alpha}=\left[L_{\alpha}+T_{\cdot} \cos \left(\alpha_{*}+\varphi\right)\right] / m V \\
Z_{\dot{d}}=L_{\dot{d}} / m V \\
Z_{q}=L_{q} / m V \\
Z_{H}=\left[T_{H} \sin \left(\alpha_{*}+\varphi\right)+L_{H}\right] / m V_{*} \\
Z_{\delta_{e}}=L_{\delta_{e}} / m V_{*} \\
Z_{\delta_{\mathrm{p}}}=T_{\delta_{\mathrm{p}}} \sin \left(\alpha_{*}+\varphi\right) / m V \\
\bar{M}_{V}=M_{V} / I_{y} \\
\bar{M}_{\dot{e}}=M_{a} / I_{y} \\
\bar{M}_{\dot{d}}=M_{d} / I_{y} \\
\bar{M}_{q}=M_{q} / I_{y} \\
\bar{M}_{H}=M_{H} / I_{y} \\
\bar{M}_{\delta_{e}}=M_{\delta_{e}} / I_{y}
\end{array}
$$

