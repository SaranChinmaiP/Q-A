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

# 4: Jar of Candies

Write the code to implement the above scenario. Display JAR at the counter with the available number of candies.

```
Input #1:
3
Output :

Number of Candies Sold: 3
Number of Candies available:7
```
```
import java.util.*;
class Main
{
	public static void main(String[] args)
	{
		Scanner sc = new Scanner(System.in);
		int n=10,k = sc.nextInt();
		if(k==0)
		{
			System.out.println("INVALID INPUT");
			System.out.println("NUMBER OF CANDIES AVAILABLE: "+n);
		}
		else
		{
			System.out.println("NUMBER OF CANDIES SOLD: "+k);
			System.out.println("NUMBER OF CANDIES AVAILABLE: "+(n-k));
		}
		sc.close();
	}
}
```

# 5: Oxygen Value

The selection of MPCS exams includes a fitness test which is conducted on the ground. There will be a batch of 3 trainees, appearing for a running test on track for 3 rounds.

You need to record their oxygen level after every round. After trainees are finished with all rounds, calculate for each trainee his average oxygen level over the 3 rounds and select the one with the highest average oxygen level as the fittest trainee. If more than one trainee attains the same highest average level, they all need to be selected. Display the fittest trainee(or trainers) and the highest average oxygen level.

Note:

1. The oxygen value entered should not be accepted if it is not in the range between 1 and 100.
2. If the calculated maximum average oxygen value of the trainees is below 70 then declare the 
   trainees as unfit with a meaningful message as “All       trainees are unfit”
3. Average oxygen values should be rounded

<code>
	Example 1:
Input #1:

95
	
92
	
95
	
92
	
90
	
92
	
90
	
92
	
90

Output:

Trainee Number: 1

Trainee Number: 3

Note: Input should be 9 integer values representing oxygen levels entered in order as 

Round 1: 

Oxygen value of trainee 1

Oxygen value of trainee 2

Oxygen value of trainee 3

Round 2:

Oxygen value of trainee 1

Oxygen value of trainee 2 

Oxygen value of trainee 3

Round 3:

Oxygen value of trainee 1

Oxygen value of trainee 2

Oxygen value of trainee 3

Note :Oxygen must be in the given format as in the above example. For any wrong input, the final output should display “INVALID INPUT”
	</code>
```
mport java.util.*;
class Main
{
	public static void main(String[] args)
	{
		Scanner sc = new Scanner(System.in);
		int i, x, T1 = 0, T2 = 0, T3 = 0, count = 1;
	    double A1, A2, A3;
	    while(count<=9)
	    {
	    	x=sc.nextInt();
	    	if(x >= 1 && x <= 100)
	        {
	            if(count % 3 == 1)
	            {
	                T1 = T1 + x;   
	            }
	            else if(count % 3 == 2)
	            {
	                T2 = T2 + x;
	            }
	            else
	            {
	                T3 = T3 + x;
	            }
	            count++;
	        }
	    	else
	    	{
	    		System.out.println("INVALID INPUT");
	    		count++;
	    		return;
	    	}
	    }
	    A1 = Math.round(T1/3);
	    A2 = Math.round(T2/3);
	    A3 = Math.round(T3/3);
	    if(A1 <= 70 && A2 <= 70 && A3 <= 70)
	    {
	        System.out.println("All trainees are unfit");
	        return;
	    }
	    if(A1 >= A2 && A1>= A3)
	    	System.out.println("Trainee Number: 1");
	    if(A2 >= A1 && A2 >= A3)
	    	System.out.println("Trainee Number: 2");
	    if(A3 >= A1 && A3 >= A2)
	    	System.out.println("Trainee Number: 3");
	    return;
	}
}
```


