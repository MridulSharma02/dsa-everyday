<div align="center">

# 💻 933. Number of Recent Calls

*Pushed on October 28, 2026 · Problem #143 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 💻 Design   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 79.2%              |
| **Language**         | 🔠 Python         |

**Tags:** `Design` `Queue` `Data Stream`

---

## 🧩 Problem Description

You have a `RecentCounter` class which counts the number of recent requests within a certain time frame.


Implement the `RecentCounter` class:



	- `RecentCounter()` Initializes the counter with zero recent requests.
	- `int ping(int t)` Adds a new request at time `t`, where `t` represents some time in milliseconds, and returns the number of requests that have happened in the inclusive range `[t - 3000, t]`, that is, the new request plus every earlier request that is no more than `3000` milliseconds older.


It is **guaranteed** that every call to `ping` uses a strictly larger value of `t` than the previous call.


 

<strong class="example">Example 1:**



**Input**
[&quot;RecentCounter&quot;, &quot;ping&quot;, &quot;ping&quot;, &quot;ping&quot;, &quot;ping&quot;]
[[], [1], [100], [3001], [3002]]
**Output**
[null, 1, 2, 3, 3]

**Explanation**
RecentCounter recentCounter = new RecentCounter();
recentCounter.ping(1);     // requests = [<u>1</u>], range is [-2999,1], return 1
recentCounter.ping(100);   // requests = [<u>1</u>, <u>100</u>], range is [-2900,100], return 2
recentCounter.ping(3001);  // requests = [<u>1</u>, <u>100</u>, <u>3001</u>], range is [1,3001], return 3
recentCounter.ping(3002);  // requests = [1, <u>100</u>, <u>3001</u>, <u>3002</u>], range is [2,3002], return 3


 

**Constraints:**



	- `1 <= t <= 10^9`
	- Each test case will call `ping` with **strictly increasing** values of `t`.
	- At most `10^4` calls will be made to `ping`.

---

## 💻 My Solution

```python
from collections import deque

class RecentCounter(object):

    def __init__(self):
        self.q = deque()

    def ping(self, t):
        """
        :type t: int
        :rtype: int
        """
        self.q.append(t)

        while self.q[0] < t - 3000:
            self.q.popleft()

        return len(self.q)


# Your RecentCounter object will be instantiated and called as such:
# obj = RecentCounter()
# param_1 = obj.ping(t)

```

---

## 🧪 Sample Test Case

```
["RecentCounter","ping","ping","ping","ping"]
[[],[1],[100],[3001],[3002]]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Design** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying design to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
