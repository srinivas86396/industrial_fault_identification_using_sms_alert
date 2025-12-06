This project monitors the industrial temperature and humidity levels and provides fault indication using LEDs/Buzzer. When a fault occurs, the automatically sends an SMS alert to predefined mobile number using a GSM module(M660A.)
The system also supports password-protected configuration, allowing the user to change temperature set point, humidity set point, and system password through an external interrupt and keypad inputs
HARDWARE REQUIREMENTS: LPC2148(ARM7) Microcontroller, 16x2 LCD AT24C256 EEPROM, DHT11 Temperature & Humidity Sensor, 4x4 Matrix Keypad, GSM Module(M660A), LED's(Green, Red), Buzzer, Switch(for External Interrupt), DB9 Cable/USB-UART Converter
SOFTWARE Requirements : Keil Micro-Vision(C Compiler), Embedded C Programming, Flash Magic(for flashing hex file)
PROJECT WORKFLOW: STEP1: All source file drivers lcd.c/lcd.h, delay.c/delay.h, keypad.c/keypad.h, i2c.c/i2c.h, adc.c/adc.h, uart.c/uart.h
STEP2: Test individual peripheral LCD, KEYPAD, UART, EEPROM, DHT11 sensor, GSM Module testing.
Step3: Develop the final project projectmain.c 1.Initialize all peripherals 2. Write set points & passswords into fixed EEPROM locations 3.continously read DHT11 sensor values 4.Compare readings with stored set points 5. If fault -> Turn ON/Buzzer + send SMS
INTERRUPT BASED MENU: 1. set point change 2. password change
SET POINT CHANGE: Enter password -> if correct -> Green LED ON -> choose parameter temperature or relative Humidity -> Enter new set point -> save to EEPROM. If wrong password Red LED/Buzzer. If wrong attempts -> System lock temporarily 
PASSWORD CHANGE: Enter current password -> Enter new password -> confirm new password -> save to EEPROM
FAULT HANDLING & ALERTS: Continuous monitoring of temperature & humidity. If current value > set point -> Turn ON red LED/Buzzer -> Send SMS to configured mobile number using GSM module.
