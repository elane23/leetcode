# 思路

先use int[] and String[] 把所有posibility都列出来, 从大到小     
再traverse int[]， 如果input number > int[i], 就append(str[i]), num -= int[i]  

`注意: 不能直接String res = 'D'; `  
`只能String res = "" + 'D';`  

```
    public String intToRoman(int num) {
        if(num == 0) return "";
        StringBuilder sb = new StringBuilder();
        // or use a map to store the key value pair.
        int[] intArr = {1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1};
        String[] strArr = {"M", "CM", "D", "CD", "C", "XC", "L", "XL", "X", "IX", "V", "IV", "I"};
        for(int i = 0; i < intArr.length; i++) {
            while(num >= intArr[i]) {
                sb.append(strArr[i]);
                num -= intArr[i];
            }
        }
        return sb.toString();
    }
```

