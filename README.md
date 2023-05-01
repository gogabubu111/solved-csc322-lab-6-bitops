Download Link: https://assignmentchef.com/product/solved-csc322-lab-6-bitops
<br>
&gt; BitOpsEnter an integer : 3030 is evenEnter an integer and a bit number : 30 630 has bit 6 offEnter an integer, start and end bit numbers : 30 4 630 has not all those bits on

Example Parameters:Start index (S) = 4, end index (E) = 6Index : 8 7 6 5 4 3 2 1 030 in binary: 0 0 0 0 1 1 1 1 0Mask: 0 0 1 1 1 0 0 0 0

We want to find the value of a mask such that when that value is convertedto binary, all the digits from start (S) to end (E) are one’s. Then we cancompare our mask to the original number (X).

In this example, X = 30, S = 4, E = 6.The mask value in binary is 001110000Converted to base 10, this is (2^6)+(2^5)+(2^4) = 64 + 32 + 16 = 112

After doing some math, I found that 2^(E+1) = 2^(6+1) = 128 and 2^(S) = 2^4 = 16Furthermore, 2^(E+1) – 2^(S) = 128 – 16 = 112 (mask value)So ( X &amp; Mask ) compares the two values to see if all digits from S to E are on.

Remember:0 &amp; 0 = 01 &amp; 0 = 01 &amp; 1 = 1

30 in binary: 0 0 0 0 1 1 1 1 0Mask: 0 0 1 1 1 0 0 0 0Result (X &amp; Mask): 0 0 0 0 1 0 0 0 0

We want the result to be zero, which would indicate that not all bits from thestarting digit (S = 4) to the ending digit (E = 6) are on. However, the problemis that the result of the comparison returns a value that is not zero. The 5th digitis a 1, which gives a value of 2^4 = 16. This non-zero result falsely suggests thatthe bits from S to E are all on, when in fact they are not. So what do we do?