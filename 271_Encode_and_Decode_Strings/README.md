# 思路

重点是怎样把word的内容和位置存到String里面
为了decode方便， 要先store word length, 再存word,
为了不要mix length and word里面的number，要用separator来隔开
```
"My", "name", "is", "Elane"
"2_My4_name2_is5_Elane"
```