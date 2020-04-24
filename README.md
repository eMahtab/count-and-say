# Count and say
## https://leetcode.com/problems/count-and-say

# Implementation :

```java
class Solution {
    public String countAndSay(int n) {
        String number = "1";
        for(int i = 1; i < n; i++) {
            number = say(number);
        }
        return number;
    }
    
    private String say(String s) {
        int num = Character.getNumericValue(s.charAt(0));
        int lastSeen = num;
        int count = 1;
        String str = "";
        int i = 1;
        for(; i < s.length(); i++){
            if(Character.getNumericValue(s.charAt(i)) == lastSeen)
                count++;
            else {
                str = str + count + lastSeen;
                count = 1;
                lastSeen = Character.getNumericValue(s.charAt(i));
            }
        }
        str = str + count + lastSeen;
        return str;
    }
}
```
