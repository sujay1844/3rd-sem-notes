
# Structural flow level

![[Full adder.excalidraw]]
When we know the logic circuit diagram
```verilog
module fullAdder(a, b, cin, sum, cout);
    input a, b, cin;
    output sum, cout;
    wire w1, w2, w3;

    xor xor1(a, b, w1);
    xor xor2(w1, cin, sum);

    and and1(w1, cin, w3);
    and and2(b, cin, w2);

	or or1(w2, w3, cout);
endmodule

module xor(input A, B, output Z);
    assign Z = A ^ B;
endmodule

module and(input A, B, output Z);
    assign Z = A & B;
endmodule

module or(input A, B, output Z);
    assign Z = A | B;
endmodule


```
# Data flow level
When we know the boolean expression
```verilog
module fullAdder(a, b, cin, sum, cout);
	input a, b, cin;
	output sum, cout;


	assign sum = a ^ b ^ cin;
	assign cout = (a&b) | (a^b)&cin;
endmodule
```

# Mapping
When we need to pass named parameters
```python
def foo(a, b):
	return a + b
x, y = 5, 6
foo(a=x, b=y)
```
Same way in verilog
```verilog
some_module(.a(x), .b(y))
```

# Dumping
The code is compiled and dumped into specified file and then can be executed.
```verilog
$dumpfile("dump.vcd");
```

# Datatype
```verilog
t0 = 1'b0;
```
- `1'b` indicates one bit 
- `0` represents the data
- `t0` is the register where it is stored

# Delay
```verilog
#5
```
Add delay of 5 clock cycles