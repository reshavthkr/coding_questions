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