# Linear Integrated Circuit
# Current Mirroring Experiment

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

The Expected gain of the circuit is 10V/V.But the obtained gain from the transient analysis is 9.65V/V.


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
|Av(in V/V)     | 10           | 9.65            |

**3db Bandwidth:**

The obatined 3db B.W=2.267GHz.

![Screenshot 2025-03-22 155941](https://github.com/user-attachments/assets/f162d225-40dd-4f49-b466-eae9243c31a6)

