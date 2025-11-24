# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
![3](https://github.com/user-attachments/assets/dade5c0e-af6f-4358-ae93-ac72219a7789)
![4](https://github.com/user-attachments/assets/eb177c38-eaa3-4618-9478-2da8854ef183)
<img width="1054" height="1364" alt="image" src="https://github.com/user-attachments/assets/40a073aa-952d-4b40-bc75-0323b6a0aa34" />





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
<img width="1053" height="985" alt="image" src="https://github.com/user-attachments/assets/24191fc3-ac73-4201-96dd-624d62738f40" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB.<br>
Gain margin = 0.7<br>
Phase Margin = -8.8865<br>
Gain crossover frequency = 3.7565<br>
Phase crossover frequency = 3.1623<br>
The system is unstable.<br>
