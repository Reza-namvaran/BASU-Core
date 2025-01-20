# BUS STRUCTURE

Suppose that a digital system has a number of n-bit registers, and that it must be possible
to transfer data from any register to any other register. A simple way of providing the desired
interconnectivity may be to connect each register to a common set of n wires, which are used
to transfer data into and out of the registers. This common set of wires is usually called a bus.
If common paths are used to transfer data from multiple sources to multiple destinations, it is
necessary to ensure that only one register acts as a source at any given time and other
registers do not interfere.

### Tri-State Buffers

Outputs of two ordinary logic gates cannot be connected together, because a short circuit
would result if one gate forces the output value 1 while the other gate forces the value 0.

Therefore, some special gates are needed if the outputs of two registers are to be connected to
a common set of wires. But what?

In these situations tri-state buffer come in handy. 

Its purpose is to provide additional electrical driving capability. In conjunction
with the output switch. When e = 1, the output reflects the logic value on the data input. 
But, when e = 0, the output is electrically disconnected from the data input, which is referred to
as a high impedance state and it is usually denoted by the letter Z (or z). 
Because this circuit element exhibits three distinct states, 0, 1, and Z, it is
called a tri-state driver (or buffer).

The triangular symbol in the figure represents a noninverting *driver*, which is a circuit 
that performs no logic operation and its output simply replicates the input signal.

![tri-state_buffer](https://www.sciencedirect.com/topics/computer-science/tristate-buffer)


``vhdl
LIBRARY IEEE;
USE IEEE.STD_LOGIC_1164.ALL

ENTITIY n_bit_tri IS
GENERIC (N : INTEGER := 8);
PORT (X : IN STD_LOGIC_VECTOR(N - 1 DOWNTO 0);
      E : IN STD_LOGIC;
      F : OUT STD_LOGIC_VECTOR(N - 1 DOWNTO 0)
);
END n_bit_tri;

ARCHITECTURE BEHAVIORAL OF n_bit_tri IS
BEGIN 
    F <= (OTHERS => 'Z') WHEN E = '0' ELSE X;
END BEHAVIORAL;
```

---

