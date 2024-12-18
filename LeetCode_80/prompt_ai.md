## use chatgpt

# promt
```幫我寫一個函式。 public int removeDuplicates(int[] nums) { return k; }    nums是一個經排列的non-decreasing陣列    removeDuplicates要讓nums裡的前k個所有數字都最多重複兩次```
```chatgpt```
```
public int removeDuplicates(int[] nums) {
    if (nums == null || nums.length == 0) {
        return 0;
    }

    int k = 1; // 設定k從1開始，因為第一個數字一定保留
    int count = 1; // 用來計算當前數字的重複次數

    for (int i = 1; i < nums.length; i++) {
        if (nums[i] == nums[i - 1]) {
            count++; // 如果當前數字與前一個數字相同，則增加count
        } else {
            count = 1; // 否則重置count為1
        }

        // 如果當前數字的重複次數小於等於2，則保留該數字
        if (count <= 2) {
            nums[k] = nums[i]; // 將當前數字放在k位置
            k++; // 移動k指標
        }
    }

    return k; // 返回新陣列的長度
}

```
```chatgpt 4o```
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
