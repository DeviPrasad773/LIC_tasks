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

### Circuit Diagram:Resistor-Loaded Differential Pair

![cir_dc](https://github.com/user-attachments/assets/593f5467-7ad0-41f1-a5d2-d3495f17475d)


The given circuit is a MOS differential amplifier, which consists of two NMOS transistors (CMOSN) configured as a differential pair. 

NMOS Transistors (M1 and M2): Act as the main amplifying elements, forming a differential pair that amplifies the difference between the two input signals.

Output Nodes (Vout1 and Vout2): The differential output signals are taken from these points.

Design

Calculation:

- Determine Iss (Source Current):

Iss = Power / Vdd

Iss = 2.2mW / 1.8V = 1.222mA

Therefore, **Id1=Id2=0.6111mA**

- Calculate Rd (Drain Resistance):

Vdd=(Id*Rd)+Vocm

Rd = (Vdd - Vocm ) / Id

Rd = (1.8V - 1.1V) / 0.6111mA

Rd = 1147 Ω

- Calculate Rss (Source Resistance):

Rss = Vp / Iss

Rss = 0.4V / 1.222mA

Rss = 327.86 Ω

### DC Analysis :
----
- Make the necessary connections as per the circuit daigram.
- Set the Rd and Rss values such that the transistors will operate in saturation region .
- Vary Rd and W/L to get the required Vocm and Id.

![out_dc](https://github.com/user-attachments/assets/2b8698db-359d-49b0-8a4a-d11a58223afb)

  
 - After this in "view command" go to " SPICE Output Log " option to check Vgs, Vth ,Vds etc.

 ![image](https://github.com/user-attachments/assets/abdb9634-15e8-4ae0-81c7-c4ac1d814244)


**- Condition for transistor to operate in saturation region,**

Vgs>Vth, 

Vds> Vov 

From the Output Log we can observe that Vgs= 0.55V , Vth= 0.498V and Vds = 0.7V . 

It is satisfying the required condition therefore, the transistors lies in saturation region .

**Q point = (Vds,Id) = (0.7V,0.610mA).**

Now lets caluculate Vincm(min), Vincm(max), Vout(min), Vout(max).

Vincm(min)= Vth + Vp = 0.366 + 0.4 = 0.766V 

Vincm(max) = Vdd - (Id*Rd) + Vth = 1.463V 

Vout(min) = Vov1 + Vp = (0.55-0.366)+0.4 = 0.584V 

Vout(max) = Vdd-(Id*Rd) = 1.1003V

### Transient Analysis :
---
let us find out the Theoretical gain 

For this circuit the theoretical gain is,

gain = Av= -Gm*Rd 

where gm= (2Id)/Vov = 6.63mS

Av= -6.63mS * 1.147kΩ = -7.605 V/V

#### Steps for transient Analysis

* Replace DC input with an AC signal.
* Use SINE(dc_offset, Amplitude, Frequency).
* Go to "Simulate" > "Edit Simulation Cmd" > "Transient".
* Set Stop Time: 10ms.
* Run the simulation.
* Our dc_offset = 0.95V and assume amplitude as 50mV and frequency as 1Khz

![cir_tran](https://github.com/user-attachments/assets/a2be498a-11f6-41a1-9779-63545cf37415)

![wave_tran](https://github.com/user-attachments/assets/da3e78ef-65e7-4c34-b032-c3c363bc6f6d)


- We can observe that it has 180 degree Phase shift.
- It has a gain of -8.56V/V

### Transient analysis for Vincm(min)=0.766V
---
![image](https://github.com/user-attachments/assets/d658325a-e927-4f89-a9ef-7d2591381ec0)

![image](https://github.com/user-attachments/assets/cc5e31e6-4538-416d-ab87-6d4ac94e5bc4)


### Transient analysis for Vincm(max)=1.463.V
---

![image](https://github.com/user-attachments/assets/1b9dff3d-9b73-4b25-a13a-84256076192a)

![image](https://github.com/user-attachments/assets/d64447ae-d150-4495-b38e-e3df6cb67797)


### AC Analysis:
---

![image](https://github.com/user-attachments/assets/cc1c0ebc-c393-4c31-a81d-a5adf7f02a58)


#### Steps to get Ac analysis Waveform:
- In simulation tab select AC Analysis.
- In the AC Analysis tab, select **Type of Sweep as Decade**.
- Enter the number of points per decade (ex:20) and the frequency range ( 0.1Hz to 1THz).

![image](https://github.com/user-attachments/assets/84691811-3dff-4c8c-9f7b-5b34146436bb)

- The theoretical gain in db is 18.65 DB
- **Obatained differential gain is around 19.53 DB**
- **3db Bandwidth=2.16Ghz**

|Parameter      |Theory value  | Practical value |
|---------------|--------------|-----------------|
|Av(in dB)      | 18.65dB      | 19.53dB         |
|Av(in V/V)     | 8.56         | 9.47            |


## Circuit 2

### Circuit Diagram:Current Source-Loaded Differential Pair

![cir2](https://github.com/user-attachments/assets/f917e7ba-9250-448a-ae9f-dd3ca8e453a4)

### DC Analysis

![cir2_dc_out](https://github.com/user-attachments/assets/bef9bd61-d951-4587-bd9f-5a62232cea57)

 - After this in "view command" go to " SPICE Output Log " option to check Vgs, Vth ,Vds etc.

![Screenshot 2025-03-06 232945](https://github.com/user-attachments/assets/dac5d637-70e6-4948-b062-a77ac383f70e)


**- Condition for transistor to operate in saturation region,**

Vgs>Vth, 

Vds> Vov 

From the Output Log we can observe that Vgs= 0.55V , Vth= 0.498V and Vds = 0.7V . 

It is satisfying the required condition therefore, the transistors lies in saturation region .

**Q point = (Vds,Id) = (0.7V,0.610mA).**

### Transient Analysis

![image](https://github.com/user-attachments/assets/847c69c6-5f6a-45a2-b623-92bc34a1fc81)

- We can observe that it has 180 degree Phase shift.
- It has a gain of -8.51V/V


### AC Analysis

![image](https://github.com/user-attachments/assets/3b0ed8ce-9b2c-412d-a1d2-565af6ee8ef3)

- The theoretical gain in db is 18.65 DB
- **Obatained differential gain is around  19.544 DB**
- **3db Bandwidth=2.11Ghz**

|Parameter      |Theory value  | Practical value |
|---------------|--------------|-----------------|
|Av(in dB)      | 18.65dB      | 19.54dB         |
|Av(in V/V)     | 8.51         | 9.488           |

## Circuit 3

### Circuit Diagram:Simple Current Source Differential Pair

![image](https://github.com/user-attachments/assets/3a6719af-af63-41fb-a9e5-aae8dbe9735e)


### DC Analysis

W.K.T

Vds = Vgs - Vt ( Vds = Vp = 0.4V )

0.4 + 0.36624 = Vg ( since source is grounded )

Vbias = Vg = 0.76624V ( Bias voltage at the gate for 3rd n type mosfet)

The width and length of the differential pair MOSFETs remain unchanged, while the third MOSFET has a width of 21.684um and a length of 180nm.

![image](https://github.com/user-attachments/assets/aa9517fe-48a2-4029-8f63-c86a8f1c6a6e)

  
 - After this in "view command" go to " SPICE Output Log " option to check Vgs, Vth ,Vds etc.

![image](https://github.com/user-attachments/assets/92dd7c93-1de4-4afa-86c9-fcbdcab9e626)



**- Condition for transistor to operate in saturation region,**

Vgs>Vth, 

Vds> Vov 

From the Output Log we can observe that Vgs= 0.55V , Vth= 0.498V and Vds = 0.7V . 

It is satisfying the required condition therefore, the transistors lies in saturation region .

**Q point = (Vds,Id) = (0.7V,0.610mA).**


### Transient Analysis

![image](https://github.com/user-attachments/assets/a97b6365-f216-45d8-ac00-0a05c050c8a5)

- We can observe that it has 180 degree Phase shift.
- It has a gain of -8.535V/V


### AC Analysis

![image](https://github.com/user-attachments/assets/6b536ef4-70cd-4a73-8fc3-e64960e50049)

- The theoretical gain in db is 18.65 DB
- **Obatained differential gain is around 19.56 DB**
- **3db Bandwidth=2.15Ghz**

|Parameter      |Theory value  | Practical value |
|---------------|--------------|-----------------|
|Av(in dB)      | 18.65dB      | 19.56dB         |
|Av(in V/V)     | 8.53         | 9.50            |

# **Final Result**

| **Parameter** | **Circuit 1** | **Circuit 2** | **Circuit 3** |
|--------------|--------------|--------------|--------------|
| **V(out1)**  | 1.1V  | 1.10024V  | 1.10001V  |
| **V(out2)**  | 1.1V  | 1.10024V  | 1.10001V  |
| **V(vp)** | 0.400141V | 0.400166V | 0.400143V |
| **Id(M1)** | 0.610213 mA | 0.61 mA | 0.610201 mA |
| **Id(M2)** | -0.610213 mA | -0.61 mA | -0.610201 mA |
| **Id(M3) (Tail Current Source)** | Not present | 1.22 mA (set with ideal current source) | 1.2204 mA |
| **Total Tail Current** | 1.22043 mA | 1.22 mA | 1.2204 mA |

   
# **Inference**

In this experiment, we explored the behavior of a differential amplifier with three different load configurations: resistor, current source, and NMOS. Each configuration affects the amplifier’s performance in unique ways, especially in terms of voltage gain and stability.

## Comparison of Differential Pair Circuits

| Feature               | **Circuit 1**                  | **Circuit 2**                  | **Circuit 3**                  |
|-----------------------|--------------------------------|--------------------------------|--------------------------------|
| **Current Source**    | Resistor (327.87Ω)               | Ideal Current Source (1.22mA) | Active Current Source (NMOS)   |
| **Practicality**      | Less Practical                | Suitable for AC Analysis       | Realistic for Circuit Design   |


- **Resistor Load (Circuit 01)**: This configuration gave a gain of 9.47 V/V. The resistor load is the most basic, and its gain is somewhat lower compared to the other two configurations.
  
- **Current Source Load (Circuit 02)**: With a gain of 9.488 V/V, this configuration achieved a slightly higher gain. This happens because a current source acts like an ideal load with very high output impedance, which helps increase the gain.

- **NMOS Load (Circuit 03)**: The NMOS configuration resulted in the highest gain of 9.50 V/V, but this gain is close to that of the current source configuration. The reason it’s not higher is that the active load (NMOS) has some finite impedance, unlike an ideal current source.

### Key Inferences:
1. **Voltage Gain**: The gain is highest in the NMOS configuration and slightly lower in the resistor configuration. The current source also increases the gain compared to the resistor, due to its high output impedance.
  
2. **Bias Current Stability**: Across all configurations, the bias current remained steady at about 0.61mA, showing that the circuit was properly biased.

3. **Common-Mode Voltage (Vocm)**: The common-mode output voltage was stable at around 1.1V, which is consistent with the design specifications.

### Conclusion:
This experiment clearly shows that the choice of load—whether a resistor, current source, or NMOS—has a noticeable impact on the performance of a differential amplifier. The current source and NMOS loads help achieve higher gains, and the circuit remains stable with the proper biasing, making it a valuable exercise in understanding how load configurations affect amplifier behavior.

