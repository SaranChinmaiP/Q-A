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
# 6: To Zero or Not Zero


Given a pair of positive integers m and n (m < n; 0 < m < 999; 1 < n < = 999), 
write a program to smartly affix zeroes, while printing the numbers from m to n.
<code>
	Example-1

Input

5 10

Expected output

05 06 07 08 09 10



Example-2

Input

9 100

Expected output

009 010 011 012 013 014 015 016 017 018 019 020 021 022 023 024 025 026 027 028 029 030 031 032 033 034 035 036 037 038 039 040 041 042 043 044 045 046 047 048 049 050 051 052 053 054 055 056 057 058 059 060 061 062 063 064 065 067 068 069 070 071 072 073 074 075 076 077 078 079 080 081 082 083 084 085 086 087 088 089 090 091 092 093 094 095 096 097 098 099 100


	</code>

```
low=int(input())
up=int(input())
for i in range(low,up+1):
    if(up>=100):
         print("{:03d}".format(i),end=" ")
    elif(up>=10):
        print("{:02d}".format(i),end=" ")
    else:
        print(i,end=" ")
```

# 7: Oddly Even
Given a maximum of 100 digit numbers as input, find the difference between the sum of odd and even position digits.
<code>
	Input 1:
 4567

Expected output: 

2

Explanation

The Sum of odd position digits 4 and 6 is 10. The Sum of even position digits 5 and 7 is 12. The difference is 12-10=2.
	</code>
	
```
num=input()
Esum=int(0)
Osum=int(0)
for i in range(0,len(num)):
    if(i%2==0):
        Esum+=int(num[i])
    else:
        Osum+=int(num[i])
print(int(abs(Esum-Osum)))
```

# 8: Minting Mints
Problem statement:

It was one of the places, where people need to get their provisions only through fair price (“ration”) shops. As the elder had domestic and official work to attend to, their wards were asked to buy the items from these shops. Needless to say, there was a long queue of boys and girls. To minimize the tedium of standing in the serpentine queue, the kids were given mints. I went to the last boy in the queue and asked him how many mints he has. He said that the number of mints he has is one less than the sum of all the mints of kids standing before him in the queue. So I went to the penultimate kid to know how many mints she has.

She said that if I add all the mints of kids before her and subtract one from it, the result equals the mints she has. It seemed to be a uniform response from everyone. So, I went to the boy at the head of the queue consoling myself that he would not give the same response as others. He said, “I have four mints”.
<code>
	Given the number of first kid’s mints (n) and the length (len) of the queue as input, write a program to display the total number of mints with all the kids.

constraints:
2<n<10

1<len<20

Input#1:
4 2

Output:
7

	</code>


```
s,n = map(int,input().split())
sum=s
for i in range(1,n):
    prev=sum-1
    sum+=prev
print(sum)
```
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
