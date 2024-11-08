# Array

### Two Sum
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

#### Appproach 1
 2 loop chalye the first mein i se chalya tha nums ki length tak,
 dusra loop i+1 se chalya tha nums.lenght tak 
 usek baaad dono ko check kar liya tha target se 
 agar uske equal aa rahe the toh un index ki value return kara di thi

 ``` java
 class Solution {
    public int[] twoSum(int[] nums, int target) {
        for(int i=0;i<nums.length;i++){
            for(int j=i+1;j<nums.length;j++){
                if(nums[i]+nums[j]==target){
                    return new int []{i,j};
                }
            }
        }
        return new int[]{};
    }
}
 ```

 #### Approach 2

 by using hashpmap,
 phele hashmap banaya then loop chala ke index ki value nikal li ,
 then fir loop chalya usmein ek variable m add kiya complement naam ka us mein tagret m se nums ka index minus kar diya
 fir ek condition m check kar liya ki value same index ki na ho 
 or fir wo return kar di

 ```java
 class Solution {
    public int[] twoSum(int[] nums, int target) {
       Map<Integer, Integer>map = new HashMap<>();
       for (int i=0;i<nums.length;i++){
        map.put(nums[i],i);
       }
       for(int i=0;i<nums.length;i++){
        int comp= target-nums[i];
        if(map.containsKey(comp) && map.get(comp) !=i){
            return new int [] {map.get(comp),i};
        }
       }
       return new int []{};
    }
}
 ```