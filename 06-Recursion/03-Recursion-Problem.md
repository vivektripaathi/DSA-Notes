# Problems on Recursion

>[!Question] Print numbers from 1 to n
>
>Test Case
>>Input : 5
>>Output : 1 2 3 4 5

>[!Question] Print numbers from n to 1
>
>Test Case
>>Input : 5
>>Output : 5 4 3 2 1

>[!Question] Natural number sum
>
>Test Case
>>Input : 5
>>Output : 15

>[!Question] Reverse and array
>
>Test Case 1
>>Input: [1, 2, 3 , 4 , 5]
>>Output: [5, 4 ,3 ,2, 1]
>
>Test Case 2
>>Input: [1]
>>Output: [1]

>[!Question] Palindrome string check
>
>Test Case 1
>>Input: abbcbba
>>Output Yes
>
>Test Case 2
>>Input: abba
>>Output: Yes
>
>Test Case 3
>>Input: dsa
>>Output: No

>[!Question] Sum of Digits
>
>Test Case
>>Input: 253
>>Output: 10

>[!Question] Nth fibonacci number
>
>Test Case 1
>>Input: 5
>>Output: 5
>
>Test Case 2
>>Input: 6
>>Output: 8

>[!Question] Rope Cutting Problem: Cut the rope n in maximum number of pieces such that every piece is of length either of a or b or c
>Test Case 1
>>Input: n  = 5, a = 2, b = 5, c = 1
>>Output: 5
>
>Test Case 2
>>Input: n = 23, a = 12, b = 9, c = 11
>>Output: 2
>
>Test Case 3
>>Input: n = 5, a = 4, b = 2, c =6
>>Output: -1
>
> Interesting Test Case
>> Input: n = 9, a = 2, b = 2, c = 2
```cpp
int maxPieces(int n, int a, int b, int c){
	if(n == 0) return 0;
	if(n < -1) return -1;
	int res = max(max(maxPieces(n-a, a, b, c),maxPieces(n-b, a, b, c)),maxPieces(n-c, a, b, c));
	if(res == -1) return -1;
	return res + 1;
}

```
- Example Explanation

![Rope Cutting Explanation](/assets/images/ropeCutting.png)

>[!Question] Generate Subsets
>Test Case 1
>>Input: "AB"
>>Output: {}, {A}, {B}, {AB}
>
>Test Case 2
>>Input: "ABC"
>>Output: {}, {A}, {B}, {C}, {AB}, {BC}, {AC}, {ABC}
```cpp
void printSubsets(string set, string current = "", int i = 0){
	if(i == set.length()){
	cout<<"{"<<current<<"} ";
	return;
	}
	printSubsets(set, current, i + 1);
	printSubsets(set, current+set[i], i + 1);
}

```
- Example Explanation

![Generate Subset Explanation Recursion Tree](/assets/images/subset.png)

>[!Question] Tower Of Hanoi
>Test Case 1
>>Input: n = 1
>>Output:
>>move 1 from A to C
>
>Test Case 2
>>Input: 3
>>Output: 
>>move 1 from A to C
move 2 from A to B
move 1 from C to B
move 3 from A to C
move 1 from B to A
move 2 from B to C
move 1 from A to C
```cpp
void towerOfHanoi(int n, char a = 'A', char b = 'B', char c = 'C'){
	if(n==1){
		cout<<"move 1 from "<<a<<" to "<<c<<endl;
		return;
	}
	towerOfHanoi(n-1, a, c, b);
	cout<<"move "<<n<<" from "<<a<<" to "<<c<<endl;
	towerOfHanoi(n-1, b, a, c);
}

```
- Example Explanation

![Tower of Hanoi Explanation1](/assets/images/toh1.jpeg)

![Tower of Hanoi Explanation1](/assets/images/toh2.jpeg)

>[!Question] Josephus Problem
>Test Case 1
>>Input: n = 2, k = 3
>>Output: 1
>
>Test Case 2
>>Input: n = 5, k = 3
>>Output: 3
```cpp
int jos(int n, int k)
{
	if (n == 1)
		return 0;
	else
		return (jos(n - 1, k) + k) % n;
}

```
- Example Explanation

![Josephus Problem Explanation](/assets/images/josephus.jpeg)

>[!Question] Subset Sum Problem
>Test Case 1
>>Input: [10, 5, 2, 3, 6], sum = 8
>>Output: 2
>
>Test Case 2
>>Input: [1, 2, 3], sum = 4
>>Output: 1
>
>Test Case 3
>>Input: [10, 20, 15], sum = 37
>>Output: 0
>
>Test Case 3
>>Input: [10, 20, 15], sum = 0
>>Output: 1
```cpp
int countSubSets(int arr[], int n, int sum) {
	if (n == 0)
		return (sum == 0) ? 1 : 0;
	return countSubSets(arr, n - 1, sum) + countSubSets(arr, n - 1, sum - arr[n - 1]);
}

```
- Example Explanation

![Subset Sum Recursion Tree Example Explanation](/assets/images/subsetSum.jpeg)

>[!Question] Print all permutations of a given string.
>Test Case 1
>>Input: ABC
>>Output: ABC ACB BAC BCA CBA CAB
>
>Test Case 2
>>Input: ABCD
>>Output: ABCD ABDC ACBD ACDB ADCB ADBC BACD BADC BCAD BCDA BDCA BDAC CBAD CBDA CABD CADB CDAB CDBA DBCA DBAC DCBA DCAB DACB DABC
```cpp
void permute(string s, int i = 0) {
	if (i == s.length() - 1) {
		cout << s << " ";
		return;
	}
	for (int j = i; j < s.length(); j++) {
		swap(s[i], s[j]);
		permute(s, i + 1);
		swap(s[i], s[j]);
	}
}

```
- Example Explanation

![Permutation Explanation Recursion Tree](/assets/images/permute1.png)

![Permutation Explanation Recursion Tree](/assets/images/permute2.png)
