# Lab 2: David Fedor

### 2-bit comparator

1. Karnaugh maps for other two functions:

   Greater than:

   ![cviko2DE_1](https://user-images.githubusercontent.com/99388268/154422709-840a4d4c-5255-4c1f-b5d2-3203af85d34f.png)

   Less than:

   ![cviko2DE_2](https://user-images.githubusercontent.com/99388268/154422937-7cfb6b93-4cdb-4369-8f4a-266789771f96.png)


2. Equations of simplified SoP (Sum of the Products) form of the "greater than" function and simplified PoS (Product of the Sums) form of the "less than" function.

   ![Logic functions](images/comparator_min.png)

### 4-bit comparator

1. Listing of VHDL stimulus process from testbench file (`testbench.vhd`) with at least one assert (use BCD codes of your student ID digits as input combinations). Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   Last two digits of my student ID: **xxxx44**

```vhdl
    p_stimulus : process
    begin
        begin
    	-- Report a note at the beginning of stimulus process
        report "Stimulus process started" severity note;
        -- Set one test case and wait 100 ns
        s_b <= "0100"; s_a <= "0100"; wait for 100 ns;
        s_b <= "0100"; s_a <= "0101"; wait for 100 ns;
        s_b <= "0101"; s_a <= "0100"; wait for 100 ns;
        wait;
        assert ((s_B_greater_A = '1') and
                (s_B_equals_A  = '1') and
                (s_B_less_A    = '1'))
        -- If false, then report an error
        report "Input combination 00, 00 FAILED" severity error;

        -- Report a note at the end of stimulus process
        report "Stimulus process finished" severity note;
        wait;
    end process p_stimulus;
```

2. Text console screenshot during your simulation, including reports.

   ![cviko2DE_3](https://user-images.githubusercontent.com/99388268/154485005-f45ad346-4935-4d90-b1dc-c0e517b7aa04.png)


3. Link to your public EDA Playground example:

   [https://www.edaplayground.com/x/miVS](https://www.edaplayground.com/x/miVS)
