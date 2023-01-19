# Dynamic-DOT-MATRIX-DISPLAY
In this project I have used an ESP8266 to control the text that is to be displayed on the DOT MATRIX DISPLAY. 
A web server is created using the IP of ESP8266 and it is customised to suit the requirements of the Project. I have used HTML to create the web server.
This is an easy way to use a dot matrix display to print text using a web server.
Before I explain the working of the project, I would first like to address a few points which would make your journey of using a DOT MATRIX LCD easier.

Here use the latest versions of the libraries "MD_Parola.h" and "MD_MAX72xx.h ". For these Libraries u don't have to play with the header files of them to 
change your hardware type. You can now change it in the code itself.

Initially the dislay might not diplay the exact text which you would have given, this is because the HARDWARE_TYPE(FC16_HW) mentioned in the line 19 of the 
code(and by this I am refering to this line:- ```#define HARDWARE_TYPE MD_MAX72XX::FC16_HW```) might not be the Hardware_type of your DotMatrix.

So in case you don't have the Hardware type of your dot matrix display, you have to experiment with these types
* GENERIC_HW
* FC16_HW
* PAROLA_HW
* ICSTATION_HW

Moving on, there comes 20th and 21st Line,
So about 20th line which is ```#define MAX_DEVICES 8``` , this refers to the number of dot matrix LCDs you will be using, here I am using 8 DOT MATRIX LCDs,
that might not be the case with you; so edit that out

and the 21st line
```#define CS_PIN    15```
here we are defining the CS_PIN config, so here 15 refers to GPIO 15.

set ```SSID``` as your WiFi's Name
and ```Password``` as the Wifi's Password

X-----------------------------------------------------------------------------------------------------------------------------------------X
**SCHEMATICS**

![image](https://user-images.githubusercontent.com/40132560/213359157-70746565-ac7b-4265-9505-1936998b09f0.png)

So here, 
* DIN of the LCD is connected to D7 Pin.
* CS of the LCD is coonected to D8 Pin.
* CLK of the LCD is connected to D5 Pin.

X-----------------------------------------------------------------------------------------------------------------------------------------X

These were some key points which I feel weren't addressed in major forums, and I hope this repository solves it.

X-----------------------------------------------------------------------------------------------------------------------------------------X

**WORKING OF THE PROJECT**

Once you have finished the wiring and have uploaded the code, the dot matrix lcd will first display its IP ADDRESS in the DISPLAY

Example:-

<img width="539" alt="image" src="https://user-images.githubusercontent.com/40132560/213360006-b5754a09-796d-4d58-8aac-8136be777934.png">

using this IP Address, you can open the web-page to send text for the LCD to print.
In the web-page you have options to send text, control the speed, the direction of printing and lastly you can chose b/w Inverse and Normal print.

Here's the photo of the website:-

<img width="324" alt="image" src="https://user-images.githubusercontent.com/40132560/213360283-beb9174c-6a64-4c4f-9410-8b764a6f89aa.png">
