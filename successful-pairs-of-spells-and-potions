https://leetcode.com/problems/successful-pairs-of-spells-and-potions/description/

# Intuition
1. brute force -> success but time limit exceeds
2. binary search -> if potions are sorted, then only find first match that satisfies `spells[i] * potions[j] >= succeess`

# Approach
1. sort potions array
2. anyway we need to iterate for spells once
3. for each loop, do binary search for searching the said condition 
4. if found, then save the count

# Complexity
- Time complexity:
1. sort potions array: O(mlogm)
2. for loop with binary search: O(n * logm)
total = 1+2 = O((n+m)logm)
wort case: O(2*10^5 * log10^5)

- Space complexity:
given: spells n, potions m
result n, Arrays.sort logm
-> result array is the main contributor to memory usage. So O(n)

# Code
```java []
class Solution {
    public int[] successfulPairs(int[] spells, int[] potions, long success) {
        int[] result = new int[spells.length];

        Arrays.sort(potions);

        for (int i = 0; i < spells.length; i++) {
            int start = 0, end = potions.length - 1;
            int count = 0;
            while (start <= end) {
                int middle = (start + end) / 2;
                long product = (long) spells[i] * potions[middle];
                if ( product < success) {
                    start = middle + 1;
                } else {
                    end = middle - 1;
                }
            }
            result[i] = potions.length - start;
        }

        return result;
    }
}
```
