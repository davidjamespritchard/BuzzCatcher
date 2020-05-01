# BuzzCatcher
LabView project for capturing vibrations from two sensors simultaneously. Used in Pritchard &amp; Vallejo Marin (2020)

# Quick Start

## To get started without understanding how it works

### Opening the Programs

To start with open the Buzz Data Collection project. Click on the *save_preview.vi* file and the *collection_main.vi* file. The *collection_main* file will be on the cRIO device, so use + to expand the cRIO to find the file.


![Started](/images/root.png)


### Setting the Parameters

The first step is to enter the parameters into the two VIs.

* The **SAMPLING RATE** determines the number of samples the cRIO collects per second. 

* The **SECONDS TO CAPTURE** determines how many samples to collect. The total number of samples collected equals (**SECONDS TO CAPTURE X SAMPLING RATE**). 

* The number of **POST-CLICK SAMPLES** determines how much of the sample comes from before the collect button was pressed and how many after. The total number of samples does not change, only the number before and after the collect button is pressed. 

* The **VIBROMETER SETTINGS** and **VOLTAGE GAIN** are for reference, do not change the collected data, and are determined by the settings on the laser vibrometer and accelerometer respectively.  

* The **FILE NAME**  determines the name of the resulting file. 

* The **FILE PATH** can be amended in the save_preview VI.


![Settings](/images/settings1.png)

![Settings](/images/settings2.png)


### Starting Reading Data

To start click **PLAY** on the top bar
 
 
![Play](/images/play.png)


### Collecting Samples

To collect a sample, press the **COLLECT** button.


![Collect](/images/collect.png)


### Saving or Discarding Samples

After evaluating the collected data you can either SAVE the collected data or discard and replace it.
To save the collected data, press the **SAVE** button.
 
 
![Save](/images/save.png)


Otherwise click **COLLECT** to discard the current collected data and to take a new sample.

