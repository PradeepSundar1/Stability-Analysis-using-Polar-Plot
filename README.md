# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
![3](https://github.com/user-attachments/assets/dade5c0e-af6f-4358-ae93-ac72219a7789)
![4](https://github.com/user-attachments/assets/eb177c38-eaa3-4618-9478-2da8854ef183)




## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[1]
den=[conv(1,0),conv(1,0.5),conv(1,0.2)]
sys=tf(num,den)
w=logspace(-1,2,1000)
[mag phase]=bode(sys,w)
mag=squeeze(mag)
phase=squeeze(phase)
theta=deg2rad(phase)
polarplot(theta,mag,'LineWidth',1.5)
[gm pm wpc wgc]=margin(sys)
if (wpc>wgc)
    disp('stable')
elseif (wpc==wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```
## Output:
<img width="1789" height="825" alt="Screenshot 2025-11-16 104814" src="https://github.com/user-attachments/assets/2036c1eb-5995-4170-97e6-280623eb9e5e" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = -23.10 db<br>
Phase Margin = -50.48 degree<br>
Gain crossover frequency = 0.9534 rad/s<br>
Phase crossover frequency =0.3162 rad/s <br>
The system is  ------------
