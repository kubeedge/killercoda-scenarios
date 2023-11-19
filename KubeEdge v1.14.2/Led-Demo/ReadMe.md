# Light Mapper


 ## Description

Light Mapper contains code to control an LED light connected to a raspberry Pi through gpio.

Here we are using a push button  switch to test the working condition of the LED, through an independent  circuit.

Depending on the expected state of the light, the program controls whether or not to provide power in pin-18 of the gpio.
When power is provided in the pin, the LED glows (ON State) and when no power is provided on it then it does not glow (OFF state).