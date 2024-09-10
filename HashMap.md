# 15. 3Sum

``` public List<List<Integer>> threeSum(int[] nums) {
        List<List<Integer>> res = new ArrayList<>();
        Arrays.sort(nums);
        for(int start = 0; start < nums.length - 2; start++){
            if(start > 0 && nums[start] == nums[start - 1]){ //避免重复的start
                    continue;
                }
            int mid = start + 1;
            int end = nums.length - 1;

            while(mid < end){
                
                int sum = nums[start] + nums[mid] + nums[end];
                if(sum == 0){
                    res.add(Arrays.asList(nums[start], nums[mid],nums[end]));
                    while(mid < end && nums[mid] == nums[mid + 1]){
                        mid++;
                    }
                    while(mid < end && nums[end] == nums[end - 1]){
                        end--;
                    }
                    mid++;
                    end--;
                }else if(sum > 0){
                    end--;
                }else{
                    mid++;
                }
            }
        }
        return res;
    }
```
Time Complexity O(n^2) 

Space Complexity: O(nlogn)





