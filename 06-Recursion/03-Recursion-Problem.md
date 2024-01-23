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
