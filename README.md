# Playing poker at the Edge, part 1 of 2

## Introduction

As sometimes happens to all of us, we are presented with a solution but don't yet have a problem to solve! In this case the solution was that I got the chance to borrow a programmable robot arm for a few weeks, but as the robot was delivered much earlier than expected, I had not yet thought about a use case for it. Among other things I needed to decide about what objects to pick and place using the suction cup, and also what software to use for controlling the robot. **Insert/rewrite** After some quick deliberation I decided to use playing cards as they are uniform in size and also lightweight. For the controlling software I had initially thought about only using Python, but I quickly moved on to explore how to also use TinyML (Tiny Machine Learning) for a more rewarding experience.

This project is part one of two, showing how to classify poker cards into three categories, by using Edge Impulse and a supported board, SiLabs xG24. Part two continues with using the same hardware setup for controlling the robot arm to sort cards, but also showcases how to easily adapt it to sorting waste.

While one might think that classifying playing cards into only three classes is a piece of cake - actually it is when using Edge Impulse - the project also serves as a base to get started using the hardware and with a low learning curve. After you've got used with it, you can easily step up the ladder to more advanced projects.

**INSERT HIGH QUALITY IMAGE w/ Edge Impulse label**

## Use-case Explanation

As earlier mentioned I chose to classify playing cards for this project. While it is possible to classify cards into different suits, I decided to start simple by using three classes or labels: red cards, black cards, and cards with back side up. In addition I added a no card label to avoid the risk of an empty table being classified as a card. While classifying cards is pretty much straightforward, the typical rules also applied in this project: more images and also different type of images --> better performing model.

![](Card-01.png)
![](Card-02.png)

After initially having tested another board, I found that board to be a tad slow for my use case as the inferencing took over 1.2 seconds. Browsing through the boards Edge Impulse supports, I then decided to use the SiLabs xG24 dev kit together with an Arducam camera as I believed they would fit my purposes better. As it turned out, the inferencing was 3 times faster than the other board I'd tried!

The SiLabs xG24 dev kit is packed with sensors and features. Among the sensors are e.g. a relative humidity and temperature sensor, inertial sensor, stereo microphones, pressure sensor etc. Important features for this project was the Cortex-M33 processor, 256 kB RAM, and especially the AI/ML Hardware accelerator. It can even be operated with a coin-cell battery. While it is not equipped with a camera, it supports e.g. the Arducam OV2640 board which I also used.

## Components and Hardware Configuration

Hardware used:
* [SiLabs xG24-DK2601B EFR32xG24 Dev Kit](https://www.silabs.com/development-tools/wireless/efr32xg24-dev-kit?tab=overview)
* [Arducam B0067 2MP OV2640 SPI Camera for Arduino](https://www.welectron.com/Arducam-B0067-2MP-OV2640-SPI-Camera-for-Arduino_1)
* [Pin Header 2.54mm 1x20 Pin](https://www.welectron.com/Pin-Header-254mm-1x20-Pin) for soldering to the SiLabs board

Configure the hardware:
* To use the xG24 board with Edge Impulse, you first need to flash the Edge Impulse firmware, detailed steps are found from the [documentation](https://docs.edgeimpulse.com/docs/development-platforms/officially-supported-mcu-targets/silabs-xg24-devkit).
* Solder the header to the board
* Connect the Dupont cable (came with the Arducam) to the headers according to the [camera assembly](https://docs.edgeimpulse.com/docs/tutorials/hardware-specific-tutorials/object-detection-xg24-devkit#camera-assembly)
    * Before powering on, double-check and triple-check the connection

**Important:** Avoid touching the board or camera when they are powered. I learned this the hard way and burned one board, probably through ESD (electrostatic discharge) when pressing the reset button. The blue magic smoke that was released was unhealthy for me and especially for my wallet...

**INSERT HIGH QUALITY IMAGE w/ Edge Impulse label**


## Data collection

Software used:
* [Edge Impulse Studio & CLI (command-line interface)](https://www.edgeimpulse.com/)

* iPhone
* xG24

## Training and building the model
## Model deployment
## Results
## Conclusion





# Data Collection Process
Next we need to describe to a reader and demonstrate how data is collected.  Depending upon the type of the project, this might be done directly in the Edge Impulse Studio, via the use of a 3rd-party dataset, or data could be collected out in the field and later uploaded / ingested to Edge Impulse.  Data being captured should be explained, the specific process to capture it should be documented, and the loading of the data into Edge Impulse should be articulated as well.  Images will be helpful here, showing the device capturing data, or if you are making use of a pre-made dataset then you will need to describe where you acquired it, how you prepared the dataset for Edge Impulse, and what your upload process entails.  Pictures of the data capture and/or screenshots of loading the data will be needed.

# Training and Building the Model
Similar to the Data Collection Process section, a thorough description of the process used to build and train a model is important, so that readers can follow along and replicate your work.  Describe the elements in the Studio, the actions you take, and why.  Talk about the need for Training and Testing data, and when creating an Impulse,  Processing and Learning block options, Feature generation, and algorithm selection (FOMO, MobileNet, Yolo, etc) available to train and build the model.  Explain the selections you make, and the reasoning behind your choices.  Again images should be used here, screenshots walking a user through the process are very helpful.

# Model Deployment
Go into detail about the process of getting your resulting model into your application and onto your hardware.  This will of course vary by the target hardware, but explain what is occurring and how to flash your firmware, import the model if it’s a Linux device, or include a Library directly in your application.  Again describe the options presented to a user, and explain why you make the selections you do.  A few screenshots of the process would be useful.

# Results
Now it is time to show the finished project, deployed and running on the device.  Let’s talk about the results of running the model, presenting data, evidence, or statistics as appropriate.  Not all projects may meet their objectives, or perform well, but we should still present the outcomes truthfully.  If the project was extremely successful, then we can articulate on how the project could be scaled to truly make an impact.  If the project fell short of its goal, that is fine as well, and we can discuss what might have gone wrong, how the project could be improved, and provide lessons learned.  Screenshots or images might be needed here, as well.  

# Conclusion
A brief summary recapping what you built, why, and the outcome you achieved.  A few sentences wrapping up the project, any next steps you might take, or giving advice to the reader on how they can take your project and replicate it as-is, iterate, expand, or even scale your work.  All Expert Projects should be Public Projects, so explain that a reader can Clone your work and has access to your data, model, and can review the steps you took.  Reinforce the human health or machine health use case, and provide any final links or attribution.  



# DONE

# Intro / Overview
Briefly provide an introduction to your project. Address the following: what you are accomplishing, what the intended outcome is, highlight the use-case, describe the reasons for undertaking this project, and give a high level overview of the build. Provide a sentence or two for each of these aspects.  
Summarize the problem you are addressing in one or two sentences, and how your solution makes an impact.  Be sure to also give a brief introduction to the hardware you have chosen and any key features, or reasons why the selected hardware is a good fit for your project. 
Include a high-quality image of the hardware.

# Problem Being Solved / Use-case Explanation
Here we will go deeper into the problem that is being addressed.  We’ll want to provide evidence and data that the problem exists, and provide some possible improved outcomes and what we are hoping to achieve.  We need to establish credibility and demonstrate competence and innovation, so that readers have trust in the solution being presented.  This could be a good place to also further document the hardware features, sensors, or interfaces available on the board, describe what they do or what data they are intended to capture, and why that is important.  An image further detailing the problem or challenge would be useful, but might not be required depending upon the project.

# Components and Hardware Configuration
If any additional components are needed to build the project, include a list / Bill of Materials.  Normally this is formatted in a bulleted list, and quantity needed, to build the project.  After that, a description of how to set up the hardware, attach any sensors or secondary devices, flash any firmware or operating systems, install needed applications, and ultimately reach a point where we’re ready for Edge Impulse in the project.  We’ll definitely want some pictures of the hardware build process, showing the journey and setup that will guide readers through the process.