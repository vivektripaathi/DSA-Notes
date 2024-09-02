# Kadane's Algorithm

> [!Question] Given an array ****arr[]**** of size ****N****. The task is to find the sum of the contiguous subarray within a ****arr[]**** with the largest sum.
> ****Input:**** arr = {-2,-3,4,-1,-2,1,5,-3}  
****Output:**** 7
> **Explanation** ![Kadane's Algorithm](/assets/images/kadane-Algorithm.png)
> **Practice** <a href="https://leetcode.com/problems/maximum-subarray/"><img src="../assets/images/LeetCode_logo_rvs.png" alt="Leetcode" width="25" height="25"></a>

**Intuition**: The intuition of the algorithm is not to consider the subarray as a part of the answer if its sum is less than 0. **_A subarray with a sum less than 0 will always reduce our answer and so this type of subarray cannot be a part of the subarray with maximum sum._**

### **Approach:**
The steps are as follows:
1. We will run a loop(say i) to iterate the given array.
2. Now, while iterating we will add the elements to the sum variable and consider the maximum one.
3. If at any point the sum becomes negative we will set the sum to 0 as we are not going to consider it as a part of our answer.

### **Example Function:**
```cpp
int maxSubArray(vector<int>& nums) {
    int sum = 0, mx = nums[0];
    for(auto i: nums) {
        sum += i;
        mx = max(mx, sum);
        if(sum < 0) sum = 0;
    }
    return mx;
}
```