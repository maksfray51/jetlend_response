# Here you can find the answer to the task specified in the response to the Python Backend position at JetLend

**Task:**
Given: a list of dict objects of the form {"key": "value"}, for example [{"key1": "value1"}, {"k1": "v1", "k2": "v2", "k3": "v3"}, {}, {}, {"key1": "value1"}, {"key1": "value1"}, {"key2": "value2"}].

Write a function that removes duplicates from this list. For the example above, the return value can be [{"key1": "value1"}, {"k1": "v1", "k2": "v2", "k3": "v3"}, {}, {"key2": "value2"}].

**Requirements**
Prerequisite: the function must not have complexity O(n^2).


**Solution**

here you can find a solution that is hidden under the first_iteration function

```Python
def first_iteration():
    json_data = [
        {"key1": "value1"}, 
        {"k1": "v1", "k2": "v2", "k3": "v3"}, 
        {}, 
        {}, 
        {"key1": "value1"}, 
        {"key1": "value1"}, 
        {"key2": "value2"}
        ]
    
    temp = []
    [temp.append(item) for item in json_data if item not in temp]
    return temp
```

We want to see how many seconds did the script work

```Python
%timeit first_iteration()
```

We can see the result as 1.59 µs ± 307 ns per loop (mean ± std. dev. of 7 runs, 1,000,000 loops each). 1.59 microseconds. 
The algorithm complexity is O(n)