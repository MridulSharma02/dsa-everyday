<div align="center">

# 🔤 649. Dota2 Senate

*Pushed on July 11, 2026 · Problem #34 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔤 String   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 50.2%              |
| **Language**         | 🔠 Python         |

**Tags:** `String` `Greedy` `Queue`

---

## 🧩 Problem Description

In the world of Dota2, there are two parties: the Radiant and the Dire.


The Dota2 senate consists of senators coming from two parties. Now the Senate wants to decide on a change in the Dota2 game. The voting for this change is a round-based procedure. In each round, each senator can exercise **one** of the two rights:



	- **Ban one senator&#39;s right:** A senator can make another senator lose all his rights in this and all the following rounds.
	- **Announce the victory:** If this senator found the senators who still have rights to vote are all from the same party, he can announce the victory and decide on the change in the game.


Given a string `senate` representing each senator&#39;s party belonging. The character `&#39;R&#39;` and `&#39;D&#39;` represent the Radiant party and the Dire party. Then if there are `n` senators, the size of the given string will be `n`.


The round-based procedure starts from the first senator to the last senator in the given order. This procedure will last until the end of voting. All the senators who have lost their rights will be skipped during the procedure.


Suppose every senator is smart enough and will play the best strategy for his own party. Predict which party will finally announce the victory and change the Dota2 game. The output should be `&quot;Radiant&quot;` or `&quot;Dire&quot;`.


 

<strong class="example">Example 1:**



**Input:** senate = &quot;RD&quot;
**Output:** &quot;Radiant&quot;
**Explanation:** 
The first senator comes from Radiant and he can just ban the next senator&#39;s right in round 1. 
And the second senator can&#39;t exercise any rights anymore since his right has been banned. 
And in round 2, the first senator can just announce the victory since he is the only guy in the senate who can vote.


<strong class="example">Example 2:**



**Input:** senate = &quot;RDD&quot;
**Output:** &quot;Dire&quot;
**Explanation:** 
The first senator comes from Radiant and he can just ban the next senator&#39;s right in round 1. 
And the second senator can&#39;t exercise any rights anymore since his right has been banned. 
And the third senator comes from Dire and he can ban the first senator&#39;s right in round 1. 
And in round 2, the third senator can just announce the victory since he is the only guy in the senate who can vote.


 

**Constraints:**



	- `n == senate.length`
	- `1 <= n <= 10^4`
	- `senate[i]` is either `&#39;R&#39;` or `&#39;D&#39;`.

---

## 💻 My Solution

```python
from collections import deque

class Solution(object):
    def predictPartyVictory(self, senate):
        """
        :type senate: str
        :rtype: str
        """
        n = len(senate)
        r = deque()
        d = deque()

        for i, ch in enumerate(senate):
            if ch == 'R':
                r.append(i)
            else:
                d.append(i)

        while r and d:
            ri = r.popleft()
            di = d.popleft()

            if ri < di:
                r.append(ri + n)
            else:
                d.append(di + n)

        return "Radiant" if r else "Dire"
        

```

---

## 🧪 Sample Test Case

```
"RD"
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **String** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying string to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
