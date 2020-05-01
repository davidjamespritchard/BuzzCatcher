# BuzzCatcher
LabView project for capturing vibrations from two sensors simultaneously. Used in Pritchard &amp; Vallejo Marin (2020)

# Quick Start

## To get started without understanding how it works


Before starting set the *parameters*. 

* The **SAMPLING RATE** determines the number of samples the cRIO collects per second. 

* The **SECONDS TO CAPTURE** determines how many samples to collect. The total number of samples collected equals (**SECONDS TO CAPTURE X SAMPLING RATE**). 

* The number of **POST-CLICK SAMPLES** determines how much of the sample comes from before the collect button was pressed and how many after. The total number of samples does not change, only the number before and after the collect button is pressed. 

* The **VIBROMETER SETTINGS** and **VOLTAGE GAIN** are for reference, do not change the collected data, and are determined by the settings on the laser vibrometer and accelerometer respectively.  

* The **FILE NAME**  determines the name of the resulting file. 

* The **FILE PATH** can be amended in the save_preview VI.


![Settings](/images/settings1.png)

![Settings](/images/settings2.png)


To start click **PLAY** on the top bar
 
 
![Play](/images/play.png)


To collect a sample, press the **COLLECT** button.


![Collect](/images/collect.png)


After evaluating the collected data you can either SAVE the collected data or discard and replace it.
To save the collected data, press the **SAVE** button.
 
 
![Save](/images/save.png)


Otherwise click **COLLECT** to discard the current collected data and to take a new sample.

