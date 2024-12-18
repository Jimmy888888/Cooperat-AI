## step0.<br>
## Find the needed items and the data format:<br>
1.each unique element appears at most twice, and return the length of ```nums``` ```k```<br>
2.limited space complexity O(1)<br>
3.the given array ```nums``` sorted in non-decreasing order<br>
## step1.<br>
## Split the logics of the solution:<br>
```class Solution {
    public int removeDuplicates(int[] nums) {
        
        int curNum = nums[0], dupCount = 0;
        int pK = 0, pAll = 0;
        while (pAll < nums.length){

            // count duplicate
            if(nums[pAll] == curNum){
                dupCount++;
            }else{
                curNum = nums[pAll];
                dupCount = 1;
            }

            // replace duplicates && move
            if(dupCount >= 3){
                // [1,1,1,1,1,1,3,3,3,4,5,5,5] --> [1,1,3,1,1,1,3,3,4,5,5,5] --> [1,1,3,3,4,5,5,-,-,-,-,-]
                pAll++;

            }else{
                nums[pK] = nums[pAll];
                pK++;
                pAll++;
            }

        }

        return pK++;
    }
} ```
