# Boyer-Moore Majority Voting Algorithm
The **Boyer-Moore voting** algorithm is one of the popular optimal algorithms which is used to find the majority element among the given elements that have more than N/ 2 occurrences.
## Approach:
1. Initialize 2 variables:  
    **Count** –  for tracking the count of element  
    **Element** – for which element we are counting
2. Traverse through the given array.
    1. If **Count** is 0 then store the current element of the array as **Element**.
    2. If the current element and **Element** are the same increase the **Count** by 1.
    3. If they are different decrease the **Count** by 1.
3. The integer present in **Element** should be the result we are expecting

>[! Question] Given an array of **N integers**, write a program to return an element that occurs more than **N/2** times in the given array. You may consider that such an element always exists in the array. Solve problem at [LeetCode](https://leetcode.com/problems/majority-element/description/) or [CodingNinja](https://www.codingninjas.com/studio/problems/majority-element_6783241?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)
>
> Test Case
> > Input: [2,2,1,1,1,2,2]
> > Output: 2

```cpp
int majorityElement(vector<int>& nums) {
	int count = 0, element;
	for(int i = 0; i < nums.size(); i++) {
		if(count == 0){
			element = nums[i];
			count = 1;
		}
		else if(nums[i] != element) count--;
		else count++;
	}
	return element;
}

```

![Boyer-Moore Majority Voting Algorithm](assets/images/moore-algo.jpeg)

- If the question states that the array must contain a majority element, the stored element will be that one but if the question does not state so, then we need to check if the stored element is the majority element or not.
