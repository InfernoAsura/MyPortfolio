---
title: Binary Search
lastmod: 2025-06-30
toc: true
---


# Binary Search 

Binary search is a searching algorithm used on arrays generally. The must condition before applying binary search is that the array must be sorted. The time complexity is O(log n), where n is the size of the array. 

# Implementation 

nums -> the array itself
Target -> value to be searched in the array
n -> size of the array


Iterative 

'''
int low = 0, high = nums.size() - 1, mid = 0;
while(low <= high){
   mid = (high + low) / 2;
   if (nums[mid] == target) return mid;
   else if(nums[mid] > target) high = mid - 1;
   else low = mid + 1;
}
return -1;
'''

Recursive

'''
    int binsearch(int low, int high, vector<int> nums, int target){
        if(high < low) return -1;
        int mid = (low + high) / 2;
        if(nums[mid] == target) return mid;
        else if(nums[mid] > target) return binsearch(low, mid - 1, nums, target);
        else return binsearch(mid + 1, high, nums, target);
    }

    int main(){
        return binsearch(0, n - 1, nums, target);
    }
'''

I have used 
''' mid = (low + high) / 2 ''' 
which is a bad practice. As, the addition of low and high might cause overflow. The good practice is to do this
''' mid = ((high - low) / 2) + low '''
