# 1: Write a JavaScript function to find the longest common starting substring in a set of strings.
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
# 2: Reverse a string but do not change the postion of the words

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
### 3. Write a JavaScript program which accept a string as input and swap the case of each character. For example if you input 'The Quick Brown Fox' the output should be 'tHE qUICK bROWN fOX'.
```javascript
function func(str){
  let res =[]
  str.split(" ").forEach((item)=>{
    for(let i = 0; i< item.length; i++){
      if(i==0){
        res.push(item[i].toLowerCase())
      }
      
      else
      res.push(item[i].toUpperCase())
      
    }
    res.push(" ")
  })
  console.log(res.reduce((acc,item)=>acc+item,""))
}
func('The Quick Brown Fox')
```
### 4. Count frequency of characters in a string without using any predefined methods using javascript.
```javascript
function getFrequency(string) {
    let freq = {};
    let res=[]
    for (let i=0; i<string.length;i++) {
        let character = string.charAt(i);
        if (freq[character]) {
           freq[character]++;
          // console.log(character+" "+freq[character])
        } else {
           freq[character] = 1;
        }
        
    }
   
    return freq;
};
console.log(getFrequency("aabbcddd"))
```
### 5. ●	Print string with the frequency greater than 1
***Input:   aaabbbbccf Output:- a3b4c2f***
```javascript
function getFrequency(string) {
    let freq = {};
    for (let i=0; i<string.length;i++) {
        let character = string.charAt(i);
        if (freq[character]) {
           freq[character]++;
        } else {
           freq[character] = 1;
        } 
    }
    for (var key in freq) {
    if (freq.hasOwnProperty(key)) {
      if(freq[key]>1)
        console.log(key + "" + freq[key]);
        else
        console.log(key)
    }
    }
};
getFrequency("aabbcddd")
```
### 6. Given a character array you have to print the string array have length equal to given length
```javascript
function permutation(arr,r){
let res2 = [];
let res = [];
let out = [];
for (let i=0;i<arr.length;i++){
    res2 = [arr[i]];
    let index=0;
    while(res[index]){
        res2.push(''+res[index]+arr[i]);
        index++;
    }
    res = res.concat(res2);
}
res.map((item)=>{
  if(item.length==r){
    out.push(item)
  }
})
return out;
}
console.log(permutation(["a","b","c","d"],3));
```
### 7. Remove the alternative duplicates from the string.
```javascript
// Duplicate characters

const testStrings = ["ppapttksl", "aattpddgh", "ooeeww","addsggghi"];
// output will be: ["paptksl", "atpdgh", "oew"]

function removeAlternateDuplicates(str) {
  // your answer here
  let a =[];
  for(let i = 0; i<str.length; i++){
    if(str[i]!= a[a.length-1]){
      a.push(str[i]);
    }
  }
  str=a.join("")
  return str;
}

testStrings.forEach((str) => console.log(removeAlternateDuplicates(str)));
```
