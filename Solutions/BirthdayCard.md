```
import java.util.*;

public class BirthdayCard {
    public static void main(String[] args) {
        //int[] nums= new int[]{1, 3, 4};
        //int d = 7;
        int[] nums = new int[]{4,6,12,8};
        int d = 14;
        Arrays.sort(nums);
        List<Integer> res = new ArrayList<>();
        HashSet<Integer> set = new HashSet<>();
        for(int i : nums){
            set.add(i);
        }

        int max = nums[nums.length - 1];
        for(int i = 1; i <= d; ++i){
            if(i <= d && !res.contains(i) && !set.contains(i)){
                res.add(i);
                d = d - i;
            }
        }

        System.out.println(res);
    }
}
```
