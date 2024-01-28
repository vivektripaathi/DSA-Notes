>[!Question] Count set bits of a number.

![Count Set Bits](/assets/images/count_set-question.png)

## Naive Solution

```cpp
int countSetBits(int n){
    int res = 0;
    while(n>0){
        res += res + (n&1);
        n/= 2;
    }
    return res;
}
```

##  Brian Kerningum's Algorithm

![Brian Kerningum's Algorithm](../assets/images/Brian-Kerningum's-Algorithm.png)

```cpp
int countSetBits(int n){
	int res = 0;
	while(n>0){
		n = n & (n - 1);
		res += 1;
	}
	return res;
}
```
