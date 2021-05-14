```js
// -----------------------------------------------------------------------------

// If you copy any part of this guide (or all of it) you will be able to paste
// it in a developer console and see the code output. To open a javascript
// developer console: open your web browser > press F12 > console tab. It's
// recommended to read this guide with the console open and fiddle with the
// code, this helps the learning process!

// Programming always involve some kind of transformation of data. You can store
// data, count it, apply math operations, trigger other flows, but the basic
// mechanism of programing languages is always about reading some data and then
// executing some kind of logic with it.

// In Javascript we have the following data types ans structures:

// -----------------------------------------------------------------------------
// Numbers
// -----------------------------------------------------------------------------

// (In javascript every number falls into the "Number" type and there is no
// distinction between integers and floating points)
1
81072865287.331
19.35

// -----------------------------------------------------------------------------
// Operators
// -----------------------------------------------------------------------------

// We can start to write some very simple programs if we know about Numbers and
// operators. Lets write a program that sums 2+2:

2 + 4 // 6
(2 * 4) // 8
// Parenthesis works as expected in math)
2 / 4 // 2
2 ** 4 // 16 (2 * 2 * 2 * 2)
5 % 4 // 1 (the remainder of the integer division)

// all 5 lines above could be seen as 5 really small programs. Each of them is
// very limited but they do perform a purposefull transformation in some initial
// data. These small programs are still quite unusable for and end user since a
// basic calculator would solve this types of problems, but the purpose of
// calling them programs is to try to consolidade the view that a program is
// simply a transformation of some given data. As we learn more complex data
// structures we'll quickly achieve some problem-solving techniques that no
// calculator can solve!

// -----------------------------------------------------------------------------
// Strings
// -----------------------------------------------------------------------------

// (Sequences of alphanumeric characters, delimited by ', " or `)

// ' or " are used for strings that has no literal linebrakes (you can add them
// with "\n" special character)
'pan'  
"cake"
'pan cake'
"pancake cake"

// both phrases bellow are the same. ` is a newer version of '/" that allows
// strings to have linebrakes and also allows for us to add variables(a concept
// still to be explanied) inside them lather on.
  
'this makes\nme hungry'

`this makes
me hungry`

// -----------------------------------------------------------------------------
// Booleans
// -----------------------------------------------------------------------------

// Some might say life is relative, but not for booleans. Boolean is a value
// that is either true or false

true
false

// you can inverse a boolean value with the ! operator

!true // false
!false // true

// you can also produce boolen values by making comparitions with these
// operators:

1 === 1 // true (equals)
1 !== 1 // false (not equals)

4 > 3 // true (greater than)
3 >= 3 // true (greate than or equals)

4 <= 3 // false (smaller than)
4 < 3 // false (smaller than or equals)

// Booleans are also used to make logical comparisons

true && true // true
true && false // false (in any order)
false && false // false

true || true // true
true || false // true (in any order)
false || false // false

// -----------------------------------------------------------------------------
// Empty values and Boolean conversion
// -----------------------------------------------------------------------------

// (We can also say something is actually nothing, and one of the worst parts of
// javascript is that we have 2 ways to say that)

undefined
null

// Whats the difference? Roughly "undefined" happens when a value wat not ever
// defined to begin with. "null" is a value that normally someone purposly added
// there because it will be filled later on. You should bother much with both
// now, just know that they exist and they act as "false" when used on boolean
// comparisons. Now that you know that, lets end this section with a reference
// table on what values are consideres "truthy" or "falsy" when used as
// booleans:

// The following values are always falsy, meaning that when used as booleans
// they are considered as false:

false
0 // (zero)
'' // (empty string)
""
``
null
undefined
NaN // Not a Number - shows up when you do math with a type that is not a number

// ALL other values will always be truthy, meaning that they will be considered
// as true on boolean operations

// -----------------------------------------------------------------------------
// Variables
// -----------------------------------------------------------------------------

// Now that we know about data types let's learn how to store those types in
// your computer memory so you can access them by your program later on

let x // (is the same as) let x = undefined
let y = 4
let someValue = "a string"
let anotherValue = 4 < 3 // in other words, anotherValue = false

y // 4
someValue // "a string"

// We use the reserver keyword "let" in order to tell javascript that we want
// our variables to not only exist but also to have a initial value. After that
// we can read or variables by simply using their names. We can always reassign
// new values to our variables that were declared with "let":

y = 6
y // 6
y = y + 2
y // 8

someValue + " " + someValue // "a string a string"
  
// it's highly not recommended to use math operators for any values that are not
// Numbers, but JS is really permissive at its core so this type of stuff
// exists, we can achieve this same result with a more modern fashion using ``

`${someValue} ${someValue}` // "a string a string"

// -----------------------------------------------------------------------------
// Objects
// -----------------------------------------------------------------------------

// An object in javascript is a structure where you can have as many data types
// as you want aggregated in a single data type.

let exampleObject = {
  "property": "value",
  "anotherProperty": 2,
}

// objects are a bunch of Key:Values. Every key has a value, if a key doesn't
// exist you will receive undefined as a value when trying to access it.

exampleObject.property // "value"
exampleObject["property"] // "value"

// Since keys are mostly always string, javascript has removed the need to use '
// in Keys so its cleaner to declare objects:

exampleObject = {
  property: "value",
  anotherProperty: 2,
}

exampleObject.property // "value"

// Object is a really powerfull data type in JS, as you learn the next data
// types (Arrays/Lists and Functions) you'll see how easy it is to achieve high
// complexity solution with only these blocks. We use objects to aggregate data
// that has some kind of connection between them. Let's say you want to register
// a shirt on an ecommerce:

let shirt = {
  color: "blue",
  price: 19.90,
  description: "A blue t-shirt, you'll never need another one in your life!"
}

shirt.price // 19.90

// Objects allow you to structure "new data types" that are specific to your
// problem's needs. Here is a secret: all the types we've ween until now are
// built on top of an "Object" because everything in JS is an Object.This will
// make more sense as you learn more concepts.

// Since a Value in an object can be any data type, it can also be an object,
// this is how our structures start to quickly gain complexity:

let setOfClothes = {
  shirt: {
    color: "blue",
    price: 19.90,
    description: "A blue t-shirt, you'll never need another one in your life!"
  },
  pants: {
    color: "red",
    price: 19.70,
    description: "A red pant!"
  },
}

setOfClothes.shirt.color // "blue"
setOfClothes.pants.color // "red"

// -----------------------------------------------------------------------------
// Arrays 
// -----------------------------------------------------------------------------

// When using an object you store values in "named keys". Objects are an
// unordered list of values where you can assign keys to access those values. An
// Array (also called a List) is an ordered list of values where the key is the
// position of the element in the list.

let listOfFruits = ["apple", "banana", "mayonese"]

listOfFruits[0] // "apple"
listOfFruits[1] // "banana"
listOfFruits[2] // "mayonese"

// (arrays have some properties because they are also objects, but you should
// not assign new properties to them)
listOfFruits.length // 3 

// Arrays and Lists are extremely usefull in many scenarios, specially when you
// want to apply operations to a large amount of data that has the same type
// We'll dive deeper into them later.

// -----------------------------------------------------------------------------
// Merge Objects or Arrays
// -----------------------------------------------------------------------------

// You can merge objects into other objects or arrays into other arrays. This is
// a largely usefull operation that javascript has a sweet new syntax for you to
// do it:

let objectA = { name: "Avocado" }
let objectB = { name: "Orange", size: 1 }

let objectAB = {
  ...objectA,
  ...objectB
} // { name: "Orange", size: 1 }

let objectBA = {
  ...objectB,
  ...objectA
} // { name: "Avocado", size: 1 }

let anotherObject = {
  ...objectB,
  ...objectA,
  color: "green",
} // { name: "Avocado", size: 1, color: "green" }

// and you can do the same with arrays

let arrayA = [1, 2, 3]
let arrayB = [4, 5, 6]

let arrayAB = [
  ...arrayA,
  ...arrayB,
] // [1, 2, 3, 4, 5, 6]

let arrayBA = [
  ...arrayB,
  ...arrayA,
] // [4, 5, 6, 1, 2, 3]

// -----------------------------------------------------------------------------
// Functions
// -----------------------------------------------------------------------------

// One of the most beautifull parts in JS are functions. Function is a data type
// that allow you to store a piece of code so you can then execute it later on.
// It allows you to easily customize the input value from the usage perspective
// and when you mix Functictions with Arrays, Objects, and the other data types
// you can achieve any operation you desire. Lets understand the basic concepts
// of functions:

let addNumbers = function (someNumber, anotherNumber) {
  // someNumber and anotherNumber are variables that we are going to use inside
  // the function and will be passed by the code who calls this function with
  // (). This comonly called "argument" or "parameter" You can name parameters
  // as you like and have as many as you want.

  // you can do lots of things here
  return someNumber + anotherNumber
}

addNumbers // Function

// in order to execute the code inside the function we need to invoke it with
// parenthesis and send the values for our variables declared in the first line
// of our function declaration

addNumbers(1, 2) // 3
addNumbers("a", "b") // "ab"

// OMG we just went full illegal and used addNumbers to actually add strings! JS
// is a really permissive language and with great power comes great
// responsibility. functions by default do not care about what types you send
// when you use them, since in js the + operator can also be used by strings our
// function will work, but it's our responsibility to build the tools that we
// want if we want to prevent unwanted scenarios (or if you want strong type
// safety in JS you can use something like typescript)

// We can write functions in a shortwer way thanks to the new versions of
// javascript:

let divide = (x, y) => {
  // you can do lots of things here
  return x / y
}

let mulitply = (x, y) => x * y
// this is a really neat way to write short functions, if you ommit {} it will
// automatically return the value

// We use many functions that are standard from JS in order to write our
// programs. A classic one is:

console.log("Hi there!")

// console.log is a default function that will print a value into your console.
// Until now we've been typyng and returing values one by one, when running a
// program with many lines and values we often use console.log to debug or
// describe actions in our developer console.

// -----------------------------------------------------------------------------
// Conditional Operations
// -----------------------------------------------------------------------------

// One last subject we need before being able to mix all concepts: Conditional
// execution of code. At many times you'll only want to execute code if a
// condition is met, and we do it like this:

// 3 === 4 below can be replaced for anything that returns a boolean, you can
// invoke function that returns a boolean for example
if (3 === 4) {
  console.log("yayy")
} else {
  console.log("nay")
} // if you run this it will only log "nay"

// You can also assign values to variables given a condition. for example:

let someVar = 3 === 4 ? "yayy" : "nay" // somevar = "nay"

// or you can use whitespace to help with readability

let otherVar = 4 === 4
  ? "yayy"
  : "nay" // somevar = "yayy"

// Both methods to execute code and assign values conditionally will be used as
// you progress.

// -----------------------------------------------------------------------------
// Mixing it all up: map, filter, ande reduce
// -----------------------------------------------------------------------------

// By now we have learned about complex types such as Functions, Objects, Arrays
// and simpler types like Number, String, Boolean, and emptiness. When
// developing javascript you can always use any type anywhere. For example you
// could have an Array of Objects that has Functions inside them, or you can
// have a Function that receives another Function as a variable. There is trully
// no limits as to what you do with the tyos that you just learned, this is both
// really awesome and really dangerous because it's easy to lose track of what
// function deals with what part of your problem if you don't organize your code
// properly.

// There is no one - right - way - fits - all to learn how to organize code, you
// will learn by writing it and applying to real cases and learning what works
// and what gives you headaches on maintance time.

// -----------------------------------------------------------------------------
// Map
// -----------------------------------------------------------------------------


// Now lets dive into a scenario where we have an Array of numbers and a
// function that increments a number by 1:

let list = [1, 2, 3]

let increment = (x) => x + 1
// this is equivalent to:
increment = function (x) {
  return x + 1
}

// Let's say we want to apply increment to all the values inside our list. It
// would be quite cumbersome to do it like this:

let newList = [increment(1), increment(2), increment(3)] // [2, 3, 4]

// If this list had 10000 elements we would last forever to write this code.
// Luckly Arrays has 3 built-in functions that helps you to apply
// transformations in the whole list: map, filter an reduce. Map is the first
// one we'll learn and it solves exactly the case above:

newList = list.map(increment) // [2, 3, 4]

// This may seem really magical but lets dive deeper into whats happening here

// list is an Array and arrays have the map function by default. The map
// functions receives a function and applies it individually to the array
// values, the return of this function will be the new value, when finished it
// returns a whole new Array with tall new values. we can write the code above
// in other ways, such as

newList = list.map((element) => increment(element))

newList = list.map(function (element) { return increment(element) })

// Lets see another example but this time using a more complex data type inside
// our Array and we'll also use some of our Merge knowledge

let anotherList = [
  {
    name: 'Apple',
    tastes: 'Really Good'
  },
  {
    name: 'Banana',
    tastes: 'Really Good'
  },
]

// this time we have a list of Objects where an objects represents a fruit and
// how do we think it tastes. Let's say that today we really hate fruits and we
// need to fix our list in order to match reality

let anotherNewList = anotherList.map((fruit) => {
  return {
    ...fruit,
    tastes: "Really Bad",
  }
})

console.log(anotherNewList) /*
[
  {
    name: 'Apple',
    tastes: 'Really Bad'
  },
  {
    name: 'Banana',
    tastes: 'Really Bad'
  },
]
*/

// this can be rewriten in a shorter manner to achieve the same result:

anotherNewList = anotherList.map((fruit) => ({
  ...fruit,
  tastes: "Really Bad",
}))

// Merging is extremelly usefull for creating new objects that inherit all old
// properties allowing you to mannualy override the values you want. We've use
// this in the examples above in order to use map to create a list of new
// objects given our list of old objects.

// Map is used to apply transformation to all data inside a list. But what if we
// want to filter some elements out before applying transformations? We use a
// method called filter for that.

// -----------------------------------------------------------------------------
// Filter
// -----------------------------------------------------------------------------


// the usage of filter is really simmilar to map. It's a built-in array function
// that you also sends a function as input just like map, but instead of
// returning a new value you return either true or false to determine wether an
// element should be kept or thrown away. Here is a simple example:

let isEven = x => x % 2 === 0
// returns true when X is even and false when X its odd

let numList = [1, 2, 3, 4, 5]

let newNumList = numList.filter(isEven) // [2, 4]

// And we could also have more complex types inside the array

let moreFruits = [
  {
    name: 'Apple',
    tastes: 'Really Good'
  },
  {
    name: 'Banana',
    tastes: 'Just Good'
  },
]

let newFruitList = moreFruits.filter(fruit => fruit.tastes === "Really Good")
// [ { name: "Apple", tastes: "Really Good" } ]

// -----------------------------------------------------------------------------
// Chaining maps and filters
// -----------------------------------------------------------------------------


// sice both map and filter are guaranteed to always return a new array we can
// always chain another map or filter, this is a really sweet way to chain
// operations even if you are working only with 1 element inside the array. As
// you progress into programming you'll see how wonderfull this property really
// is, but by noew let's just try to grasp the basic usage:

let products = [
  { name: "Skate", category: "Sports", price: 100 },
  { name: "Ball", category: "Sports", price: 10 },
  { name: "Shirt", category: "Clothes", price: 50 },
]

// lets say we sant to generate a list that has only Sports products and we'll
// also apply a 20% discount on them.

products
  .filter(product => product.category === "Sports")
  .map(product => ({ ...product, price: product.price * 0.8 }))
// [{
//  { name: "Ball", category: "Sports", price: 8 }, { name: "Shirt", category:
//  "Clothes", price: 40 },
// }]

// you can chain maps and filters as much as you want!

// -----------------------------------------------------------------------------
// Reduce
// -----------------------------------------------------------------------------

// aka: the father of map and filter

// Reduce is the most powerfull function in our triad (map, filter, reduce)
// because you can simply write both map and filter with reduce and really you
// can do whatever you want with its power. Reduce allows you to produce any
// data type you want by reading an array and applying a function to all
// elements, but the difference between map and reduce is that the reduce
// function will maintain a variable that is always passed forward to the next
// iteration so you can build up anything you want by reading the array element
// by alement and then building up this shared variable (called accumulator).
// Let's see this in pratice:

let moreProducts = [
  { name: "Skate", category: "Sports", price: 100 },
  { name: "Ball", category: "Sports", price: 10 },
  { name: "Shirt", category: "Clothes", price: 50 },
]

// how would you summ the prices of all products? Let's do it with reduce:

moreProducts.reduce((accumulator, product) => accumulator + product.price, 0)
// 160

// the execution of the above code happens like this:

// (0, { ... price: 100 }) =>  0 + 100 (100, { ... price: 10 }) =>  100 + 10
// (110, { ... price: 50 }) =>  110 + 50

// Note that the accumulator is always the result of the previous function
// invokation, and the initial accumulator is passed to the initial reduce
// function as a seccond argument.

// In this case we reduced an array to a number but you could use any type and
// any kind of operation you want. Lets use reduce in a more complex scenario
// where we want to apply a series of functions to a value:

let someFunctions = [
  x => x + 2,
  x => x * 10,
  x => `The final result is ${x}`
]

someFunctions.reduce((accumulator, func) => func(accumulator), 30)
// The final result is 320
```
