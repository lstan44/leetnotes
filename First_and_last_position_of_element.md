#  Find First and Last Position of Element in Sorted Array

**Medium** 
_https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/_

Description
-------------
Given an array of integers nums sorted in ascending order, find the starting and ending position of a given target value.

Your algorithm's runtime complexity must be in the order of O(log n).

If the target is not found in the array, return [-1, -1].

## Solution in Log(n) using the C++ STL

```
 vector<int> searchRange(vector<int>& nums, int target) {
        if(nums.empty()) return vector<int>{-1,-1};
        vector<int>::iterator up, low;
        
        up = upper_bound(nums.begin(), nums.end(), target);
        low = lower_bound(nums.begin(), nums.end(), target);
        
        int first = low - nums.begin();
        int last = up - nums.begin() -1;
        
        if(first < 0 || first >=  nums.size() || last < 0 || last >= nums.size())
            return vector<int>{-1,-1};
        
        if (nums[first] == nums[last] && nums[last] == target)
            return vector<int>{first,last};
        
        return vector<int>{-1,-1};
    }

```
