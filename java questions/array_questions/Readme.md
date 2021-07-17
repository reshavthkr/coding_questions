### 1. Convert number to words like 1234-->one two three four
```java
import java.util.*;

public class HelloWorld {
  static void numToWord(int n){
    int num=0,length =0;
    length = (int) Math.log10(n);
    // System.out.println(length);
    
    while(n!=0){
      num = (num*10)+(n%10);
      n /=10;
    }
    length = length - ((int) Math.log10(num));
    // System.out.println((int) Math.log10(num));
    while(num!=0){
      switch(num%10){
        case 0:
          System.out.print("Zero ");
          break;
        case 1:
          System.out.print("One ");
          break;
        case 2:
          System.out.print("Two ");
          break;
        case 3:
          System.out.print("Three ");
          break;
        case 4:
          System.out.print("Four ");
          break;
        case 5:
          System.out.print("Five ");
          break;
        case 6:
          System.out.print("Six ");
          break;
        case 7:
          System.out.print("Seven ");
          break;
        case 8:
          System.out.print("Eight ");
          break;
        case 9:
          System.out.print("Nine ");
          break;
      }
      num /=10;
    }
    while(length>0){
      System.out.print("Zero ");
      length--;
    }
  }
    public static void main(String[] args) {
       Scanner sc = new Scanner(System.in);
       int n = sc.nextInt();
       numToWord(n);
    }
}
```
### 2. Find no of prime no within given no n 
```java
import java.util.*;

public class HelloWorld {
  static boolean isPrime(int n){
    if(n <=1)return false;
    for(int i = 2; i<n ;i++){
      if(n%i==0)
      return false;
    }
    return true;
  }
  static void findPrimeNumber(int n){
    int count = 0;
    for(int i = 1; i <= n; i++){
      if(isPrime(i)){
        System.out.print(i+" ");
      count++;}
    }
    System.out.println();
    System.out.println(count);
  }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        findPrimeNumber(n);
    }
}
```
### 3. find Largest sum contiguous Subarray
```java
import java.util.Date;

public class HelloWorld {
  static void maxSubArray(int[] a){
    int maxSoFar =Integer.MIN_VALUE;
    int sum = 0;
    int n =a.length;
    for(int i = 0; i <n ; i ++){
      sum+=a[i];
      if(sum>maxSoFar){
        maxSoFar = sum;
      }
      if(sum<0)
      sum=0;
    }
    System.out.print(maxSoFar);
    
  }
    public static void main(String[] args) {
       int a[] = {-2, -3, 4, -1, -2, 1, 5, -3};
       maxSubArray(a);
    }
}
```
### 4.