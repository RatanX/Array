# Array
Top 20 questions and their solutuion with Practical Use case
                   <h1>🛠️ Section 2: 10 Most Asked Array Methods</h1>

==============================================================================================
<h2> #1 . What is an array in JavaScript, and how does it differ from an object? </h2>

Ans: An arry is order collection of data . while an object are key-value pairs
Ex.  ```let arr= [1,'two',3,4]```

===============================================================================================
<h2> #2 . How do you create an array in JavaScript? </h2> 

Ans: using [], new Array(), Array.of()
Ex. ``` let a= [1,2] ```
``` let b= new Array(3) ```
``` let c= Array.of(1,3) ```
===============================================================================================
<h2> #3. What is the default behavior when accessing an array index that does not exist?</h2>

Ans: e.g., returns _undefined_ instead of error

AS IT IS OBJECT DATA TYPE IT BEHAVE LIKE OBJECT;
let obj = { name: "Alice" };
console.log(obj.age); // undefined

ex. let A=[5,6,8,5]

     console.log(A[5]) ---- Undefine
     console.log(A[4]) ---- 5
 ===============================================================================================    
<h2> #4 How are arrays indexed in JavaScript, and can they store different data types?</h2>

Ans: (Expected: zero-based indexing; arrays can store mixed data types.)
ex. A=['String',55,{a:555}]

================================================================================================
  
<h2> #5 How does JavaScript determine the length of an array? What happens if you assign a value to a higher index than the current length?</h2>

Ans: The last value of arry deside the length of arry;
      ex. let A = [5,6]
              A[100]= 2
              Then A.length=101

so if we console not assign index it show undefine but when we check availibility it show false
let arr = [, , 'a'];

arr.map(x => console.log(x)); ------ Only logs "a"
console.log(A[10]); ------ "undefine" but it is empty(because it's a hole)
console.log(10 in A)---------- false (index 10 does NOT exist

======================================================================================================
                  <h1>🛠️ Section 2: 10 Most Asked Array Methods</h1>

<h2> #6. What is the difference between map() and forEach()? When would you use one over the other?</h2>

Ans:(map returns a new array, forEach does not)

ex.  
              let A= [5,6,4,9]
              A.forEach(a=> a+2) ------7,6,4,9  --it give values
          let  B=  A.map(a=> a+2) 
          console.log(B)         ------[7,6,4,9] --it give return Array

          
=====================================================================================================
<h2> #7 How does the filter() method work and give an example use case?</h2>
Ans: A filter method is used to filter array by using conditional function
ex. let array =[5,6,7,8,5]

        let A=  array.filter(number => (number > 5))
        console.log(A) // ---return array A--[6,7,8]
        console.log(array) ----immutable --[5,6,7,8,5]

        //use case -- in shoping product filter
        let products = [{name:'shoes1' price:600},{name:'shoes2',price:400}]
        // search shoes less than 500
       cheap=  product.filter(item=>  item.price < 500)
       console.log(cheap) ------[{name:'shoes2',price:400}]
          
=====================================================================================================
<h2> #8 Explain the purpose of the reduce() method and provide a real-world example.</h2>

Ans: It return single value(not array),(E.g., summing numbers or flattening an array).
       
       let arr =[5,8,8,9]
       let sum= arr.reduce((acc,curr)=> acc+curr
       console.log(sum) //----------30
       console.log(arr) //-----original immutable. [5,8,8,9]

       //use case -calculate cart value of selected product
       let product =[{name:'shoes',price:1200},{name:'shirt',price:2000}]
       // calculate total price of selected product
       let total=product.reduce((acc,curr)=>(acc + curr.price),0) //0 is initial value set for acc
       cosole.log(total) //---------------- 3200

  we can check repeted value as well, like counting voting.

        let votes= ['congre','bjp','bjp','aap','bjp','aap','bjp']
        let counts= votes.reduce((acc,vote) => {
        acc[vote]= (acc[vote] || 0) + 1
        return acc
        },{})
        console.log(counts)
  ====================================================================================================
<h2> #9 How do push() and unshift() differ from pop() and shift()?</h2>
Ans: 
     push() --- take argument what we want to push at the last in main array
    unshift()--- also takes argument what we want to push at start in main array
    pop() --- dosent take argument, it just remove last item from array
    shift() --- dosent take argument, it just remove first item from array
 
        let arr= [4,5,6]
        let b=[7,8]
        
        arr.push(b) //----- [4,5,6,[7,8]]--push at the end(nested)
        console.log(arr)
        arr.push(...b) //----- [4,5,6,[7,8],7,8]--push at the end(by spread...b)
        console.log(arr)
        
        arr.unshift(b) //----[[7,8],4,5,6,[7,8],7,8]--push at the end(nested)
        console.log(arr)
        arr.unshift(...b) //----[7,8,[7,8],4,5,6,[7,8],7,8]--push at the end(by spread...b)
        console.log(arr)

        // pop and shift dosent take argument it just remove one item
        arr.pop() //----[7,8,[7,8],4,5,6,[7,8],7]---remove last item(8)
        console.log(arr)
        arr.shift() //--[8,[7,8],4,5,6,[7,8],7]---remove first item(7)
        console.log(arr)
    
              
 // Note: this function mutate/change the original array

 ===================================================================================================
 <h2> #9 What does Array.prototype.splice() do, and how is it different from slice()?</h2>
 Ans:  syntex: 
       splice(startingindex,deletecount,iteminsert1,iteminsert2)
            spliec:it deletes the items from starting index to upto deleted number provide in deletcount ,as per we deside 
       and also deleted item replace by passing it in parameter as iteminsert.

         let array =[5,6,7,8]
         let  b = array.splice(1,2,9)  //  It mutate original array & return deleted array
         console.log(array)  //-----------[5,9,8] remove 2(6,7) item & added 1(8) in original changed
         console.log(b)      //-----------[5,8]    ------return deleted array[5,8]

         //slice
         let c= array.slice(0,1)  //------it does not mutate/change original array
         console.log(c)            //------[5]----slice(0 to 1 index)
         console.log(array)        //------[5,9,8] ------unchange array


           //use case:let cart = [ 
           { id: 1, name: "Laptop", qty: 1 }, 
           { id: 2, name: "Phone", qty: 2 },
           { id: 3, name: "Tablet", qty: 1 }];
           
           // User removes the phone and replaces it with headphones

            let removed = cart.splice(1, 1, { id: 4, name: "Headphones", qty: 1 });
            console.log("Updated cart:", cart);
            console.log("Removed item:", removed);


         //  output
         
       
  updated cart = { id: 1, name: "Laptop", qty: 1 },
  { id: 4, name: "Headphones", qty: 1 },
  { id: 3, name: "Tablet", qty: 1 }
]

Removed item: [
     { id: 2, name: "Phone", qty: 2 }
]
           

       
       
        
        

        

  



        














