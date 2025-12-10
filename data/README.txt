README: HEI-VOC conc vs distance



DATASET OVERVIEW

File Name: HEI-VOC conc vs distance.xlsx

This dataset contains environmental monitoring and modeling data related to Oil & Gas (O&G) operations. It links specific emission sources (well pads) to monitoring sites ("Trigger Sites") and provides extrapolated Volatile Organic Compound (VOC) concentrations.

The dataset combines field measurements (canister samples) with AERMOD dispersion modeling to estimate VOC concentrations at the monitoring site and at incremental distances (500 ft to 5000 ft) from the source.



DATA STRUCTURE

The dataset contains metadata regarding the operation, temporal data, meteorological data, and three primary categories of concentration data:

1. Extrapolated 1-hr VOC Concentrations: Extrapolated from triggered canister samples.
2. AERMOD Simulation Data: Normalized dispersion factors based on a 1 g/s emission rate.
3. Estimated Distance-Based Concentrations: VOC specific concentrations calculated for distances ranging from 500 to 5000 ft.



VARIABLE DICTIONARY

1. Metadata & Operational Information

* Source: Name of the emission well pad (Source of emission).
* Trig_Site: Name of the monitoring site where the canister sample was collected.
* Operation: Type of O&G operation occurring at the Source well pad (e.g., Drilling, Flowback).
* distance (site, pad) ft: The distance between the Source and the Trig_Site. Unit: Feet.
* Start_Date_Time: Date and time when sample collection began.
* Stop_Date_Time: Date and time when sample collection ended.
* Temperature (K): Ambient temperature during the sampling hour. Unit: Kelvin.

2. Measured VOC Concentrations (1-hour Extrapolated)

There are 53 columns representing different VOC species measured. These are generally formatted as "1-hr_[VOC Name]".

NMVOC: Non-Methane Volatile Organic Compounds. This represents the sum of all measured VOC concentrations excluding Methane.

1-hour extrapolation method: The triggered samples were collected in approximately 1-minute. VOC concentrations in these triggered canister samples were extrapolated to 1-hour concentrations based on the corresponding PID sensor readings.

While most VOC species are measured in ppb, there are specific exceptions:

* General VOCs: ppbv
* Methane: ppmv
* C2HCl3 and C2Cl4: pptv

3. AERMOD Simulated Concentrations (Unit Emission Rate)

These columns represent dispersion modeling results using AERMOD, assuming a normalized emission rate of 1 g/s.

* AERMOD CONC Site (unit ER): Simulated concentration at the exact location of Trig_Site. Unit: ug/m3.
* AERMOD CONC [X]ft (unit ER): Simulated concentration at distance X from the Source in the direction of the Trig_Site. Increments occur every 500ft up to 5000ft. Unit: ug/m3.

4. Estimated VOC Concentrations at Distances

This section comprises approximately 530 columns. It represents the estimated concentration of the 53 specific VOC species at 10 different distance increments.

* Naming Convention: [VOC Name] [Distance]ft (ppb)
* Distance Increments: 500 ft to 5000 ft (in 500 ft steps).
* Direction: Estimates are calculated along the vector from the Source to the Trig_Site.
* Unit: ppb.



NOTE ON BACKGROUND CORRECTION (ZERO VALUES):

Background correction was performed when estimating these concentrations (calculated as 1-hr concentration minus background concentration). In cases where the background concentration exceeded the 1-hour concentration (resulting in a negative value), the concentration estimate has been assigned a value of 0.



SUMMARY OF DISTANCES

For both AERMOD and Estimated VOC data, the following distance intervals are provided:

* 500 ft
* 1000 ft
* 1500 ft
* 2000 ft
* 2500 ft
* 3000 ft
* 3500 ft
* 4000 ft
* 4500 ft
* 5000 ft
