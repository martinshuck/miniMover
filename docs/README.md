## miniMover

This is a project that lets you send GCode to an XYZ da Vinci prniter.  It will also convert from a .3w file to .gcode and back, and can monitor and setup the printer as well.  This works with newer printers that implement the version 3 serial protocol. These include the Nano, Mini W, miniMaker and Jr. line of printers among others.

You can read up on the development progress in this forum.

http://www.soliforum.com/topic/17028/print-gcode-files-to-minimaker/

This works with the following printers over a USB connection.  There is no wireless support yet, but I could look into it if there is any interest.

   da Vinci Nano  
   da Vinci miniMaker  
   da Vinci Mini w  
   da Vinci Jr. 1.0  
   da Vinci Jr. 1.0W  
   da Vinci Jr. 1.0A  
   da Vinci Jr. 1.0 3in1  
   da Vinci Jr. 1.0 3in1 (Open filament)  
   da Vinci Jr. 1.0 Pro  
   da Vinci Jr. 2.0 Mix  
   da Vinci 1.0 Pro  
   da Vinci 1.0 Pro 3in1  
   da Vinci 1.0 Super  

With these printers I can only convert from gcode to 3w files and back.  They use an older communication protocol that I have not implemented yet, so I can't send data to them directly. 

   da Vinci 1.0  
   da Vinci 1.0A  
   da Vinci 1.0 AiO  
   da Vinci 1.1 Plus  
   da Vinci 2.0 Duo  
   da Vinci 2.0A Duo  

This uses a modified version of the tiny-AES project by kkoke.

https://github.com/kokke/tiny-AES-c

It also uses a stripped down version of miniz by richgel999

https://github.com/richgel999/miniz

This comes in two flavors, a win32 GUI and a command line utility.

![My image](http://soliforum.com/i/?PDJlohX.png)

Here is a summary of the commands that the command line can take.

```
usage: miniMover <args>
  -? - print help message
  -a+ - enable auto level
  -a- - disable auto level
  -b+ - enable buzzer
  -b- - disable buzzer
  -cl - clean nozzle
  -ca - calibrate bed
  -c file - convert file
  -f file - upload firmware, experimental!
  -h - home printer
  -l - load filament
  -o num - increment/decrement z offset by num
  -po num - set serial port number, -1 auto detects port
  -p file - print file
  -s - print status
  -u - unload filament
  -x num - jog x axis by num, or 10 if num not provided
  -y num - jog y axis by num, or 10 if num not provided
  -z num - jog z axis by num, or 10 if num not provided
  file - print file if .gcode, otherwise convert to gcode if .3w
```

This is inspired by the threedub programs listed below but it is based on a fresh reverse engineering of the serial protocol.

https://gitlab.com/anthem/py-threedub

https://gist.github.com/companje/b700748a49f4af73d57011c644f5a778

http://www.soliforum.com/topic/15639/jr-cura-230-threedub/

https://github.com/mwm/xyzify

https://www.thingiverse.com/thing:1915076
