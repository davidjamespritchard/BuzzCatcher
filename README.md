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

To start click **PLAY** on the top bar. The live data will then start to be displayed in the **LIVE** figure and the realised sampling rate and loop frequency will be displayed.
 
 
![Play](/images/play.png)


### Collecting Samples

To collect a sample, press the **COLLECT** button.


![Collect](/images/collect.png)


### Saving or Discarding Samples

After evaluating the collected data you can either SAVE the collected data or discard and replace it.
To save the collected data, press the **SAVE** button.
 
 
![Save](/images/save.png)


Otherwise click **COLLECT** to discard the current collected data and to take a new sample.


# Under the Hood

## A Simplified View of How it Works

### The LIVE loop

Pressing **PLAY** starts data collection, feeding data into the **LIVE** data loop, which is displayed in the **LIVE figure**.
The loop contains **X** samples, in which **X = SECONDS TO CAPTURE X SAMPLING RATE**.
 
 
 ![StartLoop](/images/startLoop.png)
 
 
When the loop is full, the size is kept at **X** samples by removing the oldest samples as new ones are added.


![StartLoop2](/images/startLoop2.png)


### Collecting Data and the EVALUATION loop

When the collect button is pressed, new data continues to feed into the **LIVE** loop for **Y** samples (determined by the **POST-CLICK SAMPLES** setting). 
 
  
 ![Collect1](/images/Collect1.png)
 
 
Once **Y** new samples have been added (and **Y** *old* samples discarded) the data in the **LIVE** loop will move to the **EVALUATION** loop. 
 
 
![Collect2](/images/Collect2.png)

  
Once all of the **LIVE** loop data has been transferred, the **EVALUATION** loop closes and the **LIVE** loop refills itself. 
The collected sample can then be inspected on each channel individually (**CHANNEL 1** and **CHANNEL 2** figures).


![Collect3](/images/Collect3.png)
 
 
### Saving or Discarding Collected Data
 
After evaluating the collected data you can either **SAVE** the collected data or discard and replace it.
Pressing the **SAVE** button results in the collected data in the **EVALUATION** loop being packaged with data about the settings and sent to the PC.


![Saving](/images/Save1.png)


To discard and replace the collected data, simply press **COLLECT** again. This results in the previously collected data being discarded. 


![Discard1](/images/Discard1.png)


And a new set of collected data will be transferred from the **LIVE** data loop to the **EVALUATION** loop for inspection.


![Discard2](/images/Discard2.png)
