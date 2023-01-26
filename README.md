# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure

1.create module encoder and decoder.

2.Get inputs and outputs for encoders and decoders.

3.perform or operation for encoder and and logic for decoders.

4.perform RTL LOGIC and get waveform.



### PROGRAM:


module encoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input d0,d1,d2,d3,d4,d5,d6,d7;
output a,b,c;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule



module decoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
endmodule 




Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: Gopika R
RegisterNumber: 22009266 



### RTL LOGIC: 


![Screenshot (75)](https://user-images.githubusercontent.com/122762773/214758879-87d36c34-b126-4c1e-a9dc-6b55bf745157.png)


![Screenshot (77)](https://user-images.githubusercontent.com/122762773/214758888-5c2fccdc-7a36-4dac-839a-7333f0fa3660.png)




### TIMING DIGRAMS:  


![Screenshot (76)](https://user-images.githubusercontent.com/122762773/214758933-703a3ec1-cb2a-4750-a48a-d8212edd54f8.png)

![213618754-b028929e-7372-4250-a245-8a84fd4b089b](https://user-images.githubusercontent.com/122762773/214759059-fb0fd25a-43aa-40d5-a259-fb4dd2a2ce2e.png)


### TRUTH TABLE 


![213618820-2a4e7b45-43b2-4776-9183-3c8ad21496c7](https://user-images.githubusercontent.com/122762773/214759113-02a8e405-572e-47d5-b187-6c68304493e8.png)


![213618833-ef914a06-39c2-47e7-a376-9eeaccc1dba0](https://user-images.githubusercontent.com/122762773/214759131-360259a2-263c-4b03-8ae2-4385a0f9e58b.png)


### RESULTS:
      Thus the program to desing encoder and decoder is done.
