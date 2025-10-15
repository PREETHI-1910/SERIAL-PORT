
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FCH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'D' 
WAIT:JNB TI, WAIT
CLR TI 
END





```
### (ii) Serial Port to Transfer a Message

ORG 00H
MOV TMOD,#20H
MOV TH1,#0FCH
MOV SCON,#40H
SETB TR1
MOV B,30H
MOV DPTR,#4500H
AGAIN:MOVX A,@DPTR
MOV SBUF,A
WAIT:JNB TI,WAIT
CLR TI
INC DPTR
DJNZ  B,AGAIN
END





```

### OUTPUT:
![WhatsApp Image 2025-10-15 at 14 39 20_cdca8c0c](https://github.com/user-attachments/assets/cb3e3b2d-5b08-4b4c-82af-1eaebdbb27e8)

![WhatsApp Image 2025-10-15 at 14 38 55_690f3da4](https://github.com/user-attachments/assets/53a6a2f7-bc73-461a-a3fc-c69060ec6f42)

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
