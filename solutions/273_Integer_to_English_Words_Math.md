<div align="center">

# 🔢 273. Integer to English Words

*Pushed on August 24, 2026 · Problem #78 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🔴 Hard |
| **Topic**            | 🔢 Math   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 35.2%              |
| **Language**         | 🔠 C++         |

**Tags:** `Math` `String` `Recursion`

---

## 🧩 Problem Description

Convert a non-negative integer `num` to its English words representation.


 

<strong class="example">Example 1:**



**Input:** num = 123
**Output:** &quot;One Hundred Twenty Three&quot;


<strong class="example">Example 2:**



**Input:** num = 12345
**Output:** &quot;Twelve Thousand Three Hundred Forty Five&quot;


<strong class="example">Example 3:**



**Input:** num = 1234567
**Output:** &quot;One Million Two Hundred Thirty Four Thousand Five Hundred Sixty Seven&quot;


 

**Constraints:**



	- `0 <= num <= 2^31 - 1`

---

## 🪄 Hints
> 💡 Did you see a pattern in dividing the number into chunk of words? For example, 123 and 123000.
> 💡 Group the number by thousands (3 digits). You can write a helper function that takes a number less than 1000 and convert just that chunk to words.

## 💻 My Solution

```cpp
class Solution {
public:
    vector<string> below20={
        "","One","Two","Three","Four","Five","Six","Seven","Eight","Nine",
        "Ten","Eleven","Twelve","Thirteen","Fourteen","Fifteen",
        "Sixteen","Seventeen","Eighteen","Nineteen"
    };

    vector<string> tens={
        "","","Twenty","Thirty","Forty","Fifty",
        "Sixty","Seventy","Eighty","Ninety"
    };

    string solve(int num){
        if(num==0)
            return "";
        if(num<20)
            return below20[num]+" ";
        if(num<100)
            return tens[num/10]+" "+solve(num%10);
        if(num<1000)
            return below20[num/100]+" Hundred "+solve(num%100);
        if(num<1000000)
            return solve(num/1000)+"Thousand "+solve(num%1000);
        if(num<1000000000)
            return solve(num/1000000)+"Million "+solve(num%1000000);
        return solve(num/1000000000)+"Billion "+solve(num%1000000000);
    }
    string numberToWords(int num) {
        if(num==0)
            return "Zero";
            
        string ans=solve(num);
        ans.pop_back();

        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
123
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Math** techniques.
> The key insight is to leverage `O(√n)` time complexity
> by applying math to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
