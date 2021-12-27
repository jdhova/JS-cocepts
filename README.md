# Basic JS concepts

## JS-Array& String Helpers

### https://www.w3schools.com/jsref/jsref_sort.asp

### concat() in Array

```
const name = [ 'jude']
const lastname = [ 'okagu']
const job = ['developer']

const fullname1 = name.concat(lastname,job)
const fullname2 = `${name},${lastname},${job}`

console.log(fullname1)
console.log(fullname2)


```

### copyWithin() in Array

```
  const cities = ['Toronto', 'Vancouver', 'Montreal', 'Baltiore', 'Ottawa', 'Calgary'];

 const a  = cities.copyWithin(3,1);
console.log(a)  //  'Toronto','Vancouver','Montreal', 'Vancouver','Montreal', 'Baltiore'

 const names = ['Juud', 'Grace', 'Kevin', 'Dan', 'Don', 'Joe'];

const b  = names.copyWithin(3,2);
console.log(b)  //  [ 'Juud', 'Grace', 'Kevin', 'Kevin', 'Dan', 'Don' ]


```

### .entries() .keys() in Arrays returns a function which can be looped over...

```
const names = ["Jude", "David", "Jane", "Grace"];
const n = names.entries();
for (let x of n) {
  console.log(x) // [ 0, 'Jude' ] [ 1, 'David' ] [ 2, 'Jane' ] [ 3, 'Grace' ]

}

const keys = names.keys();
for(let x of keys){
  console.log(x) // 0,1,2,3
}
for(let n in names) {
  console.log(n) // 0,1,2,3
}


for(let x of names.values()){
  console.log(x) // Jude,David,Jane,Grace
}
for(let n in names) {
  console.log(names[n]) // Jude,David,Jane,Grace
}


```

### In Summary

```
const names = ["Jude", "David", "Jane", "Grace"];
for in returns keys
for off retuens values
.entries() retuens keys and value pair

```

### fill() push() pop() shift() unshift() slice() splice() sort() valueOf() indexOf() includes() in Arrays

```
const names = ["Juud", "Dave", "Grace", "Phil"];
```

```
names.fill("Grace") ["Grace", "Grace", "Grace", "Grace"];
```

```
names.pop() // returns Phil
```

```
names.push("Jane")
console.log(names)
[ 'Juud', 'Dave', 'Grace', 'Phil', 'Jane' ]
```

```
names.shift() //returns  Juud
```

```
names.unshift("Jane")
console.log(names)
[ 'Jane','Juud', 'Dave', 'Grace', 'Phil']
```

```
cost n = names.slice(1,3) // ["Dave", "Grace"]
```

```
names.splice(1, 3) // ['Dave', 'Grace', 'Phil']
```

```
const s = names.sort() // [ 'Dave', 'Grace', 'Juud', 'Phil' ]
```

```
names.valueOf() // [ 'Jane','Juud', 'Dave', 'Grace', 'Phil']
```

```
names.indexOf('Grace') // 2
```

```
names.includes('Juud') // true

```

## High Order Array Methods

### find() every() filter() some() map() findIndex() indexOf() forEach() Arrays.. takes in a function

```
const names = ['juud','Grace', 'David','Daniel', 'Mike']
```

```
const find = names.find( n =>  n.length === 5 )
console.log(find)  Grace // returns the first only
```

```
const filt = names.filter(f => f.length < 5)
console.log(filt)  [ 'Juud', 'Mike' ] // returns all
```

```
const ev = names.every(n => n.length > 2) // true
const ev = names.every(n => n.length < 2) // false
```

```
const sm = names.some(n =>  n.length > 6)
console.log(sm) // false // returns boolean


const sm = names.some(n =>  n.length > 5)
console.log(sm) // true // returns boolean
```

```
const maps = filt.map(j => ` <li>${j}</li>`)
console.log(maps)  [ ' <li>Juud</li>', ' <li>Mike</li>' ]
```

```
const age = [22,33,11,43]
const y = age.findIndex(j=> j === 43)
console.log(i)  // 3

```

```s
names.forEach((e,i,r) =>  {
console.log(`${e} is at index,${i}`,r)

juud is at index,0 [ 'juud', 'Grace', 'David', 'Daniel', 'Mike' ]
Grace is at index,1 [ 'juud', 'Grace', 'David', 'Daniel', 'Mike' ]
David is at index,2 [ 'juud', 'Grace', 'David', 'Daniel', 'Mike' ]
Daniel is at index,3 [ 'juud', 'Grace', 'David', 'Daniel', 'Mike' ]
Mike is at index,4 [ 'juud', 'Grace', 'David', 'Daniel', 'Mike' ]

```

### Array.from() .join().toString()

```
const str = 'Juud'
const s = Array.from(str)
console.log(s) // [j'u'u'd]  String to Array

const names = ['Juud', 'Grace', 'David']
names.join() Juud, Grace,David // Array to String
names.toString()  Juud, Grace,David // Array to String

const newFrom = Array.from({length: 5}, (i='Juud',a) => {
 console.log(a*3) // 0 3 6 9 12
})

 const m = Array.from ({length: 5},(i,a)=>{
  console.log((a+5) * (a+5)) // 25 36 49 64 81
})

```

### Capitalize first letter in Array

```
const name = ["Juud"]
const g = name.toString().slice(0,1).toUpperCase()
const f = name.toString().slice(1)
console.log(g+f) // Juud

 const names = ['Juud', 'don', 'grace']

names.forEach((a,i,r) => {
  console.log (a.slice(0,1).toUpperCase() + a.slice(1))
}) 'Juud', 'Don', 'Grace'

for(let n of names) {
console.log (n.slice(0,1).toUpperCase() + n.slice(1,n.length-1)+ n.slice(n.length-1).toUpperCase())
}

'JuuD', 'DoN', 'GracE'

```

### reduce() in Arrays

```
const numbers = [175, 50,50, 10,10,10,10,10];
numbers.reduce((v,a) =>{
return v-a // 25
})

const numbers = [50,50, 10,10,10,10,10,175];
numbers.reduceRight((v,a) =>{
return a-v // 25
})

```

## Strings

### charAt()& charCodeAt() in String

```
let city = 'Toronto'
console.log(city.charAt(2)) // r
console.log(city.charAt(1)) // o
console.log(city.charAt(0)) // T
```

```
let name = 'AAaa'
console.log(name.charCodeAt(0)) // 65
console.log(name.charCodeAt(1)) // 65
console.log(name.charCodeAt(2)) // 97
console.log(name.charCodeAt(3)) // 97

```

### includes() indexOf() search() length match(/u/) repeat() replace() slice() split() endsWith() startsWith() toLowerCase() toUpperCase()

```
const family = "Juud Grace Muna Don Uzo Gift "
```

```
family.includes('Grace') // Returns true
```

```
family.indexOf(Grace) // 5
family.search(Grace) // 5
family.indexOf("Muna") // 2
family.search("Muna") // 2
```

```
family.length  // 28
```

```
family.match(/u/g) // [ 'u', 'u', 'u' ]
family.match(/Grace/g) [ 'Grace' ]
```

```
family.repeat(2) //Juud Grace Muna Don Uzo Gift Juud Grace Muna Don Uzo Gift

```

```
family.replace('Juud', 'Ikechukwu') // Ikechukwu Grace Muna Don Uzo Gift
```

```
family.slice(0, 6)  // Juud G
family.substr(0, 6) // Juud G
family.substring(0, 6) // Juud G

family.slice(0, 7) // Juud Gr
family.substr(0, 7) // Juud Gr
family.substring(0, 7) // Juud Gr
```

```
family.split(' ')  [
  'Juud', 'Grace',
  'Muna', 'Don',
  'Uzo',  'Gift',
  ''
]

```

```
let name  = 'Juud'
name.endsWith(d) // true
name.endsWith(D) // false

let name  = 'Juud'
name.startsWith(j) // true
name.startsWith(J) // false

```

```
family.toLowerCase() // juud grace muna don uzo gift
family.toUpperCase() // JUUD GRACE MUNA DON UZO GIFT
```

```
str.trim() // removes spaces after string
```

### localeCompare

```
let str1 = "56";
let str2 = "23";
str1.localeCompare(str2) //1

let str1 = "23";
let str2 = "56";
str1.localeCompare(str2) // -1

let str1 = "23";
let str2 = "23";
str1.localeCompare(str2) // 0

```

## Objects

```
const person = {
fname:" Jude",
lname:" Hova",
age: 23,
address:[
{home: '11 Humber Blvd Toronto'},
{office: '21 downtown Blvd Toronto'},
{home: '12A Accord Blvd Toronto'}
],
fullName: function() {
    return this.fname + " " + this.lname;
  }
  }

person.fullName()
person.address[home]

```

```
person.age = 33
delete person.fname;


const person = {
lname:" Hova",
age: 33,
address:[
{home: '11 Humber Blvd Toronto'},
{office: '21 downtown Blvd Toronto'},
{home: '12A Accord Blvd Toronto'},
fullname: 'JUDE HOVA'
]};

```

```
for (let n in person){
  console.log(person[n])
}
---------
33
[
  { home: '11 Humber Blvd Toronto' },
  { office: '21 downtown Blvd Toronto' },
  { home: '12A Accord Blvd Toronto' },
]
fullname: 'JUDE HOVA'
```

```
for (let n in person.address){
  console.log(person.address[n])
}
// returns a string...
-------
{ home: '11 Humber Blvd Toronto' }
{ office: '21 downtown Blvd Toronto' }
{ home: '12A Accord Blvd Toronto' }

```

```

const person = {
fname:" Jude",
lname:" Hova",
age: 23,
address:[
{home: '11 Humber Blvd Toronto'},
{office: '21 downtown Blvd Toronto'},
{home: '12A Accord Blvd Toronto'},

]}

const m = Object.keys(person);
console.log(m) //[ 'fname', 'lname', 'age', 'address' ]

const n = Object.values(person);
console.log(n)  [
  ' Jude',
  ' Hova',
  23,
  [
    { home: '11 Humber Blvd Toronto' },
    { office: '21 downtown Blvd Toronto' },
    { home: '12A Accord Blvd Toronto' }
  ]
]

// returns an array of strings
```

### Object Getters and Setters

#### Getters

```
const person = {
firstName: "Grace",
lastName: "Juud",
city: "Toronto",
get city() {
return this.city;
}
};

console.log(person.city) // 'Toronto'
```

#### Setters

```
const person = {
firstName: "Grace",
lastName: "Juud",
city: "",
set city(city) {
this.city = Qubec;
}
};
console.log(person.city) // Qubec
```

### Object Oriented Programing.. Managing Objects Similar to Inheritance

```

const person = {
  firstName: "John",
  lastName : "Doe",
  sex : "male"
};

```

```
const emeka =  Object.create(person)
 const e = emeka.firstName = 'emekaa'

console.log(e) // emekaa
```

```

Object.defineProperties(person,{
  firstName:{
  value: 'juud',
    writable: true
  },
  lastName:{
    value: 'okagu',
    writable: false
  }
})
```

```
Object.defineProperty(person, 'firstName', {
  value: 'jay',
    writable: false

})

person.firstName = 'Grace' // immutable
person.lastName = 'Amara' // immutable

console.log(person) // { firstName: 'jay', lastName: 'okagu', sex: 'male' }

```

```
Object.getOwnPropertyDescriptor(person, 'firstName')
{ value: 'jay', writable: false, enumerable: true, configurable: true }

```

```

const toyota = {name:''};
const honda = {name:''};
const bmw = {name: ''};

// Create a new Map
const cars = new Map([
  [toyota, 500],
  [honda, 300],
  [bmw, 200]
]);

cars.get(toyota) // 500

```

### Protypical Inheritance with Classes...

```
class Person {

   constructor(name){
     this.name = name

   }

   code(){
     console.log(`${this.name} can code` )
   }
   sleep(){
     console.log(`${this.name} can sleep` )
   }
   eat(){
     console.log(`${this.name} can eat` )
   }

 }


 class Person1 extends Person{
   drinks() {
     console.log(`${this.name} can drink`)
   }

 }

  class Person2 extends Person{
   cook() {
     console.log(`${this.name} can cook`)
   }

 }

 const grace = new Person1('Grace')
    grace.code() // Grace can code
    grace.sleep() // Grace can sleep
    grace.eat() // // Grace can eat
    grace.drinks()


 const jane = new Person2('Jane')
    jane.code() // jane can code
    jane.sleep() // jane can sleep
    jane.eat()
    jane.cook()    // Jan can code

 jane.drink()   // Jan can drink is not poissible
 grace.cook()   // Grace can drink is not poissible

```

### Protypical Inheritance with Constructor functions

```
function Duties (duty1,duty2,duty3) {
    this.duty1 = duty1
    this.duty2 = duty2
    this.duty3 = duty3
}

Duties.prototype.duty4 = 'travel'

const grace = new Duties('code','cook','eat')
const jane = new Duties('work','sing','drink')

grace.duty4 // travel

```

## Execution Contest and Global Execution Contest.

#### Code in the Global Contest executes first and then put in a stack before the Execution contect in the function is run.

```
const b = () => {
  let x;
  console.log(x);
  ///Execution Contest
};

const a = () => {
  let x = 2;
  console.log(x);
  b();
  //Execution Contest
};


//Global Execution Contest.

let x = 1;
console.log(x);
x = 2
a();
console.log(x);

```

### In Scoping the Variable automatically takes the Global context if varaible is not assigned within the "Scope of the particular function"..

```
const b = () => {
  console.log('3rd call=3',x)
  // global scope
}

const a = () => {
  let x = 20
  console.log('sec call = 20',x)
  b()
  console.log('last call =20',x)
  // function scope
}

let x = 3
console.log(x,'first call =3')
a()
// global context

```

### An objerct is also known as a collection of key value pairs.."collection of variables"...

### Symbol variable **_ still new_**

```
let sym = Symbol('jjj')
console.log(sym)
```

### Operators in JS

```
const a = 'Juud' > 'boy'
console.log(a)
// true

const a = 3 < 2
console.log(a)
// false

const a = 3+2
console.log(a)
// 5

```

### BODMAS in JS

#### https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence

```
let a = 4 + 3 * 10
console.log(a)
// a = 34

let a = 'Juud', b = 'code', c = 'sleep'
 a = b = c

 // b = c runs first

console.log(a) // sleep
console.log(b) // sleep
console.log(c) // sleep

 b = c = a

 // c = a runs first

console.log(a) // Juud
console.log(b) // Juud
console.log(c) // Juud

 a = c = b

 // c = a runs first

console.log(a) // code
console.log(b) // code
console.log(c) // code
```

```
console.log(3 >2 > 1) // false
left to right
first it checks 3 > 2 true
true > 1 which is 1 > 1 // false

console.log(3 >2 > 0) // true
left to right
first it checks 3 > 2 true
true > 0 ? which is 1 > 0 // true

```

### President logging the last letter in a string

```
let x = ('Juud','fill','give','code','sleep',null)
console.log(x) // null

let x = ('Juud','fill','give','code','sleep'||null)

console.log(x) // sleep

```

### Passing a default value to a function using the ||...

```
const info=(name) => {
  name = name || 'default info here'
  console.log(`hello, ${name} `)
}

info('Juud')
info()

```

### Nesting Objects in Objects...

```
const person = {
  firstname:'Juud',
   lasttname:'Grace',
   sex:'female',
   address :{
     main:'222 killon Blvd Humber',
     street:{

       previousstreet:'12 killon Blvd Humber',
       currentstreet: '20 Jameson Blvd Humber',

     },
     city: 'Humber', surburb :{
        town: 'North Humber'
     },
     state: 'Toronto',
   }
}

console.log(person)

```

### Functions as Objects...

```
const name = () => {
  console.log('ddd')
}

name.first = 'Mike'
name.last = 'cole'

console.log(name.first) 'Mike'
console.log(name.last) 'cole'
console.log(name) { first: 'Mike', last: 'cole' }

```

### Relationship by Primitive Value ** person2 cannot over-writes person1 **.

#### Immutable reason every new variable gets a new address in call stack

```
let person1 = 'Grace'

let person2 = person1

person1 = 'Jude'

console.log(person1). // Jude
console.log(person2) // Grace

```

### Relatiosnhip by Refrence Value which allows you mutate an object value pairs on the fly ** person2 over writes person2 **.

#### Mutable

```
const person1 = {
  name: 'Grace',
  age: 22,
  sex: 'female'
}

const person2 = person1

person2.age = 20

console.log(person1) // { name: 'Grace', age: 20, sex: 'female' }
console.log(person2) // { name: 'Grace', age: 20, sex: 'female' }


```

### Closures => Functions in functions call back functions...

##### In closures the outer function has access to the values produced by the inner function..

```
const person = (sex) => {

  return function (firstname, lastname) {
    if ( sex === 'boy') {
     console.log(`my name is ${firstname} ${lastname} and i am a man`)
    }

    if (sex === 'girl') {
      console.log(`my name us ${firstname} ${lastname} and I am a woman`)
    }
  }
}

const Juud =  person('boy')
const grace = person ('girl')

Juud('jude','okagu')
grace('grace','igba')

```
