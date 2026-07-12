Class Test Fig A1 shows the grounding arrangement of a mixed signal embedded system comprising analogue sensor interfaces, digital processing circuitry, a switched-mode power supply (SMPS), excessive radiated and high-speed communication interfaces. During EMC compliance testing, the system exhibits excessive radiated emissions, intermittent communication errors, and unstable sensor measurement. Preliminary analysis indicates that analogue & digital circuits share a common grounding path connected to the metal enclosure through long grounding conductors.

The following parameters are provided: Ground Resistance: Rg​=0.04Ω Ground Inductance: Lg​=2.0μH Interference frequency: f=100MHz Noise current: In​=0.5A

a) Discuss the role of grounding in EMC control and explain how poor grounding practices can increase conducted & radiated emissions.

b) Determine 
i) The grounding-conductor inductive reactance XL​=2πfL 
ii) The grounding impedance Zg​=Rg​+jXL​ 
iii) The induced noise voltage: Vn​=In​Zg​

c) Recommend and justify an improved grounding strategy for the system: Single-point and multi-point grounding; chassis grounding; ground plane implementation; separation of analogue & digital grounding; cable shield grounding & bonding.

**Possible Response**

i) Provides a low-impedance reference and return path for currents

ii) Minimizes voltage differences between circuit nodes (reduces noise coupling)

iii) Shunts high frequency noise to ground by providing control path

a) Improper grounding practices (Long paths, loops, shared impedance) increase:

i) Common-impedance coupling and ground bounce

ii) Ground loops & circulatory currents

iii) Common-mode noise & radiated emissions

iv) Signal integrity degradation.

b) Given:

$R_g = 0.04\Omega$

$L_g = 2.0\mu H = 2 \times 10^{-6} H$

$f = 100MHz = 100 \times 10^6 Hz$

$I_n = 0.5A$

i) Inductive Reactance

$X_L = 2\pi fL$

$X_L = 2\pi(100 \times 10^6)(2 \times 10^{-6})$

$X_L = 2\pi(200) = 400\pi$

$X_L = 1256.4 \Omega$

ii) $Z_g = R_g + j X_L$

$Z_g = 0.04 + j 1256.64 \Omega$

$\vert{}Z_g\vert{} = \sqrt{R_g^2 + X_L^2}$

$= \sqrt{(0.04)^2 + (1256.4)^2}$

$= 1256.42$

$V = I_n Z_g$

$= 0.5 \times 1256.42$

$= 628V$

at 100MHz the inductive reactance dominates the ground impedance

$X_L \gg R_g$

Even a moderate noise (0.5A) produces a large ground voltage ($\approx 628V$) which can couple into sensitive circuits & cause significant EMI problems.

### c) Recommended Grounding Strategy

| **Item**                               | **Recommendation**                                                     | **Justification**                                                             |
| -------------------------------------- | ---------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| **Separated analog & digital grounds** | Use partitioned ground planes & connect at a single point (star point) | Prevents digital switching noise from entering analog sectors                 |
| **Ground Planes**                      | Use continuous, low-impedance ground planes on PCB                     | Provide short return paths, low inductance & reduces radiation                |
| **Single point/ Multipoint**           | Star (single point) at low frequencies, multipoint at high frequency   | Single point avoids ground loops; multipoint reduces high frequency impedance |
| **Chassis grounding**                  | Bond chassis to earth with short, wide, low-inductance connection      | Maintains chassis at earth potential improves shielding & safety              |
| Cable shield grounding                 | Terminate shields $360^\circ$ to chassis at both ends                  | Prevent shield current & reduces common-mode noise leakage                    |
| Minimize ground impedance              | Use short, wide connectors, use copper planes, straps & multiple vias  | reduces $X_L$, lowers noise voltage, and improves EMI performance.            |

### Question 2

Shows a six-layer mixed signal PCB comprising a 200MHz microcontroller, analogue sensor-conditioning circuits, a 500kHz switching power supply, Ethernet interfaces, and a chassis ground connection. During EMC compliance tests the system exceeded radiated emission limits, experienced intermittent communication errors and exhibited excessive noise in the analogue measurement channels.

The following parameters are provided:

Ground inductance: $L = 8nH$

Transient current: $\Delta I = 1.5A$

Rise time: $t_r = 2ns$

a) Using figure 1, identify and analyze the likely causes of the EMC issues. Your discussion should consider radiated emissions, conducted emissions, coupling mechanisms and signal integrity degradation.

b) Determine

i) The rate of current change $di/dt$

ii) The voltage developed across the grounding inductance $V = L(di/dt)$

iii) The significance of the calculated voltage with respect to EMC performance.

c) Critically evaluate the PCB layout in terms of return current paths, ground planes discontinuities, decoupling strategy, high-speed signal routing and common-mode/differential mode noise generation.

d) Recommend and justify practical design modifications to improve EMC performance considering component placement, routing, grounding, power distribution, via stitching and chassis ground implementation.

**Possible Response**

a) The long clock trace and large switching current loops are the most likely sources of radiated emissions. Conducted emissions are generated by the switching power supply and propagated through shared power & ground paths.

The ground-plane splits disrupts return current flow, increasing loop area and common mode radiates.

Dense parallel routing increases crosstalk.

Shared analog & digital paths allow switching noise into the sensor-conditioning circuit.

b) i) Rate of Current Charge

$$\frac{di}{dt} = \frac{\Delta I}{t_r}$$

$$\frac{di}{dt} = \frac{1.5}{2 \times 10^{-9}} = 7.5 \times 10^8 A/s$$

ii) Voltage across Ground Inductance

$$V = L \left( \frac{di}{dt} \right)$$

$$V = (8 \times 10^{-9})(7.5 \times 10^8) = 6V$$

iii) A 6V transient is significant and can increase ground noise and signal integrity problems.

c) Critical evaluation of the PCB layout

The ground-plane split creates currents that are forced to go around the ground plane, which adds EMI, the decoupling capacitors are not close to the microcontroller, which means they are not very effective during switching events. The long clock trace is an effective radiator and parallel routing causes crosstalk.

Analog & digital return paths are shared, which can cause digital switching noise to affect sensitive signals. These layout issues have a direct impact on the observed EMC failure.

d) PCB Design Strategy: Use a continuous ground plane and avoid high speed signals crossing plane discontinuities. Move decoupling capacitors near the power pins of the IC and keep the clock trace short. Functional placement of analogue, digital and power sectors.

Use matched differential pairs to improve Ethernet route. Install ground via stitching around high speed and noisy areas, and reduce the length of the chassis to the ground connection to reduce common mode emission.

These changes will help to better control return current, decrease loop area and help to improve overall EMC performance.

Would you like to explore how to calculate the optimal placement for decoupling capacitors to further minimize ground bounce in your PCB design?