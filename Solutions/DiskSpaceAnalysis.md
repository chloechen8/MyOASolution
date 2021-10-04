```
public class DiskSpaceAnalysis {
    public static void main(String[] args) {
        //sliding window
        int x = 2;
        int[] space = new int[]{8,2,4,6};
        int max = 0;

        for(int i = 0; i <= space.length - x; i++){
            int min = space[i];
            for(int j = i; j < x; j++){
                if(space[j] < min)
                    min = space[j];
            }

            if(min > max)
                max = min;
        }

        System.out.println(max);
    }
}

```
