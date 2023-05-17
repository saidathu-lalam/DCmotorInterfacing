# DC Motor Speed & Direction control using PIC18F4550

Here, we are going to interface a dc motor with a PIC18F4550 microcontroller. In which we can control the dc motor speed by using the pot connected to ADC of PIC18F4550 and direction by using a switch.

### COMPONENTS USED:
1. PIC18F4550
2. DC Motor
3. L293D Motor Driver
4. Resistor - 4.7k
5. Bread Board
6. Variable Resistor
7. Jumper wires
8. Switch
### SOFTWARE USED
1. Proteus 8
2. MPLabx IDE 5.1

## THEORY
### DC motor
A DC motor converts electrical energy in the form of Direct Current into mechanical
energy.
- In the case of the motor, the mechanical energy produced is in the form of a
rotational movement of the motor shaft.
- The direction of rotation of the shaft of the motor can be reversed by
reversing the direction of Direct Current through the motor.
- The motor can be rotated at a certain speed by applying a fixed voltage to it. If
the voltage varies, the speed of the motor varies.
- Thus, the DC motor speed can be controlled by applying varying DC voltage;
whereas the direction of rotation of the motor can be changed by reversing
the direction of current through it.
- For applying varying voltage, we can make use of the PWM technique.
- For reversing the current, we can make use of H-Bridge circuit or motor driver
ICs that employ the H-Bridge technique or other any other mechanisms
### L293D Motor driver
The L293D IC receives signals from the microprocessor and transmits the relative
signal to the motors. It has two voltage pins, one of which is used to draw current for
the working of the L293D and the other is used to apply voltage to the motors.

We are going to use the L293D motor driver IC to control the DC motor movement in
both directions. It has an in-built H-bridge motor drive.

- As shown in the above figure we have connected 1KΩ Potentiometer at ADC
channel 0 of PIC18F4550 to change the speed of the DC motor.
- One toggle switch is connected to the INT0 pin which controls the motor
rotating direction.
- PORTD is used as an output control signal port. It provides control to motor1
input pins of the L293D motor driver which rotates the motor clockwise and
anticlockwise by changing their terminal polarity.

### PIC18F4550
PIC18F4550 is an 8-bit microcontroller manufactured by Microchip with nano-Watt
technology with enhanced flash, USB, and high-performance. It is a 40-pin microcontroller
that comes with several features such as memory endurance, self-programmability,
extended instruction set, enhanced CCP module, and addressable USART and 10-bit ADC.

## Code Explanation
- Enable ADC and map its output into 0-255 range.
- Enable Global interrupt, INT0 external interrupt with a rising edge-triggered
mode.
- Set PWM mode.
- Vary Duty cycle with ADC value and in an interrupt routine, we are toggling
motor direction.
- Now continuously check for an interrupt for direction and read the ADC value
for speed control.
- A switch will produce an interrupt which causes a change in motor direction.

## RESULT
After interfacing the DC motor with a PIC18F4550 microcontroller, the speed of the
motor can be regulated using variable resistance. The direction of the dc motor can
be changed using the switch. By turning it off, the motor turns in a clockwise
direction. In the on position, the motor turns in anti-clockwise direction.

