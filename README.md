
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

```
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
![WhatsApp Image 2025-10-15 at 14 38 55_4bae42fb](https://github.com/user-attachments/assets/0d7970bc-4931-4bb6-84cc-442517316806)
![WhatsApp Image 2025-10-15 at 14 39 20_2d12c7ac](https://github.com/user-attachments/assets/78099099-338f-4f23-9328-b0a785cc6ccd)

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
