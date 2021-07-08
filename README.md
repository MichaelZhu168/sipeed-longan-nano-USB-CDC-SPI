# sipeed-longan-nano-USB-CDC-SPI
this project use SPI to get a temperature value from a BMP280 temperature module,   and then use USB CDC to sent it to a host (PC or Android)
modified from a example project of GD32VF103(GigaDevice Semiconductor Inc)


    chip:GD32VF103CBT6 ( or  GD32VF103VBT6)
    board:sipeed Longan Nano (you can also use GD32VF103V-EVAL-V1.0 board which has GD32VF103VBT6 on it.
    the linker is same. but the pinouts has a little difference)


created by mzhu thru basing on CDC_ACM example from GD32VF103 example projects.

   This example is based on the GD32VF103V-EVAL-V1.0 board(I use sipeed Longan Nano),it provides a description of 
 how to use the USBFS and SPI.

  The target of this example is to read data from and write data to USB devices using 
the CDC protocol.
 
  It makes the USB device look like a serial port (NO serial cable connectors: You 
can see the data transferred to and from via USB instead of USB-to-USART bridge connection).
 
  This example loops back the contents of a text file over usb port. To run the example, 
Type a message using the Pc's keyboard. Any data that shows in HyperTerminal is received 
from the device.

  This CDC_ACM Demo provides the firmware examples for the GD32VF103V families.

  - OUT transfers -- receive the data from the PC(usb host) to GD32(usb device):
  When a packet is received from the PC on the OUT pipe (EP3),by calling cdc_acm_data_receive()
  it will be stored in the usb_data_buffer[]. 
 
  - IN transfers -- to send the data from the GD32 to the PC:
  When a packet is sent from the GD32 on the IN pipe (EP1), by calling cdc_acm_data_send(),
  put the data into the usb_data_buffer_to_host[] buffer for sending data to the host.
  
   
  pin connections
   
Longan Nano      	BMP280(from adafruit)
SPI0_SCK(PA5)	<--->	CS
SPI0_MISO(PA6)	<--->	SDO
SPI0_MOSI(PA7)	<--->	SDI
CS(Here I use PB0)<-->	CS
V5		<--->	VIN
GND		<--->	GND
