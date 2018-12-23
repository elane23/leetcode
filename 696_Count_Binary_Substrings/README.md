# 思路
input: String:"10101"   "11100011"  
output: 6 				5   
数连续的0和1个数相同的substring有几个？   

brute force solution  
time : O(N2)  

improved solution:  
用preCount and currCount 记录下连续的0或1 的个数  
`count += Math.min(preCount, currCount)`  
time: O(N)  

**注意traverse到最后一个元素时:**  
要加到count上： `count += Math.min(preCount, currCount)`  

最开始因为`preCount初始值 = 0`, 所以Math.min() return 0, 可以不单独拎出来计算。  