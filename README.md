[![MCHP](images/microchip.png)](https://www.microchip.com)

# Getting Started with External High-Frequency Oscillator on AVR® DB MCUs

The High Frequency Crystal Oscillator (XOSCHF) enables the use of an external crystal or an external clock signal up to 32 MHz. This can be used as a clock source for the Main Clock (CLK_MAIN), the Real-Time Counter (RTC) and the 12-Bit Timer/Counter Type D (TCDn).

The Clock Failure Detection (CFD) feature can be used to detect if the output from a clock source stops and can switch the Main Clock to a different clock source to continue operation or shut down operation safely.

These examples show the following use cases for XOSCHF and CFD on AVR® DB MCUs:

* **XOSCHF with External Crystal**:
  Initialize XOSCHF for external crystal and change the main clock source to XOSCHF
* **XOSCHF with External Clock**:
  Initialize XOSCHF for external clock signal and change the main clock source to XOSCHF
* **RTC with XOSCHF**:
  Use XOSCHF as clock source for the RTC
* **TCD with XOSCHF**:
  Use XOSCHF as clock source for TCD0
* **TCD with XOSCHF and PLL**:
  Initialize the PLL with XOSCHF as clock source and use the PLL as clock source for TCD0
* **CFD on XOSCHF**:
  Initialize the CFD to monitor XOSCHF, enable the interrupt, toggle an LED if the clock source fails
* **CFD on Main Clock with NMI**:
  Initialize the CFD to monitor Main Clock with XOSCHF as clock source, enable the interrupt as a Non-Maskable Interrupt (NMI), toggle an LED with frequency derived from Main Clock

## Related Documentation

* [TB3272 - Getting Started with External High-Frequency Oscillator on AVR DB](https://microchip.com/DS90003272)
* [AVR128DB48 Device Page](https://www.microchip.com/wwwproducts/en/AVR128DB48)
* AVR128DB48 Curiosity Nano User Guide (link will be added once available)

## Software Used

* [MPLAB® X IDE](https://www.microchip.com/mplab/mplab-x-ide) 5.40 or later
* [MPLAB® XC8](https://www.microchip.com/mplab/compilers) 2.20 or later
* MPLAB® X AVR-Dx_DFP version 1.4.75 or later
* For the Atmel Studio version of these projects, please go to [this repository](https://github.com/microchip-pic-avr-examples/avr128db48-getting-started-with-xoschf)


## Hardware Used

* [AVR128DB48 Curiosity Nano](https://www.microchip.com/DevelopmentTools/ProductDetails/PartNO/EV35L43A)
* Optional external clock source

## Setup

The AVR128DB48 Curiosity Nano comes with a 16 MHz crystal soldered on. This can be used for most of the example projects, except for the external clock and RTC examples.

* **XOSCHF with External Clock**:
  * Disconnect the crystal by cutting the two straps on the top side of the board next to the crystal (J215, J216)
  * Connect the I/O lines to the edge connector by placing solder blobs on the circular solder points marked PA0 and PA1 on the bottom side of the board (J213, J214)
  * Connect a clock source to PA0 on the edge connector
* **RTC with XOSCHF**:
  Replace the 16 MHz crystal with one running at maximum 1/4 of the CLK_MAIN frequency

## Operation

* Connect the AVR128DB48 Curiosity Nano to a computer using a USB cable
* Clone the repository or download the zip to get the source code
* Open the project folder you want to run with MPLAB X
* Compile and run the code

## Conclusion

After going through these examples you should have a better understanding of how to set up different use cases for the XOSCHF on AVR DB family microcontrollers.
