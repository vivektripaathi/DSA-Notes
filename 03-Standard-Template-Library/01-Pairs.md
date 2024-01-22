## Pair

```cpp
void examplePair(){
    pair<int, int> p = {1, 2};
    cout<<p.first<<" "<<p.second<<endl;
    pair<int, pair<float, string>> p1 = {1, {1.1, "Vivek"}};
    cout<<p1.first<<" "<<p1.second.first<<" "<<p1.second.second<<endl;
    pair<int, int> p2[] = {{1, 2}, {3, 4}, {5, 6}, {7, 8}};
    cout<<p2[1].second<<endl;
}
```
