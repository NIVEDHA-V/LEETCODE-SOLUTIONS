# STRIVER-SOLUTIONS
## Step - 1
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

### 4. Prime Number

A prime number is a positive integer that is divisible by exactly 2 integers, 1 and the number itself.
You are given a number 'n'.
Find out whether 'n' is prime or not.

```java
public class Solution {
    public static String isPrime(int num) {
	int c = 0;
    for(int i =1 ; i*i<= num; i++){
        if(num%i==0)
        {
            c++;
            if((num/i) != i) c++;
        }
    }
    if(c==2) return "YES";
    else return "NO";
	}
}
```

### 5. GCD or HCF



```java
import java.util.*;
public class Solution {
    public static int calcGCD(int n, int m){
        int x=0;
        for(int i=1;i<=Math.min(n, m);i++){
            if(n%i==0&&m%i==0){
                x=i;
            }
        }
        return x;
    }
}
```

to reduce time complexity

```java
import java.util.*;
public class Solution {
	
	public static int gcd(int a,int b)
	{
        int x=1;
		int c = Math.min(a,b);

		if(a%c == 0 && b%c == 0){
			return c;
		}
        for(int i=1;i<=Math.min(a, b);i++){
            if(a%i==0&&b%i==0){
                x=i;
            }
        }
        return x;
    }
}
```

### 6. Print 1 to N without loop

You are given an integer ‘n’.
Your task is to return an array containing integers from 1 to ‘n’ (in increasing order) without using loops.

```java
public class Solution {
    static int c=1,i=0;
    static void num(int arr[],int x){
        if(c>x){
            return ;
        }
        arr[i]=c;
        c++;
        i++;
        num(arr,x);
    }
    public static int[] printNos(int x) {
        int[] arr= new int[x];
        num(arr,x);
        return arr;
    }
}
```

### 7. Print name N times

You are given an integer ‘n’.
Print “Coding Ninjas ” ‘n’ times, without using a loop.

```java
import java.util.ArrayList;
import java.util.List;
public class Solution {
    static void fun(List<String> li,int i,int n){
        if(i>n){
            return;
        }
        li.add("Coding Ninjas ");
        fun(li,i+1,n);
    }
    public static List<String> printNtimes(int n){
        List<String> li = new ArrayList<String>();
        fun(li,1,n);
        return li;
    }
}
```

### 8. N to 1 without loop

You are given an integer ‘n’.
Your task is to return an array containing integers from ‘n’ to ‘1’ (in decreasing order) without using loops.

```java
public class Solution
{
    static void num(int[] li,int i,int x){
         li[x-i]=i;
        if(i==1){
            return ;
        }
        num(li,i-1,x);
    }
    public static int[] printNos(int x) {
        int[] li= new int[x];
        num(li,x,x);
        return li;
    }
}
```

### 9. Sum of N natural numbers

You are given an integer ‘n’.
Your task is determining the sum of the first ‘n’ natural numbers and returning it.

```java
public class Solution {
    public static long sumFirstN(long n) {
        return (n*(n+1))/2;
    }
}
```

### 10. Factorial Numbers Not Greater Than N

You are given an integer ’n’.
Your task is to return a sorted array (in increasing order) containing all the factorial numbers which are less than or equal to ‘n’.
The factorial number is a factorial of a positive integer, like 24 is a factorial number, as it is a factorial of 4

```java
import java.util.*;;
public class Solution {
    static long fact (long n){
        if(n==0||n==1){
            return 1;
        }
        return n*fact(n-1);
    }
    public static List<Long> factorialNumbers(long n) {
        List<Long> li = new ArrayList<>();
        for(long i=1;i<=n;i++){
            long x=(fact(i));
            if(x<=n){
                li.add(x);
            }
            else{
                break;
            }
        }
        return li;
    }
}
```

### 11. Reverse an array [inplace algo]

Given an array 'arr' of size 'n'.
Return an array with all the elements placed in reverse order.

```java
public class Solution {
    static void rev(int i, int n,  int[] nums){
        if(i>=n/2){
            return ;
        }
        int t=nums[i];
        nums[i]=nums[n-i-1];
        nums[n-i-1]=t;
        rev(i+1,n,nums);
          
    }
    public static int[] reverseArray(int n, int []nums) {
        rev(0,n,nums);
        return nums;
    }
}
```

### 12. Palindrome

A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.
Given a string s, return true if it is a palindrome, or false otherwise.

```java
import java.util.*;
import java.io.*;
class Solution {
    
    static boolean checkPalindrome(String s){
        int i = 0;
        int j = s.length() - 1;
        s = s.toLowerCase();


        while (i < j) {

            if (!Character.isLetterOrDigit(s.charAt(i))) {
                i++;
            }
            else if (!Character.isLetterOrDigit(s.charAt(j))) {
                j--;
            } else {
                if (s.charAt(i) != s.charAt(j)) {
                    return false;
                }
                i++;
                j--;
            }
        }

        return true;
    }
    public boolean isPalindrome(String s) {
        
        return checkPalindrome(s);
    }
}
```

Another approach
```java
class Solution {
    public boolean isPalindrome(String s) {
        char[] charArray = s.toCharArray();
        int ind = sanitize(charArray);
        if (ind < 2) {
            return true;
        }
        int i = 0;
        int j = ind - 1;
        while (i < j) {
            if (charArray[i] != charArray[j]) {
                return false;
            }
            i++;
            j--;
        }
        return true;
    }

    private int sanitize(char[] charArray) {
        int index = 0;
        for (int i = 0; i < charArray.length; i++) {
            if (charArray[i] >= 48 && charArray[i] <= 57) {
                charArray[index] = (char) charArray[i];
                index++;
            } else if (charArray[i] >= 65 && charArray[i] <= 90) {
                charArray[index] = (char) (charArray[i] + 32);
                index++;
            } else if (charArray[i] >= 97 && charArray[i] <= 122) {
                charArray[index] = (char) charArray[i];
                index++;
            }
        }
        return index;
    }
}
```

### 13. Fibonacci series

The Fibonacci numbers, commonly denoted F(n) form a sequence, called the Fibonacci sequence, such that each number is the sum of the two preceding ones, starting from 0 and 1. That is,
F(0) = 0, F(1) = 1
F(n) = F(n - 1) + F(n - 2), for n > 1.
Given n, calculate F(n).

```java
class Solution {
    public int fib(int n) {
        if(n<=1) return n;
        return fib(n-1) + fib(n-2);
    }
}
```
### 14. Count frequency in the range

You are given an array 'arr' of length 'n' containing integers within the range '1' to 'x'.
Your task is to count the frequency of all elements from 1 to n.

```java
public class Solution {
    public static int[] countFrequency(int n, int x, int []nums){
        // Write your code here.
        int hash[] = new int[n];
        for(int i=0;i<n;i++){
            if(nums[i]<=n){
                hash[nums[i]-1]+=1;
            }
        }
        return hash;
    }
}
```
