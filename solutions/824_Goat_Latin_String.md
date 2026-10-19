<div align="center">

# 🔤 824. Goat Latin

*Pushed on October 19, 2026 · Problem #134 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🔤 String   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 70.3%              |
| **Language**         | 🔠 C++         |

**Tags:** `String`

---

## 🧩 Problem Description

You are given a string `sentence` that consist of words separated by spaces. Each word consists of lowercase and uppercase letters only.


We would like to convert the sentence to &quot;Goat Latin&quot; (a made-up language similar to Pig Latin.) The rules of Goat Latin are as follows:



	- If a word begins with a vowel (`&#39;a&#39;`, `&#39;e&#39;`, `&#39;i&#39;`, `&#39;o&#39;`, or `&#39;u&#39;`), append `&quot;ma&quot;` to the end of the word.

	
		- For example, the word `&quot;apple&quot;` becomes `&quot;applema&quot;`.
	
	
	- If a word begins with a consonant (i.e., not a vowel), remove the first letter and append it to the end, then add `&quot;ma&quot;`.
	
		- For example, the word `&quot;goat&quot;` becomes `&quot;oatgma&quot;`.
	
	
	- Add one letter `&#39;a&#39;` to the end of each word per its word index in the sentence, starting with `1`.
	
		- For example, the first word gets `&quot;a&quot;` added to the end, the second word gets `&quot;aa&quot;` added to the end, and so on.
	
	


Return* the final sentence representing the conversion from sentence to Goat Latin*.


 

<strong class="example">Example 1:**

**Input:** sentence = "I speak Goat Latin"
**Output:** "Imaa peaksmaaa oatGmaaaa atinLmaaaaa"
<strong class="example">Example 2:**

**Input:** sentence = "The quick brown fox jumped over the lazy dog"
**Output:** "heTmaa uickqmaaa rownbmaaaa oxfmaaaaa umpedjmaaaaaa overmaaaaaaa hetmaaaaaaaa azylmaaaaaaaaa ogdmaaaaaaaaaa"

 

**Constraints:**



	- `1 <= sentence.length <= 150`
	- `sentence` consists of English letters and spaces.
	- `sentence` has no leading or trailing spaces.
	- All the words in `sentence` are separated by a single space.

---

## 💻 My Solution

```cpp
// Brute Force
// class Solution {
// public:
//     string toGoatLatin(string sentence) {
//         stringstream ss(sentence);
//         string word;
//         string ans;
//         int index=1;
//         while(ss>>word){
//             char c=word[0];
//             if(c=='a' || c=='e' || c=='i' || c=='o' || c=='u' ||
//                c=='A' || c=='E' || c=='I' || c=='O' || c=='U'){
//             }
//             else{
//                 word.erase(word.begin());
//                 word.push_back(c);
//             }
//             word += "ma";

//             for(int i=0;i<index;i++)
//                 word += 'a';
//             if(!ans.empty())
//                 ans += " ";

//             ans += word;
//             index++;
//         }

//         return ans;
//     }
// };

// Optimized
class Solution {
public:
    string toGoatLatin(string sentence) {
        stringstream ss(sentence);
        string word;
        string ans;
        int index=1;
        while(ss>>word){
            if(word[0]=='a' || word[0]=='e' || word[0]=='i' ||
               word[0]=='o' || word[0]=='u' ||
               word[0]=='A' || word[0]=='E' || word[0]=='I' ||
               word[0]=='O' || word[0]=='U'){
            }
            else{
                char first=word[0];
                word.erase(0,1);
                word += first;
            }
            word += "ma";
            for(int i=0;i<index;i++)
                word += 'a';
            if(!ans.empty())
                ans += " ";

            ans += word;
            index++;
        }

        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
"I speak Goat Latin"
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
