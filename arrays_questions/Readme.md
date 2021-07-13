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
## Write a JavaScript program which accept a number as input and insert dashes (-) between each two even numbers. For example if you accept 025468 the output should be 0-254-6-8
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
