# 思路
先搞一个private static map method来 switch case， 把char map到 int  
然后for loop traverse 一遍， 如果当前map到的value < 下一个元素map到的value， 就减curr value, 否则＋    

`注意整个逻辑写完后， 一定要检查有没有cover edge cases`  
normal edge cases: `input为null，空，只有一个元素时`  

time : O(N)  
space: O(1)  

```
    public int romanToInt(String s) {
        int ans = 0;
        if(s == null || s.length() == 0) return 0;
        //map(s.charAt(i)) < map(s.charAt(i + 1)) 说明要做减法，否则+
        for(int i = 0; i < s.length(); i++) {
            if(i < s.length() - 1 && map(s.charAt(i)) < map(s.charAt(i + 1))) {
                ans -= map(s.charAt(i));
            } else {
                ans += map(s.charAt(i));
            }
        }
        return ans;
    }
    private static int map(char c) {
        switch(c) {
            case 'I': return 1;
            case 'V': return 5;
            case 'X': return 10;
            case 'L': return 50;
            case 'C': return 100;
            case 'D': return 500;
            case 'M': return 1000;
            default: return 0;
        }
    }
```