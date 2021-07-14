# Ques1: Write a JavaScript function to find the longest common starting substring in a set of strings.
Sample array : console.log(longest_common_starting_substring(['go', 'google']));
Expected result : "go"

### pictorial representation: 
![pictorial Representation](https://github.com/reshavthkr/javascript_coding_questions/blob/master/strings_questions/longest%20common%20starting%20substring/Screenshot_1.jpg)

### flow Chart: 
![flow Chart](https://github.com/reshavthkr/javascript_coding_questions/blob/master/strings_questions/longest%20common%20starting%20substring/Screenshot_2.jpg)

```javascript
function longest_common_starting_substring(arr1){
    const arr= arr1.sort();
    console.log(arr)
    const a1= arr[0];
    const a2= arr[arr.length-1];
    const L= a1.length;
    let i= 0;
    while(i< L && a1.charAt(i)=== a2.charAt(i)) i++;
    return a1.substring(0, i);
}
console.log(longest_common_starting_substring(['gofrance','google'])); 
```
# Ques2: Reverse a string but do not change the postion of the words

```javascript
//Method 1
var str = "Full Stack Tutorials";
let temp=""
for(let i=str.length-1; i >=0; i--){
  temp+=str[i];
}
let a=temp.split(" ");
let b = [];
for(let i = a.length-1; i >=0; i--){
  b.push(a[i])
}
console.log(b.join(" "))

//Method 2:
var str = "Full Stack Tutorials";
let str2 = str.split(" ").map((word)=>{
  let temp = "";
  for(let i = word.length-1 ; i>=0; i--){
    temp+=word[i];
  }
    return temp
}).reduce((acc,word)=>acc+word+" ","")
console.log(str2)

//Method 3
// console.log(str.split(" ").reverse().join(" ").split("").reverse().join(""))
```
