## Ques1. WAP to calculate the sum using reduce method
```javascript
var arr = [1, 2, 5, 10, 20];


let sum =arr.reduce((acc,sum)=>{
  return(
    acc+sum
    )
},0)
console.log(sum)
```
## Ques2. Write a JavaScript program which accept a number as input and insert dashes (-) between each two even numbers. For example if you accept 025468 the output should be 0-254-6-8
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
### Ques3. Write a JavaScript function to get the last element of an array. Passing a parameter 'n' will return the last 'n' elements of the array.
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
### Ques4. Write a JavaScript program to sort the items of an array. Sample array : var arr1 = [ 3, 8, 7, 6, 5, -4, 3, 2, 1 ]; Sample Output : -4,-3,1,2,3,5,6,7,8
```javascript
function func(a){
  let l = a.length
  for(let i =0; i <l; i++){
    for(let j = 0; j<l; j++){
      if(a[i] < a[j]){
      [ a[i],a[j]] = [a[j] ,a[i]]
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
### Ques4. Write a JavaScript function to check whether an `input` is an array or not. Test Data : console.log(is_array('w3resource')); console.log(is_array([1, 2, 4, 0])); false true
```javascript
const is_array = function(input){
  if(toString.call(input)==='[object Array]')
  return true;
  return false;
}
console.log(is_array('w3resource'))
console.log(is_array([1,2,5,7]))
```
