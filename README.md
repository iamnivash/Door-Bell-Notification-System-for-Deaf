# Door-Bell-Notification-For-Deaf
OBJECTIVE:- 

   Living with a deaf person at times can be really challenging, as the person you are trying to communicate with is not able to hear anything you say. You stand at the door for minutes, you keep on knocking the door and no matter how many times you ring the bell, you get no response at all. The same thing happens when a baby is crying, or you are in the room and you need help. I will make a prototype model that can be used to let the deaf person know someone is on the door. This is my academic mini project.

COMPONENTS:- 

1.Arduino UNO and NANO
2.NRF24L01 And antenna (2)
3.Push Button
4.Vibrator
5.Connecting Wires

CONNECTION:- 

Transmitter side circuit diagram is provided in the repository. 
->The VCC and GND pins of the NRF24L01 module are connected with the Arduino’s 3.3V and GND pins. 
->A decoupling capacitor of 10uF is also connected between the VCC and GND pins. 
->CE pin is connected with Pin9, CSN is connected with the Pin10, SCK is connected with pin13, MOSI pin is connected with Pin11, and the MISO pin of the NRF24L01 Transceiver module is connected with the Arduino’s Pin12.
->A push button is connected with the Arduino’s pin 5.

Receiver side circuit diagram is provided in the repository. 
->The NRF24L01 Transceiver module connection with the Arduino remains exactly the same. The Red wire of the Micro vibration motor is connected with the Arduino’s PWM pin 5 and the Black wire is connected with the Arduino’s ground.

PROGRAM:-

->I have given the program for both Transmitter and Receiver in the repository.

Code Explanation:-

TRANSMITTER SIDE:- 

int Pushbutton = 5;
int bstate = 0;
For the pushbutton. In the void setup function I set the pushbutton as the input. In the void loop function we read the digital state of the Arduino’s pin 5 and store it in the bstate variable which is then stored in the data array at location 0 and finally we send the data array to the node00 which is the receiver side. Now, let’s take a look at the receiver side programming.

RECIEVER SIDE:-

On the receiver side I deleted the libraries which I added for the i2c LCD. I defined a pin for the micro vibration motor. I selected pin 5 of the Arduino which is the PWM pin. The reason I am using a PWM pin is to control the vibration intensity. In the void setup function I set the Vibration motor as output.

Finally, we check if we have received the data from the node01. So, if the data is received then store the value in data1. Then we use the two if conditions to check if the received number is 1 or 0. If the received number is 1 then stop the vibration motor and if the received number is 0 then it means the pushbutton on the transmitter side is pressed, so the Arduino starts the vibration motor, 200 represents the vibration intensity. You can set any value between 0 and 255. So, that’s all about the programming.

Finally, I uploaded the two codes and I successfully controlled the Micro Vibration motor wirelessly. For the practical demonstration watch video tutorial given below.  If you have any questions regarding this project, let me know in a comment.


library link:- 

https://drive.google.com/file/d/1MttZpeeNsuolQiRNqxvIdMPRzixAfLoE/view?usp=drive_link

https://drive.google.com/file/d/1zr-OX6XwLv8CwA9sM877eJLOCksy5DjT/view?usp=drive_link
 
