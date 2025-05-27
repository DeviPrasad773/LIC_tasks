# **Monostable Multivibrator using 555 Timer IC**

## **Aim**

To create a circuit using a 555 Timer IC in monostable mode that produces a single output pulse lasting 0.5 milliseconds.

## **Theory**

A monostable multivibrator is a circuit that has one stable state and one temporary (unstable) state. It stays in the stable (LOW) state until it gets a trigger signal. When a trigger is applied, the output switches to HIGH for a short time and then goes back to LOW automatically.

The time the output stays HIGH is controlled by a resistor (R) and a capacitor (C), and it is calculated using this formula:

**T = 1.1 × R × C**

Where:

* **T** = Time in seconds (how long the output stays HIGH)
* **R** = Resistance in ohms (Ω)
* **C** = Capacitance in farads (F)

This setup is often used in applications like timers, delay circuits, and to avoid switch bounce.

## **Working**

In monostable mode:

* The 555 Timer's output is LOW by default.
* When a negative pulse is applied to pin 2, the output becomes HIGH.
* During this time, the capacitor charges through the resistor.
* Once the capacitor voltage reaches 2/3 of the supply voltage (Vcc), the timer switches the output back to LOW and discharges the capacitor.
* This process repeats every time a new trigger pulse is applied.

The time the output stays HIGH depends on the values of R and C using:
**T = 1.1 × R × C**

This mode is useful in systems where one trigger press should result in a single output pulse.

## **Calculation**

Given:

* **T = 0.5 ms = 0.0005 seconds**
* **C = 1 µF = 0.000001 farads**

Using the formula:
**R = T / (1.1 × C)**

Substitute the values:
**R = 0.0005 / (1.1 × 0.000001) = 454.54 Ω**

So, you can use a resistor close to **455 Ω**.

## **Procedure**

1. **Build the Circuit**: Set up the 555 Timer IC in monostable mode using standard circuit connections.
2. **Select Components**: Use R = 455 Ω and C = 1 µF to get a 0.5 ms pulse.
3. **Trigger the Timer**: Use a signal generator (or a push button) to send a trigger to pin 2.
4. **Observe Capacitor**: Watch how the capacitor charges and discharges.
5. **Measure Output**: Check if the output pulse is about 0.5 ms when the trigger is applied.

## **Simulation Result**


## **Inference**

* The output stays LOW until a trigger is given.
* After receiving the trigger, it becomes HIGH for 0.5 ms and then goes LOW again.
* This duration is controlled by the chosen resistor and capacitor values.
* The experiment proves that the 555 Timer in monostable mode can give accurate time delays.

## **Conclusion**

The 555 Timer IC worked as expected in monostable mode. It gave a 0.5 ms pulse when triggered, matching the value calculated using the formula **T = 1.1 × R × C**. This confirms its usefulness in timing applications.

---

# **Astable Multivibrator**

An astable multivibrator is a circuit that keeps switching between HIGH and LOW on its own. It doesn't need any trigger to work—it keeps generating a square wave signal continuously.

The ON and OFF times are decided by two resistors and one capacitor. These components set the frequency (how fast it switches) and the duty cycle (how long it stays HIGH vs LOW).

---

# **Op-Amp Differentiator**

This is a circuit using an op-amp where a capacitor is connected at the input and a resistor is used in the feedback path.

This circuit gives an output that is related to how fast the input changes. A quick change in input causes a sharp spike at the output. This is useful to detect edges or fast signal changes.

---

## **Complete Circuit Procedure**

1. **Build the Circuit**: Create a setup with four stages—Astable Multivibrator, Differentiator, Clipper, and Monostable Multivibrator.
2. **Calculate Components**:

   * Use suitable values of R1, R2, and C for the astable circuit to set frequency.
   * Choose values for the differentiator to get sharp spikes.
   * Design the clipper to limit the signal.
   * For monostable, calculate R and C to get a 0.5 ms output pulse.
3. **Trigger Flow**: The output from the clipper is used to trigger the monostable multivibrator.
4. **Analyze Outputs**: Check capacitor voltages and output signals at each stage using simulation or oscilloscope.
5. **Verify Output Time**: Measure the pulse width from the monostable and compare it with your calculation.

---


## **Simulation Results**



## **Inference**

* The monostable output remains LOW until triggered.
* On receiving a trigger, it turns HIGH for 0.5 ms and returns to LOW.
* Using C = 1 µF, the resistor was calculated as about 455 Ω to get this output.
* The setup successfully shows how a 555 Timer can generate exact delays.

