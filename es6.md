MISC
```
  Browser Sync
```


New String Methods:
```
.startsWith();
.endssWith();
.includes();
.repeat();
```
Destructure and Name:

```
const matt = {
  First: 'Matt',
  Last: 'Coady',
  Social: {
    Twitter: 'twitter.com/mattcoady',
    Facebook: 'facebook.com/mattcoady'
  }
}

Const { twitter: tweet, facebook: fb} = matt.social;
```

Destructure Defaults:
```
Const settings = {width: 300, color: 'black'};
Const { width = 100; height = 100, color = 'blue'} = settings;
// width = 300, height = 100, color = black
```
Destructure Array:
```
Const details = ['Matt', 32, 'mattcoady.me'];
Const [name, age, site] = details;

Const data = 'basketball,sports,90210,23';
Const [sport, category, sku, inventory] = data.split(',');

Rest Opertator

Const team = ['matt','harry','sarah','keegan','riker'];
Const [captain, assistant, ...players] = team;

// players = sarah, keegan, riker
```

For Of Loop

```

const cuts = ['chuck','brisket','shank','short rib'];

for (const cut of cuts){
  console.log(cuts);
}

// can use break; or continue;
// break; ends the loop
// continue; ends that iteration but continues the loop 

```

Destructured For Of

```
for (const [i, cut] of cuts.entries()){
  console.log(i, cut);
}
```

Default Function Args

```
function calcBill(total, tax = 0.12, tip = 0.15){
  return total + (total * tax) + (total * tip);
}

const totalBill = calculateBill(100, undefined, 0.25);
console.log(totalBill);
```

Object Function Shorthand

```
const person = {
  age() {
    return 32;
  }
}

person.age(); //32
```

For Of Loop iterator

```
const cuts = ['Chuck', Brisket, 'Shank', 'Short Rib'];

for(const [i, cut] of cuts.entries()){
  console.log(i, cut);
}
```

Array .from() and .of()

```
// From
const people = document.querySelectorAll('.people');
//const peopleArray = Array.from(people);
//const names = peopleArray.map(person => person.textContent);
const peopleArray = Array.from(people, person => {
  console.log(person);
  return person.textContent;
});
console.log(peopleArray); // ["Matt", "Coady", "Awesome"];

// Of
const ages = Array.of(43,16,74,46,24,68);
console.log(ages); //[43,16,74,46,24,68];

```

Find

```
const posts = [
     {
        "code":"BAcyDyQwcXX",
        "caption":"Lunch #hamont",
        "likes":56,
        "id":"1161022966406956503",
        "display_src":"https://scontent.cdninstagram.com/hphotos-xap1/t51.2885-15/e35/12552326_495932673919321_1443393332_n.jpg"
     },
     {
        "code":"BAcJeJrQca9",
        "caption":"Snow! ⛄️🌨❄️ #lifewithsnickers",
        "likes":59,
        "id":"1160844458347054781",
        "display_src":"https://scontent.cdninstagram.com/hphotos-xaf1/t51.2885-15/e35/12407344_1283694208323785_735653395_n.jpg"
     },
     {
        "code":"BAF_KY4wcRY",
        "caption":"Cleaned my office and mounted my recording gear overhead. Stoked for 2016!",
        "likes":79,
        "id":"1154606670337393752",
        "display_src":"https://scontent.cdninstagram.com/hphotos-xpf1/t51.2885-15/e35/923995_1704188643150533_1383710275_n.jpg"
     }
 ];
 
 const post = posts.find(post => post.code === 'BAcJeJrQca9');
 const postIndex = posts.findIndex(post => post.code === code); //1
 
```

Some

```
  const ages = [32,15,19,12];
  const adultPresent = ages.some(age => age >= 18); //true
  const oldEnough = ages.every(age => age >= 18); //false
```

Spead operator

```
  ['matt']; // ['matt'];
  [...'matt'] // ['m','a','t','t'];

  const featured = ['Deep Dish', 'Peperoni', 'Hawaiian'];
  const specialty = ['Meatzza', 'Spicy Mama', 'Margherita'];
  
  const pizzas = [...featured, 'veggie', ...specialty];
  //[
  //  'Deep Dish', 
  //  'Peperoni', 
  //  'Hawaiian', 
  //  'veggie', 
  //  'Meatzza', 
  //  'Spicy Mama', 
  //  'Margherita'
  //];
  
  const deepDish = {
    pizzaName: 'Deep Dish',
    size: 'Medium',
    ingredients: ['Marinara', 'Italian Sausage', 'Dough', 'Cheese']
  };
  
```

Push Spread

```
  const inventors = ['einstein','newton','galileo'];
  const newInventors = ['musk','jobs'];
  inventors.push(...newInventors);
  //['einstein','newton','galileo','musk','jobs'];
```

Spread Function

```
  const name = [`matt`, `coady`];
  function sayHi(first,last){
    alert(`Hey there ${first} ${last}`);
  }
  
  sayHi(...name);
```

Spread Rest

```
  function convertCurrency(rate, ...amounts){
    return amounts.map(amount => amount * rate);
  }
  
  const amounts = convertCurrency(1.54, 10, 23, 52);
  // [15.4, 35.42, 80.08];
  
  //////////
  
  const runner = ['Matt', 1325, 5, 3, 2.2, 7, 5];
  
  const [name, id, ...runs] = runner;
  console.log(name, id, runs);
```

Object Shorthand

```
  const modal = {
    create(selector){},
    open(selector){},
    close(selector){},
  }
```

Promise Resolve in Function

```
function hydrateAuthor(post) {
  return new Promise((resolve, reject) => {
    const authorDetails = authors.find(person => person.name === post.name);
    if(authorDetails){
      post.author = authorDetails;
      resolve(post);
    } else {
      reject(Error('Can not find the author'));
    }
  });
}
```

Promise All

```
  Promise.
    .all([weather, tweets]) //will wait until both load
    .then(response => {
      console.log(response);
    })
```

Classes

```

class Animal {
  constructor(name){
    this.name = name;
    this.thirst = 100;
    this.belly = [];
  }
  
  drink(){
    this.thirst -= 10;
    return this.thirst;
  }
  
  eat(food){
    this.belly.push(food);
    return this.belly;
  }
}

// The Dog class
class Dog extends Animal {
  // this is what you pass in and set
  // const james = new Dog('James', 'Boston Terrier');
  constructor(name, breed){
    // Call Animal class first and get everything from it
    // Include name since it's a shared property
    super(name);
    this.name = name;
    this.breed = breed;
  }
  
  // james.bark(); => "bark bark"
  bark(){
    console.log('bark bark');
  }
  
  // Dog.info();
  static info() {
    console.log("Dogs are awesome");
  }
  
  // james.description
  // "james is a boston terrier type of dog"
  get description() {
    console.log(`${this.name} is a ${this.breed} type of dog`)
  }
  
  //james.nicknames = '         james    ';
  set nicknames(value){
    this.nick = value.trim();
  }
  
  //james.nicknames; => 'JAMES'
  get nicknames() {
    return this.nick.toUppercase();
  }
}
```