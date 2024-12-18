## use chatgpt
```
class Solution {
    public int removeDuplicates(int[] nums) {
        // 檢查特殊情況
        if (nums == null || nums.length == 0) {
            return 0;
        }

        // 設置指針，用於追蹤修改後陣列的有效長度
        int k = 0;

        for (int num : nums) {
            // 如果目前指針小於2，或者當前數字與nums[k-2]不同，則保留該數字
            if (k < 2 || num != nums[k - 2]) {
                nums[k] = num;
                k++;
            }
        }

        return k;
    }
}
```
