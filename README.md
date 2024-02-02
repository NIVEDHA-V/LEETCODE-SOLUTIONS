# LEETCODE-SOLUTIONS

### 1. Palindrome number
Given an integer x, return true if x is a palindrome, and false otherwise.
```java
class Solution {
    public boolean isPalindrome(int x) {
        if (x < 0 || (x != 0 && x % 10 == 0))
            return false;
        int rev = 0;
        while (x > rev) {
            rev = rev * 10 + x % 10;
            x = x / 10;
        }
        return (x == rev || x == rev / 10);
    }
}
```

### 2. Armstrong Number

You are given an integer 'n'.
Return 'true' if 'n' is an Armstrong number, and 'false' otherwise.
Note:
An Armstrong number is a number (with 'k' digits) such that the sum of its digits raised to 'kth' power is equal to the number itself. For example, 371 is an Armstrong number because 3^3 + 7^3 + 1^3 = 371.

```java
import java.util.*;
public class Main {
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		int a=sc.nextInt();
		int n=a;
		String s=Integer.toString(n);
		int size=s.length();
		int c=0;
		while(n!=0){
			int x= (int)Math.pow(n%10,size);
			c+=x;
			n/=10;
		}
		if(a==c){
			System.out.println("true");}
		else{
			System.out.println("false");}
	}
}

```

### 3. Sum of all Divisors

You are given an integer ‘n’.
Function ‘sumOfDivisors(n)’ is defined as the sum of all divisors of ‘n’.
Find the sum of ‘sumOfDivisors(i)’ for all ‘i’ from 1 to ‘n’.

We need to find the sum of ‘sumOfDivisors(i)’ for all ‘i’ from 1 to 5. 
‘sumOfDivisors(1)’ = 1
‘sumOfDivisors(2)’ = 2 + 1 = 3
‘sumOfDivisors(3)’ = 3 + 1 = 4
‘sumOfDivisors(4)’ = 4 + 2 +1 = 7 
‘sumOfDivisors(5)’ = 5 + 1 = 6
Therefore our answer is sumOfDivisors(1) + sumOfDivisors(2) + sumOfDivisors(3) + sumOfDivisors(4) + sumOfDivisors(5) = 1 + 3 + 4 + 7 + 6 = 21.

```java
import java.util.*;
public class Solution {
    public static int sumOfAllDivisors(int n){
        int s=0;
        for(int i=1;i<=n;i++){
            s+=i*(n/i);
        }
        return s;
    }
}
```
