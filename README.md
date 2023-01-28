# Experiment-08--Encoders-and-decoders

# AIM:
To implement 8 to 3 Encoder and 3to8 Decoder using verilog and validate its outputs

# HARDWARE REQUIRED: –
PC, Cyclone II , USB flasher

# SOFTWARE REQUIRED:
Quartus prime

# THEORY
# Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

Encoders –

An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![Screenshot (136)](https://user-images.githubusercontent.com/119476322/215269677-af8e4c64-df73-431b-a633-6acc4e71e921.png)

# Figure -01 3 to 8 Encoder 

Implementation –

X = D4 + D5 + D6 + D7

Y = D2 +D3 + D6 + D7

Z = D1 + D3 + D5 + D7

Hence, the encoder can be realised with OR gates as follows:

![Screenshot (137)](https://user-images.githubusercontent.com/119476322/215269741-320e64f5-effa-4977-be8f-322dff3fe312.png)

# Figure -02 3 to 8 Encoder implenentation

# Decoders

A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.

Implementation –

D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ Similarly,

D1 = X’ Y’ Z

D2 = X’ Y Z’

D3 = X’ Y Z

D4 = X Y’ Z’

D5 = X Y’ Z

D6 = X Y Z’

D7 = X Y Z

![Screenshot (138)](https://user-images.githubusercontent.com/119476322/215269778-832b58af-2157-403b-8331-b9a018fb1998.png)

# Figure -03 8 to 3 Decoder

![Screenshot (139)](https://user-images.githubusercontent.com/119476322/215269817-b79c5129-47e3-415b-a9a2-8a03e44c7950.png)

# Figure -04 8 to 3 Decoder implementation

# Procedure
```
1.Using OR Gates construct 8:3 Encoder

2.Repeat the same for 3:8 Decoder using AND Gate 

3.Find RTL logic and Timing Diagram for both Encoder and Decoder

4.End the Program
```

# PROGRAM
```
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: Sivaramakrishnan B 
RegisterNumber:  22006798
 
Encoder

module encoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input d0,d1,d2,d3,d4,d5,d6,d7;
output a,b,c;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule

# Decoder

module decoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0=(~a&~b&~c),
    d1=(~a&~b&c),
	 d2=(~a&b&~c),
	 d3=(~a&b&c),
	 d4=(a&~b&~c),
	 d5=(a&~b&c),
	 d6=(a&b&~c),
	 d7=(a&b&c);
endmodule
```

# RTL LOGIC

# Encoder

![Screenshot (140)](https://user-images.githubusercontent.com/119476322/215269891-31993b60-b364-4b9a-a3b2-a975c8cbdc69.png)

# Decoder

![Screenshot (141)](https://user-images.githubusercontent.com/119476322/215269898-28684a1c-dd19-4374-a647-a86415c01316.png)

# TIMING DIGRAMS

# Encoder

![Screenshot (142)](https://user-images.githubusercontent.com/119476322/215269914-962bc7d3-1f77-47ae-b1ac-71911ea1f378.png)

# Decoder

![Screenshot (143)](https://user-images.githubusercontent.com/119476322/215269930-9053fbaf-1ffd-4edb-9aa5-92482e2b1a4c.png)

# TRUTH TABLE

# Encoder 

![Screenshot (144)](https://user-images.githubusercontent.com/119476322/215269954-6b54fc7a-3324-41cd-b11b-afa9f580c2ca.png)

# Decoder

![Screenshot (145)](https://user-images.githubusercontent.com/119476322/215269979-260180a7-1614-4bcc-a261-921234192f34.png)

# RESULTS
Thus the Encoder and Decoder circuits are designed and truth tables are verified using quartus software
