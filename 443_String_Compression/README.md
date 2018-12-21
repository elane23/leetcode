# 思路

这一题要求被压缩的string length一定要不大于原string
`count == 1`时， 不把count加入char[]

初始count = 1
traverse时，
1. 如果已经是最后一个char 或者 当前char和下一个char不同时，要把当前char和count加入char[], reset `count = 1`
注意edge case：如果count > 10, if count = 998, **因为ASCII表格中char 只包含'0','1',....'9', 所以
必须把int convert to String convert to char[], 然后把‘9’‘9’‘8’加入char[]**


2. 如果当前char 和下一个char相同，则count++


time: O(N)
space: O(1)  in place