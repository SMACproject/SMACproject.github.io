---
title: Developing simple LED app with Atmosphere Part 1
layout: post
author: yasmin
tags:
- News
- LED
- Atmosphere
---

<p>In order to program the The Anaren Bluetooth Smart Development kit, an account was created in https://atmosphere.anaren.com/. Creating an account gave us access to the Atmosphere Development Tool where the programming tools are located to create one’s project. In addition, the Atmosphere Programmer was downloaded to program the board once one’s project was uploaded located in the website above.</p>

<p>In the Atmosphere Development Tool:</p>

* Eight Button elements were used for four LED lights. Four of the eight were specifically to turn on and four to turn off.

    ![Broken image link](/assets/OriginalLED_Screenshot.PNG)

* Using the AIR_UART_Write pre-built function, we are able to assign each button to write a specific JSON command when pressed under a function element.
* A background picture was created using Microsoft Clip Art. It was added to the app by adding an image element and importing the picture.

    ![Broken image link](/assets/LED2_Screenshot.PNG)

* LED labels were added using the label element.
* A light bulb picture was created using Microsoft Clip Art to serve as an indicator. It was added to the app by adding an image element and importing the picture. The image properties are adjusted to appear when their corresponding button is pressed. For example, if the ON button is pressed, the yellow light bulb will be visible. If the OFF button is pressed, the white light bulb will be visible.

    ![Broken image link](/assets/LED3_Image_Screenshot.PNG)

* We were able to program two images to function as buttons instead of having two separated function, a button and an image indicator. The images were connected to each other and their properties were set similarily to a button’s. For example, having triggers, or connectors, set to mousePressed like a button’s trigger.

    ![Broken image link](/assets/LED5_Screenshot.PNG)

* The project works exactly as the above one when using images as buttons.

To make things easier, you can [get the result code](/assets/LED5_LightBulb.atmo) of the above steps directly.