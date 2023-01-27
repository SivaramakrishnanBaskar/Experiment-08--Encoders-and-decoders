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

# Figure -01 3 to 8 Encoder
Implementation –

X = D4 + D5 + D6 + D7

Y = D2 +D3 + D6 + D7

Z = D1 + D3 + D5 + D7

Hence, the encoder can be realised with OR gates as follows:

image
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

image
# Figure -03 8 to 3 Decoder

image
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
Developed by: NAVIN KUMAR J
RegisterNumber:  22009212
 
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

# Decoder

# TIMING DIGRAMS

# Encoder

# Decoder


# TRUTH TABLE

# Encoder 

# Decoder

# RESULTS
Thus the Encoder and Decoder circuits are designed and truth tables are verified using quartus software
