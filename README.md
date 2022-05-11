# class-Solution-public-vector-int-targetIndices-vector-int-nums-int-target-sort
find target indices after sorting the array 
class Solution {
public:
    vector<int> targetIndices(vector<int>& nums, int target) {
        sort(nums.begin(), nums.end());
        vector<int> ans;
        auto lb = lower_bound(nums.begin(), nums.end(), target);
        auto ub = upper_bound(nums.begin(), nums.end(), target);
        if(ub != lb){
            ans.push_back(lb - nums.begin());
            ans.push_back(ub - nums.begin() - 1);
        }else{
            ans.push_back(lb - nums.begin());
        }
        
        return ans;
    }
};
