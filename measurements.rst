PAS measurements
-------------------

Here we provide a brief description of SWA-PAS measurements.

Design
======
PAS is designed to continuously determine the 3D distribution functions of the dominant ions of the solar wind, from 200 eV to 20 KeV, without mass and charge selection. In practice, this concerns mostly the proton and alpha populations. These measurements are used to calculate the density, speed, pressure, and temperature tensors of the main component of the solar wind.

Resolution and coverage
=======================
At full resolution, PAS measures the 3D ion distribution function, in the form of arrays of 96 energies, 11 azimuth angles, and 9 elevation angles, in about ~1 second. The energy and the angle of elevation are selected by imposing different high voltages on the electrodes of the deflection system and the electrostatic analyzer. The 11 azimuthal angles correspond to the 11 detectors of the instrument (called "channeltron").

Reduced set and coverage for burst mode
=======================================
In "burst" mode, the measurement rate can reach up to 20 Hz. The phase space sampling is then reduced, for example by 24 energies and 5 deflections, which allows to increase the time cadence of distribution functions measurements. An algorithm (peak tracking procedure) is used to select the peak of the distribution and to center sampling around this peak.

Different settings for normal mode and burst mode
=================================================
The different types of sampling are programmed in the form of cyclograms. They define the operation of the instrument over periods of several days. In normal mode, the functions are measured every 4 s with, every 300 s, a short burst mode of 9 s (SnapShot). ‘Long’ burst mode is also acquired every day, consisting of 300 s of continuous sampling at high cadence. The sampling frequency during bursts or snapshots is generally of 4 distributions / s (4 Hz analysis).


.. seealso::
   See full description at https://doi.org/10.1051/0004-6361/201937259
