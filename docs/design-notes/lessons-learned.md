# Lessons Learned

##### 1/25/26

While testing out my A3909 breakout board, I noticed that during reset of the Nucleo board my power supply would hit current limit and coils would audibly whine, indicating I was driving them during reset unintentionally. I thought that this should be covered by the pulldowns included on the A3909 inputs, but quickly realized that during reset of the MCU the OEINV pin for the shift registers is floating. Big mistake! If the pin floats around, then any garbage data (caused by floating pins on the rest of the gpio into the SER, SRCLK, RCLK) can be continuously sent to the a3909. While this doesnt impair functionality of the breakout board, this should be fixed in future revisions, and this issue should also be fixed in the final clock design.