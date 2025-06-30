---
title: Binary Search
lastmod: 2025-06-30
toc: true
---


Binary search is a searching algorithm used on arrays generally. The must condition before applying binary search is that the array must be sorted. The time complexity is O(log n), where n is the size of the array. 

# Implementation of Binary Search

nums -> the array itself <br>
Target -> value to be searched in the array <br>
n -> size of the array


Iterative 

``` cpp
int low = 0, high = nums.size() - 1, mid = 0;
while(low <= high){
   mid = (high + low) / 2;
   if (nums[mid] == target) return mid;
   else if(nums[mid] > target) high = mid - 1;
   else low = mid + 1;
}
return -1;
```

Recursive

``` cpp
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
```

I have used 
``` mid = (low + high) / 2 ```
which is a bad practice. As, the addition of low and high might cause overflow. The good practice is to do this
``` mid = ((high - low) / 2) + low ```


# Upper Bound and Lower Bound 

Upper bound of an element x is the number which is just greater than x in the array. <br/>
Lower bound of an element x is the number which is either equal to x or just greater than x in the array.

# Implementation of Upper bound

``` cpp
        int low = 0, high = nums.size() - 1, mid = 0, index = nums.size();
        while(low <= high){
            mid = (high - low) / 2 + low;
            if(nums[mid] > x) {
                index = mid; 
                high = mid - 1;
            }
            else low = mid + 1;
        }
        return index;
```

CPP STL:
``` cpp
auto ub = upper_bound(nums.begin(), nums.end(), x); // This will give the iterator pointing at the position of upper bound in array.
cout << *ub << endl; // This will print the element which is upper bound of x
cout << ub - nums.begin() << endl; // This will give us the index of the element which is upper bound of x
```


# Implementation of Lower bound

``` cpp
        int low = 0, high = nums.size() - 1, mid = 0, index = nums.size();
        while(low <= high){
            mid = (high - low) / 2 + low;
            if(nums[mid] >= x) {index = mid; high = mid - 1;}
            else low = mid + 1;
        }
        return index;
```


CPP STL:
``` cpp
auto lb = lower_bound(nums.begin(), nums.end(), x); // This will give the iterator pointing at the position of lower bound in array.
cout << *lb << endl; // This will print the element which is lower bound of x
cout << lb - nums.begin() << endl; // This will give us the index of the element which is lower bound of x
```
