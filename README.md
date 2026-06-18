# crt-phase 2
day 1
two sum - leetcode 1
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> map;
        for(int i= 0;i<nums.size(); i++){
            int compliment = target - nums[i];

            if(map.find(compliment)!= map.end()){
                return {map[compliment], i};
            }
            map[nums[i]] = i;
        }
        return{-1,-1};
    
    }
};

sort colors - leetcode 75
class Solution {
public:
    void sortColors(vector<int>& nums) {
        int count0 = 0;
        int count1 = 0;
        int count2 = 0;

        for(int i =0; i< nums.size(); i++){
            if(nums[i] == 0){
                count0++;
            }else if(nums[i] == 1){
                count1++;
            }else {
                count2++;
            }
        }
        for(int i = 0; i<nums.size(); i++){
            if(i < count0){
                nums[i] = 0;
            }else if(i < count0 + count1){
                nums[i]=1;
            }else{
                nums[i]=2;
            }
        }

    }
};

max. subarray - leetcode 53

class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int maxSum = INT_MIN;
        int sum = 0;
        for(int i=0; i< nums.size(); i++){
            sum = sum +nums[i];
            
            if(sum> maxSum){
                maxSum = sum;
            }
            if(sum < 0){
                sum = 0;
            }
        }
        return maxSum;
    }
};


