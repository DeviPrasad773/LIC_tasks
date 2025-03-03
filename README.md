# LIC_tasks
Linear Integrated Circuit (LIC) 

# Analysis of MOSFET Circuit Using LTspice

## Introduction

This report presents a analysis of a simple MOSFET circuit using LTspice. The study includes DC operating point analysis, transient analysis, and AC frequency response over a broad frequency range.(0.1hz – 1Thz).

Library File used: tsmc018.lib where tsmc018 is the file we have used that consists of all specification.

•	DC Analysis (Operating Point - .op)

In DC analysis we  will  determine the DC biasing conditions of the MOSFET, including drain current (Id), drain voltage (Vds), and gate voltage (Vgs).

•	Transient Analysis

Used to find Gain and to observe the time-domain response of the circuit when an AC signal (1 kHz, 50 mV peak) is applied to the gate along with a DC offset of 0.9V.

•	AC Analysis

Used to determine the frequency response of the circuit by performing small-signal AC analysis over a wide frequency range (0.1 Hz to 1 THz).

## Questions For Understanding these analysis:


Q1)  i) Find DC operating point ii) Do transient analysis and find Gain iii) Do AC Analysis.

![Screenshot 2025-02-16 231039](https://github.com/user-attachments/assets/05329a17-f7ca-4e6b-81e7-52b61fe421a8)


### Given:

	The above circuit is a common source amplifier.

	VDD(V2) = 1.8V

	Vg(V1)=0.9V

	Circuit consist of a resister (R) of 1K ohm with power rating of 100

## i) Find DC operating point 

WKT P=VI where P=100µW and V=1.8V we can find Id, Id=P/V=55.55µA. Now we know Id, so by trial and error we can find the width and length of the MOSFET by keeping anyone of the parameter constant. From trial and error we found out that the w/l should be 6.86  to get Id as 55.55µA. To find other parameters we need to do simulation, select DC op pnt to find operating point and other parameters.

![Screenshot 2025-02-16 232005](https://github.com/user-attachments/assets/fbc2f7ca-889c-41f1-bbef-252885dfe6ad)

## ii)Do transient analysis and find gain

Transient analysis observes voltage and current changes over time with respect to input voltage. Use a sine wave with 0.9V DC offset, 50mV amplitude, and 1kHz frequency for input voltage.

![Screenshot 2025-03-03 210405](https://github.com/user-attachments/assets/7c709c1b-fbcd-4b2b-80aa-beff0293a2d2)


## Input and Output Waveform:

![q_t1wav](https://github.com/user-attachments/assets/8f26bd87-9eb5-4dd5-9a81-8acf898da2de)

## iii) AC analysis 

In AC analysis, we examine circuits across varying frequencies. Choose a sweep type of "decade" with 20 points per decade, starting from 0.1 to 1T. This method provides detailed frequency response data for the circuit under analysis.

![Screenshot 2025-03-03 210542](https://github.com/user-attachments/assets/7ac094fa-ff34-4fe7-893a-0c0a6abb4509)


![Screenshot 2025-02-17 214228](https://github.com/user-attachments/assets/6a6a7d79-e13d-4907-8666-9c9c93a271e1)

### Wave Response:

![Screenshot 2025-02-17 214918](https://github.com/user-attachments/assets/eafdb60d-660c-4d58-8ddf-cfe419f79bd8)

# Q2)  i) Find DC operating point ii) Do transient analysis and find Gain iii) Do AC Analysis.

## i) Find DC operating point 

To set the DC operating point in the saturation region for NMOS, the condition is:

VDS>VGS−VTH

where VGS-VTH=VOV

From the given data:

NMOS threshold voltage: 

𝑉𝑇𝐻=0.36624𝑉

Overdrive voltage: 

𝑉𝑂𝑉=𝑉𝐺𝑆−𝑉𝑇𝐻=0.9𝑉−0.36624𝑉=0.53376𝑉

 
For NMOS to be in saturation, we need:


VB>0.301V

Choosing 

VB​=0.7V, we ensure both MOSFETs remain in saturation.

From LTspice simulation, the DC operating point results:

Drain current: 

𝐼𝐷=5.55×10−5𝐴

![image](https://github.com/user-attachments/assets/83108891-5838-442f-a48b-1e76be85e5ba)


![Screenshot 2025-02-17 235734](https://github.com/user-attachments/assets/bdc539ce-7293-489f-9cb2-17aa7b85b0b1)

## ii)Do transient analysis and find gain

![image](https://github.com/user-attachments/assets/0c106d28-4695-4489-8092-e4eca529ca9c)



### Output WAveform

![Screenshot 2025-02-18 000059](https://github.com/user-attachments/assets/c5d2b23e-53cb-475a-81c8-5f1ce75e2345)

## iii) AC analysis 

![image](https://github.com/user-attachments/assets/22a31775-cb56-4ab0-b05c-3fd11d83fd9b)


![Screenshot 2025-02-18 112121](https://github.com/user-attachments/assets/18970d5d-ce1f-414b-997b-10b1952ecc8f)

![image](https://github.com/user-attachments/assets/e2c41513-bd3e-4ad8-8e31-a9313e58bf4d)

For AC analysis, the gain is determined over a frequency range of:

0.1Hz to 1THz


## Inference

The LTspice simulation verifies that the designed NMOS circuit operates efficiently as an amplifier, with both DC biasing and AC response aligning with theoretical expectations. The circuit provides moderate gain with stable frequency characteristics.

## Conclusion

This report presents an LTspice-based analysis of an MOSFET circuit through DC, transient, and AC analysis. 
The results show:

•	DC Analysis confirms the operating region of the MOSFET.

•	Transient Analysis validates the time-domain response for a 1 kHz input.

•	AC Analysis provides insight into the frequency-dependent gain characteristics.

These findings help in understanding MOSFET behavior in analog circuits.







