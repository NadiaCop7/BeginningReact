## Chapter 1
Though react seems to be a bit too busy for its own good (very verbose) its actually not too hard to learn to read and write. Assuming code is code, it does require a basic understanding of JavaScript. If JS is not your strong suit….just a quick rundown of JS syntax as it applies to our most commonly used ingredients:

**Variables**- These will be called `const` or `let` depending on whether you want them to be reassignable or not. 
    Data Types- JS only has 6! String, Number (say goodbye to floats and ints), Boolean, Null, Undefined, and Symbol. (these will become more prominent when you transition to typescript)
    
    Examples of written variables in js: 
    
    `const someNum = 5;`
    
    `const stringNum = “5”;`
    
    `const isBool = true;`
    
    `let inputName = “”;`
    
    `inputName = “AustinPowers”;`

Not so different from what you already know, right? :D

**Methods/Functions**- they are always either written as a named function or as a const with an arrow function.
Examples of writing a function: 

Named function:

```
function doCodeStuff()  {

        return code stuff
        
};
```

OR

Arrow function:

```
const doCodeStuff = () => {

       return code stuff 
       
};
```


^^^^^ Same difference!! :D 

**Objects**- as with any OOP, you’ll have objects with properties and values, or key-value pairs. We pass the word props and property around a lot, and property in our line of work could also be referring to a house! LOL…so I’ll go with key and its value to prevent confusion, but the key is the property, or “characteristic” of that object, that has a value.

Examples of writing an object: 
 
`const object = {key: value};`

There can be multiple keys

`const object = { key: value, key2: value2, key3: value3 };` and just like you can do division horizontally or vertically, so can you type out your object:

```
const object = {

   key: value,
   
   key2: value2,
   
   key3: value 3
   
};
```

```
const objectThing = {

   age: 12,
   
   name: “Goofy”,
   
   isHuman: false
   
};
```

Though our linter will usually format this for you :D 

Want to know objectThings name coming from api? Just *console.log(objectThing.name);*
Remember, this is review….too easy and you can skip ahead…. :D 

**Arrays**- just like you learned them but initialized with a const. Contents can be numbers, strings, objects, or a combination thereof. JS is very forgiving (and why we need typescript! lol)

`const reactArray = [5, {shirt: blue}, “Happy”];`

`const propertyZipArray = [11111, 22222, 33333, 44444, 55555, 66666, 77777];`

Say you want to add an item, remove an item,  or run through the items in the array….no need to go the old school route of doing the calcs within a loop. Use an iterator method! 

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array

*A common one you’ll see in our codebase is .map()*

reactArray.map() will perform a function on each item and return the end result for each item.

