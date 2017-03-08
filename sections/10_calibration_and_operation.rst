Controller software, calibration, and acquisition
=================================================

Control system software
-----------------------

If you’ve gotten to this point, then all the hardware you need to do RTI is complete, with the exception of some minor optional extras. So it’s time to load the software into the Arduino that makes the control box fully operational for acquiring RTI datasets. The software’s name is RTI-Mage_Main_Control, and the latest version will always be in the Files section of the Hackaday project page.
But before you upload it to the Arduino, there are some constants you may want to modify, either right away or sometime in the future. Load the program into the Arduino IDE, and you’ll see right at the top a whole bunch of constants are defined. Many of them are hardware related, so if you modify those, the system may not work. But there’s a number of them that can/should be modified depending on your needs. Here are the relevant program strings, what they mean, and how you can change them.

.. code-block:: none

   String Current_setting="700mA";

This is a text string that shows up on the boot-up splash screen, telling people what the current output value you set earlier is. The system has no way to detect the current output setting, so you should definitely specify it here. Make sure it stays in quotes.

   const unsigned int Min_Data_Transfer_Time=500;   // minimum time after LED goes off to save photo data
   const unsigned int Max_Data_Transfer_Time=6000; // maximum time after LED goes off to save photo data

These are the minimum and maximum values for the “Delay” time, controlled by the right “Delay” knob on the front panel. This delay is to allow the camera time to save the photo it’s just taken to memory. For high-quality DSLRs, this time can be a fraction of second; for lower-end cameras, it can take a few seconds. The values are in milliseconds, thousandths of a second, so the number above correspond to 0.5 seconds and 6 seconds. Feel free to modify either of these if you feel the values are too high or too small for your needs. Make sure you only enter an integer value, no decimal point.

.. code-block:: none

   const unsigned int Min_LED_Time=100; //minimum time LED is on for picture to be taken
   const unsigned int Max_LED_Time=4000; // maximum time LED is on for picture to be taken; set by USB microscope time

These specify the minimum and maximum times the LED light is on during picture taking, controlled by the left “LED” knob on the control panel. This will depend on the exposure time required. Don’t increase the maximum time unless you absolutely have to, since the longer the LED is on, the warmer it gets. For example, I sometimes have these set to a wider range (100 to 8000) since one of the USB microscopes I’m using requires a long exposure time, roughly 6 seconds. However, for that system I also have the current set to a very low value of 150 mA, so it won’t get hot despite the longer on time.

   const unsigned long White_Balance_Time=3000; //time for one white balance LED before switching to the next one
   const unsigned long White_Balance_Max_Time=24000; //maximum total time for white balance before it turns off (to prevent LED stress)

Pressing the black “WB” button starts a long light cycle, where the LEDs in a single row are lit up in succession, each for the time specified by the White Balance time. This is to allow you to set the camera white balance, focus, and exposure parameters. The time is limited to prevent the LEDs from getting too warm, and the Max_Time is set to turn off the function after a limited time, to keep it from going forever. I wouldn’t modify these unless you absolutely have to.

.. code-block:: none

   const unsigned long Min_LED_On_Time=500; //Minimum on time for LED in manual mode
   const unsigned long Max_LED_On_Time=4000; //Maximum on time in manual mode for LED (to prevent overheating); turn back on with white balance button. Higher values not recommended.

These are the minimum/maximum LED on times in manual mode; you set the actual value using the LED potentiometer knob. Probably shouldn’t modify these unless absolutely necessary. If the LED goes off in manual mode before you have a chance to press the camera shutter, pressing the black WB button will turn that LED back on again.

.. code-block:: none

   const unsigned int Frequency=1000; //Sets default frequency of beeper (in Hz, cycles per second)

Sets the base frequency for the beeper in Hz; 1000 Hz was chosen as the default because it’s a balance between high human ear sensitivity and annoyance. Lower frequencies are more pleasant, but the ear’s response drops off significantly below 1000 Hz. Frequencies up to 5000 Hz have a better ear response, but sound more annoying. Change this if you like, won’t affect actual operation. And remember that there is a switch on the control box that turns off all sounds.

.. code-block:: none

   const unsigned int Rows=8; //Number of Rows being used (cathode connection to CAT4101s)
   const unsigned int Columns=8; //Number of Columns being used (anode connection to MOSFET driver outputs)

These two are the most important variables to modify. The defaults of 8 are the maximum number of rows and columns the RTI-Mage control box can support. If you are using a dome with fewer rows or columns, you should modify these values accordingly. These values are also displayed on the boot-up splash screen.

.. code-block:: none

   const int Shutter_Voltage_Time=100; //Time for 5V at USB to either fire CHDK or remote wired shutter.

This is the length of the positive voltage pulse used by the CHDK or wired remote shutter systems. This value has worked fine for every Canon camera I’ve used with CHDK. If you’re having problems getting your wired remote cable to work, you might try increasing this value.

Camera constants
----------------

Below the constant variables is a section of commands related to using the IR remote shutter function with various makes of cameras. Only one camera make can be enabled at any time. The default is Canon. To change to a different make, take the two Canon lines:

.. code-block:: none

   Canon CanonCamera(USB_Camera_Pin);
   String Camera_type="Canon";

And put two forward slashes in the beginning of each line; this makes the line a comment that the program interpreter will ignore. Remove the slashes from the similar lines for the desired camera make, and that will enable those lines. You’re not quite done yet – you need to change one more line as well. Scroll down in the program to the IR Shutter subroutine, where you will see another set of commands with camera makes associated with them, e.g this one for Canon:

.. code-block:: none

   CanonCamera.shutterNow();

As above, put two forward slashes at the beginning of the line you want to deactivate (Canon in this example), then remove the two forward slashes from the make you want to activate.

Once you’ve modified whatever constants you need to, upload the program to the control box. Once uploaded, you don’t need to have the system connected any longer to your computer via the USB cable; in fact, it won’t serve any purpose at all.

A quick visual review of the controls/jacks on various panels of the control box:

Front

