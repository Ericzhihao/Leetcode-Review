# 443. String Compression

```
 public int compress(char[] nums) {
        int slow = 0;
        int fast = 0;

        while(fast < nums.length){
            char currentChar = nums[fast];
            int count = 0;
            while(fast < nums.length && currentChar == nums[fast]){
                fast++;
                count++;
            }
            nums[slow++] = currentChar;
            if(count > 1){
                char[] ch = String.valueOf(count).toCharArray();
                for(char c : ch){
                    nums[slow++] = c;
                }
            }
        }
        return slow;
    }
```

# 8. String to Integer

```
public int myAtoi(String s) {
        s = s.trim();
        if(s == null || s.length() == 0){
            return 0;
        }
        int sign = 1;
        int res = 0;
        int index = 0;
        if(s.charAt(0) == '+' || s.charAt(0) == '-'){
                sign = (s.charAt(0) == '-') ? -1 : 1; //预处理sign
                index++;
        }
        while(index < s.length()){
            char currentChar = s.charAt(index);
            if(currentChar < '0' || currentChar > '9') break;

            int digit = currentChar - '0';
            if(res > (Integer.MAX_VALUE - digit) / 10){
                return sign == -1 ? Integer.MIN_VALUE : Integer.MAX_VALUE;
            }
            res = res * 10 + digit;
            index++;
        }
        return res * sign;
    }
```


