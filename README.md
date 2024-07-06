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

**1. 555 TIMER IC:** 555 timer starts generating the pulse, This pulse is sent to the 4026 IC’s clock. 555 timer is powered by a DC source, threshold and the DC pin is connected to the 470K ohm resistor and then the 555 timer is connected to ground. 

 **2. 4026 IC:**  The 555 timer clock signal is passed through a NOR gate that further passes on to the 4026 IC. It is responsible for displaying the timer i.e digits on the seven segment display. 4026 display initiates a mod counter and that will proceed upto 9 and on reaching 9 and the zero it will add plus on into the next 7 segment display, hence 4 7 segment displays are used for 4 4026 ICs and in this way the decade counter works.
 ![image](https://github.com/WAJIHAALI1070/WATER-LEVEL-CONTROLLER/assets/121358629/7d8fd23d-5353-4a9f-a83f-9648a648183a)

A typical 555 timer can be seen as follows:
![image](https://github.com/WAJIHAALI1070/WATER-LEVEL-CONTROLLER/assets/121358629/138153a6-2379-4ae3-99eb-93a0a4206212)


# WATER LEVEL SENSORS AND INDICATORS
Each end of wire dipped in water acts as a sensor 
and would give the logic 1 when submerged in water so that the level to level timer would go off. There are a total of 4 level that would display the level to level timer and would pause when once the next level activates meaning they are attached with an enable so that each level timer is activated at a single time now, when the tank if fully filled with water final sensor is turned on or gives logic 1 and the kill switch freezes the timer and the buzzer goes off indicating to turn off the dc source. The water level is set-up using a the following components: 
 1. 470k ohm resistor equivalent to the level numbers
 2. 74HC147 which is a priority encoder
 3. HEX Invertors
 4. 7 segment display to display the level number
 5. The 74LS90 is a simple counter (IC 7490), i.e. it can count from 0 to 9 cyclically in its natural mode. It counts the input pulses and the output is received as a 4-bit binary number through pins A, B, C and D. The binary output is reset to 0000 at every tenth pulse and count starts from 0 again.
 6. 7447 which is also an equivalent BCD to 7 segment decoder
    ![image](https://github.com/WAJIHAALI1070/WATER-LEVEL-CONTROLLER/assets/121358629/cae0724b-7741-4146-99cd-e242e0b49778)

# MEMPORY STORAGE
The memory storage will store the time of level to level timer and will keep displaying the output when the clock signal is turned off of each level. The memory storage will help to store the level to level timer and store all the times of various levels. Now when the DC power is turned off, all the data is lost and the register is reset. The memory storage will be possible using the 8 bit shift register or flip flops using latches or simple registers, basically anything that can store the value of timers will be the memory block of the system. We used 74198 IC which is a shift register. Synchronous parallel loading is accomplished by applying the 8- bits of data and taking both mode control inputs,S0 and S1 high. The data is loaded into the associated flip flop and the outputs after the positive transition of clock input. During loading serial data flow is inhibited. 
![image](https://github.com/WAJIHAALI1070/WATER-LEVEL-CONTROLLER/assets/121358629/4a79a01d-8ca4-4761-9cb7-51a7b38d6046)
