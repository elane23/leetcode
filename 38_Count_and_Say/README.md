＃思路

这个题注意用recursion找到前一个string，然后写code
count and say the previous string.

过程中append string to stringbuilder 时**注意integer和char一起append时， 要 + "" 在中间，
不然会calculate int ＋ char value！**