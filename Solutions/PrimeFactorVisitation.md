```
import java.util.HashMap;
import java.util.Map;

public class PrimeFactorVisitation {
    public static void main(String[] args) {
        int[] nums = new int[]{1 ,1, 0, 0, 1, 1, 0, 1, 1, 1};
        int[] numbers = new int[]{3,4,15};
        Map<Integer, Integer> map = new HashMap<>(); //记录出现的prime和次数
        for(int n : numbers){
            //find prime of i
            if(n % 2 == 0) map.put(2, map.getOrDefault(2, 0) + 1);
            while(n % 2 == 0){ //n为偶数
                n = n/2;
            }

            for(int i = 3; i <= Math.sqrt(n); i = i + 2){
                if(n % i == 0) map.put(i, map.getOrDefault(i, 0) + 1);
                while(n % i == 0){
                    n = n/i;
                }
            }

            if(n > 2){
                map.put(n, map.getOrDefault(n, 0) + 1);
            }

        }

        //traversal map, and change the nums according the map
        for(int key : map.keySet()){
            int value = map.get(key);
            while(value > 0){
                int tmp = key;
                while(tmp <= nums.length){
                    int origin = nums[tmp - 1];
                    if(origin == 1) nums[tmp - 1] = 0;
                    else nums[tmp - 1] = 1;
                    tmp += key;
                }
                --value;
            }
        }
        for(int i : nums){
            System.out.println(i);
        }

    }
}
```
