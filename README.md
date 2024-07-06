# WATER LEVEL CONTROLLER AND INDICATOR

Water level indicator powered by the 5V DC source is a setup used to measure the water level of a certain tank, the time it takes to fill the whole tank and the display the time. The time will be stored on the 7 seven segment display, The level to level timer is displayed on individual 7 segment displays and they will be stored in memory i.e Universal shift register. The water from the source into the desired container would done using the Suction pump that would also be the 5V derived pump. 

The setup would be based on the following components
  1. Suction Pump 
  2. Counter 
  3. Water Level Sensor

# SUCTION PUMP
When the power is turned on, the suction starts to suck the water from the source into the container under observation containing the water level sensor. When the power is turned on the counter starts and at the same time the water will start pumping into the tank. 

# COUNTER
The counter starts when the suction pump is powered on. So the decade counter starts. The counter works as follows:
**1. 555 TIMER IC: ** 555 timer starts generating the pulse, This pulse is sent to the 4026 IC’s clock. 555 timer is powered by a DC source, threshold and the DC pin is connected to the 470K ohm resistor and then the 555 timer is connected to ground. 
 **2. 4026 IC: **  The 555 timer clock signal is passed through a NOR gate that further passes on to the 4026 IC. It is responsible for displaying the timer i.e digits on the seven segment display. 4026 display initiates a mod counter and that will proceed upto 9 and on reaching 9 and the zero it will add plus on into the next 7 segment display, hence 4 7 segment displays are used for 4 4026 ICs and in this way the decade counter works.

# WATER LEVEL SENSORS AND INDICATORS
