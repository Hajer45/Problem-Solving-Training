<picture><img align="right" width="80" src="/logos/hackerrank.png"></img></picture>

# HackerRank OJ - Algorithms Basics <br> Sorting `15 problems`

## Big Sorting
Problem Link: https://hackerrank.com/challenges/big-sorting/problem

<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/python.png"></img></picture>
<details>
    <summary>Python Solution</summary>

```python
def bigSorting(unsorted):
    return sorted(unsorted, key=lambda x: (len(x), x))
```

</details>
<br>
<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/cpp.png"></img></picture>
<details>
    <summary>CPP Solution</summary>

```cpp
vector<string> bigSorting(vector<string> unsorted) {
    auto comp = [](const string &x, const string &y) {
        return make_pair(size(x), x) < make_pair(size(y), y);
    };
    sort(unsorted.begin(), unsorted.end(), comp);
    return unsorted;
}
```

</details>
<br>

## Intro to Tutorial Challenges
Problem Link: https://hackerrank.com/challenges/tutorial-intro/problem

<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/python.png"></img></picture>
<details>
    <summary>Python Solution</summary>

```python
def introTutorial(V, arr):
    for i in range(len(arr)):
        if arr[i] == V:
            return i
    return -1
```

</details>
<br>
<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/cpp.png"></img></picture>
<details>
    <summary>CPP Solution</summary>

```cpp
int introTutorial(int V, vector<int> &arr) {
    for (int i = 0; i < size(arr); i++) {
        if (arr[i] == V)
            return i;
    }
    return -1;
}
```

</details>
<br>

## Insertion Sort - Part 1
Problem Link: https://hackerrank.com/challenges/insertionsort1/problem

<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/python.png"></img></picture>
<details>
    <summary>Python Solution</summary>

```python
def insertionSort1(n, arr):
    temp = arr[-1]
    for i in range(n-2, -1, -1):
        if arr[i] > temp:
            arr[i+1] = arr[i]
            print(*arr)
        else:
            arr[i+1] = temp
            print(*arr)
            return
    arr[0] = temp
    print(*arr)
```

</details>
<br>
<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/cpp.png"></img></picture>
<details>
    <summary>CPP Solution</summary>

```cpp
void insertionSort1(int n, vector<int> &arr) {
    int temp = arr[size(arr)-1];
    auto print_arr = [](vector<int> &arr) {
        for (int &i : arr)
            cout << i << ' ';
        cout << '\n';
    };
    for (int i=n-2; i>-1; i--) {
        if (arr[i] > temp) {
            arr[i+1] = arr[i];
            print_arr(arr);
        }
        else {
            arr[i+1] = temp;
            print_arr(arr);
            return;
        }
    }
    arr[0] = temp;
    print_arr(arr);
}
```

</details>
<br>

## Insertion Sort - Part 2
Problem Link: https://hackerrank.com/challenges/insertionsort2/problem

<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/python.png"></img></picture>
<details>
    <summary>Python Solution</summary>

```python
def insertionSort2(n, arr):
    for i in range(1, n):
        temp = arr[i]
        j = i
        while j > 0 and temp < arr[j-1]:
            arr[j] = arr[j-1]
            j -= 1
        arr[j] = temp
        print(*arr)
```

</details>
<br>
<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/cpp.png"></img></picture>
<details>
    <summary>CPP Solution</summary>

```cpp
void insertionSort2(int n, vector<int> &arr) {
    auto print_arr = [](vector<int> &arr) {
        for (int &i : arr)
            cout << i << ' ';
        cout << '\n';
    };
    for (int i=1; i<n; i++) {
        int temp = arr[i];
        int j = i;
        while (j > 0 and temp < arr[j-1]) {
            arr[j] = arr[j-1];
            j --;
        }
        arr[j] = temp;
        print_arr(arr);
    }
}
```

</details>
<br>

## Correctness and the Loop Invariant
Problem Link: https://hackerrank.com/challenges/correctness-invariant/problem

<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/python.png"></img></picture>
<details>
    <summary>Python Solution</summary>

```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        j = i
        while j > 0 and arr[j] < arr[j-1]:
            arr[j], arr[j-1] = arr[j-1], arr[j]
            j -= 1
```

</details>
<br>
<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/cpp.png"></img></picture>
<details>
    <summary>CPP Solution</summary>

```cpp
void insertionSort(int N, int arr[]) {
    for (int i = 1; i < N; i++) {
        int j = i;
        while (j > 0 and arr[j] < arr[j-1]) {
            int temp = arr[j-1];
            arr[j-1] = arr[j];
            arr[j] = temp;
            j --;
        }
    }
}
```

</details>
<br>

## Running Time of Algorithms
Problem Link: https://hackerrank.com/challenges/runningtime/problem

<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/python.png"></img></picture>
<details>
    <summary>Python Solution</summary>

```python
def runningTime(arr):
    res = 0
    for i in range(1, len(arr)):
        value = arr[i]
        j = i - 1
        while j >= 0 and value < arr[j]:
            arr[j+1] = arr[j]
            j -= 1
            res += 1
        arr[j+1] = value
    return res
```

</details>
<br>
<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/cpp.png"></img></picture>
<details>
    <summary>CPP Solution</summary>

```cpp
int runningTime(vector<int> &arr) {
    int res = 0;
    for (int i=1; i<size(arr); i++) {
        int value = arr[i];
        int j = i - 1;
        while (j >= 0 and value < arr[j]) {
            arr[j+1] = arr[j];
            j --;
            res ++;
        }
        arr[j+1] = value;
    }
    return res;
}
```

</details>
<br>

## Quicksort 1 - Partition
Problem Link: https://hackerrank.com/challenges/quicksort1/problem

<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/python.png"></img></picture>
<details>
    <summary>Python Solution</summary>

```python
def quickSort(arr):
    left  = [i for i in arr if i < arr[0]]
    right = [i for i in arr if i > arr[0]]
    equal = [i for i in arr if i == arr[0]]
    return left + equal + right
```

</details>
<br>
<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/cpp.png"></img></picture>
<details>
    <summary>CPP Solution</summary>

```cpp
vector<int> quickSort(vector<int> &arr) {
    auto comp_lt = [](const int &x, const int &y) { return x < y; };
    auto comp_gt = [](const int &x, const int &y) { return x > y; };
    auto comp_eq = [](const int &x, const int &y) { return x == y; };

    auto select_fn = [](vector<int> &arr, function<bool(int, int)> fn, vector<int> &res) {
        for (int &i : arr)
            if (fn(i, arr[0]))
                res.push_back(i);
    };

    vector<int> res;
    select_fn(arr, comp_lt, res);
    select_fn(arr, comp_eq, res);
    select_fn(arr, comp_gt, res);
    return res;
}
```

</details>
<br>

## Counting Sort 1
Problem Link: https://hackerrank.com/challenges/countingsort1/problem

<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/python.png"></img></picture>
<details>
    <summary>Python Solution</summary>

```python
def countingSort(arr):
    counts = [0] * 100
    for i in arr:
        counts[i] += 1
    return counts
```

</details>
<br>
<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/cpp.png"></img></picture>
<details>
    <summary>CPP Solution</summary>

```cpp
vector<int> countingSort(vector<int> &arr) {
    vector<int> counts(100, 0);
    for (int &i : arr)
        counts[i] ++;
    return counts;
}
```

</details>
<br>

## Counting Sort 2
Problem Link: https://hackerrank.com/challenges/countingsort2/problem

<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/python.png"></img></picture>
<details>
    <summary>Python Solution</summary>

```python
def countingSort(arr):
    counts = [0] * 100
    for i in arr:
        counts[i] += 1
    res = []
    for i in range(100):
        while counts[i]:
            res.append(i)
            counts[i] -= 1
    return res
```

</details>
<br>
<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/cpp.png"></img></picture>
<details>
    <summary>CPP Solution</summary>

```cpp
vector<int> countingSort(vector<int> &arr) {
    vector<int> counts(100, 0);
    for (int &i : arr)
        counts[i] ++;
    vector<int> res;
    for (int i=0; i<100 ;i++) {
        while (counts[i]) {
            res.push_back(i);
            counts[i] --;
        }
    }
    return res;
}
```

</details>
<br>

## Closest Numbers
Problem Link: https://hackerrank.com/challenges/closest-numbers/problem

<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/python.png"></img></picture>
<details>
    <summary>Python Solution</summary>

```python
def closestNumbers(arr):
    res = []
    arr = sorted(arr)
    min_diff = 2e7
    for i in range(1, len(arr)):
        diff = abs(arr[i-1] - arr[i])
        if min_diff > diff:
            res = [arr[i-1], arr[i]]
            min_diff = diff
        elif diff == min_diff:
            res.extend([arr[i-1], arr[i]])
    return res
```

</details>
<br>
<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/cpp.png"></img></picture>
<details>
    <summary>CPP Solution</summary>

```cpp
vector<int> closestNumbers(vector<int> &arr) {
    vector<int> res;
    sort(arr.begin(), arr.end());
    int min_diff = 2e7;
    for (int i=1; i<size(arr); i++) {
        int diff = abs(arr[i-1] - arr[i]);
        if (min_diff > diff) {
            res = {arr[i-1], arr[i]};
            min_diff = diff;
        }
        else if (diff == min_diff) {
            auto temp = {arr[i-1], arr[i]};
            res.insert(res.end(), temp.begin(), temp.end());
        }
    }
    return res;
}
```

</details>
<br>

## Find the Median
Problem Link: https://hackerrank.com/challenges/find-the-median/problem

<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/python.png"></img></picture>
<details>
    <summary>Python Solution</summary>

```python
def findMedian(arr):
    arr = sorted(arr)
    return arr[len(arr)//2]
```

</details>
<br>
<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/cpp.png"></img></picture>
<details>
    <summary>CPP Solution</summary>

```cpp
int findMedian(vector<int> &arr) {
    sort(arr.begin(), arr.end());
    return arr[size(arr)/2];
}
```

</details>
<br>

## The Full Counting Sort
Problem Link: https://hackerrank.com/challenges/countingsort4/problem

<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/python.png"></img></picture>
<details>
    <summary>Python Solution</summary>

```python
#TODO
```

</details>
<br>
<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/cpp.png"></img></picture>
<details>
    <summary>CPP Solution</summary>

```cpp
//TODO
```

</details>
<br>

## Fraudulent Activity Notifications
Problem Link: https://hackerrank.com/challenges/fraudulent-activity-notifications/problem

<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/python.png"></img></picture>
<details>
    <summary>Python Solution</summary>

```python
#TODO
```

</details>
<br>
<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/cpp.png"></img></picture>
<details>
    <summary>CPP Solution</summary>

```cpp
//TODO
```

</details>
<br>

## Lily's Homework
Problem Link: https://hackerrank.com/challenges/lilys-homework/problem

<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/python.png"></img></picture>
<details>
    <summary>Python Solution</summary>

```python
#TODO
```

</details>
<br>
<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/cpp.png"></img></picture>
<details>
    <summary>CPP Solution</summary>

```cpp
//TODO
```

</details>
<br>

## Insertion Sort Advanced Analysis
Problem Link: https://hackerrank.com/challenges/insertion-sort/problem

<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/python.png"></img></picture>
<details>
    <summary>Python Solution</summary>

```python
#TODO
```

</details>
<br>
<picture><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/master/repos-logos/cpp.png"></img></picture>
<details>
    <summary>CPP Solution</summary>

```cpp
//TODO
```

</details>
<br>
