# Dutch Flag Algorithm
- Dutch Flag Algorithm (DFA) is one of the most basic and important algorithms for arrays. It is used to sort an array consisting of 3 numbers in linear time complexity.
- The worst time complexity for DFA is O(n) and the space complexity for the algorithm is O(1). The problem statement is as follows:

>[! Question] An array consisting of 0s, 1s, and 2s is provided to you. The task is to write a function that segregates all the numbers together. The order can be anything. Solve problem at [LeetCode](https://leetcode.com/problems/sort-colors/) or [CodingNinja](https://www.codingninjas.com/studio/problems/sort-an-array-of-0s-1s-and-2s_892977?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)
>
> Test Case
> > Input: [2, 2, 2, 2, 0, 0, 1, 0]
> > Output: [0, 0, 0, 1, 2, 2, 2, 2]

This algorithm contains 3 pointers i.e. low, mid, and high, and 3 main rules.  The rules are the following:
- arr[0….low-1] contains 0. [Extreme left part]
- arr[low….mid-1] contains 1.
- arr[high+1….n-1] contains 2. [Extreme right part], n = size of the array
The middle part i.e. arr[mid….high] is the unsorted segment. So, hypothetically the array with different markers will look like the following:

![Dutch Flag Algorithm](/assets/images/DNF-sort.png)

**Approach**:
1. First, we will run a loop that will continue until **mid <= high**.
2. There can be three different values of mid pointer i.e. arr[mid]
    1. **If arr[mid] == 0,** we will swap arr[low] and arr[mid] and will increment both low and mid. Now the subarray from index 0 to (low-1) only contains 0.
    2. **If arr[mid] == 1,** we will just increment the mid pointer and then the index (mid-1) will point to 1 as it should according to the rules.
    3. **If arr[mid] == 2,** we will swap arr[mid] and arr[high] and will decrement high. Now the subarray from index high+1 to (n-1) only contains 2.  
        In this step, we will do nothing to the mid-pointer as even after swapping, the subarray from mid to high(_after decrementing high_) might be unsorted. So, we will check the value of mid again in the next iteration.
3. Finally, our array should be sorted.

![Dutch Flag Algorithm Example Explanation](/assets/images/dnf-example.jpg)

```cpp
void sortColors(vector<int>& nums) {
	int low = 0, mid = 0, high = nums.size()-1;
	while(mid <= high) {
		if (nums[mid] == 2) {
			swap(nums[mid], nums[high]);
			high--;
		}
		else if (nums[mid] == 0){
			swap(nums[mid], nums[low]);
			mid++;
			low++;
		}
		else mid++;
	}
}

```
