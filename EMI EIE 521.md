AOC

**Class Test**

Fig A1 shows the grounding arrangement of a mixed signal embedded system comprising analogue sensor interfaces, digital processing circuitry, a switched-mode power supply (SMPS), excessive radiated and high-speed communication interfaces. During EMC compliance testing, the system exhibited excessive radiated emissions, intermittent communication errors, and unstable sensor measurement. Preliminary analysis indicates that analogue and digital circuits share a common grounding path connected to the metal enclosure through long grounding conductors.

The following parameters are provided:

Ground Resistance: $R_g = 0.04\,\Omega$

Ground Inductance: $L_g = 2.0\,\mu H$

Interference frequency: $f = 100\,MHz$

Noise current: $I_n = 0.5\,A$

a) Discuss the role of grounding in EMC control and explain how poor grounding practices can increase conducted/radiated emissions.

b) Determine

i) The grounding-component inductive reactance $X_L = 2\pi f L$

ii) The grounding impedance $Z_g = R_g + j X_L$

iii) The induced noise voltage: $V_n = I_n Z_g$ 

i) Inductive Reactance

$X_L = 2\pi f L$

$X_L = 2\pi(100 \times 10^6)(2 \times 10^{-6})$

$X_L = 1256.4\,\Omega$

ii) $Z_g = R_g + j X_L$

$Z_g = 0.04 + j 1256.64\,\Omega$

$\vert{}Z_g\vert{} = \sqrt{R_g^2 + X_L^2}$

$= \sqrt{(0.04)^2 + (1256.4)^2}$

$= 1256.4\,\Omega$

$V_n = I_n Z_g$

$= 0.5 \times 1256.42$

$= 628V$

At $100\,MHz$ the inductive reactance dominates the ground impedance

$X_L \gg R_g$

The text extracted from the image is as follows:

|**Cable Belt**|**Terminate shields 360° to chassis at both ends**|**Prevent shield current & reduce common-mode noise leakage**|
|---|---|---|
|Minimize ground|Use short, wire short connections, use|reduces $X_L$, lowers noise voltage, and improves|
|modules|Copper planes|EMI performance.|

**Question 2**

Shows a six-layer mixed signal PCB comprising a 200MHz microprocessor, analogue sensor-condory circuits, a 500kHz switching power supply, Ethernet interfaces, and a chassis ground connection. During EMC compliance test, the system exceeded radiated emission limits, experienced intermittent communication errors and exhibited excessive noise in the analogue measurement channels.

The following parameters are provided:

Ground inductance: $L = 8nH$

Transient current: $\Delta I = 1.5A$

Rise time: $t_r = 2ns$

d) Recommend and justify an improved grounding strategy for the system: Single-point and multi-point grounding; Chassis grounding; Ground-plane implementation; Separation of analogue & digital grounding, cable-shield grounding & bonding.

**Possible Response**

1. Provides a low-impedance reference and return path for currents.
    
2. Minimizes voltage differences between circuit nodes (reduces noise coupling).
    
3. Shunts high frequency noise to ground by providing control path.
    

a) Improper grounding practices (Long paths, loops, shared impedance) increase:

i) Common-impedance coupling and ground bounce.

ii) Ground loops & circulatory currents.

iii) Common-mode noise & radiated emissions.

iv) Signal integrity degradation.

b) Given

$R_g = 0.04\,\Omega$

$L_g = 2.0\,\mu H = 2 \times 10^{-6}\,H$

$f = 100\,MHz = 100 \times 10^6\,Hz$

$I_n = 0.5\,A$

Even a moderate noise 0.5A produces a large ground voltage (628V) which can couple into sensitive circuits & cause significant EMI problems.

### c) Recommended Grounding Strategy

|**Item**|**Recommendation**|**Justification**|
|---|---|---|
|**Separated analog & digital grounds**|Use partitioned ground planes & connect at a sole point (star point)|Prevents digital switching noise from entering analog sectors|
|**Ground Planes**|Use continuous, low-impedance ground planes on PCB|Provide short return paths, low inductance & reduces radiation|
|**Single point / Multipoint**|Star (single point) at low frequencies; multipoint at high frequency|Single point avoids ground loops; multipoint reduces high frequency impedance|
|**Chassis grounding**|Bond chassis to earth with short, wire, low-inductance connection|Maintain chassis at earth potential, improve safety & stability|
d) PCB redesign strategy Use a continuous ground plane and avoid high speed signals crossing over discontinuities. Move decoupling capacitors near the power pins of the IC and keep the clock trace short. Functional placement of analogue, digital and power sections. Use matched differential pairs to improve element routs. Install ground via closely around high speed and noisy areas, and reduce the length of the chassis to the ground connection to reduce common mode emission. These changes will help to better control return current, decrease loop area and help to improve overall EMC performance.

