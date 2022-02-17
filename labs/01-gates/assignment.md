# Lab 1: David  Fedor

### De Morgan's laws


1. Listing of VHDL architecture from design file (`design.vhd`) for all three functions. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
architecture dataflow of demorgan is
begin
    f_o     <= (not b_i and a_i) or (not c_i and not b_i);
    fnand_o <= ((not b_i nand a_i) nand (not c_i nand not b_i));
    fnor_o  <= b_i nor (a_i nor not c_i);
end architecture dataflow;
```

2. Complete table with logic functions' values:

| **c** | **b** |**a** | **f(c,b,a)** | **f_NAND(c,b,a)** | **f_NOR(c,b,a)** |
| :-: | :-: | :-: | :-: | :-: | :-: |
| 0 | 0 | 0 | 1 | 1 | 1 |
| 0 | 0 | 1 | 1 | 1 | 1 |
| 0 | 1 | 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 | 0 | 0 |
| 1 | 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 | 1 | 1 |
| 1 | 1 | 0 | 0 | 0 | 0 |
| 1 | 1 | 1 | 0 | 0 | 0 |

### Distributive laws

1. Screenshot with simulated time waveforms. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

   ![cviko1DE](https://user-images.githubusercontent.com/99388268/154420666-d92c69e3-deb0-4d7a-a0fc-4590b7437551.png)


2. Link to your public EDA Playground example:

   [https://www.edaplayground.com/x/KXRB](https://www.edaplayground.com/x/KXRB)
