# LIC_tasks
Linear Integrated Circuit (LIC) 

Analysis of MOSFET Circuit Using LTspice

Introduction

This report presents a analysis of a simple MOSFET circuit using LTspice. The study includes DC operating point analysis, transient analysis, and AC frequency response over a broad frequency range.(0.1hz – 1Thz).

Library File used: tsmc018.lib where tsmc018 is the file we have used that consists of all specification.

•	DC Analysis (Operating Point - .op)

In DC analysis we  will  determine the DC biasing conditions of the MOSFET, including drain current (Id), drain voltage (Vds), and gate voltage (Vgs).

•	Transient Analysis

Used to find Gain and to observe the time-domain response of the circuit when an AC signal (1 kHz, 50 mV peak) is applied to the gate along with a DC offset of 0.9V.

•	AC Analysis

Used to determine the frequency response of the circuit by performing small-signal AC analysis over a wide frequency range (0.1 Hz to 1 THz).

Questions For Understanding these analysis:


Q1)  i) Find DC operating point ii) Do transient analysis and find Gain iii) Do AC Analysis.

![Screenshot 2025-02-16 231039](https://github.com/user-attachments/assets/05329a17-f7ca-4e6b-81e7-52b61fe421a8)


Given:

	The above circuit is a common source amplifier.

	VDD(V2) = 1.8V

	Vg(V1)=0.9V

	Circuit consist of a resister (R) of 1K ohm with power rating of 100

i) Find DC operating point 

WKT P=VI where P=100µW and V=1.8V we can find Id, Id=P/V=55.55µA. Now we know Id, so by trial and error we can find the width and length of the MOSFET by keeping anyone of the parameter constant. From trial and error we found out that the w/l should be 6.86  to get Id as 55.55µA. To find other parameters we need to do simulation, select DC op pnt to find operating point and other parameters.

![Screenshot 2025-02-16 232005](https://github.com/user-attachments/assets/fbc2f7ca-889c-41f1-bbef-252885dfe6ad)
