# Exercise-07-Multiplexer-and-De-multiplexer
### AIM: 
To implement 4 X1 multiplexer and 1X4 de multiplexer using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## What are Multiplexer and Demultiplexer?
In-network transmission, both the multiplexer and demultiplexer are combinational circuits. A multiplexer selects an input from several inputs then it is transmitted in the form of a single line. An alternative name of the multiplexer is MUX or data selector. A demultiplexer uses one input signal and generates many. So it is known as Demux or data distributor.

## What is a Multiplexer?
The multiplexer is a device that has multiple inputs and single line output. The select lines determine which input is connected to the output, and also increase the amount of data that can be sent over a network within a certain time. It is also called a data selector.

The single-pole multi-position switch is a simple example of a non-electronic circuit of the multiplexer, and it is widely used in many electronic circuits. The multiplexer is used to perform high-speed switching and is constructed by electronic components.

![image](https://user-images.githubusercontent.com/36288975/170912485-73c395c7-23c0-4e78-a53d-a2f0d07d9662.png)
          Figure-01 multiplexer block diagram 

Multiplexers are capable of handling both analog and digital applications. In analog applications, multiplexers are made up of relays and transistor switches, whereas in digital applications, the multiplexers are built from standard logic gates. When the multiplexer is used for digital applications, it is called a digital multiplexer.

4-to-1 Multiplexer
The 4X1 multiplexer comprises 4-input bits, 1- output bit, and 2- control bits. The four input bits are namely 0, D1, D2, and D3, respectively; only one of the input bits is transmitted to the output. The o/p ‘q’ depends on the value of control input AB. The control bit AB decides which of the i/p data bit should transmit the output. The following figure shows the 4X1 multiplexer circuit diagram using AND gates. For example, when the control bits AB =00, then the higher AND gates are allowed while remaining AND gates are restricted. Thus, data input D0 is transmitted to the output ‘q”

![image](https://user-images.githubusercontent.com/36288975/170912568-3598c60a-5035-41f3-b0c4-ccedba13aca5.png)

Figure2 4X1 multiplexer 
If the control input is changed to 11, then all gates are restricted except the bottom AND gate. In this case, D3 is transmitted to the output, and q=D0. If the control input is changed to AB =11, all gates are disabled except the bottom AND gate. In this case, D3 is transmitted to the output, and q = D3. The best example of a 4X1 multiplexer is IC 74153. In this IC, the o/p is the same as the i/p. Another example of a 4X1 multiplexer is IC 45352. In this IC, the o/p is the compliment of the i/p

## What is Demultiplexer?
De-multiplexer is also a device with one input and multiple output lines. It is used to send a signal to one of the many devices. The main difference between a multiplexer and a de-multiplexer is that a multiplexer takes two or more signals and encodes them on a wire, whereas a de-multiplexer does reverse to what the multiplexer does.

![image](https://user-images.githubusercontent.com/36288975/170912606-a30e4b74-1726-4430-b245-2c3c3d9c232d.png)

Figure 3 De-multiplexer 
1-4 Demultiplexer
The 1-to-4 demultiplexer comprises 1- input bit, 4-output bits, and control bits. The 1X4 demultiplexer circuit diagram is shown below.

![image](https://user-images.githubusercontent.com/36288975/170912683-00fb746a-1d45-4023-91d1-3a70b841073c.png)

![image](https://user-images.githubusercontent.com/36288975/170912741-7cbd52af-7e0d-4be3-b5c6-6fb9c4eca7c9.png)

Figure4 1X4 De-multiplexer 
The i/p bit is considered as Data D. This data bit is transmitted to the data bit of the o/p lines, which depends on the AB value and the control i/p.

When the control i/p AB = 01, the upper second AND gate is permitted while the remaining AND gates are restricted. Thus, only data bit D is transmitted to the output, and Y1 = Data.

If the data bit D is low, the output Y1 is low. IF data bit D is high, the output Y1 is high. The value of the output Y1 depends upon the value of data bit D, the remaining outputs are in a low state.

If the control input changes to AB = 10, then all the gates are restricted except the third AND gate from the top. Then, data bit D is transmitted only to the output Y2; and, Y2 = Data. . The best example of 1X4 demultiplexer is IC 74155.
 
### Procedure
1. Open the quartus 2 software give the file name to write the program.
2. Declare input and output variable throuugh module and filename.
3. Now,declare input,output and wire variables.
4. for multiplexer we use 2 not gate,4 and gate and 1 or gate which is output. similary, for demultiplexer we use 2 not gate and 4 and gate which is output.
5. After completing program , we have to end program by using endmodule command which is used in verilog. STEP 6: now we can save and run the porgram.
### PROGRAM 
```
/*
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: Laakshit D
RegisterNumber: 212222230071
*/

i) MULTIPLEXER
module mux(i0,i1,i2,i3,s0,s1,y);
input i0,i1,i2,i3,s0,s1;
output y;
wire p,q,r,s,s0c,s1c;
not(s0c,s0);
not(s1c,s1);
and(p,s0c,s1c,i0);
and(q,s0c,s1,i1);
and(r,s0,s1c,i2);
and(s,s0,s1,i3);
or(y,p,q,r,s);
endmodule 
```
```
ii) DEMULTIPLEXER
module mux(y0,y1,y2,y3,s0,s1,i);
input s0,s1,i;
output y0,y1,y2,y3;
wire s0c,s1c;
nor(s0c,s0);
nor(s1c,s1);
and(y0,i,s0c,s1c);
and(y1,i,s0c,s1);
and(y2,i,s0,s1c);
and(y3,i,s0,s1);
endmodulev
```
### RTL LOGIC  
#### MULTIPLEXER

![image](https://github.com/laakshit-D/Exercise-07-Multiplexer-and-De-multiplexer/assets/119559976/22b331b4-3948-4fc8-a7dc-d7af5ce5e563)

#### DEMULTIPLEXER

![image](https://github.com/laakshit-D/Exercise-07-Multiplexer-and-De-multiplexer/assets/119559976/1e4129ea-7418-4ccf-ac4f-cee905a9eb6b)

### TIMING DIGRAMS  
#### MULTIPLEXER
- i0=1:

![image](https://github.com/laakshit-D/Exercise-07-Multiplexer-and-De-multiplexer/assets/119559976/f3b09d1d-5964-4f63-bf99-21dda1a89f6a)

- i1=1:

![image](https://github.com/laakshit-D/Exercise-07-Multiplexer-and-De-multiplexer/assets/119559976/fa26f1b5-4f90-4ca0-9f7a-043736747913)

- i2=1:

![image](https://github.com/laakshit-D/Exercise-07-Multiplexer-and-De-multiplexer/assets/119559976/ceada9ef-0878-4247-a6ea-2e6cfb8b886b)

- 13=1:

![image](https://github.com/laakshit-D/Exercise-07-Multiplexer-and-De-multiplexer/assets/119559976/1badaee8-fe18-4108-9f8e-f0129abd957c)

#### DEMULTIPLEXER

![image](https://github.com/laakshit-D/Exercise-07-Multiplexer-and-De-multiplexer/assets/119559976/469599a9-29d5-45e2-9fed-c55531aae67a)

### TRUTH TABLE 
#### MULTIPLEXER

![image](https://github.com/laakshit-D/Exercise-07-Multiplexer-and-De-multiplexer/assets/119559976/e682f0fc-76f5-4b94-8700-001d9d6b4654)

#### DEMULTIPLEXER

![image](https://github.com/laakshit-D/Exercise-07-Multiplexer-and-De-multiplexer/assets/119559976/4a55c009-1a1a-4efc-91f7-eb799ec67a9b)

### RESULTS 
4X1 multiplexer and 1X4 de multiplexer has been implemented using verilog and outputs are validated.
