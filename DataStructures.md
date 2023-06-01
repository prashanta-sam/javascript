## Javascript data structure questions
​
### level 1:
1. Convert [1, 2, 3] to [2, 3, 4] using one line of code.
Output should be [2, 3, 4]
================Answer 1========================================
let arr=[1,2,3]
let newArr=arr.map((item)=> item+1)
console.log(newArr)
=========================================================== End============================


2. Calculate total of all the numbers in array [1, 2, 3] using one line of code.
Output should be a number: 6
================Answer 2========================================
let arr=[1,2,3]
let newArr=arr.reduce((item,sum)=> sum+=item)
console.log(newArr) // 6
=========================================================== End============================

3. Print all the properties of the object along with value {name: 'Elie', rank: 'Pro'}.
Output should be a string: "name: Elie, rank: Pro"
================Answer 3========================================
let obj={name: 'Elie', rank: 'Pro'}
let s=""
let last = Object.keys(obj).pop();
for (let i in obj)
{
    s+=i+":"+obj[i]
    s+=(last==i) ? "" : ","
}
print(s)
=========================================================== End============================



### level 2:
1. Write a function to remove all even numbers from an Array.
```
Input array: 
[1, 3, 4, 6, 7, 8]
```
```
Output should be array: [1, 3, 7]
```
================Answer level 2.1========================================

let arr=[1, 3, 4, 6, 7, 8]
let newArr=arr.filter(a=> a%2)
print(newArr)
=========================================================== End============================


2. Replace all the vowels in a string with uppercase vowels.
```
Input string: 'Elie'
```
```
Output should be string: 'ElIE'
================Answer level 2.2========================================

let name ='Elie'
print(name.toUpperCase())



```
3. Write a function to find the maximum number in an array.
```
Input array: [1, 3, 4, 6, 7, 8, 2, 5]
```
```
Output should be a number: 8
```
================Answer level 2.3 ========================================

let arr=[1, 3, 4, 6, 7, 8, 2, 5]
let a=arr.reduce((v,m)=>{
    return v > m ? v : m
})
print(a)


​
### level 3:
1. Write a recursive function that transforms all the strings to uppercase.
```
// Input object
​
const user = {
    name: "Elie",
    job: "Instructor",
    workDetails: {
        type: "Part Time",
        hours: "40 hours"
    }
    educationQualifications: [
        {
            name: "Full Stack",
            type: "Certification"
        },
        {
            name: "Javascript",
            type: "Certification"
        }
    ]
}
// Output should be
​
{
    name: "ELIE",
    job: "INSTRUCTOR",
    workDetails: {
        type: "PASRT TimeTIME",
        hours: "40 HOURS"
    }
    educationQualifications: [
        {
            name: "FULL STACK",
            type: "CERTIFICATION"
        },
        {
            name: "JAVASCRIPT",
            type: "CERTIFICATION"
        }
    ]
}
```
================Answer level 3.1 ========================================
const user = {
    name: "Elie",
    job: "Instructor",
    workDetails: {
        type: "Part Time",
        hours: "40 hours"
    }
    educationQualifications: [
        {
            name: "Full Stack",
            type: "Certification"
        },
        {
            name: "Javascript",
            type: "Certification"
        }
    ]
}
const convertToUpper=(item)=>{
      if (Array.isArray(item)) 
      {
        return item.map(el => convertToUpper(el))
          
      }
      else if (item !== Object(item)) {
        return item.toString().toUpperCase();
      }
    
     return Object.fromEntries(
      		 Object.entries(item).map(([key, value]) => [key,convertToUpper(value)])
       )  
  
}

console.log(convertToUpper(user));

================END ========================================


2. Write a function that takes a string with key value pairs sum the value of all unique properties and return an object from it.
```
Input string: "a:2,b:3,c:4,a:5,b:6"
```
```
Output should be object: {a: 7, b: 9, c: 4}
```

================Answer Level 3.2 ========================================
let st="a:2,b:3,c:4,a:5,b:6"
let sp_arr=st.split(',')
let obj={}
for (let i in sp_arr)
  {
    let item=sp_arr[i] || []
    let arr=item.split(':') || []
    let k=arr[0] || ""
    let v=parseInt(arr[1]) || 0
    obj[k]= (isNaN(parseInt(obj[k])) ? 0 : parseInt(obj[k]) ) + v
  }
console.log(obj) //output
================END ========================================
3. Check for balanced parentheses using a stack
```
Example:
exp = "{[({})]}" should be valid
but "{[(]} should be invalid
```
================Level 3.3 ========================================

function isBlanacedBracket(str)
{  
    let stack=[] // created an empty array
    for (let i in str)
    {
      	// stored a bracket from string to 'b' variable
          let b=str[i]; 
        // checked for opening bracket
          if(b=='(' || b=='{' || b=='[')
          {   
            // pushed the bracket to the stack
            stack.push(b)           
          } 
      	 // checked for closing bracket
          else if( b == ')' || b=='}' || b==']')
          {
            //used pop method to remove the corresponding closing bracket
              const p=stack.pop();
            //checked the corresponding bracket is closing or not 
            // if not then return false  
            if(
                 ((b == ')' && p!='(')) ||
                 ((b == '}' && p!='{')) || 
                 ((b == ']' && p!='['))
                )
               return false
          }  
    }  
   // finaly sends the count of item in stack  
  	return (stack.length==0)
}
const st="{[()]}"
const result=isBlanacedBracket(st) ? 'Balanced' :'Not Balanced';
console.log(result)


================END ========================================

