TCS Ninja Coding Questions 
# 1. Sweet Seventeen
Given a maximum of four digit to the base 17(10 -> A, 11 -> B, 12 -> C, 16 -> G) as input, output its decimal value.

*Code* :
<code>
  Input : 23GF
  </code>
```
num = '23GF'
print(int(num,17))
```
```
Output: 10980
```

#2. A Sober Walk

- He first turns and travels 10 units of distance
- His second turn is upward for 20 units
- Third turn is to the left for 30 units
- Fourth turn is the downward for 40 units
- Fifth turn is to the right(again) for 50 units
- [x]  … And thus he travels, every time increasing the travel distance by 10 units.

<code>
  Constraints:
  2<=n<=1000

  Input: 3 
	
  Output : -20 20 
  </code>
```
import java.util.*;
import java.lang.*;

class Main {
	public static void main (String[] args) {
	    Scanner sc = new Scanner(System.in);
	    int n=sc.nextInt();
	    char c = 'R';
        int x = 0, y = 0;
        while(n>0){
        switch(c){
            case 'R':
                x = Math.abs(x) + 10;
                y = Math.abs(y);
                c ='U';
                break;
            case 'U':
                y = y + 20;
                c = 'L';
                break;
            case 'L':
                x = -(x + 10);
                c = 'D';
                break;
            case 'D':
                y = -(y);
                c = 'R';
                break;
            }
        n--;
    }
		System.out.println(x+" "+y);
	}
}
```


