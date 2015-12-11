to program

while true; do openocd -f /usr/local/share/openocd/scripts/interface/stlink-v2.cfg -f /usr/local/share/openocd/scripts/target/stm32f1x.cfg ; sleep 1;done

In another terminal window we telnet to the openocd console on port 4444

telnet localhost 4444

In the telnet session issue a reset halt command.

reset halt

flash write_image erase cdctest.bin 0x08000000

and restart

reset run

unplug replug and dmesg
dmesg | grep -i usb
some where in the usb bits 
you should find the device 

lsusb

should give a quick view.

could use stlink
~/stlink/st-flash write cdctest.bin 0x08000000
the program is in my home at /stlink
