## 1. WAP to calculate the sum using reduce method
```javascript
var arr = [1, 2, 5, 10, 20];


let sum =arr.reduce((acc,sum)=>{
  return(
    acc+sum
    )
},0)
console.log(sum)
```
## 2. Write a JavaScript program which accept a number as input and insert dashes (-) between each two even numbers. For example if you accept 025468 the output should be 0-254-6-8
```javascript
function last(str){
let res = [str[0]]
for(let i = 1; i < str.length; i++){
  if(str[i-1]%2==0&&str[i]%2 ==0){
  res.push("-",str[i])
}
else
res.push(str[i])

}
return res.reduce((acc,str)=>acc+str,"")
  
}
console.log(last("123546871"));
```
### 3. Write a JavaScript function to get the last element of an array. Passing a parameter 'n' will return the last 'n' elements of the array.
```javascript
function last(arr,n){
  if(n==null){
    return arr[arr.length-1]
  }
  return arr.splice(Math.max(arr.length-n,0))
  
}
console.log(last([7, 9, 0, -2],2)); //[ 0, -2 ]
console.log(last([7, 9, 0, -2]));//-2
```
### 4. Write a JavaScript program to sort the items of an array. Sample array : var arr1 = [ 3, 8, 7, 6, 5, -4, 3, 2, 1 ]; Sample Output : -4,-3,1,2,3,5,6,7,8
```javascript
function func(a){
  let l = a.length
  for(let i =0; i <l; i++){
    for(let j = 0; j<l; j++){
      if(a[i] < a[j]){
      [a[i],a[j]] = [a[j] ,a[i]]
      // let temp = a[i];
      // a[i] = a[j];
      // a[j] = temp
      }
    }
  }
  return a;
  
}
console.log(func( [ 3, 8, 7, 6, 5, -4, -3, 2, 1 ]));
```
### 5. Write a JavaScript function to check whether an `input` is an array or not. Test Data : console.log(is_array('w3resource')); console.log(is_array([1, 2, 4, 0])); false true
```javascript
const is_array = function(input){
  if(toString.call(input)==='[object Array]')
  return true;
  return false;
}
console.log(is_array('w3resource'))
console.log(is_array([1,2,5,7]))
```
### 6. Write a JavaScript program to find the most frequent item of an array. Sample array : var arr1=[3, 'a', 'a', 'a', 2, 3, 'a', 3, 'a', 2, 4, 9, 3]; Sample Output : a ( 5 times )
```javascript
function func(a){
  let mf = 1; 
  let m = 0; 
  let item
  for(let i = 0; i < a.length; i ++){
    for(let j=i; j < a.length; j++){
      if(a[i] == a[j]){
        m++
      }
    }
    if(mf<m){
        mf = m 
        item=a[i]
      }
      m=0
  }
  console.log(`${item} occur ${mf} times`)
}
func([3, 'a', 'a',3, 'a', 2, 3, 'a', 3, 3,'a', 2, 4, 9, 3])
```
### 7.  Write a JavaScript program which prints the elements of the following array. Go to the editor
***Sample array : var a = [[1, 2, 1, 24], [8, 11, 9, 4], [7, 0, 7, 27], [7, 4, 28, 14], [3, 10, 26, 7]];***
***Sample Output :***
***"row 0"***
***" 1"***
***" 2"***
***" 1"***
***" 24"***
***"row 1"***
```javascript
function func(arr){
  arr.forEach((item,i)=>{
    console.log(`row${i}`)
    item.forEach((value)=>{
      console.log(value)
    })
  })
}
func([[1, 2, 1, 24], [8, 11, 9, 4], [7, 0, 7, 27], [7, 4, 28, 14], [3, 10, 26, 7]])
```
### 8. Write a JavaScript program to remove duplicate items from an array (ignore case sensitivity).
```javascript
//Method 1
function func(arr){
let str = new Set(arr)
let s = Array.from(str)
console.log(s)
}
func([1, 2, 2, 4, 5, 4, 7, 8, 7, 3, 6])
//Method 2
function func(arr){
let x,
      l = arr.length,
      res=[],
      obj={};
      for(x =0; x<l;x++){
        obj[arr[x]]=0;
      }
      for(x in obj)
      res.push(x);
      return res
}
console.log(func([1, 2, 2, 4, 5, 4, 7, 8, 7, 3, 6]))
```
### 9. Print the second largest element in the array without using any predefined methods.
```javascript
function sortElement(a){
  for(let i = 0; i< a.length; i++){
    for(let j = 0; j < a.length; j++){
      if(a[i]<a[j]){
        [a[i],a[j]] = [a[j] , a[i]]
      }
    }
  }
}

function secondLargestNum(arr){
  sortElement(arr)
  for(let i= arr.length-2; i >=0; i--){
    if(arr[i]!=arr[arr.length-1]){
      console.log(`secondLargestNum is ${arr[i]}`)
      return
    }
  }
}
secondLargestNum([1,8,7,2,5,6,7,5,3,9])
_______________________________________
//method 2
function findSecondLarge(a){
  let max = Math.max(a[0],a[1]);
  // console.log(max)
  let secondMax = Math.min(a[0],a[1]);
  // console.log(secondMax)
 for(let i = 2; i <a.length; i++) {
    if(a[i]>=max){
      secondMax =max;
      max = a[i];
    }
    else if(a[i] >= secondMax){
      secondMax =a[i];
    }
  }
  // console.log(max)
  console.log(secondMax);
}
findSecondLarge([5,7,3,9,9,10,5,7,9,8])
```

### 10. Selection sort algorithm
```javascript
let a  = [0,1,2,0,1,2,0]
let l = a.length
let k = 4
for(let i = 0; i < l-1; i ++){
  let minIndex =i;
  for(let j = i; j < l; j++){
    if(a[j] < a[minIndex]){
      minIndex = j
    }
  }
  [a[i] ,a[minIndex]]=[a[minIndex],a[i]]
}
console.log(a)
```
### 11. Find the Union and Intersection of the two sorted arrays.
```javascript
function union(a1,a2){
  let l1 = a1.length;
  let l2 =a2.length;
  let b = [] 
  for(let i = 0; i< l1; i++){
    let flag = 0
    for(let j = 0; j < l2; j++ ){
      if(a1[i] ==a2[j]){
        flag++
      a2.splice(j,1)
      }
    }if(flag==0)
    b.push(a1[i]);
  }
  b.push(a2)
  console.log(b.flat())
}
union([85, 25, 1, 32,54 ,6],[85,2,3])
```
