# Linear Integrated Circuit
# Differential Amplifier Experiment

## Aim

Design and Analyze the MOS differential amplifier circuit for the following specifications:

- Supply Voltage (Vdd) = 1.8V
- Power (P) <= 2.2mW
- Common Mode Input Voltage (Vicm) = 0.95V
- Output Common Mode Voltage (Vocm) = 1.1V
- Voltage at point P (Vp) = 0.4V

Perform:

DC Analysis, Transient Analysis, AC Analysis, Extract required parameters

## Circuit 1

### Circuit Diagram:

![exp-3_cir_dc](https://github.com/user-attachments/assets/8848c74c-cc72-4f3a-b6f1-9b68bfa684f7)

The given circuit is a MOS differential amplifier, which consists of two NMOS transistors (CMOSN) configured as a differential pair. 

NMOS Transistors (M1 and M2): Act as the main amplifying elements, forming a differential pair that amplifies the difference between the two input signals.

Output Nodes (Vout1 and Vout2): The differential output signals are taken from these points.

Design

Calculation:

Determine Iss (Source Current):

Iss = Power / Vdd

Iss = 2.2mW / 1.8V = 1.22mA

Therefore, Id1=Id2=0.61mA

Calculate Rd (Drain Resistance):

Vdd=(Id*Rd)+Vocm

Rd = (Vdd - Vocm ) / Id

Rd = (1.8V - 1.1V) / 0.61mA

Rd = 1147 Ω

Calculate Rss (Source Resistance):

Rss = Vp / Iss

Rss = 0.4V / 1.22mA

Rss = 327.86 Ω

DC Analysis :

- Make the necessary connections as per the circuit daigram.
- Set the Rd and Rss values such that the transistors will operate in saturation region .
- Vary Rd and W/L to get the required Vocm and Id.
- Go to "Simulate" -> "Edit Simulation Cmd" -> "DC op pnt".
  
  ![exp-3_out_dc](https://github.com/user-attachments/assets/9d90d2d6-151e-4456-9599-98a1306c6a62)
  
 - After this in "view command" go to " SPICE Output Log " option to check Vgs, Vth ,Vds etc.
  
  ![exp-3_op_log_dc](https://github.com/user-attachments/assets/5f8bed14-ea3a-40e1-9897-28879c361961)

