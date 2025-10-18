# squarewaveform
Aim

To generate a square wave of 50 kHz frequency at pin P2.3 using Timer 1 of the 8051 microcontroller with a 12 MHz crystal frequency.

Appratus Required

      1.Personal Computer
      2.Keil µVision Software
      
Program
```
MOV TMOD, #10H
AGAIN: MOV TH1,#0FFH
MOV TL1,#0F6H
SETB TR1
BACK: JNB TF1, BACK
CLR TR1
CPL P2.3
CLR TF1
SJMP AGAIN
END
```

Output
<img width="1920" height="1200" alt="Screenshot (202)" src="https://github.com/user-attachments/assets/578c5c45-bedd-487f-994e-7cffbc13ec29" />



Result
The program successfully generates a continuous 50 kHz square wave at the output pin P2.3.
Timer 1 (in Mode 1) is used to create the precise time delay required for a 50 kHz frequency, and the output pin P2.3 toggles continuously to form the square waveform.
