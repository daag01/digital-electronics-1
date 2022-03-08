# Lab 4: David Fedor
### Seven-segment display decoder

1. Listing of VHDL stimulus process from testbench file (`tb_hex_7seg.vhd`) with asserts. Verify all input combinations. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
    p_stimulus : process
    begin
        report "Stimulus process started" severity note;

        -- First test case
        s_hex <= "0000"; wait for 50 ns;
        assert (s_seg = "0000001")
        report "Input combination 0000 FAILED" severity error;
        -- Second test case
        s_hex <= "0001"; wait for 50 ns;
        assert (s_seg = "1001111")
        report "Input combination 1001111 FAILED" severity error;
        -- Third test case
        s_hex <= "0010"; wait for 50 ns;
        assert (s_seg = "0010010")
        report "Input combination 0010010 FAILED" severity error;
        -- Fourth test case        
        s_hex <= "0011"; wait for 50 ns;
        assert (s_seg = "0000011")
        report "Input combination 0000011 FAILED" severity error;
        -- Fifth test case
        s_hex <= "0101"; wait for 50 ns;
        assert (s_seg = "0100100")
        report "Input combination 0100100 FAILED" severity error;
        -- Sixth test case        
        s_hex <= "0110"; wait for 50 ns;
        assert (s_seg = "0100000")
        report "Input combination 0100000 FAILED" severity error;
        -- Seventh test case        
        s_hex <= "0111"; wait for 50 ns;
        assert (s_seg = "0001111")
        report "Input combination 0001111 FAILED" severity error;      
        -- Eight test case        
        s_hex <= "1000"; wait for 50 ns;
        assert (s_seg = "0000000")
        report "Input combination 0000000 FAILED" severity error;    
        -- Nineth test case
        s_hex <= "1001"; wait for 50 ns;
        assert (s_seg = "0000100")
        report "Input combination 0000100 FAILED" severity error;  
        -- A test case
        s_hex <= "1010"; wait for 50 ns;
        assert (s_seg = "0001000")
        report "Input combination 0001000 FAILED" severity error;  
        -- B test case
        s_hex <= "1011"; wait for 50 ns;
        assert (s_seg = "1100000")
        report "Input combination 1100000 FAILED" severity error;       
         -- C test case
        s_hex <= "1100"; wait for 50 ns;
        assert (s_seg = "0110001")
        report "Input combination 0110001 FAILED" severity error;  
         -- D test case
        s_hex <= "1101"; wait for 50 ns;
        assert (s_seg = "1000010")
        report "Input combination 1000010 FAILED" severity error;  
         -- E test case
        s_hex <= "1110"; wait for 50 ns;
        assert (s_seg = "0110000")
        report "Input combination 0110000 FAILED" severity error;  
         -- F test case
        s_hex <= "1111"; wait for 50 ns;
        assert (s_seg = "0111000")
        report "Input combination 0111000 FAILED" severity error;  

        report "Stimulus process finished" severity note;
        wait;
    end process p_stimulus;
```

2. Screenshot with simulated time waveforms. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

   ![Snímek obrazovky 2022-03-08 203209](https://user-images.githubusercontent.com/99388268/157311449-2c4f5744-7347-41b1-8e48-dcb12a35f5f2.png)


### LED(7:4) indicators

1. Listing of LEDs(7:4) part of VHDL architecture from source file `top.vhd`. Try to write logic functions as simple as possible. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   ```vhdl
   --------------------------------------------------------------------
   -- Experiments on your own: LED(7:4) indicators

    -- Turn LED(4) on if input value is equal to 0, ie "0000"
    -- LED(4) <= `0` when WRITE YOUR CODE HERE
       LED(4) <= '1' when SW = "0000" else '0';
       
    -- Turn LED(5) on if input value is greater than "1001", ie 10, 11, 12, ...
    -- LED(5) <= WRITE YOUR CODE HERE
       LED(5) <= '1' when (SW > "1001") else '0';

    -- Turn LED(6) on if input value is odd, ie 1, 3, 5, ...
    -- LED(6) <= WRITE YOUR CODE HERE
       LED(6) <= SW(0);

    -- Turn LED(7) on if input value is a power of two, ie 1, 2, 4, or 8
    -- LED(7) <= WRITE YOUR CODE HERE
       LED(7) <= '1' when SW = "0001" else
                 '1' when SW = "0010" else
                 '1' when SW = "0100" else
                 '1' when SW = "1000" else '0';

   ```
