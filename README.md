# CECS-460-GA2
The goal of group project 2 was to use the onboard BRAM and an 8-bit data bus to implement a AXI4-Lite slave interface.  Our project uses the onboard switches for both reading data as well as the address. A buffer is created in order to store different segments of our 8-bit information using only four switches and two buttons. The top buffer is constructed through the onboard switches that will control the value of data/or address we wish and onboard buttons 2 and 3 which determine which set of bits we will be writing to. Pressing button 2 will set bits [0-3] as active for our buffer, while pressing button 3 will set bits [4-7] as active for our buffer to send to either data or address. Depending on the mode of the board different actions will occur.  Mode 0 is the default mode of the board.  Mode 1: the buffer, our currently stored information from the pins,  is read into the address bits. Mode 2: The buffer is read into the data bits, with readWrite = 0. Readwrite = 0 means that the BRAM will use the buffer as the new address and show to output to. Mode 3: the buffer is read into the databits, with readWrite = 1. ReadWrite = 1 means that our BRAM will use the buffer as new data to be written into address passed.  


# Project Tests/Simulations

BRAM TESTS
![image](https://github.com/user-attachments/assets/34e6ff25-aa75-493b-a7d1-8bd4cf445212)
Test 1:
The addresses are looped through from 0 to 256 in order to display the data inside of them on start.  For example, address 1 will have data = 1 stored, while address = 125 will have data = 125 stored.

![image](https://github.com/user-attachments/assets/b86fbd31-38c0-4336-886c-6132253e0c27)
Test 2: 
Again, loop through the addresses; however, this time set data = address + 1 in order to verify that changing data will change what is stored in BRAM. For example, address 1 will have data = 2 stored, while address = 125 will have data = 126 stored.


AXI TESTS
![image](https://github.com/user-attachments/assets/66fce465-2de0-4294-8511-3949c88177fa)
Ensure that information is being passed through the axi bus correctly. To do this, BRAM test 2 is used


TOP TESTS
