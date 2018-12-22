# 思路
题目：   
input: a compressed String, e.g. "a3b1c998d1"  -> aaabcccccc....cd
design next() and hasNext()  

`input string format: one letter then a positive integer`  

首先要先有一个pointer p 来traverse input string  
还要有char currLetter 来存当前的字母  
也要有int count 来记录目前还有多少个字母  

注意 `p == compressedString.length` 时，不一定没有next(),  
如果count > 0, 说明还有next字母没有打完

```
    //need p point to letter c
    private int findCount() {
            count = 0;
            currLetter = compressedString.charAt(p);
            p++;
            while(p < compressedString.length() && Character.isDigit(compressedString.charAt(p))) {
                count = count * 10 + compressedString.charAt(p) - '0';
                p++;
            }
            return count;
    }
    
    public char next() {
        if(!hasNext()) {
            return ' ';
        }
        if(count == 0) {
            count = findCount();
        }
        count--;
        return currLetter;
    }
    
    public boolean hasNext() {
        return p < compressedString.length() || count != 0;
    }
```


