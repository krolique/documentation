Transitor Symbols
-----------------


+---------------------------------------------+------------------------+-------------------------------------------------------------------------------+
|   Symbol                                    |    Name                |   Description                                                                 |
+=============================================+========================+===============================================================================+
| .. image:: images/NPN-transistor.gif        | NPN Bipolar Transistor | Allows current flow when high potential at base (middle)                      |
+---------------------------------------------+------------------------+-------------------------------------------------------------------------------+
| .. image:: images/PNP-transistor.gif        | PNP Bipolar Transistor | Allows current flow when low potential at base (middle)                       |
+---------------------------------------------+------------------------+-------------------------------------------------------------------------------+
| .. image:: images/Darlington-transistor.gif | Darlington Transistor  | Made from 2 bipolar transistors. Has total gain of the product of each gain.  |
+---------------------------------------------+------------------------+-------------------------------------------------------------------------------+
| .. image:: images/JFET-N-transistor.gif     | JFET-N Transistor      | N-channel field effect transistor                                             |
+---------------------------------------------+------------------------+-------------------------------------------------------------------------------+
| .. image:: images/JFET-P-transistor.gif     | JFET-P Transistor      | P-channel field effect transistor                                             |
+---------------------------------------------+------------------------+-------------------------------------------------------------------------------+
| .. image:: images/NMOS-transistor.gif       | NMOS transistor        | N-channel MOSFET transistor                                                   |
+---------------------------------------------+------------------------+-------------------------------------------------------------------------------+
| .. image:: images/PMOS-transistor.gif       | PMOS Transistor        | P-channel MOSFET transistor                                                   |
+---------------------------------------------+------------------------+-------------------------------------------------------------------------------+



NPN
---
NPN is one of the two types of bipolar transistors, consisting of a layer of 
P-doped semiconductor (the "base") between two N-doped layers. A small current
entering the base is amplified to produce a large collector and emitter
current. That is, when there is a positive potential difference measured from
the emitter of an NPN transistor to its base (i.e., when the base is high
relative to the emitter) as well as positive potential difference measured from
the base to the collector, the transistor becomes active. In this "on" state,
current flows between the collector and emitter of the transistor. Most of the
current is carried by electrons moving from emitter to collector as minority
carriers in the P-type base region. To allow for greater current and faster
operation, most bipolar transistors used today are NPN because electron
mobility is higher than hole mobility.

PNP
---
The other type of BJT is the PNP, consisting of a layer of N-doped
semiconductor between two layers of P-doped material. A small current leaving
the base is amplified in the collector output. That is, a PNP transistor is
"on" when its base is pulled low relative to the emitter. In a PNP transistor,
emitter-base region is forward biased. so electric field and carriers will be
generated. They should flow towards the base junction, but the base part is
very thin and has low conductivity. the reverse biased collector base part has
generated holes. so due to the electric field, carriers or electrons get
pulled by the holes.

The arrows in the NPN and PNP transistor symbols are on the emitter legs and
point in the direction of the conventional current flow when the device is in
forward active mode.

Darlington
----------
In electronics, the Darlington transistor (often called a Darlington pair) is
a compound structure consisting of two bipolar transistors (either integrated
or separated devices) connected in such a way that the current amplified by
the first transistor is amplified further by the second one. This configuration
gives a much higher current gain than each transistor taken separately and, in
the case of integrated devices, can take less space than two individual
transistors because they can use a shared collector. Integrated Darlington
pairs come packaged singly in transistor-like packages or as an array of
devices (usually eight) in an integrated circuit.

JFET Transistor
-----------------
The junction gate field-effect transistor (JFET or JUGFET) is the simplest
type of field-effect transistor. They are three-terminal semiconductor devices
that can be used as electronically-controlled switches, amplifiers, or
voltage-controlled resistors.

Unlike bipolar transistors, JFETs are exclusively voltage-controlled in that
they do not need a biasing current. Electric charge flows through a
semiconducting channel between source and drain terminals. By applying a
reverse bias voltage to a gate terminal, the channel is "pinched", so that the
electric current is impeded or switched off completely. A JFET is usually on
when there is no potential difference between its gate and source terminals.
If a potential difference of the proper polarity is applied between its gate
and source terminals, the JFET will be more resistive to current flow, which
means less current would flow in the channel between the source and drain
terminals. Thus, JFETs are sometimes referred to as depletion-mode devices.

JFETs can have an n-type or p-type channel. In the n-type, if the voltage
applied to the gate is less than that applied to the source, the current will
be reduced (similarly in the p-type, if the voltage applied to the gate is
greater than that applied to the source). A JFET has a large input impedance
(sometimes on the order of 1010 ohms), which means that it has a negligible
effect on external components or circuits connected to its gate.

MOS transistor 
--------------
The metal–oxide–semiconductor field-effect transistor (MOSFET, MOS-FET, or
MOS FET) is a type of transistor used for amplifying or switching electronic
signals.

Although the MOSFET is a four-terminal device with source (S), gate (G), drain
(D), and body (B) terminals,[1] the body (or substrate) of the MOSFET is often
connected to the source terminal, making it a three-terminal device like other
field-effect transistors. Because these two terminals are normally connected
to each other (short-circuited) internally, only three terminals appear in
electrical diagrams. The MOSFET is by far the most common transistor in both
digital and analog circuits, though the bipolar junction transistor was at one
time much more common.

The main advantage of a MOSFET over a regular transistor is that it requires
very little current to turn on (less than 1mA), while delivering a much higher
current to a load (10 to 50A or more).

In enhancement mode MOSFETs, a voltage drop across the oxide induces a
conducting channel between the source and drain contacts via the field effect.
The term "enhancement mode" refers to the increase of conductivity with
increase in oxide field that adds carriers to the channel, also referred to as
the inversion layer. The channel can contain electrons (called an nMOSFET or
nMOS), or holes (called a pMOSFET or pMOS), opposite in type to the substrate,
so nMOS is made with a p-type substrate, and pMOS with an n-type substrate
(see article on semiconductor devices). In the less common depletion mode
MOSFET, detailed later on, the channel consists of carriers in a surface
impurity layer of opposite type to the substrate, and conductivity is
decreased by application of a field that depletes carriers from this surface
layer.

