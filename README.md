# Learn.js


<details>
  <summary>The table of content is available in the top left corner of this document. Click here to see a reference image on how to find it.</summary>
  
  ![image](https://user-images.githubusercontent.com/7863230/118364980-2c0e5200-b571-11eb-8237-4c4355579de0.png)
</details>


## Usage

```js

// If you copy any part of this guide inside the code blocks you will be able to
// paste it in a developer console and see the code output. To open a javascript
// developer console: open your web browser > press F12 > console tab. It's
// recommended to read this guide with the console open and fiddle with the
// code, this helps the learning process!

// Programming always involve some kind of transformation of data. You can store
// data, count it, apply math operations, trigger other flows, but the basic
// mechanism of programing languages is always about reading some data and then
// executing some kind of logic with it.

```

# Data types and structures

```js
// In Javascript we have the following data types ans structures:
```

## Numbers

```js

// In javascript every number falls into the "Number" type and there is no
// distinction between integers and floating points
1
81072865287.331
19.35
```

## Operators

```js
// We can start to write some very simple programs if we know about Numbers and
// operators. Lets write a program that sums 2+2:

2 + 4 // 6
(2 * 4) // 8
// Parenthesis works as expected in math)
2 / 4 // 0.5
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
```

## Strings

```js

// Sequences of alphanumeric characters, delimited by ', " or `

// ' or " are used for strings that has no literal linebrakes (you can add them
// with "\n" special character)
'pan'  
"cake"
'pan cake'
"pancake cake"

// both phrases bellow are the same. ` is a newer version of '/" that allows
// strings to have line breaks and also allows for us to add variables (a concept
// still to be explained) inside them later on.
  
'this makes\nme hungry'

`this makes
me hungry`
```

## Booleans

```js

// Some might say life is relative, but not for booleans. Boolean is a value
// that is either true or false

true
false

// you can inverse a boolean value with the ! operator

!true // false
!false // true

// you can also produce boolean values by making comparisons with these
// operators:

1 === 1 // true (equals)
1 !== 1 // false (not equals)

4 > 3 // true (greater than)
3 >= 3 // true (greater than or equals)

4 <= 3 // false (smaller than)
4 < 3 // false (smaller than or equals)

// Booleans are also used to make logical comparisons

true && true // true
true && false // false (in any order)
false && false // false

true || true // true
true || false // true (in any order)
false || false // false

```

## Empty values and Boolean conversion

```js

// We can also say something is actually nothing, and one of the worst parts of
// javascript is that we have 2 ways to say that

undefined
null

// Whats the difference? Roughly "undefined" happens when a value was not ever
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
```

## Variables

```js
// Now that we know about data types let's learn how to store those types in
// your computer memory so you can access them by your program later on

let x // (is the same as) let x = undefined
let y = 4
let someValue = "a string"
let anotherValue = 4 < 3 // in other words, anotherValue = false

y // 4
someValue // "a string"

// We use the reserved keyword "let" in order to tell javascript that we want
// our variables to not only exist but also to have a initial value. After that
// we can read our variables by simply using their names. We can always reassign
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

```

## Objects

```js

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
// problem's needs. Here is a secret: all the types we've seen until now are
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

```

## Arrays 

```js

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

// Arrays and Lists are extremely useful in many scenarios, specially when you
// want to apply operations to a large amount of data that has the same type
// We'll dive deeper into them later.

```

## Merge Objects or Arrays

```js

// You can merge objects into other objects or arrays into other arrays. This is
// a largely useful operation that javascript has a sweet new syntax for you to
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

```

## Functions

```js

// One of the most beautiful parts in JS are functions. Function is a data type
// that allow you to store a piece of code so you can then execute it later on.
// It allows you to easily customize the input value from the usage perspective
// and when you mix Functions with Arrays, Objects, and the other data types
// you can achieve any operation you desire. Let's understand the basic concepts
// of functions:

let addNumbers = function (someNumber, anotherNumber) {
  // someNumber and anotherNumber are variables that we are going to use inside
  // the function and will be passed by the code who calls this function with
  // (). This commonly called "argument" or "parameter". You can name parameters
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
// responsibility. Functions by default do not care about what types you send
// when you use them, since in js the + operator can also be used by strings our
// function will work, but it's our responsibility to build the tools that we
// want if we want to prevent unwanted scenarios (or if you want strong type
// safety in JS you can use something like typescript)

// We can write functions in a shorter way thanks to the new versions of
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
// Until now we've been typing and returing values one by one, when running a
// program with many lines and values we often use console.log to debug or
// describe actions in our developer console.
```

## Conditional Operations

```js

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

let someVar = 3 === 4 ? "yayy" : "nay" // someVar = "nay"

// or you can use whitespace to help with readability

let otherVar = 4 === 4
  ? "yayy"
  : "nay" // otherVar = "yayy"

// Both methods to execute code and assign values conditionally will be used as
// you progress.

```

# Leveling up

```js

// By now we have learned about complex types such as Functions, Objects, Arrays
// and simpler types like Number, String, Boolean, and emptiness. When
// developing in javascript you can always use any type anywhere. For example you
// could have an Array of Objects that has Functions inside them, or you can
// have a Function that receives another Function as a variable. There is trully
// no limits as to what you do with the types that you just learned, this is both
// really awesome and really dangerous because it's easy to lose track of what
// function deals with what part of your problem if you don't organize your code
// properly.

// There is no one - right - way - fits - all to learn how to organize code, you
// will learn by writing it and applying to real cases and learning what works
// and what gives you headaches on maintance time.

```

## Map

```js

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

// Let's see another example but this time using a more complex data type inside
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

// this time we have a list of Objects where an object represents a fruit and
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

// this can be rewritten in a shorter manner to achieve the same result:

anotherNewList = anotherList.map((fruit) => ({
  ...fruit,
  tastes: "Really Bad",
}))

// Merging is extremelly useful for creating new objects that inherit all old
// properties allowing you to manually override the values you want. We've use
// this in the examples above in order to use map to create a list of new
// objects given our list of old objects.

// Map is used to apply transformation to all data inside a list. But what if we
// want to filter some elements out before applying transformations? We use a
// method called filter for that.

```

## Filter

```js


// the usage of filter is really similar to map. It's a built-in array function
// that you also sends a function as input just like map, but instead of
// returning a new value you return either true or false to determine whether an
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

```

## Chaining maps and filters

```js


// since both map and filter are guaranteed to always return a new array we can
// always chain another map or filter, this is a really sweet way to chain
// operations even if you are working only with 1 element inside the array. As
// you progress into programming you'll see how wonderfull this property really
// is, but for now let's just try to grasp the basic usage:

let products = [
  { name: "Skate", category: "Sports", price: 100 },
  { name: "Ball", category: "Sports", price: 10 },
  { name: "Shirt", category: "Clothes", price: 50 },
]

// let's say we want to generate a list that has only Sports products and we'll
// also apply a 20% discount on them.

products
  .filter(product => product.category === "Sports")
  .map(product => ({ ...product, price: product.price * 0.8 }))
// [{
//  { name: "Ball", category: "Sports", price: 8 }, { name: "Shirt", category:
//  "Clothes", price: 40 },
// }]

// you can chain maps and filters as much as you want!

```

## Reduce

```js

// aka: the parent of map and filter

// Reduce is the most powerfull function in our triad (map, filter, reduce)
// because you can simply write both map and filter with reduce and really you
// can do whatever you want with its power. Reduce allows you to produce any
// data type you want by reading an array and applying a function to all
// elements, but the difference between map and reduce is that the reduce
// function will maintain a variable that is always passed forward to the next
// iteration so you can build up anything you want by reading the array element
// by element and then building up this shared variable (called accumulator).
// Let's see this in pratice:

let moreProducts = [
  { name: "Skate", category: "Sports", price: 100 },
  { name: "Ball", category: "Sports", price: 10 },
  { name: "Shirt", category: "Clothes", price: 50 },
]

// how would you sum the prices of all products? Let's do it with reduce:

moreProducts.reduce((accumulator, product) => accumulator + product.price, 0)
// 160

// the execution of the above code happens like this:

// (0, { ... price: 100 }) =>  0 + 100
// (100, { ... price: 10 }) =>  100 + 10
// (110, { ... price: 50 }) =>  110 + 50

// Note that the accumulator is always the result of the previous function
// invocation, and the initial accumulator is passed to the initial reduce
// function as a second argument.

// In this case we reduced an array to a number but you could use any type and
// any kind of operation you want. Let's use reduce in a more complex scenario
// where we want to apply a series of functions to a value:

let someFunctions = [
  x => x + 2,
  x => x * 10,
  x => `The final result is ${x}`
]

someFunctions.reduce((accumulator, func) => func(accumulator), 30)
// The final result is 320

```

## Mutability

```js

// With all the tools above you are ready to transform anything into anything
// you want. I'd like to introduce you now to the concept of Mutability and
// Imutability so we can learn about state management, which will help us
// understand how to better manage our code
```

## Mutations

```js 

// Mutation is the act of changing an existing variable without creating a new
// variable. Throrougt this guide there were a few examples where a variable was
// declared with "let" and then later on it was reassigned to another variable,
// that is a mutation. Here are some examples of mutations:
  
let a = 1 // No mutation happened here
a = a + 1 // This is a mutation
  
let b = { value: "something" } // No mutation happened here
b.value = "something else" // This is a mutation

let c = [1, 2, 3] // This is a mutation
c[0] = c[0] + 1 // This is a mutation
c[1] = c[1] + 1 // This is a mutation
c[2] = c[2] + 1 // This is a mutation
console.log(c) // [4, 5, 6]
  
// Here are the same examples avoiding mutations
  
let a = 1
let newA = a + 1
  
let b = { value: "something" }
let newB = { value: "something else", ...b }

let c = [1, 2, 3]
let newC = c.map(x => x + 1) //[4, 5, 6]
  
// Note: map, filter, and reduce will always produce new values instead of
// mutating the old value, this is part of why they are amazing tools
  
// We can clearly see that in the second example we had to create more variables
// and invent more names, but in the long run you'll be able to grasp how this
// allows you to write clearer and more debugable code.

// One of the most common source of errors in programming happensby sharing a
// variable among many functions and mutating it, but this procedure is also a
// necessity for most of the programs. Let's learn now how to share a variable
// with functions to act as a storage and try to keep our mutations contained so
// our program's complexity doesn't outgrow us.
```
  
## Scopes and State Management 

```js

// Our functions have access to all variables in the scope that it was declared.
// Let's see what this means in pratice:

let x = 1

let someFunc = () => {
  console.log(x) // 1
}

// see how someFunc can access x. Lets see how this wouldn't be possible

let somefunc = () => {
  let x = 2
}

let otherFunc = () => {
  console.log(x) // x is not defined (undefined)
}

// otherFunc cant acess x because its only visible inside someFunc scope. Let's see other example:

let somefunc = () => {
  let otherFunc = () => {
    let x = 2
  }
  console.log(x) // x is not defined (undefined)
}

//  someFunc cant aceess X because only otherFunc can. But now lets make an example where it works:
let x = 1
let somefunc = () => {
  let y = 2
  let otherFunc = () => {
    let z = 3
    console.log(x) // 1
    console.log(y) // 2
    console.log(z) // 3
  }
}

// otherFunc can acess everythins. someFunc can acess x, and y. The rest of the program will only be able to acess x. Lets see how we use this in pratice:

let createStatefullObject = (initialValue) => {

  let value = initialValue

  return {
    increment: (amount = 1) => {
    // "amount = 1" means that if amount is not sent it will be defaulted to 1
      value = value + amount
    },
    display: () => {
      console.log(`Value is: ${value}`)
    }
  }

}

let object = createStatefullObject(0)
  
object.display() // Value is: 0

object.increment()

object.display() // Value is: 1
  
object.increment(5)
  
object.display() // Value is: 6
  
// The thing to note here is that we cannot access "value" inside our object
// without using the functions that we returned. This is a technique that uses
// the parent function scope to hold a variable that can be used by all inner
// functions but cannot be accessed by outside. This property of sharing scopes
// between functions is called "Closure"
  ```

# Classes
A class can be thought of as a blueprint, a template. It contains a set of properties and methods(which are functions in a class) related to it. Let me give an example:

```
//Here we created a "blueprint" for a car(which basically contains a set of things that makes a car what it is)
class Car{
  //The vroom function is an example of a method inside a class. When we add this method inside of it we state that every car has a method called vroom in it.
  vroom(){
    //A car goes vroom vroom right?
    console.log("vroom vroom");
  }
}
```

But how do we actually use this class? We can create(or instantiate) an object! An object(or instance) can be thought of as something that uses the class blueprint. An object has access to the properties and methods that a class uses. Referring back to the class example:

```
//Here we instantiate(or create) two Car objects. Each object gets its OWN set of Car methods and properties. Make sure to add the new keyword!
var toyota = new Car();
var lamborghini = new Car();

//We use the dot operator to access a method or property in a class
toyota.vroom(); //Will output "vroom vroom"
lamborghini.vroom(); //Will output "vroom vroom"
```

This works great, but what if I wanted to set a "color" property? or what if i wanted to set the brand? You can use a constructor to do so.

A constructor can be thought of as a special function that allows you to pass data to a class, and to set attributes(properties) of one. Here's an example:

```
class Car{
  //The constructor allows you to pass data in a class, like so. Here we are passing the color and brand attributes to the class. The color, and brand, are parameters which are passed.
  constructor(color, brand, owner){
    //This refers to the current class(We set this class's color and brand to the color and brand passed into the constructor)
    this.color = color;
    this.brand = brand;
    this.owner = owner;
  }
  vroom(){
    //Just for reference, this is an alternative to concatenating strings. Make sure to use the back quotes key(the small one to the left of one and above tab on qwerty)
    //This is the equivalent to doing: console.log("A " + this.color + " " + this.brand + " owned by " + this.owner + " goes vroom vroom")
    console.log(`A ${this.color} ${this.brand} owned by ${this.owner} goes vroom vroom`);
  }
}
```


To pass data in an object, put your arguments in the parenthesis of one. For example, you could do:

```
//When you instantiate an object, the constructor is called, with these arguments being passed!
var toyota = new Car("blue", "toyota", "john");
var lamborghini = new Car("red", "lamborghini", "@dewball345");

toyota.vroom(); //A blue toyota owned by john goes vroom vroom
lamborghini.vroom(); //A red lamborghini owned by @dewball345 goes vroom vroom
```

Suppose you had a car counter, which would record the number of car objects created. Would it make sense to give each car a separate car count, like how properties are given? No, because a car counter is supposed to not be for each and every individual car, but for all the cars. For cases like these, it makes sense to use a static variable. Static variables are kept in the main class and are not passed to the objects. While an object can refer to a static variable, it will not have it as a separate property. Hence if you change a static variable once, all objects will have the variable changed.

For example:

```
class Car{
  //this is the syntax for creating a static variable
  static car_count = 0;
  constructor(){
    //here we increment the variable by one
    car_count++;  
  }
}

//here we instantiate the car objects
var car1 = new Car()
var car2 = new Car()

//There are two ways of referring to a static variable:

//1)
Car.car_count

//2)
car1.car_count
car2.car_count

//Both will give the same result
```

Methods can also be static as well. 

```
class Car{
  static honk(){
    console.log("All cars honk. Honk Honk!");
  }
}

Car.honk() //outputs "All cars honk. Honk Honk!"
```

Not all cars(and not all classes) are the same. But some share the same functionalities(methods). For example, all cars can honk, wash themselves, and rev. So how can we model this relationship with classes?

Inheritance!

Let me give you an example:

```
//This is our superclass(or our parent class). This can be thought of as the most generic one, the one that fits all. 
class Car{
  constructor(){
    console.log("this is a car");
  }
  honk(){
    console.log("A car can honk");
  }
  wash(){
    console.log("A car can wash");
  }
  rev(){
    console.log("Vroom vroom!");
  }
}

//Here we say that Lamborghini "inherits" the methods of the car class, and that the Lamborghini is the child class while the Car is the parent class. This means it automatically has the methods of the car. Even though we didn't add the methods to this class, the lamborghini can honk, wash, and rev. Keep in mind that properties(variables) are not inherited. 

class Lamborghini extends Car{
  constuctor(){
    //When we use the super() function we get the functionality of the parent class's constructor. 
    super() //will console.log "this is a car"
    console.log("This type of car is a lamborghini");
  }
  
  //Here we "override" the method from the Car class. This means that when we call the rev() method, we will get this one instead of the cars
  rev(){
    console.log("A lamborghini goes vroom vroom VERY FAST");
  }
  
  wash(){
    //When overriding a method, we can call the parent class's implementation of the method by calling super.*method name*()
    super.wash()
    console.log("A lamborghini needs to be washed very carefully!");
  }
}

var regular_car = new Car() //this is a car

var lambo = new Lamborghini() 
//This is a car
//The type of car is a lamborghini

regular_car.rev() //vroom vroom
lambo.rev() //A lamborghini goes vroom vroom VERY FAST

regular_car.wash() //A car can wash
lambo.wash() 
//A car can wash
//A lamborghini needs to be washed very carefully
```


# Interacting with the world

```js
// to be done: about async interactions, npm, node, how to use other people's 
// code, and where to learn more about the tools you learned here and the ones
// you didn't
```
