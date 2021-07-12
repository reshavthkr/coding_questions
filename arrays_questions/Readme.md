# Ques1. WAP to calculate the sum using reduce method
```javascript
var arr = [1, 2, 5, 10, 20];


let sum =arr.reduce((acc,sum)=>{
  return(
    acc+sum
    )
},0)
console.log(sum)
```