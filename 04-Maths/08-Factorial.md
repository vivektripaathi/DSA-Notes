```cpp
int multiply(int x, vector<int> &fact, int &fact_size){
    int carry = 0;
    for(int i = 0; i < fact_size; i++){
        int product = fact[i] * x + carry;
        fact[i] = product % 10;
        carry = product / 10;
    }
    while(carry){
        fact.push_back(carry % 10);
        carry /= 10;
        fact_size++;
    }
    return fact_size;
}

vector<int> factorial(int number){
    vector<int> fact;
    fact.push_back(1);
    int fact_size = 1;
    for(int i = 2; i <= number; i++){
        fact_size = multiply(i, fact, fact_size);
    }
    return fact;
}
```