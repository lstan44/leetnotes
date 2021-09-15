# Sliding Window Problems and Solutions

## Maximum Average Subarray 1 - Leetcode
_https://leetcode.com/problems/maximum-average-subarray-i/submissions/_

```
     double findMaxAverage(vector<int>& nums, int k) {
        double maxValue = 0.0;
        double maxAverage = 0.0;
        for(int i = 0; i < k; i++) maxValue += nums[i];
        
        maxAverage = maxValue / (double) k;
        
        int x = 0, y = k;
        
        while( y < nums.size()){
            maxValue += nums[y];
            maxValue -= nums[x];
            x++;
            y++;
            if(maxValue / (double) k > maxAverage) maxAverage = maxValue / (double) k;
        }
        return maxAverage;
    }
```

