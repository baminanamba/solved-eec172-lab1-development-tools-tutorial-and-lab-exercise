Download Link: https://assignmentchef.com/product/solved-eec172-lab1-development-tools-tutorial-and-lab-exercise
<br>
<strong>Objective: </strong>This tutorial will cover the basic software development tools that will be used in this course, including Code Composer Studio (CCS), CCS UniFlash, and the TI Pin Mux Tool.

<h1>Equipment Needed</h1>

<ul>

 <li>CC3200 LaunchPad (CC3200-LAUNCHXL)</li>

 <li>USB Micro-B plug to USB-A plug cable (included in Kit)</li>

 <li>Optional: USB Flash Drive for saving code</li>

</ul>

<strong>Note: </strong>Do not lose the shorting blocks (Jumpers) that come with the board. They are used to configure different hardware functions on the board and may be needed for this and future labs.

<h1>Development Tool Installation Procedure</h1>

The following software must be installed on your own computer to use it for project development. Note that to download some of the TI software, you will need to set up a TI account. Establish your own account to download the software instead of trying to get it in some other way.

1. Code Composer Studio (CSS) Integrated Development Environment (v9.3.0) <a href="http://processors.wiki.ti.com/index.php/Download_CCS">http://processors.wiki.ti.com/index.php/Download_CCS</a>

Download and install the latest version of CCS. You will have access to the full-featured version (not code-size or time limited) when using the CC3200 Launchpad.




<ol start="2">

 <li><strong>CC3200 Software Development Kit (v1.4.0) </strong>and <strong>CC3200SDK-ServicePack (v1.0.1.13-2.11.0.1) </strong><a href="https://www.ti.com/tool/cc3200sdk">http://www.ti.com/tool/cc3200sdk</a> You will be asked to create a TI account.</li>

</ol>




<ol start="3">

 <li><strong>TI Pin Mux Tool (</strong><strong>0.1223) </strong><a href="http://processors.wiki.ti.com/index.php/TI_PinMux_Tool">http://processors.wiki.ti.com/index.php/TI_PinMux_Tool</a></li>

</ol>

You can use either the Cloud version of the Pin Mux Tool or the stand-alone desktop version.




<ol start="4">

 <li><strong>CCS UniFlash (</strong><strong>4.1.00012) </strong><a href="http://processors.wiki.ti.com/index.php/CCS_UniFlash_v3.4.1_Release_Notes">http://processors.wiki.ti.com/index.php/CCS_UniFlash_v3.4.1_Release_Notes</a></li>

</ol>




<h1>5. PuTTY or Tera Term</h1>

You will use a terminal emulator program for serial input and output to you CC3200. You can use any terminal emulator program that you prefer. The lab machines will have PuTTY (available at <a href="http://www.putty.org/">http://www.putty.org/</a><a href="http://www.putty.org/">)</a> and Tera Term (available from <a href="https://ttssh2.osdn.jp/index.html.en">https://ttssh2.osdn.jp/index.html.en</a><a href="https://ttssh2.osdn.jp/index.html.en">)</a>.

<h1>Part I. Testing Example Programs in Code Composer Studio</h1>

In this part, you will create a workspace and import two example programs to test with your CC3200 processor. <strong>A.</strong><strong> Blinky example program </strong>

<strong> </strong>

<ol>

 <li>Launch Code Composer Studio (CCS) from the desktop icon or from the Start Menu.</li>

</ol>




CCS will prompt you to select a directory for your workspace. Enter a directory in your user space, such as:




<h1>C:Users<em>your_name</em>workspace_v9_cc3200</h1>

<strong> </strong>

Do <strong><em><u>NOT</u> </em></strong>check the box “<u>Use this as the default and do not ask again</u>” on any of the lab machines since these machines will be shared among many users. Even on your own machine, we recommend that you avoid this option.







<ol start="2">

 <li>Select <strong>Import Project </strong>from the Getting Started page or select <strong>Import CCS Projects… </strong>from the Project pull-down menu in the Edit Perspective of CCS.</li>

</ol>




<h1>Browse to C:tiCC3200SDK_1.4.0cc3200-sdkexampleblinky</h1>

<strong> </strong>

Check the box to <strong>Automatically import referenced projects found in the same search-directory </strong>(if the checkbox is not disabled) and click <strong>Finish</strong>.




<ol start="3">

 <li>In Project Explorer, right-click on <strong>blinky </strong>and select <strong>Properties</strong>. Change the Compiler version from to TI v18.12.04.LTS or higher to get rid of a warning message. You should explore other Properties. For example, expand ARM Linker and select Basic Options in order to see the default heap and stack sizes for this project. When you are done examining project properties, click</li>

</ol>

<strong> </strong>

<ol start="4">

 <li>Also, in the Properties window, go to the <strong>Processor Options </strong>page and from the drop-down menu in front of the Specify floating point support (–float_support), select the <strong>FPv4SPD16 </strong></li>

</ol>




<ol start="5">

 <li>Click the hammer icon or select <strong>Project &gt; Build Project </strong>to build the blinky project. The project should build without any errors or warnings.</li>

</ol>




<ol start="6">

 <li>Connect the CC3200 LaunchPad to your host computer using the supplied USB cable.</li>

</ol>




<ol start="7">

 <li>Click the bug icon or select <strong>Run &gt; Debug </strong>to launch the Debug Perspective. In the older versions of Code Composer Studio, the first time you attempt to run a program on the CC3200, you might get the following message:</li>

</ol>




<strong>You require a target configuration to start a debug session. Do you want to create a new target configuration file and open it in the editor? </strong>

<strong> </strong>

If so, Click <strong>Yes</strong>.




Give the new Target Configuration file a name, such as <strong>cc3200.ccxml</strong>.




Click the box “<strong>Use shared location</strong>” so that this configuration file can be used for all of your projects in this workspace. Then click <strong>Finish</strong>.

For the Connection, select <strong>Stellaris In-Circuit Debug Interface </strong>and select the box for “<strong>CC3200</strong>” for the board or device. Then scroll to the right of the window and select <strong>Save</strong>. You should now see CC3200.ccxml listed under the User Defined folder in the Target Configurations window. Make sure that CC3200.ccxml is selected as the <strong>default </strong>target configuration. Close the cc3200.ccxml window and click the bug icon or <strong>Run &gt; Debug </strong>again. This time, your program will be loaded into the CC3200’s RAM. (Make sure that the CC3200 LaunchPad is still connected to the PC via the USB cable.)          If you don’t see this message you can ignore the step 7.




<ol start="8">

 <li>Now the Micro Controller is programmed and has paused at the main function. Click on the green “Play” button icon or select <strong>Run &gt; Resume </strong>or type <strong>F8 </strong>to run the program. You should see the red, yellow and green LEDs blink in a continuous sequence. Examine the program to see how it works.</li>

</ol>




<ol start="9">

 <li>Make a simple modification to make the LEDs blink faster than in the default program. For example, you can easily make the LEDs blink two times to ten times faster with simple code modifications. Download the code again and verify that the program works as expected.</li>

</ol>




<h1>B. Uart_demo example program</h1>

<strong> </strong>

Follow the steps above to import the <strong>uart_demo </strong>project. You can make the project Active for Debugging by clicking on the project’s name in the Project Explorer window inside the Code Composer Studio App. Build and download the program as you did for the blinky program. Before running the program, you will need to open a terminal window using PuTTY or TeraTerm (Although not recommended, you can open the Terminal window from the CCStudio as well).




Open the Windows <strong>Device Manager </strong>(Start Menu -&gt; right click on Computer -&gt; select Manage -&gt; select Device Manager from under System Tools). Expand the Ports (COM &amp; LPT) entry and determine which COM port is used for communicating with the CC3200. You will need to open this COM port in PuTTY or TeraTerm.




Open the terminal emulator program and configure it for a serial terminal connection to the COM port used by the CC3200. Set the baud rate to 115200.




Once your terminal window is open, run the uart_demo program in the CCS Debug window. Verify that the program echoes text that you type into the terminal window using the keyboard.




Remember that while flashing the CC3200, the serial terminal connection should be closed and reopened later.

<h1>Part II. Lab1 Application Program Exercise</h1>

In this part, you will develop a simple program that interfaces a console window to switches and LEDs on the CC3200 LaunchPad.




<h2>1.Create a project in CCS</h2>

Instead of creating a new, empty project, it is easier to import an example project from the CC3200SDK and modify that project according to the new project specs. In this case, we recommend that you start with the <strong><em>blinky </em></strong>project since it is similar to the new project you will develop. Note that you cannot import <strong><em>blinky </em></strong>into your project when it is already there. However, you can rename the <strong><em>blinky </em></strong>project to a new name, such as <strong><em>Lab1</em></strong>. That way, you could re-import the original <strong><em>blinky </em></strong>project into your workspace, if desired.







<h2>2.Configure the pins for your project using the TI Pin Mux Tool</h2>

The TI Pin Mux Tool is a utility used to select the appropriate pin multiplexing configuration to satisfy the application requirements. This tool makes it easy to understand the various pin configuration options and to implement your desired pin configuration without error. You can use either the Cloud-hosted Pin Mux Utility or the stand-alone desktop version. In this section, we will describe using the desktop version. For information on using the TI Cloud-hosted tool, see the following video:

<a href="https://www.youtube.com/watch?v=Q8yby_i3N_M">https://www.youtube.com/watch?v=Q8yby_i3N_M</a>




− Launch the TI Pin Mux Tool from either the Start menu, the desktop icon, or from the cloud version at <a href="http://dev.ti.com/">dev.ti.com</a><a href="http://dev.ti.com/">,</a> if it exists. Select

<strong>CC3200 </strong>as the device and click on the <strong>Start </strong>button.




− We will first configure the desired GPIO signals. For this project, we want to interface to the following devices/pins on the CC3200 LaunchPad: Red, Yellow and Green LEDs, SW2 and SW3, P18 on the P2 header, and the UART Rx and Tx pins which interface to the console window. To determine which pins or GPIO signals you need to specify, consult the LaunchPad schematic (CC3200-LAUNCHXL_SCH_Rev4p1-a.pdf) available on the course website. <u>Make sure that you</u> <u>can verify the following signal names and pin numbers on the schematic</u>. (It will be very important that you consult this schematic when deciding which pins to use for hardware interfacing. Many of the pins that are brought to the headers are already being used on the LaunchPad board and are not actually available for general use.)







<table width="461">

 <tbody>

  <tr>

   <td width="134">Signal Name</td>

   <td width="135">Pin Number</td>

   <td width="192">Device</td>

  </tr>

  <tr>

   <td width="134">GPIO_9</td>

   <td width="135">64</td>

   <td width="192">Red LED</td>

  </tr>

  <tr>

   <td width="134">GPIO_10</td>

   <td width="135">1</td>

   <td width="192">Yellow LED</td>

  </tr>

  <tr>

   <td width="134">GPIO_11</td>

   <td width="135">2</td>

   <td width="192">Green LED</td>

  </tr>

  <tr>

   <td width="134">GPIO_13</td>

   <td width="135">4</td>

   <td width="192">SW3</td>

  </tr>

  <tr>

   <td width="134">GPIO_22</td>

   <td width="135">15</td>

   <td width="192">SW2</td>

  </tr>

  <tr>

   <td width="134">GPIO_28</td>

   <td width="135">18</td>

   <td width="192">P18 on P2 header</td>

  </tr>

 </tbody>

</table>




− Select the GPIO peripheral in the Peripherals tab on the left.




− Click on the Add button in the Requirements tab so that you can add GPIO signals.




− Unselect all the GPIO signals by unchecking the box in the top left labeled GPIO Signals. Next,

add the GPIO signals that you want to use as GPIO in your design.




− Check the appropriate box for Input, Output or Output OD (Open Drain) for each of your signals. In this design, the switches should drive input pins and outputs signals (<em>not </em>open drain outputs) will drive the LEDs and P18.




− Verify that the pin numbers match the ones in the table above. If they don’t match, use the pull- down option to select the correct pin number. Your GPIO section should look like the following screenshot. (The name of the module is arbitrary.)




<strong>PinMux Configuration of GPIO signals </strong>

<strong> </strong>

− Next configure the UART peripheral. Note that you will need to configure the UART0_RX to pin number 57 and UART0_TX to pin number 55 as these are not the default pin assignments for these signals on the CC3200 LaunchPad. The lock icon shows that you have locked that pin number

to the specified signal. For details, see the UART MUXING and the EMULATION sub- circuits on the CC3200 LaunchPad schematic. Your UART configuration should look similar to the screenshot below.







<table width="461">

 <tbody>

  <tr>

   <td width="134">Signal Name</td>

   <td width="135">Pin Number</td>

   <td width="192">Device</td>

  </tr>

  <tr>

   <td width="134">UART0_RX</td>

   <td width="135">57</td>

   <td width="192">FTDI_TX</td>

  </tr>

  <tr>

   <td width="134">UART0_TX</td>

   <td width="135">55</td>

   <td width="192">FTDI_RX</td>

  </tr>

 </tbody>

</table>










<h1>PinMux Configuration of UART signals</h1>

<strong> </strong>

− Save your design to your project directory. For example, you can use the name lab1 and the file will be stored as lab1.pinmux. You can open this file with the Pin Mux Tool to change your pin configuration instead of starting over.




<table width="728">

 <tbody>

  <tr>

   <td colspan="2" width="728"> <strong>PinMux output files </strong></td>

  </tr>

  <tr>

   <td width="111"><strong> </strong></td>

   <td width="618"> </td>

  </tr>

  <tr>

   <td width="111">− </td>

   <td width="618">Select the download button to download pin_mux_config.c and pin_mux_config.h to your project directory. The download button is the down-arrow icon to the right of the filename, as shown in the screenshot below. Open these files and verify the code that has been generated to configure the pins. (You could use the rom_pin_mux_config.c file instead of the pin_mux_config.c file if you choose.) Note that these files will replace the pinmux.c and pinmux.h used in the original blinky project.</td>

  </tr>

  <tr>

   <td width="111">−</td>

   <td width="618">Remove the old pinmux.c and pinmux.h files from your project directory. In main.c, modify the #include to use “pin_mux_config.h” instead of “pinmux.h”.</td>

  </tr>

 </tbody>

</table>




<ol start="3">

 <li><strong> <u>Modify your program code to meet the application specifications</u> </strong>The program specifications are as follows:</li>

</ol>




− When your program starts, it should display a message on the console window (i.e. TeraTerm or other terminal emulator) with a header and usage instructions as shown below. A good example project to look at for basic UART functions is uart_demo in the CC3200SDK examples folder.







************************************************* CC3200 GPIO Application

*************************************************







****************************************************

Push SW3 to start LED binary counting

Push SW2 to blink LEDs on and off

****************************************************

<table width="737">

 <tbody>

  <tr>

   <td width="111">− </td>

   <td width="627">Your program should poll the SW3 and SW2 switches on the CC3200 LaunchPad. When SW3 is pressed, you should start a binary counting sequence on the LEDs, counting from 000 – 111 <em>continuously </em>on the three LEDs. The count should be relatively slow so that you can see each count value easily. You should also print a message to the console “SW3 pressed”. This message should not be printed again until after SW2 has been pressed.When SW2 is pressed, your program should blink the LEDs ON and OFF in unison. Again, the blink pattern should be relatively slow so that you can see each pattern clearly and easily. You should print the message “SW2 pressed” to the console. This message should not be printed again until after SW3 has been pressed.</td>

  </tr>

  <tr>

   <td width="111">−   </td>

   <td width="627">Set the output signal P18 high whenever SW2 is pressed and low whenever SW3 is pressed. You can verify this signal using an oscilloscope.NOTE: For polling the switches and controlling the outputs, you can use CC3200 Peripheral Driver Library APIs such as GPIOPinRead() and GPIOPinWrite(). The CC3200 Peripheral Driver Library User’s Guide can be found at<a href="http://software-dl.ti.com/ecs/cc31xx/APIs/public/cc32xx_peripherals/latest/html/index.html">http://software</a><a href="http://software-dl.ti.com/ecs/cc31xx/APIs/public/cc32xx_peripherals/latest/html/index.html">–</a><a href="http://software-dl.ti.com/ecs/cc31xx/APIs/public/cc32xx_peripherals/latest/html/index.html">dl.ti.com/ecs/cc31xx/APIs/public/cc32xx_peripherals/latest/html/index.html</a></td>

  </tr>

 </tbody>

</table>

Verify your program using the CCS Debug mode.

<h1>Part III. Using CCS UniFlash</h1>

In this part, you will learn how to program the external flash memory so that the program will remain in non- volatile memory through power cycles. This section will demonstrate how to load the <strong><em>blinky </em></strong>program onto the external flash device on the CC3200 LaunchPad.




On launching the UniFlash tool, you will see a window as shown below. To start, click on the <em>New Target Configuration </em>link under the Quick Start Guide heading, or under the File &gt; New Configuration on the menu bar. This should open up the new configuration window.










<h1>Launch Screen of the CCS UniFlash tool</h1>

<strong> </strong>

From the Connection drop down menu, select the ‘<strong>CC3x Serial(UART) Interface</strong>’ option, and the ‘<strong>SimpleLink </strong>

<strong>Wifi CC3100/CC3200</strong>’ for the Board or Device in the screen-shot below. After the selections are made, click <strong>OK</strong>.




<h1>New Configuration Window</h1>

This will open up the main screen shown below. First, the correct COM Port for the device must be identified to the UniFlash tool. If you are unsure of which COM Port to use, plug in the CC3200 Launchpad and open up the Device Manager to check. In this example, the CC3200 Launcpad was on COM Port 4. Enter the COM Port number into the text box, and then select the ‘/sys/mcuimg.bin’ option on System Files on the left of the screen.










<h1>CCS UniFlash Flash Setup and Control Screen</h1>

This panel will allow you to identify the compiled .bin file that will be loaded into the flash memory. Click on the <em>Browse </em>button next to the Url text box, and locate the .bin file that you would like to load into flash. For this example, the compiled Blinky example program, blinky.bin was selected from the CCS workspace. In addition, make sure the <em>Update</em>, and <em>Verify </em>check boxes are selected. The UniFlash tool should now be ready to flash the CC3200 LaunchPad hardware.










<h1>System File Options Screen</h1>

Before connecting the CC3200 Launchpad to the computer, a jumper will need to be placed on SOP2 as shown below. This will allow the flash memory to be programmed by CCS UniFlash, and will prevent the previously flashed program from being executed.




<h1>Minimum Jumper Configuration for Flashing the CC3200</h1>

(Source: Figure 1 of the CC3200 SimpleLink Wi-Fi and IoT Solution With MCU LaunchPad Getting Started Guide)




Once you have verified the jumpers are correctly set, connect the Launchpad to the computer, and return to the <em>Flash Setup and Control </em>panel that was shown earlier and click the <strong>Program </strong>button. This should successfully program the board. To see the program run, disconnect the Launchpad from the computer, and remove the SOP2 jumper, and reconnect the board to the computer. (Note: Do not lose the jumper since you will often need to use it.) The blinky.bin file should now run at launch instead of the out of the box demo program (or whatever program was previously programmed in flash). If this does not work, double check that the necessary jumpers are placed on the Launchpad, as well as reviewing the options on the <em>‘/sys/mcuimg.bin’ </em>panel are set correctly.




<strong><u>Use the CCS UniFlash utility to program your application into the on-board serial Flash chip</u> </strong>Once your application program from Part II works, load it into the serial Flash chip on the CC3200 LaunchPad so that your program can run without downloading the code from CCS into RAM in Debug Mode.




To test your program, power the LaunchPad by connecting the USB cable to a host PC. Then open a terminal window using TeraTerm or PuTTY on the appropriate COM port. To see your header message, press the Reset button on the LaunchPad to restart your application program.


