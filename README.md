# Leetcode----1749
Maximum Absolute Sum of Any Subarray
//code in java
class Solution {
    public int maxAbsoluteSum(int[] nums) {
        int maxSum = 0, minSum = 0, currMax = 0, currMin = 0;
        
        for (int num : nums) {
            currMax = Math.max(0, currMax + num);  // Kadane's for max subarray
            maxSum = Math.max(maxSum, currMax);

            currMin = Math.min(0, currMin + num);  // Kadane's for min subarray
            minSum = Math.min(minSum, currMin);
        }
        
        return Math.max(maxSum, Math.abs(minSum));
    }
}
