# Zigzag-Conversion-Problem

The string "PAYPALISHIRING" is written in a zigzag pattern on a given number of rows like this: (you may want to display this pattern in a fixed font for better legibility)

P   A   H   N
A P L S I I G
Y   I   R
And then read line by line: "PAHNAPLSIIGYIR"

Write the code that will take a string and make this conversion given a number of rows:

string convert(string s, int numRows);
 

Example 1:

Input: s = "PAYPALISHIRING", numRows = 3
Output: "PAHNAPLSIIGYIR"
Example 2:

Input: s = "PAYPALISHIRING", numRows = 4
Output: "PINALSIGYAHRPI"
Explanation:
P     I    N
A   L S  I G
Y A   H R
P     I
Example 3:

Input: s = "A", numRows = 1
Output: "A"
 

Constraints:

1 <= s.length <= 1000
s consists of English letters (lower-case and upper-case), ',' and '.'.
1 <= numRows <= 1000


Code Solution : (In Python)


class Solution(object):
    def convert(self, s, numRows):
        if numRows <= 1:
            return s
        
        res = ""
        p = numRows * 2 - 2
        
        temp = p
        for i in range(0,numRows):
            index = i
            flag = 0
            while index < len(s):
                res = res + s[index]
                if i == 0 or i == numRows-1:
                    index = index + p
                else:
                    if flag == 0:
                        index = index + temp
                        flag = 1
                    else:
                        index = index + p-temp
                        flag = 0
                        
            temp = temp - 2
            
        return res

