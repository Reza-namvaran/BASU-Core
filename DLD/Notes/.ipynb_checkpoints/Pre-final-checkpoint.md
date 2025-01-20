# Registers
The term **register** is merely a convenience for referring to n-bit structures 
consisting of flip-flops. A common clock is used for each flip-flop in a register, and each flip-flop operates as described in the
previous sections.

# Shift Registers
If a given number is multiplied by 2 if its bits are shifted one bit position to the left and a 0 is inserted as the new least-significant bit. Similarly, the number is divided by 2 if the bits are shifted one bit-position to the right. A register that
provides the ability to shift its contents is called a shift register.

### Question? 
Why **Latches** aren't suitable for implementing a shift registers? because a change in the value of the Input would propagate 
through more than one latch during the time when the clock is equal to 1 (Rising-edge).

# PARALLEL-ACCESS SHIFT REGISTER

In computer systems it is often necessary to transfer n-bit data items from one location to another. 
This may be done by transmitting all bits at once using n separate wires, in which case we say that the transfer is performed in parallel.
But it is also possible to transfer all bits using a single wire, by performing the transfer one bit at a time, in n consecutive clock
cycles. We refer to this scheme as serial transfer. 
To transfer an n-bit data item serially, we can use a shift register that can be loaded with all n bits in parallel (in one clock cycle).
Then during the next n clock cycles, the contents of the register can be shifted out for serial
transfer. The reverse operation is also needed. If bits are received serially, then after n clock
cycles the contents of the register can be accessed in parallel as an n-bit item.

---

## Important Example
