# JK FLIPFLOP-USING-IF-ELSE

## AIM: 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

## **SOFTWARE REQUIRED:**

Quartus prime

## **THEORY**

### **JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

## **Procedure**


Start the program.

Declare the module name and define the input and output ports.

Inputs: J, K, Clock, and Reset.

Outputs: Q and QB.

Create an always block that is triggered on the positive edge of the clock signal.

Inside the always block, first check the reset condition.

If the reset input is active, maintain or initialize the outputs as required.

When reset is inactive, implement the JK flip-flop logic based on the inputs J and K.

If both J and K are 0, the output remains unchanged (Hold condition).

If J and K are different, the output follows the value of J (Set or Reset condition).

If both J and K are 1, the output toggles (changes to its complement).

End the always block and complete the module definition.

Simulate the design by applying various combinations of J and K along with clock pulses to observe the hold, set, reset, and toggle conditions.

## **PROGRAM**

Program for flipflops and verify its truth table in quartus using Verilog programming.
### Developed by: MADHUMITHA R R 
### RegisterNumber: 212224240083
```
module JK_FLIP_FLOP(q, qb,j,k,clock,reset);
    input j,k,clock,reset;
    output reg q, qb;
	 
always @ (posedge (clock))

    begin 
        if (!reset)
            begin
               q <= q;
               qb <=qb;
            end
else 
      begin
        if (j==0 && k==0)
		       begin
			    q <= q;
			    q <= qb;
			    end	 
        
        else if (j!=k)
             begin
	          q <= j;
	          qb <= k;
	          end
        else if (j==1 && k==1)
             begin
	          q <= ~q;
	          qb <= ~qb;
	          end
	  
      end
 
end           
endmodule 
```

## **RTL LOGIC FOR FLIPFLOPS**
<img width="1496" height="754" alt="Screenshot 2025-11-05 085659" src="https://github.com/user-attachments/assets/77d00faf-1f21-494e-ab68-250a9694bb05" />

## **TIMING DIGRAMS FOR FLIP FLOPS**
<img width="1920" height="1140" alt="image" src="https://github.com/user-attachments/assets/2a6516d4-aef2-4ac2-b1f9-030f197808cd" />

## **RESULTS**
Studied and verified the truth table of JK flip-flop in  Quartus II using verilog programming successfully.
