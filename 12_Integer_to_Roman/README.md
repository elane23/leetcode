# 思路

先use int[] and String[] 把所有posibility都列出来, 从大到小     
再traverse int[]， 如果input number > int[i], 就append(str[i]), num -= int[i]  

`注意: 不能直接String res = 'D'; `  
`只能String res = "" + 'D';`  



