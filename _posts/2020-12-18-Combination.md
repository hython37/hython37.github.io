---
title:  "Combination"
excerpt: "조합"

categories: 
  - Algorithm
tags:
  - study
toc: true
toc_label: "Algorithm of Python"
---

## 조합
### itertools
```python
from itertools import combinations

items= [1, 2, 3, 4]

array = []
for i in list(combinations(items, 2)):
    array.append(i)
print(array)
```

### 재귀
```python
def combi(depth, pre):
    if depth == r:
        print(result)
    else:
        for i in range(pre, len(items)):
            result[depth] = items[i]
            combi(depth+1, i+1)


items = [1, 2, 3, 4]
r = 2
result = [0] * r

combi(0, 0)
```

### DFS
```python
def combi(items, n):
    ans = []
    for i in range(len(items)):
        if n == 1:
            ans.append([items[i]])
        elif n > 1:
            for next in combi(items[i+1:], n-1):
                ans.append([items[i]]+next)
    return ans


items = [1, 2, 3, 4]
print(combi(items, 2))
```

