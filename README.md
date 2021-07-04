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


Code Solution : (In C++)

class Solution {
public:
    string convert(string s, int numRows) {
        
string Solution::convert(string a, int b) {
   if(b == 1)return a;
   string arr[b];
   int row = 0;
   bool down = true;
   for(int i = 0; i < a.size(); i++){
      arr[row].push_back(a[i]);
      if(row == b - 1) down = false;
      else if(row == 0)down = true;
      if(down) row++;
      else row--;
   }
   string ans = "";
   for(int i = 0; i < b; i++){
      ans += arr[i];
   }
   return ans;
}
main(){
   Solution ob;
   cout << ob.convert("PAYPALISHIRING", 3);
        
    }
};
