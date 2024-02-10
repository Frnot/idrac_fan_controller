# idrac_fan_controller
A (hopeful) c implementation of [idracfancontrol.py](https://github.com/Frnot/unix-scripts/blob/main/idracfancontrol.py), a PID controller that modifies system fan speed through idrac in response to various system temperatures


IPMI 2.3 should contain the necessary relevant info.

Notes:

 * When setting the fan speed (i.e: `ipmitool raw 0x30 0x30 0x02 0xff 0x32`), the third byte controls which fans the new speed will apply to.
 * Supposedly setting this byte to 0x00 to 0x05 can control the six fnas independently. I suspect there is a way to use this byte as a bitmask to control multiple fans with a single command.
