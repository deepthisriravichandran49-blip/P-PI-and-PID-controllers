# Analysis of P, PI and PID Controllers using MATLAB
## Aim:
To analyse the effect of P, PI and PID controllers for the system having open loop transfer function, G(S)=1/(S^2+10S+20) using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
	A controller is a device introduced in the system to modify the error signal and to produce a control signal. 
	The way the controller produces the control signal is called the control action.

Consider the following unity feedback system,
 <img width="823" height="281" alt="image" src="https://github.com/user-attachments/assets/36e49512-cf47-4fec-b00c-f79dc0af1c5f" />

### Proportional (P) Controller:
The proportional controller produces an output, which is proportional to error signal.<br>
u(t)∝e(t) <br>
⇒u(t)=Kpe(t) <br>
Apply Laplace transform on both the sides - <br>
U(s)=KpE(s) <br>
U(s)/E(s)=Kp <br>
Therefore, the transfer function of the proportional controller is Kp.

### Proportional Integral (PI) Controller:
The proportional integral controller produces an output, which is the combination of outputs of the proportional and integral controllers. <br>
u(t)=Kp e(t)+Ki ∫e(t)dt <br>
Apply Laplace transform on both sides - <br>
U(s)=(Kp+Ki/s)E(s) <br>
U(s)/E(s)=Kp+Ki/s <br>
Therefore, the transfer function of proportional integral controller is Kp+Kis. <br>

### Proportional Integral Derivative (PID) Controller:
The proportional integral derivative controller produces an output, which is the combination of the outputs of proportional, integral and derivative controllers. <br>
u(t)=Kp e(t)+Ki ∫e(t)dt+ Kd (de(t)/dt) <br>
Apply Laplace transform on both sides - <br>
U(s)=(Kp+Ki/s+Kds)E(s) <br>
U(s)/E(s)=Kp+Ki/s+Kd s <br>
Therefore, the transfer function of the proportional integral derivative controller is Kp+Ki/s+Kd s

### Characteristics of Kp, Ki and Kd terms:

Increasing the proportional gain ( ) has the effect of proportionally increasing the control signal for the same level of error. The fact that the controller will "push" harder for a given level of error tends to cause the closed-loop system to react more quickly, but also to overshoot more. Another effect of increasing   is that it tends to reduce, but not eliminate, the steady-state error.
The addition of a derivative term to the controller ( ) adds the ability of the controller to "anticipate" error. With derivative control, the control signal can become large if the error begins sloping upward, even while the magnitude of the error is still relatively small. This anticipation tends to add damping to the system, thereby decreasing overshoot. The addition of a derivative term, however, has no effect on the steady-state error.
The addition of an integral term to the controller ( ) tends to help reduce steady-state error. If there is a persistent, steady error, the integrator builds and builds, thereby increasing the control signal and driving the error down. 
 


## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the steady state error and analyse the controllers.
## Program: 
### Without Controller (Open loop System)
num=[1];
den=[1 10 20];
sys=tf(num,den)
step(sys)

### With P-Controller
num=[1];
den=[1 10 20];
sys=tf(num,den)
Kp=300;
C=pid(Kp);
T=feedback(C*sys,1);
step(T)

### With PI Controller
num=[1];
den=[1 10 20];
sys=tf(num,den)
Kp=30;
Ki=70;
C=pid(Kp,Ki);
T=feedback(C*sys,1);
step(T)

### With PID Controller
num=[1];
den=[1 10 20];
sys=tf(num,den)
Kp=350;
Ki=300;
Kd=50;
C=pid(Kp,Ki,Kd);
T=feedback(C*sys,1);
step(T)
## Output: 
### Without Controller (Open loop System)
<img width="1914" height="1137" alt="image" src="https://github.com/user-attachments/assets/521ce5eb-c5aa-42da-b25b-b07e68eb6453" />

### With P-Controller
<img width="1917" height="1127" alt="image" src="https://github.com/user-attachments/assets/08e43cdf-f0f0-433d-9c70-642b69ac01e9" />

### With PI Controller
<img width="1916" height="1140" alt="image" src="https://github.com/user-attachments/assets/5aa7f3b7-bf35-4c78-8f30-2deb91355ad4" />

### With PID Controller
<img width="1915" height="1136" alt="image" src="https://github.com/user-attachments/assets/337538a8-616b-424c-a6b5-dc646aaea269" />


## Result:
Thus the P, PI and PID controllers for the given system was analysed and the following conclusions were arrived using MATLAB. <br>
### With-out controller
```
Delay time = 0.458s
Rise time = 1.56s
Peak time = 0.999s
Settling time = 1.96s
Steady State Error = 0
```
### With P Controller 
```
Delay time = 0.0887s
Rise time = 0.16s
Peak time = 0.19s
Settling time = 1.1s
Steady State Error = 0.1
```
### With PI Controller 
```
Delay time = 0.303s
Rise time = 0.649s
Peak time = 0.82s
Settling time = 1.87s
Steady State Error = 0.87
```
### With PID Controller 
```
Delay time = 0.0243s
Rise time = 0.0615s
Peak time = 1.04s
Settling time = 0.882s
Steady State Error = 0.018
```
