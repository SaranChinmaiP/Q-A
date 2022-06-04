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

  Input:
  3
  Output :
  -20 20
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

# 3. Word is the key
One programming language has the following keywords that cannot be used as identifiers:
Write a program to find if the given word is a keyword or not.

<code>Input #1: defer /
  Output: defer is a keyword
	</code>
```
import java.util.Scanner;
class Main
{
    public static void main(String args[])
    {

     String str[]= {"break", "case", "continue", "default", "defer", "else","for", "func", "goto", 
     "if", "map", "range", "return", "struct", "type", "var"};

    int flag = 0;
    Scanner sc = new Scanner(System.in);
    String input=sc.nextLine();

    for(int i = 0; i<16;i++){

        if(str[i].equals(input)){
            flag = 1;
            break;
        }
    }

    if(flag==1){
        System.out.println(input+" is a keyword");
    }
    else{
        System.out.println(input+" is not a keyword");
    }

}
}
```

