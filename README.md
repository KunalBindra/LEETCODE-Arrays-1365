# LEETCODE-Arrays-1365

---

# ✅ **Given Code**

```java
class Solution {
    public int[] smallerNumbersThanCurrent(int[] nums) {
        int n = nums.length;        
        int[] ans = new int[n];
        for(int i = 0; i < n; i++) {
            int count = 0;
            int j = 0;
            while(j < n) {
                if(nums[i] > nums[j]) count++;
                j++;
            }
            ans[i] = count;
        }
        return ans;
    }
}
```

---

# 💡 **What this code does**

For each number in `nums`, it counts how many numbers in the array are **strictly smaller** than it.

---

# 🧪 **Let’s dry run with an example**

Let’s take:

```
nums = [8, 1, 2, 2, 3]
```

`n = 5`
`ans = [0,0,0,0,0]`

---

## 🔁 **i = 0 → nums[0] = 8**

`count = 0`

| j | nums[j] | Compare (8 > nums[j]?) | count |
| - | ------- | ---------------------- | ----- |
| 0 | 8       | No                     | 0     |
| 1 | 1       | Yes                    | 1     |
| 2 | 2       | Yes                    | 2     |
| 3 | 2       | Yes                    | 3     |
| 4 | 3       | Yes                    | 4     |

`ans[0] = 4`

---

## 🔁 **i = 1 → nums[1] = 1**

`count = 0`

| j | nums[j] | Compare (1 > nums[j]?) | count |
| - | ------- | ---------------------- | ----- |
| 0 | 8       | No                     | 0     |
| 1 | 1       | No                     | 0     |
| 2 | 2       | No                     | 0     |
| 3 | 2       | No                     | 0     |
| 4 | 3       | No                     | 0     |

`ans[1] = 0`

---

## 🔁 **i = 2 → nums[2] = 2**

`count = 0`

| j | nums[j] | Compare (2 > nums[j]?) | count |
| - | ------- | ---------------------- | ----- |
| 0 | 8       | No                     | 0     |
| 1 | 1       | Yes                    | 1     |
| 2 | 2       | No                     | 1     |
| 3 | 2       | No                     | 1     |
| 4 | 3       | No                     | 1     |

`ans[2] = 1`

---

## 🔁 **i = 3 → nums[3] = 2**

Same as previous

`ans[3] = 1`

---

## 🔁 **i = 4 → nums[4] = 3**

`count = 0`

| j | nums[j] | Compare (3 > nums[j]?) | count |
| - | ------- | ---------------------- | ----- |
| 0 | 8       | No                     | 0     |
| 1 | 1       | Yes                    | 1     |
| 2 | 2       | Yes                    | 2     |
| 3 | 2       | Yes                    | 3     |
| 4 | 3       | No                     | 3     |

`ans[4] = 3`

---

# 🎯 **Final Output**

```
ans = [4, 0, 1, 1, 3]
```

---
