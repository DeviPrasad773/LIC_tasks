# Linear Integrated Circuit
# Differential Amplifier Experiment

## Aim

Design and Analyze the MOS differential amplifier circuit for the following specifications:

- Supply Voltage (Vdd) = 1.8V
- Output Common Mode Voltage (Vocm) = 1.1V
- Power (P) <= 2.2mW
- Voltage at point P (Vp) = 0.4V
- Common Mode Input Voltage (Vicm) = 0.95V


Perform:

DC Analysis, Transient Analysis, Frequency Response and Extract the parameters

## Circuit 1

### Circuit Diagram:

![exp-3_cir_dc](https://github.com/user-attachments/assets/8848c74c-cc72-4f3a-b6f1-9b68bfa684f7)

The given circuit is a MOS differential amplifier, which consists of two NMOS transistors (CMOSN) configured as a differential pair. 

NMOS Transistors (M1 and M2): Act as the main amplifying elements, forming a differential pair that amplifies the difference between the two input signals.

Output Nodes (Vout1 and Vout2): The differential output signals are taken from these points.

Design

Calculation:

- Determine Iss (Source Current):

Iss = Power / Vdd

Iss = 2.2mW / 1.8V = 1.22mA

Therefore, **Id1=Id2=0.61mA**

- Calculate Rd (Drain Resistance):

Vdd=(Id*Rd)+Vocm

Rd = (Vdd - Vocm ) / Id

Rd = (1.8V - 1.1V) / 0.61mA

Rd = 1147 Ω

- Calculate Rss (Source Resistance):

Rss = Vp / Iss

Rss = 0.4V / 1.22mA

Rss = 327.86 Ω

### DC Analysis :
----
- Make the necessary connections as per the circuit daigram.
- Set the Rd and Rss values such that the transistors will operate in saturation region .
- Vary Rd and W/L to get the required Vocm and Id.


  ![exp-3_out_dc](https://github.com/user-attachments/assets/9d90d2d6-151e-4456-9599-98a1306c6a62)
  
 - After this in "view command" go to " SPICE Output Log " option to check Vgs, Vth ,Vds etc.
  
  ![exp-3_op_log_dc](https://github.com/user-attachments/assets/5f8bed14-ea3a-40e1-9897-28879c361961)

**- Condition for transistor to operate in saturation region,**

Vgs>Vth, 

Vds> Vov 

From the Output Log we can observe that Vgs= 0.552V , Vth= 0.481V and Vds = 0.759V . 

It is satisfying the required condition therefore, the transistors lies in saturation region .

**Q point = (Vds,Id) = (0.759V,0.607mA).**

Now lets caluculate Vincm(min), Vincm(max), Vout(min), Vout(max).

Vincm(min)= Vth + Vp = 0.366 + 0.4 = 0.766V 

Vincm(max) = Vdd - (Id*Rd) + Vth = 1.463V 

Vout(min) = Vov1 + Vp = (0.55-0.366)+0.4 = 0.584V 

Vout(max) = Vdd-(Id*Rd) = 1.1003V

### Transient Analysis :
---

* Replace DC input with an AC signal.
* Use SINE(dc_offset, Amplitude, Frequency).
* Go to "Simulate" > "Edit Simulation Cmd" > "Transient".
* Set Stop Time: 10ms.
* Run the simulation.
* Our dc_offset = 0.95V and assume amplitude as 50mV and frequency as 1Khz

![exp-3_cir_tra](https://github.com/user-attachments/assets/dc1f9c01-39a1-4e23-baeb-a7f3247fc6ae)

![exp-3_out_tra](https://github.com/user-attachments/assets/4853fda8-6388-4299-9257-7caaec532ef7)

- We can observe that it has 180 degree Phase shift.
- It has a gain of 1.48V/V

### Transient analysis for Vincm(min)=0.766V
--

![min_cir](https://github.com/user-attachments/assets/915f6be8-c3dd-4510-9597-a8c021a61c8c)

![min_wave](https://github.com/user-attachments/assets/f81c933b-3013-4a90-b77f-25f7ff702135)


### Transient analysis for Vincm(max)=1.463.V
---

![max_cir](https://github.com/user-attachments/assets/009ac520-c4ce-4ec4-be74-677401dbd702)


![max_wave](https://github.com/user-attachments/assets/162b7f00-7b94-4d40-be20-8600ca2297d2)

### AC Analysis:
---
![ac_cir](https://github.com/user-attachments/assets/0d549fd2-893e-459e-ac37-76f50d633c8e)

For this circuit the theoretical gain is,

gain = Av= -Gm*Rd 

where gm= (2Id)/Vov = 6.63mS

Av= -6.63mS * 1.147kΩ = -7.605 V/V

as we know Av= 20Log(Av)

therefore in dB scale theoretical gain is 17.621dB 

![ac_wave](https://github.com/user-attachments/assets/859b4f44-4bfa-4c88-822c-7642de88a26c)



