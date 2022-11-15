# Experiment-08- Encoders-and-decoders 
### AIM: 

To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED: – 

PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:

Quartus prime
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
```
Step1:- Open the quartus II software.

Step2:- Create a new project.

Step3:- Name the projects such that the same name is used for mentioning the name of the module.

Step4:- Develop programmes for both Encoder and Decoder using verilog programming.

Step5:- Run RTL Simulation.

Step6:- Create the Timing diagram.

Step7:- Validate the outputs.
```



### PROGRAM 
```
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: D.vishnu vardhan reddy
RegisterNumber:  212221230023
```
### Encoder:
```
module encoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule
```
### Decoder:
```
module decoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
output d0,d1,d2,d3,d4,d5,d6,d7;
input a,b,c;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
endmodule
```





### RTL LOGIC 
Encoder

![image](https://user-images.githubusercontent.com/94175324/201830659-f3313bb9-7fac-4fe2-b7a9-d82bf18b3a09.png)

 Decoder
 
![image](https://user-images.githubusercontent.com/94175324/201830698-4c76b0c6-ba64-4cca-aa35-9e75b55433b5.png)








### TIMING DIGRAMS 

Encoder

![image](https://user-images.githubusercontent.com/94175324/201830872-dad68250-4034-41e0-a89f-885a1f7c8a17.png)

Decoder

![image](https://user-images.githubusercontent.com/94175324/201830841-b76133eb-5a49-45e8-ae70-0b169845a436.png)





### TRUTH TABLE 

Encoder

![image](https://user-images.githubusercontent.com/94175324/201830887-67e334e5-3e72-49fb-a0ee-9fe7cf81b03e.png)

Decoder

![image](https://user-images.githubusercontent.com/94175324/201830911-6e869260-b285-4351-b172-3528c9627d3f.png)






### RESULTS 
Therefore 8 to 3 Encoder and 3 to 8 Decoder are implemented successfully using verilog and validate its outputs.


