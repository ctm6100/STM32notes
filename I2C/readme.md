## I2C Dataframe
![image](https://github.com/ctm6100/STM32notes/blob/main/I2C/DataFrame.png?raw=true)
<P>
S is the staring signal(falling edge)<br>
P is the falling signal(starting edge)<br>
</P>
<img src="https://github.com/ctm6100/STM32notes/blob/main/I2C/address.png?raw=true"/>
<P>
Starting address (normally 7bit --- 7-10 bits)<br>
R/W read or write(1bit) --->0 write , 1 read<br>
</P>

## I2C Communication
![image](https://github.com/ctm6100/STM32notes/blob/main/I2C/SDA.png?raw=true)<br>
Noraml speed is 100kbit/s<br>
Fast speed 400kbit/s<br>
Very very fast speed 3.4Mbit/s<br>

## Hal Code
###Send
```C++
static const uint8_t I2CslavesAddress = 0x48 << 1;
uint8_t* dataToSend[];
noOfbytes= strlen((char*)dataToSend);
returnState = HAL_I2C_Master_Transmit(&hi2c1, I2CslavesAddress, dataToSend, noOfbytes, maxTime);
```
I2CslavesAddress: The address of the I2C slaves devices
dataToSend: the data to sebt 
