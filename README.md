# 💧 LeetCode 11: Container With Most Water (C++)

An efficient solution to the 'Container With Most Water' problem using a greedy two-pointer approach to maximize the area.

## 📖 Problem Description
You are given an integer array `height` of length `n`. There are `n` vertical lines drawn such that the two endpoints of the `i-th` line are `(i, 0)` and `(i, height[i])`. Find two lines that, together with the x-axis, form a container, such that the container contains the most water.

### Example
- **Input:** `height = [1,8,6,2,5,4,8,3,7]`
- **Output:** `49`
- **Explanation:** The lines of height 8 and 7 create a container with a width of 7 and height of 7. Area = `7 * 7 = 49`.

## 🛠️ Technical Approach
This solution uses the **Two-Pointer** strategy:
1. **Initialization:** Start with one pointer at the beginning (`left = 0`) and one at the end (`right = n - 1`).
2. **Area Calculation:** Calculate the volume based on the shorter of the two lines: `Area = min(height[left], height[right]) * (right - left)`.
3. **Greedy Movement:** To find a potentially larger area, we must find a taller line. Since the width only decreases as we move pointers closer, we move the pointer that points to the **shorter** line.
4. **Iterate:** Repeat until the pointers meet, keeping track of the `maxWater` found.

## 📊 Complexity Analysis
- **Time Complexity:** $O(n)$ — We scan the array only once as the pointers move toward each other.
- **Space Complexity:** $O(1)$ — No additional data structures are required; only a few variables to store pointers and current area.

## 💡 Key Edge Cases Handled
- Arrays with only two elements (the minimum required).
- Arrays where heights are in strictly increasing or decreasing order.
- Containers where the two lines have equal heights.
