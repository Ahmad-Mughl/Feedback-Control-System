💡 Light Intensity Control Using Hardware-Based PID Controller

📌 Project Overview

This project focuses on the design and implementation of an analog hardware-based PID (Proportional-Integral-Derivative) controller to regulate the light intensity of a 5V DC tungsten filament bulb.

The system uses LM741 operational amplifiers to implement the proportional, integral, and derivative control actions. A Light Dependent Resistor (LDR) senses the bulb's light intensity and provides feedback to the controller. The PID controller processes the difference between the user-defined reference voltage and the feedback voltage to adjust the bulb's intensity automatically.

A 2N2222 NPN transistor is used as the output driver, while an oscilloscope is used to observe and analyze the system response.

The project demonstrates practical applications of analog control systems, operational amplifier configurations, feedback mechanisms, and PID controller design.

🎯 Project Objectives

Design and implement an analog PID controller using LM741 operational amplifiers.

Regulate the light intensity of a 5V DC tungsten filament bulb.

Implement a closed-loop feedback control system using an LDR.

Generate proportional, integral, and derivative control actions using analog circuits.

Minimize steady-state error and improve transient response.

Analyze system performance using an oscilloscope.

Maintain stable light intensity under external disturbances.

✨ Key Features

Fully analog PID controller implementation.

Real-time light intensity sensing through an LDR.

User-defined reference voltage for desired light intensity.

Differential amplifier for error signal generation.

Separate proportional, integral, and derivative stages.

Summing amplifier for combining PID outputs.

BJT-based output driver for controlling bulb power.

Closed-loop feedback mechanism.

Oscilloscope-based response monitoring and analysis.

🛠️ Hardware Components

Component

Quantity / Specification

Purpose

LM741 Operational Amplifier

5 ICs

PID controller and signal processing

2N2222 NPN BJT

1

Bulb output driver

Light Dependent Resistor

1

Light intensity sensing

Tungsten Filament Bulb

5V, 500mA

Controlled plant

Resistors

Assorted values

Gain adjustment and voltage division

Capacitors

Assorted values

Integration and differentiation

Potentiometer

1

Reference voltage and disturbance adjustment

Oscilloscope

1

Signal monitoring and response analysis

DC Power Supply

±6V and 5V

Circuit and bulb power

Component Values

Component

Value

R1

10kΩ

R2

100kΩ

R3

10kΩ

R4

100kΩ

R5

1MΩ

R6

10kΩ

R7

1kΩ

R8

10Ω

C1

1µF

C2

0.1µF

C3

10µF

⚙️ System Architecture

The system consists of five major functional blocks:

Input Sensing Block

Error Amplifier Block

PID Controller Block

Output Driver Block

Feedback Loop

1. Input Sensing Block

An LDR is used to detect variations in the light intensity of the tungsten filament bulb.

The LDR is configured in a voltage divider circuit.

Its resistance decreases as light intensity increases.

The resulting voltage variation represents the actual light intensity.

The feedback voltage is supplied to the error amplifier.

2. Error Amplifier Block

An LM741 operational amplifier is configured as a differential amplifier.

It compares the reference voltage with the LDR feedback voltage to generate the error signal:

[
e(t)=V_{ref}-V_{feedback}
]

The error signal represents the difference between the desired and actual light intensity.

3. PID Controller Block

The PID controller is implemented using separate operational amplifier configurations.

Proportional Controller (P)

Implemented using an inverting amplifier.

Produces an output proportional to the instantaneous error.

Provides an immediate response to changes in the reference or feedback signal.

[
P(t)=K_p e(t)
]

Integral Controller (I)

Implemented using an op-amp integrator with an RC network.

Accumulates the error over time.

Helps eliminate steady-state error.

[
I(t)=K_i\int e(t),dt
]

Derivative Controller (D)

Implemented using an op-amp derivative configuration.

Responds to the rate of change of error.

Improves transient response and helps reduce overshoot.

[
D(t)=K_d\frac{de(t)}{dt}
]

The outputs of all three stages are combined using a summing amplifier.

The overall PID control equation is:

[
u(t)=K_p e(t)+K_i\int e(t),dt+
K_d\frac{de(t)}{dt}
]

4. Output Driver Block

A 2N2222 NPN BJT is used to drive the tungsten filament bulb.

The PID output controls the transistor's base current.

The transistor regulates the power delivered to the bulb.

The bulb's intensity changes according to the controller output.

The output stage is designed around the bulb's 5V, 500mA operating constraints.

5. Feedback Loop

The LDR continuously senses the bulb's actual light intensity and sends the corresponding feedback voltage to the error amplifier.

The controller compares this feedback with the reference voltage and adjusts the output accordingly.

This process creates a closed-loop control system that compensates for disturbances and maintains the desired light intensity.

🔄 Working Principle

The project was developed using a modular implementation approach.

Open-Loop Testing: Initially, the bulb was operated without a controller. Changes in the applied voltage caused variations in light intensity, demonstrating that an open-loop system could not automatically compensate for disturbances.

Feedback Implementation: An LDR was introduced to measure the bulb's light intensity and convert the variations into a feedback voltage.

Error Generation: A differential amplifier compared the LDR feedback voltage with the user-defined reference voltage.

Proportional Control: The proportional stage was implemented first to provide an immediate response to the error signal.

Integral Control: The integral stage was introduced to reduce and eliminate steady-state error.

Derivative Control: The derivative stage was added to improve system dynamics and reduce oscillations and overshoot.

PID Output Combination: A summing amplifier combined the P, I, and D outputs to generate the final control signal.

Bulb Intensity Regulation: The control signal was applied to the 2N2222 transistor, which adjusted the power supplied to the bulb.

Performance Validation: An oscilloscope was used to observe the error signal and bulb voltage and evaluate the system response.

📊 Experimental Results

The implemented PID controller demonstrated effective light intensity regulation under the tested conditions.

Performance Parameter

Observed Result

Reference Voltage

3.3V

Feedback Accuracy

Within ±0.1V of reference

Settling Time

Approximately 1–2 seconds

Initial Overshoot

Approximately 10%

Overshoot After Tuning

Below 5%

Disturbance Recovery

Approximately 1.2–1.5 seconds

Operating Bulb Voltage

Approximately 3–3.5V

Operating Current

Approximately 300–350mA

Performance Observations

The proportional stage improved the initial response of the system.

The integral stage reduced steady-state error.

The derivative stage helped minimize overshoot and oscillations.

The controller compensated for changes in ambient light and other disturbances.

The LDR's nonlinear response required careful calibration.

Fine-tuning the PID gains improved system stability and transient performance.

🧪 Testing and Validation

The system was tested using different operating conditions:

Open-loop response without PID control.

Closed-loop response with proportional control.

Response after introducing integral control.

Response after introducing derivative control.

System behavior under external light disturbances.

Oscilloscope monitoring of error and bulb voltage.

PID gain adjustment to improve stability and reduce overshoot.

🧠 Concepts and Technologies Used

Concept

Application

PID Control Theory

Automatic light intensity regulation

Operational Amplifiers

Analog mathematical operations

Differential Amplifier

Error signal generation

Inverting Amplifier

Proportional control

Integrator

Integral control

Differentiator

Derivative control

Summing Amplifier

Combining PID outputs

LDR

Light intensity sensing

BJT Switching

Bulb power regulation

Closed-Loop Control

Feedback-based correction

Oscilloscope

System response analysis

📚 Alternative Design Approaches

Three possible approaches were considered:

Solution 1: Analog PID Using LM741

Uses separate op-amp stages for proportional, integral, and derivative control, along with a BJT driver and LDR feedback.

Solution 2: Hybrid Analog-Digital PID

Uses an analog sensing circuit and a microcontroller to calculate PID control digitally and generate a PWM output.

Solution 3: Single Op-Amp PID

Uses a simplified single-op-amp implementation to combine the PID control functions.

Selected Approach: Solution 1 was selected because it complied with the project constraints and provided a practical way to understand and implement individual PID control actions using analog circuitry.

⚠️ Challenges and Limitations

Nonlinear resistance characteristics of the LDR.

PID gain selection and tuning.

Stability and overshoot reduction.

Limited bandwidth and phase characteristics of LM741 op-amps.

Bulb load variations during operation.

Calibration of the reference and feedback voltages.

🚀 Future Improvements

Use higher-performance operational amplifiers.

Implement LDR signal linearization.

Improve PID gain tuning for better transient response.

Investigate more efficient transistor or MOSFET driver stages.

Improve disturbance rejection and system stability.

Introduce adaptive PID tuning while maintaining the analog control architecture where possible.# Feedback-Control-System
