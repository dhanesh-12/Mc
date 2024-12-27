1a)Write an assembly language program to transfer n =10 bytes of data from location
8035h to location 8041h (without overlap).
ORG 0000H
SJMP 30H
ORG 30H
MOV DPH,#80H
MOV R0,#35H //source address
MOV R1,#41H //destination address
MOV R3,#0AH //count
BACK: MOV DPL, r0
MOVX A,@dptr
MOV DPL, R1
MOVX @dptr,A
INC R0
INC R1
DJNZ R3, BACK
HERE: SJMP HERE
END
