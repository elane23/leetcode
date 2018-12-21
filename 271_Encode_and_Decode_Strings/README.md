# 思路

重点是怎样把word的内容和位置存到String里面
为了decode方便， 要先store word length, 再存word,
为了不要mix length and word里面的number，要用separator来隔开
```
"My", "name", "is", "Elane"
"2_My4_name2_is5_Elane"
```

decode每次要先定位separator, two pointers
再用substring method, 取出word， 存入list, pointer -> sepIndex + 1 + len

```
        int pointer = 0;

        while(pointer < s.length()) {
            int sepIndex = s.indexOf('_', pointer);
            int len = Integer.parseInt(s.substring(pointer, sepIndex));
            String word = s.substring(sepIndex + 1, sepIndex + 1 + len);
            decoded.add(word);
            pointer = sepIndex + 1 + len;
        }

```

*记得考虑edge case, if empty list*

time: O(N)
space: O(N)