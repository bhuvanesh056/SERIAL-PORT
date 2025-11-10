
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FCH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'A' 
WAIT:JNB TI, WAIT
CLR TI 
END

```
### (ii) Serial Port to Transfer a Message

```
#include<reg51.h>
void main(void)
{
unsigned char msg[]="AJITH KUMAR";
unsigned char i;
TMOD=0X20;//TIMER 1,MODE 2
TH1=0XFC;
SCON=0X40;
TR1=1;
for (i=0; i<17;i++)
{
SBUF= msg[i];
while(TI==0);
TI=0;
}
while(1);
}


```

### OUTPUT:

<img width="1197" height="516" alt="image" src="https://github.com/user-attachments/assets/022f1a9a-2dea-4b6d-a8df-ed8e2a4e148a" />


<img width="1024" height="640" alt="image" src="https://github.com/user-attachments/assets/1ed34f63-5d9c-4851-85a0-b2098a1e1640" />


### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
