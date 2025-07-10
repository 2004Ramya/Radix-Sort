# Radix-Sort

Eg:-

i=0 i=1 i=2 i=3 i=4 i=5 i=6 i=7 i=8 i=9
432 008 530 090 088 231 011 045 677 199

---> Round-1:--For LSB Bits
  

  Index                            0     1    2      3     4     5     6     7     8     9
                                   -------------------------------------------------------------
LSB Bits of above no's             | 1+1 | 1+1 |  1  |  0  |  0  |  1  |  0  |  1  | 1+1 |  1  | 
                                   -------------------------------------------------------------
 Add Of LSB Bits values            |  2  |  4  |  5  |  5  |  5  |  6  |  6  |  7  |  9  | 10  | 
                                   -------------------------------------------------------------


--> take i=9 the LSb bit is 9 is at position 10 in Added LSB Bits So 10-1=9 So place 199 at index 9
--> Repeate the process upto i=6 i.e=011
--> again 1 is arrived at i=5 so the added LSB Bits value of 1 is index 4  so already placed at index 4-1=3 so subtract 4-2=2 place 1 at index 2.
--> Repeate the same process for all the remaining numbers till get placed
 
placing based on occured sum like CountSort: 

Index Values                                      0     1      2     3     4     5     6     7     8     9
                                                  -------------------------------------------------------------
Previously sorted values using Count_Sort         | 530 | 090 | 231 | 011 | 432 | 045 | 677 | 008 | 088 | 199 |
                                                  -------------------------------------------------------------

Obtained Values After Round-1:

 530  090  231   011   432   045   677   008   088   199 


---------------------------------

---> Round-2:- For Between MSB And LSB Bits

 i=0  i=1    i=2   i=3   i=4   i=5   i=6   i=7   i=8   i=9
| 530 | 090 | 231 | 011 | 432 | 045 | 677 | 008 | 088 | 199 |




Index                            0     1     2      3      4     5     6     7     8    9
                                ---------------------------------------------------------------
B/W Bits of resulted no's       |  1  |  1  |  0  | 1+1+1 |  1  |  0  |  0  |  1  |  1  | 1+1 | 
                                ---------------------------------------------------------------
Add Of B/W Bits values          |  1  |  2  |  2  |   5   |  6  |  6  |  6  |  7  |  8  | 10  | 
                                ---------------------------------------------------------------

placing based on occured sum like CountSort: 

Index Values                                      0     1      2     3     4     5     6     7     8     9
                                                  -------------------------------------------------------------
Previously sorted values using Count_Sort         | 008 | 011 | 530 | 231 | 432 | 045 | 677 | 088 | 090 | 199 |
                                                  -------------------------------------------------------------


Obtained Values After Round-2:

 i=0    i=1   i=2   i=3   i=4   i=5   i=6   i=7   i=8   i=9
| 008 | 011 | 530 | 231 | 432 | 045 | 677 | 088 | 090 | 199 |





----------------------------------------------------------------------------------------
#ALGORITHM 
1.Find the maximum number to determine number of digits.
2.Set 10^0 , for digit position .
3.Increment digit position , with rspcect to pass.
4.maxnum//exp>0
  - Perform count sort based on current digit
  - (num//exp)%10
  - multiply exp by 10

-->Time Complexity in all cases - O(nk)
-->Space Complexity in all cases - O(n)
