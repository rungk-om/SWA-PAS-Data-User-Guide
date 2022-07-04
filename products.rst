PAS L2 Data Products
--------------------

We produce 3 PAS Level-2 (L2; scientific data level) products in `CDF <https://cdf.gsfc.nasa.gov/>`_ (NASA's Common Data Format) as follows.

1. **3D velocity distribution function**

   e.g., solo_L2_swa-pas-vdf_YYYYMMDD_Vxx.cdf

2. **1D energy differential flux**

   e.g., solo_L2_swa-pas-eflux_YYYYMMDD_Vxx.cdf

3. **Ground moments**

   e.g., solo_L2_swa-pas-grnd-mom_YYYYMMDD_Vxx.cdf

where *YYYYMMDD* is the year, month, day of the data (e.g., 20220403) and *Vxx* is the version of the file (e.g., V02).

.. tip::
   Visualization of SWA-PAS data are available through CLweb (http://clweb.irap.omp.eu/) and AMDA (http://amda.cdpp.eu/).

3D velocity distribution function data
======================================
In this section the CDF variables are shown in bold.

The 3D velocity distribution function CDF file consists of 3D arrays (variable “**vdf**”) of [11 azimuth, 9 elevations, 96 energies] of the ion number density in the phase space expressed in s :math:`^3` m :math:`^{-6}`. Since the instant sampling may cover just a part of the full angular-energy range, the data record contains also the start and number of the elevation bins (“**start_elevation**”, “**nb_elevation**”), the start and number of the azimuth bins (“**start_CEM**”,”**nb_CEM**”), and the start and number of the energy bins (“**start_energy**”,”**nb_energy**”). User shall use only records of the categories (variable “Info”) as follows:

1. Normal sampling, one “**vdf**” each 4 sec
2. Snapshot sampling, “**nb_K**” VDFs per second
3. Burst sampling, “**nb_K**” VDFs per second

As of the version 2 (V02) of VDF data products, we have the following parameters.

..
   .. csv-table:: Brief description of key parameters
      :file: table/CDF_VDF_PAS_parameters-var_type-data.csv
      :header-rows: 1


.. list-table:: Table 5.1 Brief description of parameters in the PAS 3D VDF file
   :header-rows: 1

   * - Parameters
     - Description
     - Data type
     - Dimension
   * - Azimuth
     - Center of CEM bins (azimuth)
     - CDF_REAL4
     - [11]
   * - Elevation
     - Center of elevation bins
     - CDF_REAL4
     - [9]
   * - Elevation_correction
     - Elevation correction for each energy
     - CDF_REAL4
     - [96]
   * - Energy
     - Center of energy bins
     - CDF_REAL4
     - [96]
   * - Epoch:
     - Epoch encoded as Terrestrial Time on rotating Earth geoid, ns since J2000
     - CDF_TIME_TT2000
     - [21314]
   * - Full_azimuth
     - Full definition azimuth table
     - CDF_REAL4
     - [11, 9, 3]
   * - Full_elevation
     - Full definition elevation table
     - CDF_REAL4
     - [11, 9, 3]
   * - Half_interval
     - Acquisition half interval
     - CDF_REAL4
     - [21314]
   * - Info
     - Info 0:Ground, 1:Normal, 2:Snapshot, 3:Burst, 4:Engineering, 5:Calib
     - CDF_UINT1
     - [21314]
   * - PAS_to_RTN
     - PAS to RTN transformation matrix
     - CDF_REAL8
     - [21314, 3, 3]
   * - SCET
     - Elapsed time on the onboard clock
     - CDF_REAL8
     - [21314]
   * - delta_Elevation
     - Delta elevation table
     - CDF_REAL4
     - [9]
   * - delta_m_Energy
     - Delta minus energy bins
     - CDF_REAL4
     - [96]
   * - delta_p_Energy
     - Delta plus energy bins
     - CDF_REAL4
     - [96]
   * - nb_CEM
     - CEM number
     - CDF_INT2
     - [21314]
   * - nb_K
     - Number of sub-sampings per second
     - CDF_INT2
     - [21314]
   * - nb_elevation
     - Number elevation bin
     - CDF_INT2
     - [21314]
   * - nb_energy
     - Number energy bin number
     - CDF_INT2
     - [21314]
   * - quality_factor
     - Data quality factor
     - CDF_REAL4
     - [21314]
   * - start_CEM
     - Start CEM
     - CDF_INT2
     - [21314]
   * - start_elevation
     - Start elevation bin
     - CDF_INT2
     - [21314]
   * - start_energy
     - Start energy bin
     - CDF_INT2
     - [21314]
   * - total_count
     - Total count
     - CDF_REAL4
     - [21314]
   * - unrecovered_count
     - Unrecovered count
     - CDF_REAL4
     - [21314]
   * - vdf
     - Velocity Distribution Function
     - CDF_REAL4
     - [21314, 11, 9, 96]

.. seealso::
   Full details of the parameters https://docs.google.com/spreadsheets/d/1dT-6wA94DajFROD3tSJ5HW7rJFuj_W_uG5ZIQjx5Z_E/edit?usp=sharing

1D Differential Energy Flux
============================

1D Differential Energy flux CDF file contain original velocity distribution function integrated over elevation and azimuth and converted to the differential energy flux. The value is expressed in cm :math:`^{-2}`  s :math:`^{-1}` eV / eV. Since the instant sampling may cover just a part of the full energy range, the data record contains also the start and number of the energy bins (“**start_energy**”,”**nb_energy**”). User shall use only records of the categories (variable “**Info**”) as follows.

1. Normal sampling, one “**eflux**” each 4 sec
2. Snapshot sampling, “**nb_K**” efluxs per second
3. Burst sampling, “**nb_K**” efluxs per second

The brief description is in Table 5.2 below.

.. list-table:: Table 5.2 Brief description of PAS 1D differential energy flux products
   :header-rows: 1

   * - Parameters
     - Description
     - Data type
     - Dimension
   * - Energy
     - Center of energy bins
     - CDF_REAL4
     - [96]
   * - Epoch
     - Epoch encoded as Terrestrial Time on rotating Earth geoid, ns since J2000
     - CDF_TIME_TT2000
     - [21314]
   * - Half_interval
     - Acquisition half interval
     - CDF_REAL4
     - [21314]
   * - Info
     - Info 0:Ground, 1:Normal, 2:Snapshot, 3:Burst, 4:Engineering, 5:Calib
     - CDF_UINT1
     - [21314]
   * - SCET
     - Elapsed time on the onboard clock
     - CDF_REAL8
     - [21314]
   * - delta_m_Energy
     - Delta minus energy bins
     - CDF_REAL4
     - [96]
   * - delta_p_Energy
     - Delta plus energy bins
     - CDF_REAL4
     - [96]
   * - eflux:
     - Energy Flux (Omni-directional)
     - CDF_REAL4
     - [21314, 96]
   * - nb_energy
     - Number energy bin number
     - CDF_INT2
     - [21314]
   * - quality_factor
     - Data quality factor
     - CDF_REAL4
     - [21314]
   * - start_energy
     - Start energy bin
     - CDF_INT2
     - [21314]
   * - total_count
     - Total count
     - CDF_REAL4
     - [21314]
   * - unrecovered_count
     - Unrecovered count
     - CDF_REAL4
     - [21314]

.. seealso::
   Full details of the parameters https://docs.google.com/spreadsheets/d/1edugYSv-E9PFOstN4KwQwRJAss5oDhqKxfKFBoEd0_M/edit?usp=sharing

PAS Ground Moments
==================

Ground moments contain the number density, the velocity vector, the pressure tensor and the temperature of the proton peak, extracted from the 3D VDF. User shall use only records of the categories (variable “**Info**”) as follows:

1. Normal sampling, one measurement each 4 sec
2. Snapshot sampling, “**nb_K**” measurements per second
3. Burst sampling, “**nb_K**” measurements per second

The “**validity**” flag shows the data quality. Do not use the data labeled as “1” since the number density and the pressure could be too low. Use the data labeled “2” with attention because the data could be noisy.

The brief description is in the Table 5.3 below.

.. list-table:: Table 5.3 Brief description of PAS ground moments data
   :header-rows: 1

   * - Parameters
     - Description
     - Data type
     - Dimension
   * - Epoch
     - Epoch encoded as Terrestrial Time on rotating Earth geoid, ns since J2000
     - CDF_TIME_TT2000
     - [21314]
   * - Half_interval
     - Acquisition half interval
     - CDF_REAL4
     - [21314]
   * - Info
     - Info 0:Ground, 1:Normal, 2:Snapshot, 3:Burst, 4:Engineering, 5:Calib
     - CDF_UINT1
     - [21314]
   * - N
     - Density in cm :math:`^{-3}`
     - CDF_REAL4
     - [21314]
   * - P_RTN
     - Pressure tensor in RTN frame
     - CDF_REAL4
     - [21314, 6]
   * - P_SRF
     - Pressure tensor in SRF frame
     - CDF_REAL4
     - [21314, 6]
   * - SCET
     - Elapsed time on the onboard clock
     - CDF_REAL8
     - [21314]
   * - T
     - Temperature
     - CDF_REAL4
     - [21314]
   * - TxTyTz_RTN
     - Temperature components (Tx, Ty, Tz) in RTN frame
     - CDF_REAL4
     - [21314, 3]
   * - TxTyTz_SRF
     - Temperature components (Tx, Ty, Tz) in SRF frame
     - CDF_REAL4
     - [21314, 3]
   * - V_RTN
     - Velocity in RTN frame
     - CDF_REAL4
     - [21314, 3]
   * - V_SOLO_RTN
     - Solar Orbiter spacecraft velocity in RTN frame
     - CDF_FLOAT
     - [21314, 3]
   * - V_SRF
     - Velocity in SRF frame
     - CDF_REAL4
     - [21314, 3]
   * - quality_factor
     - Data quality factor
     - CDF_REAL4
     - [21314]
   * - total_count
     - Total count
     - CDF_REAL4
     - [21314]
   * - unrecovered_count
     - Unrecovered count
     - CDF_REAL4
     - [21314]

.. seealso::
   Full details of the parameters https://docs.google.com/spreadsheets/d/1_f5nZnHbt26nR4SFmdiRa7MjjHdQC0GxJDqEyoFxFIM/edit?usp=sharing
