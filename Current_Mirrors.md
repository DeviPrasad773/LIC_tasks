# Linear Integrated Circuit
# Current Mirroring Experiment
# PART-A
## Aim

Design and Analyze Current mirror circuit as active load in amplifier circuit.

**Given** :

Vdd=1.8V.<br>
P<=1mW. <br>
Av>-10V/V.<br>

**Circuit Diagram:**

![image](https://github.com/user-attachments/assets/efbf9c25-9402-4c19-b28b-53f7f284ae52)


It=P/Vdd.<br>
It=Iref+Ix.<br>

## DC Analysis:(for mirror ratio 1:1)

As we know It=Iref+Ix<br>
Therefore, for 1:1 ratio Iref=Ix<br>
So,Iref=It/2<br>
It=P/Vdd<br>
It=1mW/1.8V<br>
It=0.555mA.<br>
Therefore,Iref=0.2778mA.<br>

To obtain the current value according to the given ratio, the provided values of W/L for M1 is 3um/180nm , M2 is 3um/180nm, and M3 is 3um/180nm.<br>
Vin is selected in such a way that it should be in saturation region so the given Vin is 0.838V.<br>

![Screenshot 2025-03-22 160459](https://github.com/user-attachments/assets/7b14e3ae-4e58-4e08-be20-b1616a220167)

**Obtained Output:**

![Screenshot 2025-03-22 160429](https://github.com/user-attachments/assets/f5f4e14e-0810-4e12-8740-0b8a02a505cf)

### Analyzing the current mirroring circuit by changing the w and L but maintaing the same ratio.

**(a)L=180nm.**

We know the (w/L) ratio is 16.667.

Therefore for L=180nm the w=3um.

|Mosfet     |  Id                 | 
|-----------|---------------------|
|  M1       |   0.000277527       |             
|  M2       |   0.000277527       |         
|  M3       |   0.0002778         |             

**(b)L=500nm.**

We know the (w/L) ratio is 16.667.

Therefore for L=500nm the w=8.334um.

|Mosfet     |  Id                   |  
|-----------|-----------------------|
|  M1       |   0.000281241         |             
|  M2       |   0.000281241         |             
|  M3       |   0.0002778           |             

**(c)L=1um.**

We know the (w/L) ratio is 16.667.

Therefore for L=1um the w=16.667um.


|Mosfet     |  Id                   | 
|-----------|-----------------------|
|  M1       |   0.000280654         |             
|  M2       |   0.000280654         |             
|  M3       |   0.0002778           |             


## Transient Analysis:

#### Steps for transient Analysis:

* Replace DC input with an AC signal.
* Use SINE(dc_offset, Amplitude, Frequency).
* Go to "Simulate" > "Edit Simulation Cmd" > "Transient".
* Set Stop Time: 10ms.
* Run the simulation.
* Our dc_offset = 0.838V and assume amplitude as 50mV and frequency as 1Khz.


![Screenshot 2025-03-22 160248](https://github.com/user-attachments/assets/44094458-400c-4e82-827a-17df48e34f91)

**OutPut Waveform:**

![Screenshot 2025-03-22 160221](https://github.com/user-attachments/assets/a778079d-22ce-46df-a7ed-92ad8639edec)

The Expected gain of the circuit is -10V/V.But the obtained gain from the transient analysis is -10.2V/V.


## AC Analysis:

![Screenshot 2025-03-22 155821](https://github.com/user-attachments/assets/cf266073-60a8-4493-8deb-4de5a19ba4c0)

#### Steps to get Ac analysis Waveform:
- In simulation tab select AC Analysis.
- In the AC Analysis tab, select **Type of Sweep as Decade**.
- Enter the number of points per decade (ex:20) and the frequency range ( 0.1Hz to 1THz).

**OutPut Waveform:**

![Screenshot 2025-03-22 155758](https://github.com/user-attachments/assets/e36365ee-5261-493a-b19f-1d09ead1ee02)

The Expected gain in db of the circuit is 20db.But the obtained gain from the AC analysis(frequency response) is 22.16db.

|Parameter      |Theory value  | Practical value |
|---------------|--------------|-----------------|
|Av(in dB)      | 20dB         | 22.16dB         |
|Av(in V/V)     | 10           | 10.2            |

**3db Bandwidth:**

The obatined 3db B.W=2.267GHz.

![Screenshot 2025-03-22 155941](https://github.com/user-attachments/assets/f162d225-40dd-4f49-b466-eae9243c31a6)

## DC Analysis:(for mirror ratio 1:2)

As we know It=Iref+Ix<br>
Therefore, for 1:2 ratio 2*Iref=Ix<br>
So,Iref=It/3<br>
It=P/Vdd<br>
It=1mW/1.8V<br>
It=0.555mA.<br>
Therefore,Iref=0.185mA.<br>

To obtain the current value according to the given ratio, the provided values of W/L for M1 is 6um/180nm , M2 is 6um/180nm, and M3 is 3um/180nm.<br>
Vin is selected in such a way that it should be in saturation region so the given Vin is 0.763V.<br>

![Screenshot 2025-03-22 162611](https://github.com/user-attachments/assets/6265822a-0538-4dcd-b93a-5d664c7ca5ff)


**Obtained Output:**

![Screenshot 2025-03-22 162553](https://github.com/user-attachments/assets/cd12cef7-8a78-4692-a8b6-40f5f4c07e09)


## Transient Analysis:

#### Steps for transient Analysis:

* Replace DC input with an AC signal.
* Use SINE(dc_offset, Amplitude, Frequency).
* Go to "Simulate" > "Edit Simulation Cmd" > "Transient".
* Set Stop Time: 10ms.
* Run the simulation.
* Our dc_offset = 0.763V and assume amplitude as 50mV and frequency as 1Khz.


![Screenshot 2025-03-22 162219](https://github.com/user-attachments/assets/3e54254a-e03f-4c8d-8a6d-e4550452668b)


**OutPut Waveform:**

![Screenshot 2025-03-22 162246](https://github.com/user-attachments/assets/430a9509-3dd4-4d23-a9e3-5c25a28849a0)


The Expected gain of the circuit is -10V/V.But the obtained gain from the transient analysis is -11.68V/V.


## AC Analysis:

![Screenshot 2025-03-22 162419](https://github.com/user-attachments/assets/34d2b2ce-9f72-4460-8a30-33eacf63de72)


#### Steps to get Ac analysis Waveform:
- In simulation tab select AC Analysis.
- In the AC Analysis tab, select **Type of Sweep as Decade**.
- Enter the number of points per decade (ex:20) and the frequency range ( 0.1Hz to 1THz).

**OutPut Waveform:**

![Screenshot 2025-03-22 162439](https://github.com/user-attachments/assets/344ca781-50ca-42e9-ba6b-70a3882a5dcc)


The Expected gain in db of the circuit is 21.34db.But the obtained gain from the AC analysis(frequency response) is 24.6db.

|Parameter      |Theory value  | Practical value |
|---------------|--------------|-----------------|
|Av(in dB)      | 21.34dB      | 24.6dB         |
|Av(in V/V)     | 10           | 11.68           |

**3db Bandwidth:**

The obatined 3db B.W=1.173GHz.

![Screenshot 2025-03-23 003335](https://github.com/user-attachments/assets/59437bf1-449e-4631-b6b4-1207507b42bc)



### **Comparison Table:**
| **Parameter**  | **Mirror Ratio 1:1** (Theory) | **Mirror Ratio 1:1** (Practical) | **Mirror Ratio 1:2** (Theory) | **Mirror Ratio 1:2** (Practical) |
|---------------|-----------------------------|-----------------------------|-----------------------------|-----------------------------|
| Av (in dB)    | 20 dB                        | 22.16 dB                     | 21.34 dB                     | 24.6 dB                     |
| Av (in V/V)   | 10                           | 10.2                          | 10                           | 11.68                         |
| 3 dB Bandwidth | -                            | 2.267 GHz                     | -                            | 1.173 GHz                     |  



### Inference:

The current mirror circuit successfully replicates the reference current with minimal deviation, ensuring accurate current mirroring for different W/L ratios.

As the W/L ratio changes while maintaining the same ratio, the drain current (Id) values remain nearly consistent, verifying the effectiveness of the mirror circuit.

The amplifier gain is slightly higher than the theoretical expectation in both mirror ratios, indicating minor variations due to transistor parameter mismatches or simulation artifacts.

Increasing the mirror ratio (from 1:1 to 1:2) leads to an increase in gain, as expected. However, it also impacts bandwidth, reducing it from 2.267 GHz to 1.173 GHz.

The obtained results closely match theoretical values, validating the simulation setup and circuit behavior.

---------------------------------------------------------------------------------------------   


# PART-B
## Aim
Design the differential amplifier using the same design specification as Experiment-3.
Perform DC analysis,trasient and AC analysis.

### DC Analysis:

![a2](https://github.com/user-attachments/assets/7a288378-fe12-443a-a758-d9724e716933)

Here’s a well-structured explanation of the **DC Analysis** for your circuit while ensuring that all MOSFETs operate in the **saturation region** and match the experimental results.

---

## **DC Analysis of the Given Circuit**

### **1. Overview of the Circuit**
The circuit consists of six MOSFETs (M1 to M6) with different **(W/L) ratios**, and we need to ensure that all transistors remain in the **saturation region** during the analysis. The given (W/L) ratios for each transistor are:

- **M1**: 108μm / 180nm  
- **M2**: 108μm / 180nm  
- **M3**: 108μm / 180nm  
- **M4**: 49.1μm / 180nm  
- **M5**: 57.33μm / 180nm  
- **M6**: 57.33μm / 180nm  

Since the circuit must maintain the same **current and voltage values** as in Experiment 3, the **DC operating point (biasing conditions)** is determined accordingly.

---


### **2. DC Analysis - Ensuring Same Current & Voltage Values**
DC analysis involves finding the **DC operating points (voltages and currents)** of each MOSFET. Based on Experiment 3, we ensure the following:

- **Current Matching:** The drain current (\( I_D \)) of matched transistors (M1, M2, M3) must be the same.
- **Voltage Consistency:** The node voltages should match experimental results.

Since **M1, M2, and M3** have the **same W/L ratio**, they will have identical drain currents, ensuring symmetry.

For **M4, M5, and M6**, their **(W/L) ratios differ**, but they must still be biased properly to maintain the same experimental **current and voltage values**.

---

### **3. Steps to Verify the DC Analysis**
1. **Compute \( V_{GS} \) for each transistor**  
   - Ensure each MOSFET is in **saturation** by checking \( V_{GS} \) and \( V_{th} \).
   
2. **Find the DC operating point (voltages and currents)**  
   - Solve Kirchhoff’s Current Law (KCL) and Kirchhoff’s Voltage Law (KVL) equations.
   
3. **Check consistency with Experiment 3 results**  
   - Verify that **simulated values** match **measured values** in the lab.


**Output:**

![a1](https://github.com/user-attachments/assets/03b527cf-4c2f-4c8c-a77e-97e929fc2504)

### Transient Analysis:

![a4](https://github.com/user-attachments/assets/5f5d6e0d-2fd0-4915-9d98-32dcdca55315)


**Output Waveform:**

![a3](https://github.com/user-attachments/assets/b9e84eb5-4cba-404f-b093-b96f7067e975)

The Expected gain of the circuit is -8.6V/V.But the obtained gain from the transient analysis is -13.68V/V.

### AC Analysis:

![a6](https://github.com/user-attachments/assets/7f25c62d-aef6-4887-ae26-ed3e339e19ff)

#### Steps to get Ac analysis Waveform:
- In simulation tab select AC Analysis.
- In the AC Analysis tab, select **Type of Sweep as Decade**.
- Enter the number of points per decade (ex:20) and the frequency range ( 0.1Hz to 1THz).

**Output Waveform:**

The Expected gain in db of the circuit is 22.72db.But the obtained gain from the AC analysis(frequency response) is db.

|Parameter      |Theory value  | Practical value |
|---------------|--------------|-----------------|
|Av(in dB)      | 21.34dB      | 24.6dB          |
|Av(in V/V)     | 8.6          | 13.68            |

![a5](https://github.com/user-attachments/assets/6f85826b-afc4-4928-956d-1dadf4af64e4)

**3db Bandwidth:**

The obatined 3db B.W=1.173GHz.

![a7](https://github.com/user-attachments/assets/e3878786-077a-4b18-aec6-b244297348b1)
