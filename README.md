# Learn.js


<details>
  <summary>The table of content is available in the top left corner of this document. Click here to see a reference image on how to find it.</summary>
  
  ![image](https://user-images.githubusercontent.com/7863230/118364980-2c0e5200-b571-11eb-8237-4c4355579de0.png)
</details>


## Usage

If you copy any part of this guide inside the code blocks you will be able to
paste it in a developer console and see the code output. To open a javascript
developer console: open your web browser > press F12 > console tab. It's
recommended to read this guide with the console open and fiddle with the
code, this helps the learning process!

Programming always involve some kind of transformation of data. You can store
data, count it, apply math operations, trigger other flows, but the basic
mechanism of programing languages is always about reading some data and then
executing some kind of logic with it.


# Data types and structures

In Javascript we have the following data types ans structures:

## Numbers

In javascript every number falls into the "Number" type and there is no
distinction between integers and floating points

```js
1
81072865287.331
19.35
```

## Math Operators

We can start to write some very simple programs if we know about Numbers and
operators. Lets write a program that sums 2+2:

```js
2 + 4 // 6
(2 * 4) // 8
// Parenthesis works as expected in math)
2 / 4 // 0.5
2 ** 4 // 16 (2 * 2 * 2 * 2)
5 % 4 // 1 (the remainder of the integer division)
```

All 5 lines above could be seen as 5 really small programs. Each of them is
very limited but they do perform a purposefull transformation in some initial
data. These small programs are still quite unusable for and end user since a
basic calculator would solve this types of problems, but the purpose of
calling them programs is to try to consolidade the view that a program is
simply a transformation of some given data. As we learn more complex data
structures we'll quickly achieve some problem-solving techniques that no
calculator can solve!

## Strings

Sequences of alphanumeric characters, delimited by ', " or `

' or " are used for strings that has no literal linebrakes (you can add them
with "\n" special character)

```js
'pan'
"cake"
'pan cake'
"pancake cake"
```

Both phrases bellow are the same. ` is a newer version of ' and " that allows
strings to have line breaks and also allows for us to add variables (a concept
still to be explained) inside them later on.

```js
'this makes\nme hungry'

`this makes
me hungry`
```

## Booleans and Comparissons

Some might say life is relative, but not for booleans. A boolean is a value
that is either true or false

```js
true
false
```

You can inverse a boolean value with the ! operator

```js
!true // false
!false // true
```

You can also produce boolean values by making comparisons with these
operators

```js
1 === 1 // true (equals)
1 !== 1 // false (not equals)

4 > 3 // true (greater than)
3 >= 3 // true (greater than or equals)

4 <= 3 // false (smaller than)
4 < 3 // false (smaller than or equals)
```

Booleans are also used to make logical comparisons

```js
true && true // true
true && false // false (in any order)
false && false // false

true || true // true
true || false // true (in any order)
false || false // false

```

## Empty values and Boolean conversion

We can also say something is actually nothing, and one of the worst parts of
javascript is that we have 2 ways to say that

```js
undefined
null
```

Whats the difference? Roughly "undefined" happens when a value was not ever
defined to begin with. "null" is a value that normally someone purposly added
there because it will be filled later on. You should bother much with both
now, just know that they exist and they act as "false" when used on boolean
comparisons. Now that you know that, lets end this section with a reference
table on what values are consideres "truthy" or "falsy" when used as
booleans:

The following values are always falsy, meaning that when used as booleans
they are considered as false:

```js
false
0 // (zero)
'' // (empty string)
""
``
null
undefined
NaN // Not a Number - shows up when you do math with a type that is not a number

```

ALL other values will always be truthy, meaning that they will be considered
as true on boolean operations

## Variables

Now that we know about data types let's learn how to store those types in
your computer memory so you can access them by your program later on

```js

let x // (is the same as) let x = undefined
let y = 4
let someValue = "a string"
let anotherValue = 4 < 3 // in other words, anotherValue = false

y // 4
someValue // "a string"

```

We use the reserved keyword "let" in order to tell javascript that we want
our variables to not only exist but also to have a initial value. After that
we can read our variables by simply using their names. We can always reassign
new values to our variables that were declared with "let":

```js

y = 6
y // 6
y = y + 2
y // 8

someValue + " " + someValue // "a string a string"

```

It's highly not recommended to use math operators for any values that are not
Numbers, but JS is really permissive at its core so this type of stuff
exists, we can achieve this same result with a more modern fashion using ``

```js

`${someValue} ${someValue}` // "a string a string"

```

## Objects

An object in javascript is a structure where you can have as many data types
as you want aggregated in a single data type.

```js
let exampleObject = {
  "property": "value",
  "anotherProperty": 2,
}
```

Objects are a bunch of Key:Values. Every key has a value, if a key doesn't
exist you will receive undefined as a value when trying to access it.

```js
exampleObject.property // "value"
exampleObject["property"] // "value"
```

Since keys are mostly always string, javascript has removed the need to use '
in Keys so its cleaner to declare objects:

```js
exampleObject = {
  property: "value",
  anotherProperty: 2,
}

exampleObject.property // "value"
```

Object is a really powerfull data type in JS, as you learn the next data
types (Arrays/Lists and Functions) you'll see how easy it is to achieve high
complexity solution with only these blocks. We use objects to aggregate data
that has some kind of connection between them. Let's say you want to register
a shirt on an ecommerce:

```js
let shirt = {
  color: "blue",
  price: 19.90,
  description: "A blue t-shirt, you'll never need another one in your life!"
}

shirt.price // 19.90
```

Objects allow you to structure "new data types" that are specific to your
problem's needs. Here is a secret: all the types we've seen until now are
built on top of an "Object" because everything in JS is an Object.This will
make more sense as you learn more concepts.

Since a Value in an object can be any data type, it can also be an object,
this is how our structures start to quickly gain complexity:

```js
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

When using an object you store values in "named keys". Objects are an
unordered list of values where you can assign keys to access those values. An
Array (also called a List) is an ordered list of values where the key is the
position of the element in the list.

```js
let listOfFruits = ["apple", "banana", "mayonese"]

listOfFruits[0] // "apple"
listOfFruits[1] // "banana"
listOfFruits[2] // "mayonese"
```

Arrays have some properties because they are also objects, but you should
not assign new properties to them

```js
listOfFruits.length // 3
```

Arrays and Lists are extremely useful in many scenarios, specially when you
want to apply operations to a large amount of data that has the same type
We'll dive deeper into them later.

## Merge Objects or Arrays

You can merge objects into other objects or arrays into other arrays. This is
a largely useful operation that javascript has a sweet new syntax for you to
do it:

```js
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
```

and you can do the same with arrays

```js
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

One of the most beautiful parts in JS are functions. Function is a data type
that allow you to store a piece of code so you can then execute it later on.
It allows you to easily customize the input value from the usage perspective
and when you mix Functions with Arrays, Objects, and the other data types
you can achieve any operation you desire. Let's understand the basic concepts
of functions:

```js
let addNumbers = function (someNumber, anotherNumber) {
  // someNumber and anotherNumber are variables that we are going to use inside
  // the function and will be passed by the code who calls this function with
  // (). This commonly called "argument" or "parameter". You can name parameters
  // as you like and have as many as you want.

  // you can do lots of things here
  return someNumber + anotherNumber
}

addNumbers // Function
```

In order to execute the code inside the function we need to invoke it with
parenthesis and send the values for our variables declared in the first line
of our function declaration

```js
addNumbers(1, 2) // 3
addNumbers("a", "b") // "ab"
```

OMG we just went full illegal and used `addNumbers` to actually add strings! JS
is a really permissive language and with great power comes great
responsibility. Functions by default do not care about what types you send
when you use them, since in js the + operator can also be used by strings our
function will work, but it's our responsibility to build the tools that we
want if we want to prevent unwanted scenarios (or if you want strong type
safety in JS you can use something like typescript)

We can write functions in a shorter way thanks to the new versions of
javascript:

```js
let divide = (x, y) => {
  // you can do lots of things here
  return x / y
}

let mulitply = (x, y) => x * y
```

This is a really neat way to write short functions, if you ommit {} it will
automatically return the value

We use many functions that are standard from JS in order to write our
programs. A classic one is:

```js
console.log("Hi there!")
```

`console.log` is a default function that will print a value into your console.
Until now we've been typing and returing values one by one, when running a
program with many lines and values we often use console.log to debug or
describe actions in our developer console.

## Conditional Operations

One last subject we need before being able to mix all concepts: Conditional
execution of code. At many times you'll only want to execute code if a
condition is met, and we do it like this:

`3 === 4` below can be replaced for anything that returns a boolean, you can
invoke function that returns a boolean for example

```js

if (3 === 4) {
  console.log("yayy")
} else {
  console.log("nay")
} // if you run this it will only log "nay"
```

You can also assign values to variables given a condition. for example:

```js
let someVar = 3 === 4 ? "yayy" : "nay" // someVar = "nay"
```

or you can use whitespace to help with readability

```js
let otherVar = 4 === 4
  ? "yayy"
  : "nay" // otherVar = "yayy"
```

Both methods to execute code and assign values conditionally will be used as
you progress.

# Leveling up

By now we have learned about complex types such as Functions, Objects, Arrays
and simpler types like Number, String, Boolean, and emptiness. When
developing in javascript you can always use any type anywhere. For example you
could have an Array of Objects that has Functions inside them, or you can
have a Function that receives another Function as a variable. There is trully
no limits as to what you do with the types that you just learned, this is both
really awesome and really dangerous because it's easy to lose track of what
function deals with what part of your problem if you don't organize your code
properly.

There is no one - right - way - fits - all to learn how to organize code, you
will learn by writing it and applying to real cases and learning what works
and what gives you headaches on maintance time.

## Map

Now lets dive into a scenario where we have an Array of numbers and a
function that increments a number by 1:

```js

let list = [1, 2, 3]

let increment = (x) => x + 1
// this is equivalent to:
increment = function (x) {
  return x + 1
}
```

Let's say we want to apply increment to all the values inside our list. It
would be quite cumbersome to do it like this:

```js
let newList = [increment(1), increment(2), increment(3)] // [2, 3, 4]
```

If this list had 10000 elements we would last forever to write this code.
Luckly Arrays has 3 built-in functions that helps you to apply
transformations in the whole list: map, filter an reduce. Map is the first
one we'll learn and it solves exactly the case above:

```js
newList = list.map(increment) // [2, 3, 4]
```

This may seem really magical but lets dive deeper into whats happening here

list is an Array and arrays have the map function by default. The map
functions receives a function and applies it individually to the array
values, the return of this function will be the new value, when finished it
returns a whole new Array with tall new values. we can write the code above
in other ways, such as

```js
newList = list.map((element) => increment(element))

newList = list.map(function (element) { return increment(element) })
```

Let's see another example but this time using a more complex data type inside
our Array and we'll also use some of our Merge knowledge

```js
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
```

This time we have a list of Objects where an object represents a fruit and
how do we think it tastes. Let's say that today we really hate fruits and we
need to fix our list in order to match reality

```js
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
```

This can be rewritten in a shorter manner to achieve the same result:

```js
anotherNewList = anotherList.map((fruit) => ({
  ...fruit,
  tastes: "Really Bad",
}))
```

Merging is extremelly useful for creating new objects that inherit all old
properties allowing you to manually override the values you want. We've use
this in the examples above in order to use map to create a list of new
objects given our list of old objects.

Map is used to apply transformation to all data inside a list. But what if we
want to filter some elements out before applying transformations? We use a
method called filter for that.

## Filter

The usage of filter is really similar to map. It's a built-in array function
that you also sends a function as input just like map, but instead of
returning a new value you return either true or false to determine whether an
element should be kept or thrown away. Here is an example:

```js
let isEven = x => x % 2 === 0
// returns true when X is even and false when X its odd

let numList = [1, 2, 3, 4, 5]

let newNumList = numList.filter(isEven) // [2, 4]
```

And we could also have more complex types inside the array

```js
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

Since both map and filter are guaranteed to always return a new array we can
always chain another map or filter, this is a really sweet way to chain
operations even if you are working only with 1 element inside the array. As
you progress into programming you'll see how wonderfull this property really
is, but for now let's just try to grasp the basic usage:

```js
let products = [
  { name: "Skate", category: "Sports", price: 100 },
  { name: "Ball", category: "Sports", price: 10 },
  { name: "Shirt", category: "Clothes", price: 50 },
]
```

Let's say we want to generate a list that has only Sports products and we'll
also apply a 20% discount on them.

```js
products
  .filter(product => product.category === "Sports")
  .map(product => ({ ...product, price: product.price * 0.8 }))
// [{
//  { name: "Ball", category: "Sports", price: 8 }, { name: "Shirt", category:
//  "Clothes", price: 40 },
// }]
```

Remember: you can chain maps and filters as much as you want!

## Reduce

Reduce, the parent of map and filter, is the most powerfull function in our triad 
(map, filter, reduce) because you can simply write both map and filter with reduce 
and really you can do whatever you want with its power. Reduce allows you to produce 
any data type you want by reading an array and applying a function to all
elements, but the difference between map and reduce is that the reduce
function will maintain a variable that is always passed forward to the next
iteration so you can build up anything you want by reading the array element
by element and then building up this shared variable (called accumulator).

Let's see this in pratice:

```js
let moreProducts = [
  { name: "Skate", category: "Sports", price: 100 },
  { name: "Ball", category: "Sports", price: 10 },
  { name: "Shirt", category: "Clothes", price: 50 },
]
```

How would you sum the prices of all products? Let's do it with reduce:

```js
moreProducts.reduce((accumulator, product) => accumulator + product.price, 0)
// 160
```

The execution of the above code happens like this:

```js
// (0, { ... price: 100 }) =>  0 + 100
// (100, { ... price: 10 }) =>  100 + 10
// (110, { ... price: 50 }) =>  110 + 50
// 160
```

Note that the accumulator is always the result of the previous function
invocation, and the initial accumulator is passed to the initial reduce
function as a second argument.

In this case we reduced an array to a number but you could use any type and
any kind of operation you want. Let's use reduce in a more complex scenario
where we want to apply a series of functions to a value:

```js
let someFunctions = [
  x => x + 2,
  x => x * 10,
  x => `The final result is ${x}`
]

someFunctions.reduce((accumulator, func) => func(accumulator), 30)
// The final result is 320
```

Note that because reduce is not guaranteed to return an Array (it will return
whatever type you want as the accumulator) you have to be carefull when chaining
maps and filters after using a reduce.

## Mutability

With all the tools above you are ready to transform anything into anything
you want. I'd like to introduce you now to the concept of Mutability and
Imutability so we can learn about state management, which will help us
understand how to better manage our code

## Mutations

Mutation is the act of changing an existing variable without creating a new
variable. Throrougt this guide there were a few examples where a variable was
declared with "let" and then later on it was reassigned to another variable,
that is a mutation. Here are some examples of mutations:

```js
let a = 1 // No mutation happened here
a = a + 1 // This is a mutation

let b = { value: "something" } // No mutation happened here
b.value = "something else" // This is a mutation

let c = [1, 2, 3] // This is a mutation
c[0] = c[0] + 1 // This is a mutation
c[1] = c[1] + 1 // This is a mutation
c[2] = c[2] + 1 // This is a mutation
console.log(c) // [4, 5, 6]
```

Here are the same examples avoiding mutations

```js
let a = 1
let newA = a + 1

let b = { value: "something" }
let newB = { value: "something else", ...b }

let c = [1, 2, 3]
let newC = c.map(x => x + 1) //[4, 5, 6]
```

Note: map, filter, and reduce will always produce new values instead of
mutating the old value, this is part of why they are amazing tools

We can clearly see that in the second example we had to create more variables
and invent more names, but in the long run you'll be able to grasp how this
allows you to write clearer and more debugable code.

One of the most common source of errors in programming happensby sharing a
variable among many functions and mutating it, but this procedure is also a
necessity for most of the programs. Let's learn now how to share a variable
with functions to act as a storage and try to keep our mutations contained so
our program's complexity doesn't outgrow us.

## Scopes and State Management 

Our functions have access to all variables in the scope that it was declared.
Let's see what this means in pratice:

```js
let x = 0

let someFunc = () => {
  console.log(x) // 0
}
```

See how `someFunc` can access `x`. Lets see how this wouldn't be possible

```js
let somefunc = () => {
  let y = 1
}

let otherFunc = () => {
  console.log(y) // y is not defined (undefined)
}
```

`otherFunc` can't acess `y` because its only visible inside `someFunc` scope.
Let's see other example:

```js
let somefunc = () => {
  let otherFunc = () => {
    let z = 2
  }
  console.log(z) // z is not defined (undefined)
}
```

`someFunc` cant aceess `z` because only `otherFunc` can. But now lets make
an example where it works:

```js
let a = 1
let somefunc = () => {
  let b = 2
  let otherFunc = () => {
    let c = 3
    console.log(a) // 1
    console.log(b) // 2
    console.log(c) // 3
  }
}
```

`otherFunc` can acess everything. `someFunc` can acess `a`, and `b`. The rest
of the program will only be able to acess `a`. Lets see how we use this
in pratice:

```js
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
```

The thing to note here is that we cannot access `value` inside our object
without using the functions that we returned. This is a technique that uses
the parent function scope to hold a variable that can be used by all inner
functions but cannot be accessed by outside. This property of sharing scopes
between functions is called "Closure"

# Interacting with the world

to be written yet:

* about async interactions
* npm, node, and how to use other people's
* where to learn more about the tools you've seen here
* where to learn about the ones you didn't

