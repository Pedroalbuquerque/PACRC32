# PACRC32
 
This is a generic CRC calculation function.
It will calculate a number (32 bits) based on an array content.
(a pointer to a structure can also be used).

This way you can always check if the content of the array has changed.

## use case

Say that you fill an array with a value and save it to file or memory location.
If you calculate the CRC for that array when you saved it, later you can chech if it has been changed by someone else just by recalculating the CRC and comparing to the original one.

## use case2
I have define a parameter struture on a code version and set values for it, saving it to EEPPROM.

later I changed the parameter structure and code and reloaded to ESP.
uppon reboot the new parameters structure expected by the code does not match anymore the one actually saved on EEPROM, and reading it without validation will lead to code breaking.
So now I am including a parameter CRC checking to ensure the parameter structure saved in the EEPROM is matching the one expected by the code.
If not I just used default parameteres instead and save them again to EEPROM (new structure).
