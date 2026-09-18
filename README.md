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
## Simulink: 


### With P-Controller
<img width="905" height="381" alt="Screenshot 2026-08-06 142138" src="https://github.com/user-attachments/assets/7659377b-9e54-4939-9318-d723eb4eb31b" />


### With PI Controller
<img width="905" height="381" alt="Screenshot 2026-08-06 142138" src="https://github.com/user-attachments/assets/ffbc6af5-95d0-4d2e-8e5b-d5715b969516" />

### With PID Controller
<img width="905" height="381" alt="Screenshot 2026-08-06 142138" src="https://github.com/user-attachments/assets/ad5deee9-4f4f-4535-b19e-c0ce4212b29b" />

## Output:


### With P-Controller
<img width="702" height="621" alt="Screenshot 2026-08-06 142653" src="https://github.com/user-attachments/assets/9a449213-9b81-400b-b50f-d4e13897137d" />

### With PI Controller
<img width="698" height="627" alt="Screenshot 2026-08-06 143941" src="https://github.com/user-attachments/assets/a0838708-1eea-4481-a877-75b2835743a5" />

### With PID Controller
<img width="685" height="635" alt="Screenshot 2026-08-06 143711" src="https://github.com/user-attachments/assets/63b2e507-c9c1-495d-90fc-f6d83d3c6846" />


## Result:
Thus the P, PI and PID controllers for the given system was analysed and the following conclusions were arrived using MATLAB. <br>

### With P Controller 
Delay time = 0.04s        <br>
Rise time = 0.08s            <br>
Peak time = 0.12s          <br>
Settling time = 1.3s          <br>
Steady State Error = 1-0.98=0.02       <br>
### With PI Controller 
Delay time = 0.06s        <br>
Rise time = 0.10s            <br>
Peak time = 0.15s          <br>
Settling time = 1.2s           <br>
Steady State Error = 1-1=0       <br>
### With PID Controller 
Delay time = 0.15s         <br>
Rise time = 0.90s            <br>
Peak time = 1.30s           <br>
Settling time = 1.2s          <br>
Steady State Error = 1-1=0    <br>




