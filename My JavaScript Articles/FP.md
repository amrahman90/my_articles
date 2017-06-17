**Functional Programming**

[]()Functional
Programming is related with the production of abstraction through clever way of
the combining the functions. In other words we can say that functional
programming is a style of writing programs by simply composing a set of the
functions. 

FP lead to wrap
everything in functions which are small reusable functions and simply call one
after the other to get the results like  (**fnc1.fnc2.fnc3**)
or in a compose fashion, like: **fnc1(fnc2(fnc3()))**.

To write the
programs correctly and efficiently, functions need to follow some of the rules
and should address the key challenges which are as following.

##### The FP Challenges:

If everything can
be done using Functions, There are some considerations which are needed to
address.

1.    
Challenge to handle If-else conditions.

2.  
Challenge to handle Null Exceptions

3.  
How to ensure functions are truly “reusable” and can be
reused anywhere, (**Hint:** **Pure functions,** **referential transparency**)?

4.  
How to ensure the data we pass to it is unchanged so
that we can reuse the data elsewhere(**Hint:** **Pure functions, immutability**)?

5.   
If a function is taking multiple values but chaining can
only pass a single value, how can we still make it part of a chain (**Hint:** “**currying” and “higher-order
functions”**)?

#####  

##### The FP Solution:

Keeping in view of
such issues, fully functional programming languages like haskell provides lot
of tools and concepts from the mathematics like Monads and Functors. 

These concepts can
be implemented by writing libraries. 

#### Fantasy-Land Specs and Functional programming Libraries

Libraries which are used for the features like Functors
, Monads and other, there is need to implement the classes and functions which
lead to provide functionalities like they are in the language like Haskell. 

While Fantasyland Specis one of the
prominent specs that explains that how each Java Scripts classes and functions
should behave.

For example:

A JS class is a
“Functor” if it implements a “map” method. And that map method must work as per
spec (ps:This is simplified version and there are more rules).

Similarly, a JS
class is an “Apply Functor” if it implements “map” and “ap” functions as per
spec.

Similarly, a JS
class is a “Monad” (aka Monad Functor), if implements requirements of
“Functor”, “Apply”, “Applicative”, “Chain” and “Monad” itself (because of the
dependency chain).

_Note: The
dependency may look like inheritance but not necessarily. For example: Monad
implements both “Applicative” and “Chain” specs (in addition to others)._

#### Example 1 — Dealing With Null Checks

**_Use-case:_**_ __We want to show different index webpage depending on the
user’s “**primary”** **language** __(inside user’s prefs, see below). And we need to write **getUrlForUser** __that returns appropriate __URL __from the
list of URLs(**indexURLs**__) for the
user’s (**joeUser**__) **primary** **language**__(“**spanish”**__)._

 

**The
problem is:**** **the
primary language could be null. 

//TODO Write this in Imperative v/s Functional style

const getUrlForUser = (user) =&gt; {

//todo

}

//User object

let joeUser = {

    name: 'joe',

    email: 'joe@abc.com',

    prefs: {

        languages: {

            primary: 'sp',

            secondary: 'en'

        }

    }

};

//Global indexURLs map for different languages

let indexURLs = {

    'en': 'http://abc.com/en',  //English

     'sp': 'http://abc.com/sp', //Spanish

    'jp': 'http://abc.com/jp'   //Japanese

}

//apply url to window.location

const showIndexPage = (url) =&gt; { window.location = url };

 

#####  

##### Solution (Imperative Vs Functional Programming):

 

 

//Imperative:

//Too many if-else and null checks; relying on global indexURLs; decided that "en" urls are default for any country

const getUrlForUser = (user) =&gt; {

  if (user == null) { //not logged in

    return indexURLs['en']; //return default page

  }

  if (user.prefs.languages.primary && user.prefs.languages.primary != 'undefined') {

    if (indexURLs[user.prefs.languages.primary]) {//if translation exists,

      return indexURLs[user.prefs.languages.primary];

    } else {

      return indexURLs['en'];

    }

  }

}

 

//call

showIndexPage(getUrlForUser(joeUser));

 

 

//Functional Programming:

//(Little hard to understand at first but is more robust and bug free)

//FP techniques used: Functors, "Maybe Monad" and "Currying"

const R = require('ramda');

const prop = R.prop;

const path = R.path;

const curry = R.curry;

const Maybe = require('ramda-fantasy').Maybe;

 

const getURLForUser = (user) =&gt; {

    return Maybe(user)//wrap user in a Maybe object 

        .map(path(['prefs', 'languages', 'primary'])) //use Ramda's to grab primary language

        .chain(maybeGetUrl); //pass language to maybeGetUrl &  get url or null Monad

}

 

const maybeGetUrl = R.curry(function(allUrls, language) {//curry to convert this to a single arg func

    return Maybe(allUrls[language]);//return Monad(url | null)

})(indexURLs);//pass indexURLs instead of accessing globally

 

 

function boot(user, defaultURL) {

   showIndexPage(getURLForUser(user).getOrElse(defaultURL));

}

 

boot(joeUser, 'http://abc.com/en'); //'http://abc.com/sp'

##### Functors

Any class / construction function or a datatype that
stores a value and implements “map” method is called a “Functor”.

 

const add1 = (a) =&gt; a + 1;

class MyFunctor { //Custom "Functor"

  constructor(value) {

    this.val = value;

  }

  map(fn) {   //Applies function to this.val + returns new Myfunctor

   return new Myfunctor(fn(this.val));

  }

}

//temp is a Functor instance that's storing value 1

let temp = new MyFunctor(1); 

temp.map(add1) //-&gt; temp allows us to map "add1"

 

##### Monads

Below is a sample implementation so you get an idea of
the internals of the Monad.

 

//Monad - a sample implementation

class Monad {

    constructor(val) {

        this.__value = val;

    }

    static of(val) {//Monad.of is simpler than "new Monad(val)

        return new Monad(val);

    };

    map(f) {//Applies the function but returns another Monad!

        return Monad.of(f(this.__value));

    };

    join() { // used to get the value out of the Monad

        return this.__value;

    };

    chain(f) {//Helper func that maps and then gets the value out

        return this.map(f).join();

    };

     ap(someOtherMonad) {//Used to deal w/ multiple Monads

        return someOtherMonad.map(this.__value);

    }

}

 

 

function Maybe(x) { //&lt;-- main constructor that returns Maybe of Just or Nothing

  return x == null ? _nothing : Maybe.Just(x);

}

 

function Just(x) {

  this.value = x;

}

util.extend(Just, Maybe);

 

Just.prototype.isJust = true;

Just.prototype.isNothing = false;

 

function Nothing() {}

util.extend(Nothing, Maybe);

 

Nothing.prototype.isNothing = true;

Nothing.prototype.isJust = false;

 

var _nothing = new Nothing();

 

Maybe.Nothing = function() {

  return _nothing;

};

 

Maybe.Just = function(x) {

  return new Just(x);

};

 

Maybe.of = Maybe.Just;

 

Maybe.prototype.of = Maybe.Just;

 

 

// functor

Just.prototype.map = function(f) { //Doing "map" on Just runs the func and returns Just out of the result

  return this.of(f(this.value));

};

 

Nothing.prototype.map = util.returnThis; // &lt;-- Doing "Map" on Nothing doesnt do anything

 

Just.prototype.getOrElse = function() {

  return this.value;

};

 

Nothing.prototype.getOrElse = function(a) {

  return a;

};

 

module.exports = Maybe;

 

//Step 1. Instead of..

if (user == null) { //not logged in

    return indexURLs['en']; //return default page

  }

 

//Use:

 Maybe(user) //Returns Maybe({userObj}) or Maybe(null). i.e. data wrapped INSIDE "Maybe"

 

 

 

//Step 2. Instead of..

 if (user.prefs.languages.primary && user.prefs.languages.primary != 'undefined') {

    if (indexURLs[user.prefs.languages.primary]) {//if translation exists,

      return indexURLs[user.prefs.languages.primary];

      

//Use:

//a library that knows how to deal w/ data inside Maybe like Ramda's map.path:

 &lt;userMaybe&gt;.map(path(['prefs', 'languages', 'primary']))

      

   

      

//Step 3. Instead of..

 return indexURLs['en']; //hardcoded default values

  

//Use:

//all Maybe libs provide 'orElse' or 'getOrElse' method that'll return either actual data or return "default value"

&lt;userMayBe&gt;.getOrElse('http://abc.com/en')      

 

Let’s look at our
solution again:

 

//The below gist shows how to take care of global variables and also make funcs chainable

 

//Global indexURLs map for different languages

let indexURLs = {

    'en': 'http://abc.com/en',  //English

    'sp': 'http://abc.com/sp', //Spanish

    'jp': 'http://abc.com/jp'   //Japanese

}

 

//Imperative

const getUrl = (language) =&gt; allUrls[language]; //Simple, but error prone and impure (accesses global variable)

 

 

//Functional Programming

 

//Before currying:

const getUrl = (allUrls, language) =&gt; {

    return Maybe(allUrls[language]);

}

 

//After currying:

const getUrl = R.curry(function(allUrls, language) {//curry to convert this to a single arg func

    return Maybe(allUrls[language]);

});

 

const maybeGetUrl = getUrl(indexURLs) //Store global value in the 'curried' function.

 

//From this point, maybeGetUrl needs only one argument(language). So we can now chain this like:

maybe(user).chain(maybeGetUrl).bla.bla

 

#### **Either Monad**

Either Monads are
great for dealing with multiple functions 

//imperative

//Returns error or price including tax 

const tax = (tax, price) =&gt; {

  if (!_.isNumber(price)) return new Error("Price must be numeric");

 

  return price + (tax * price);

};

 

//Returns error or price indluding discount

const discount = (dis, price) =&gt; {

  if (!_.isNumber(price)) return (new Error("Price must be numeric"));

 

  if (price &lt; 10) return new Error("discount cant be applied for items priced below 10");

 

  return price - (price * dis);

};

 

const isError = (e) =&gt; e && e.name == 'Error';

 

const getItemPrice = (item) =&gt; item.price;

 


const showTotalPrice = (item, taxPerc, disount) =&gt; {

  let price = getItemPrice(item);

  let result = tax(taxPerc, price);

  if (isError(result)) {

    return console.log('Error: ' + result.message);

  }

  result = discount(discount, result);

  if (isError(result)) {

    return console.log('Error: ' + result.message);

  }

  //display result

  console.log('Total Price: ' + result);

}

 

let tShirt = { name: 't-shirt', price: 7 };

let pant = { name: 't-shirt', price: '8 dollars' };

let chips = { name: 't-shirt', price: 5 }; //less than 10 dollars error

 

showTotalPrice(tShirt) // Total Is: 9.075

showTotalPrice(pant)   // Error: Price must be numeric

showTotalPrice(chips)  //Error: discount cant be applied for items priced below 10