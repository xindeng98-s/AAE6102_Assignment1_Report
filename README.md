# AAE6102 Satellite Communication and Navigation Assignment 1 Report

## DENG Xin 23131686R


## Task 1: Acquisition
The first step in GNSS signal processing is acquisition, where Intermediate Frequency (IF) data is processed using a GNSS Software-Defined Radio (SDR). The acquisition process aims to detect satellite signals and estimate their coarse Doppler shift and code phase. The results of the acquisition provide an initial assessment of signal availability, ensuring that the satellites can be successfully tracked in subsequent steps.
Urban:
<img width="432" alt="image" src="https://github.com/xindeng98-s/AAE6102_Assignment1_Report/blob/main/figs/acqUrban.png" />
OpenSky:
<img width="432" alt="image" src="https://github.com/xindeng98-s/AAE6102_Assignment1_Report/blob/main/figs/acqOpensky.png" />


---

## Task 2: Tracking
The tracking phase involves adapting the tracking loop, specifically the Delay-Locked Loop (DLL), to maintain a steady lock on the satellite signals. Multiple correlators are implemented to generate correlation plots, allowing for an in-depth analysis of tracking performance. The impact of urban interference, such as multipath and signal blockage, is examined by analyzing the correlation peaks. In urban environments, reduced signal strength and distorted correlation functions can negatively affect tracking stability.

### Tracking results for Opensky Dataset and Urban Dataset
OpenSky:

<img width="432" alt="image" src="https://github.com/xindeng98-s/AAE6102_Assignment1_Report/blob/main/figs/TrackingOpenskyChannel1(PRN16)Results.png" />
<img width="432" alt="image" src="https://github.com/xindeng98-s/AAE6102_Assignment1_Report/blob/main/figs/TrackingOpenSkyChannel1CNO.png" />

Urban:

<img width="432" alt="image" src="https://github.com/xindeng98-s/AAE6102_Assignment1_Report/blob/main/figs/TrackingUrbanChannel1(PRN1)Results.png" />
<img width="432" alt="image" src="https://github.com/xindeng98-s/AAE6102_Assignment1_Report/blob/main/figs/TrackingUrbanChannel1CNO.png" />


### 2.1 Analysis of Tracking Performance Based on CN₀ and DLL Discriminator

When CN₀ exceeds 35 dB-Hz, DLL tracking remains consistently stable.
In contrast, a CN₀ level below 30 dB-Hz is associated with erratic DLL performance, indicating challenges in maintaining a reliable signal lock.
Satellites exhibiting intermediate CN₀ values (30-40 dB-Hz) occasionally encounter tracking instabilities, likely due to sporadic urban interference.

### 2.2 Impact of Urban Interference on Correlation Peaks
Urban environments significantly degrade GNSS tracking due to:
(1)Reflections from surrounding structures, such as buildings, introduce delayed signal replicas that interfere with the primary signal.
This phenomenon distorts correlation peaks, resulting in elevated DLL tracking errors.
(2)Physical obstructions, including buildings, trees, and tunnels, can abruptly reduce signal strength or completely block signals.
Consequently, the affected signals generate erratic outputs from the DLL discriminator, highlighting reduced tracking stability.
(3)Mobile receivers experience rapid shifts in signal strength, causing fluctuations in CN₀. Satellites exhibiting high CN₀ variability demonstrate inconsistent tracking performance.


## Task 3: Navigation Data Decoding
Once tracking is achieved, the navigation message is decoded to obtain essential parameters, such as ephemeris data. This data delivers accurate information about the satellite's position and clock, which is crucial for precise positioning. Successfully decoding at least one satellite’s data confirms the capability to extract vital orbital parameters needed for estimating the user's position.

output eph data:
<img width="432" alt="image" src="https://github.com/xindeng98-s/AAE6102_Assignment1_Report/blob/main/figs/OpenskyNavigation.png" />

## Task 4: Position and Velocity Estimation

## Task 5: Kalman Filter-Based Positioning


## Conclusion
The code is based on GPS_L1CA : https://github.com/gnsscusdr/CU-SDR-Collection/tree/main/GPS/GPS_L1CA .
