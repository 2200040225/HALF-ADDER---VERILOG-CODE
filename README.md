Design code:

//gate level modelling

module halfadder(a,b,s,c);
input a,b;
output s,c;
xor(s,a,b);        
and(c,a,b);
endmodule

//data flow modelling

module halfadder(a,b,s,c);
input a,b;
output s,c;
assign s=a^b;
assign c=a&b;
endmodule

Test bench:

module halfadder_tb();
reg a,b;
wire s,c;
halfadder uut(a,b,s,c);
initial begin
a=0;
b=0;
#10
a=0;
b=1;
#10
a=1;
b=0;
#10
a=1;
b=1;
#10
end
$finish();
endmodule




