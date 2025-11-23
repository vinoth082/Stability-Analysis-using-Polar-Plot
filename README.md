# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:

<img width="463" height="863" alt="image" src="https://github.com/user-attachments/assets/d9c1b60d-d1ec-40bc-a772-85fe901e4116" />


## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program:
```
num=[10]
den=[0.1 0.7 1 0]
sys=tf(num,den)
[mag,phase,W]=bode(sys)
mag=squeeze(mag)
phase=squeeze(phase)
phase1=deg2rad(phase)
polarplot(phase1,mag,'linewidth',1.5)
grid on
[Gm Pm Wpc Wgc]=margin(sys)
if(Wpc>Wgc)
    disp('stable')
elseif(Wpc == Wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```
## Output:
<img width="1158" height="1090" alt="image" src="https://github.com/user-attachments/assets/5cbb6613-4a2d-40f7-8ffa-13aaf14399c8" />
<img width="1027" height="813" alt="image" src="https://github.com/user-attachments/assets/391e5377-dde5-40b5-a0b5-29e988336073" />



## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 0.70 <br>
Phase Margin =-8.88 <br>
Gain crossover frequency = 3.75<br>
Phase crossover frequency = 3.16<br>
The system is  unstable
