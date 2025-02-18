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

![q_t1](https://github.com/user-attachments/assets/9664111a-f07c-434e-97d7-f16c97292ca4)

## Input and Output Waveform:

![q_t1wav](https://github.com/user-attachments/assets/8f26bd87-9eb5-4dd5-9a81-8acf898da2de)

## iii) AC analysis 

In AC analysis, we examine circuits across varying frequencies. Choose a sweep type of "decade" with 20 points per decade, starting from 0.1 to 1T. This method provides detailed frequency response data for the circuit under analysis.

![Screenshot 2025-02-17 214307](https://github.com/user-attachments/assets/19023b2f-227f-4c92-9e7b-4455f42120ef)

![Screenshot 2025-02-17 214228](https://github.com/user-attachments/assets/6a6a7d79-e13d-4907-8666-9c9c93a271e1)

### Wave Response:

![Screenshot 2025-02-17 214918](https://github.com/user-attachments/assets/eafdb60d-660c-4d58-8ddf-cfe419f79bd8)

# Q2)  i) Find DC operating point ii) Do transient analysis and find Gain iii) Do AC Analysis.

## i) Find DC operating point 

![image](https://github.com/user-attachments/assets/425618fc-9128-45ba-a06c-0421a15b937e)

![Screenshot 2025-02-17 235734](https://github.com/user-attachments/assets/bdc539ce-7293-489f-9cb2-17aa7b85b0b1)

## ii)Do transient analysis and find gain

![Screenshot 2025-02-18 112025](https://github.com/user-attachments/assets/8fecf8cd-4887-4b55-b71c-ce33beb1f250)


### Output WAveform

![Screenshot 2025-02-18 000059](https://github.com/user-attachments/assets/c5d2b23e-53cb-475a-81c8-5f1ce75e2345)

## iii) AC analysis 

![Screenshot 2025-02-18 112145](https://github.com/user-attachments/assets/dbdf5ff8-acac-4d37-8ad5-2b29e6f2d9a4)

![Screenshot 2025-02-18 112121](https://github.com/user-attachments/assets/18970d5d-ce1f-414b-997b-10b1952ecc8f)

![image](https://github.com/user-attachments/assets/e2c41513-bd3e-4ad8-8e31-a9313e58bf4d)

## Result

ID=5.55 *10^-5 A

VDS1=0.9v

Gain = 20.2929dB

## Inference

Active PMOS Load offers higher gain but lower bandwidth, making it suitable for applications prioritizing amplification over frequency range. The choice of load, whether passive or active, plays a crucial role in determining circuit performance. Understanding these differences helps optimize gain, bandwidth, and overall signal integrity in CMOS analog design. Active loads can provide higher gain due to the increased transconductance, but this comes at the cost of reduced bandwidth. Conversely, passive loads typically offer broader bandwidth but with lower gain. The selection between these two types of loads depends on the specific requirements of the application, such as the need for high gain versus the need for wide bandwidth. By carefully considering these factors, designers can make informed decisions to meet the performance criteria of their analog circuits, leading to more efficient and reliable designs in various applications.


## Conclusion

This report presents an LTspice-based analysis of an MOSFET circuit through DC, transient, and AC analysis. 
The results show:

•	DC Analysis confirms the operating region of the MOSFET.

•	Transient Analysis validates the time-domain response for a 1 kHz input.

•	AC Analysis provides insight into the frequency-dependent gain characteristics.

These findings help in understanding MOSFET behavior in analog circuits.







