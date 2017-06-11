# OOP in JavaScript

Object Oriented Programming is most popular way of programming era. Before starting with OOP, make a list of instructions that will be implemented in steps. But in case of OOP we have to deal with their Objects and find how those objects can interact with each other&#39;s.

# Object Oriented Programming Concepts

#

-Object
-Class
-Constructor
-Inheritance
-Encapsulation
-Abstraction
-Polymorphism

#

##
# Preparing the workspace

#

We have to create a new file with a name &quot;oop.html&quot; and write a code on it. We will have to write all the JavaScript&#39;s code in the file.



&lt;html&gt;

&lt;head&gt;

&lt;title&gt;OOP in JavaScript &lt;/title&gt;

&lt;/head&gt;

&lt;body&gt;

&lt;script type=&quot;text/javascript&quot;&gt;

      //Write the simple code there.....

&lt;/script&gt;

&lt;/body&gt;

&lt;/html&gt;

#
# 1) Object

Any entity which is considered in a real time is known as an Object and every object have a multiple functions and properties. As example, we have to consider a person as our object, then the person has some properties like his name, his age, his diet etc., and some of the functions like eat, talk, walk, drink, etc. now we see that how we create an object in  our JavaScript: here is some multiple ways to create the objects.

//1)Creating by using a new keyword

function Person() {}

var obj = new Person();

//2)Creating through Object.create

var obj = Object.create(null);

//3) Creating Object via literal

var obj = {};

#
# Example

&lt;!DOCTYPE html&gt;

&lt;html&gt;

&lt;body&gt;

&lt;p id=&quot;myid&quot;&gt;&lt;/p&gt;

&lt;script&gt;

var personp = {firstName:&quot;Muhammad&quot;, lastName:&quot;MeerHazaar&quot;, countryname: &quot;Pakistan&quot;};

document.getElementById(&quot;myid&quot;).innerHTML = personp.countryname;

&lt;/script&gt;

&lt;/body&gt;

&lt;/html&gt;

#
# 2) Class

We have a slight change in the case of class because we cannot use any of classes in the JavaScript and this is done because it is not more than a Prototype based languages. But here we have a feature to simulate these class based concepts by using a JavaScript&#39;s functions.

function Personp() {

    //Property

    this.name = &quot;meer&quot;;

    this.age = &quot;25&quot;;

    //function

    this.hello = function() {

        return this.name + &quot; hello world&quot;;

    }

}

//Creating a personp&#39;s instance

var p = new Personp();

alert(p.hello());

#
# Example

We have to Creating a new class (declarative-form)

class Polygon1 {

 constructor() { }

  constructor(height1, width1) {

    this.name1 = &#39;Polygon1&#39;;

    this.height1 = height1;

    this.width = width1;

  }

  // declaration

  sayName1() {

    ChromeSamples.log(&#39;Hi, I am a &#39;, this.name1 + &#39;.&#39;);

  }

  sayHistory1() {

    ChromeSamples.log(&#39;&quot;Polygon1&quot; is derived from the Greek polus (many) &#39; +

&#39;and gonia (angle).&#39;);

  }

}

let p1 = new Polygon1(300, 400);

p.sayName1();

ChromeSamples.log(&#39;The width of this polygon is &#39; +p1.width1);

#
#   3) Constructor

Truly, a Constructor is a formal model that often comes under a Class. The constructors are mostly used to assign different values to their properties of the given Classes while they are creating objects by using the new operators.  In our code we will use a name and age&#39;s properties for  **Personp class** , and then we will assigning a value while creating these new objects for  **Personp class**  as mentioned.

function Personp(name1, age1) {

    this.name1 = name;

    this.age1 = age;

    this.sayHi1 = function() {

        return this.name1 + &quot; Says Hi1&quot;;

    }

}

var p1 = new Person1(&quot;meer&quot;, 23);

alert(p.sayHi1());

var p1 = new Person1(&quot;khan&quot;, 23);

alert(p.sayHi1());

#
# Example

&lt;!DOCTYPE html&gt;

&lt;html&gt;

&lt;body&gt;

&lt;p id=&quot;myid&quot;&gt;&lt;/p&gt;

&lt;script&gt;

var a = new Object();   // A new Object object

var b = new String();   // A new String object

var c = new Number();   // A new Number object

var d = new Boolean();  // A new Boolean object

var e = new Array();    // A new Array object

var f = new RegExp();   // A new RegExp object

var g = new Function(); // A new Function object

var h = new Date();     // A new Date object

document.getElementById(&quot;myid&quot;).innerHTML =

&quot;a: &quot; + typeof a + &quot;&lt;br&gt;&quot; +

&quot;b: &quot; + typeof b + &quot;&lt;br&gt;&quot; +

&quot;c: &quot; + typeof c + &quot;&lt;br&gt;&quot; +

&quot;d: &quot; + typeof d + &quot;&lt;br&gt;&quot; +

&quot;e: &quot; + typeof e + &quot;&lt;br&gt;&quot; +

&quot;f: &quot; + typeof f+ &quot;&lt;br&gt;&quot; +

&quot;g: &quot; + typeof g + &quot;&lt;br&gt;&quot; +

&quot;h: &quot; + typeof h + &quot;&lt;br&gt;&quot;;

&lt;/script&gt;

&lt;h2&gt;here there is no need to use a String() method, Number() method, Boolean()method , Array() method, and RegExp()method&lt;/h2&gt;

&lt;p&gt;Read this JavaScript tutorials.&lt;/p&gt;

&lt;/body&gt;

&lt;/html&gt;

#
# 4) Inheritance

Inheritance is like a method of gaining the given functions and properties of one of each class to the other classes. As like, let us we have a &quot;Student1&quot; Class, here is the Student1 also has a property named a name&#39;s and age&#39;s which we have used in Person1 class. So this case is much better to gaining the property of the Person1 instead of reconstructing the property.

 function Student1() {}

Student1.prototype = new Person1();

Student1.prototype = Object.create(Person1);

var stobj1 = new Student1();

alert(stobj1.sayHi1());

#
# Example

 var ClassA1 = function() {

    this.name1 = &quot;class A1&quot;;

}

var a1 = new ClassA1();

ClassA1.prototype.print = function() {

    console.log(this.name1);

}

A1.print();

var ClassA1 = function() {

    this.name1 = &quot;class A1&quot;;

}

ClassA1.prototype.print = function() {

    console.log(this.name1);

}

var a1 = new ClassA1();

a1.print();

var inheritsFrom = function (child1, parent1) {

    child1.prototype = Object.create(parent1.prototype);

};

var ClassB1 = function() {

    this.name1 = &quot;class B1&quot;;

    this.surname1 = &quot;I&#39;m the child&quot;;

}

inheritsFrom(ClassB1, ClassA1);

var b1 = new ClassB1();

b1.print();

ClassB1.prototype.print = function() {

    ClassA1.prototype.print.call(this);

    console.log(this.surname1);

}

var ClassC1 = function () {

    this.name1 = &quot;class C1&quot;;

    this.surname1 = &quot;I&#39;m the grandchild&quot;;

}

inheritsFrom(ClassC1, ClassB1);

ClassC.prototype.foo = function() {

    }

ClassC1.prototype.print = function () {

    ClassB1.prototype.print.call(this);

    console.log(&quot;its working&quot;);

}

var c1 = new ClassC1();

c1.print();

#
# 5) Encapsulation

Before we are going to the concepts of Encapsulation and like Abstraction firstly we have to need the sound knowledge of what the type of Data that is being Hide and how we can gaining this by JavaScript. Date hiding is a method of protects the data from retrieving it outside of this scope. As example, In Person1 class, we have a Date of Birth property which should be protected.

function Person1() {

    var dob1 = &quot;12 June 2014&quot;;

    return {

        age: &quot;26&quot;,

        name: &quot;meer&quot;,

        getDob1: function() {

            return dob1;

        }

    }

}

var pobj1 = new Person1();

console.log(pobj1.dob1);

console.log(pobj1.getDob1());

#
# Example



&lt;html&gt;

&lt;body&gt;

&lt;script&gt;

   (function() {

      var x1 = &#39;&#39;;

      function myFunction 1() {

         alert(&#39;Hello1: &#39; + x1);

      }

      x = &#39;Bob&#39;;

      myFunction();

      alert(typeof x1);

      alert(typeof myFunction1);

   })();

   alert(typeof x1);

   alert(typeof myFunction1);

&lt;/script&gt;

&lt;script src=&quot;other-javascript1.js&quot;&gt;&lt;/script&gt;

&lt;/body&gt;

&lt;/html&gt;



#
# Example

function UserProfile1(username, password)

{

  this.username1 = username1;

  this.password1 = password1;

  this.authenticate1 = function()

  {

    if(this.username1 == &#39;MuhammadMeer1&#39; &amp;&amp; this.password1 == &#39;khan1&#39;)

    {

      return true;

    }

    return false;

  }

}

&lt;html&gt;

&lt;head&gt;

&lt;title&gt;OOP concept in JavaScript using Encapsulation&lt;/code&gt;

&lt;script language=&quot;&#39;javascript&#39;&quot; type=&#39;text/javascripts&#39; src=&#39;UserProfile.js&#39;&gt;&lt;/script&gt;

&lt;script language=&quot;&#39;javascript&#39;&quot; type=&#39;text/javascripts&#39;&gt;

 /\*\*

 \* (C) 2017,Muhammad meer hazaar, liaison services Ltd

 \* http://www.jobsprtalpakistan.com

  \* http://liaisonservices.com

 \*/

function validateUser1()

 {

 var uname1 = document.getElementById(&#39;u1&#39;).value;

 var pwd1 = document.getElementById(&#39;p1&#39;).value;

var e1 = document.getElementById(&#39;result1&#39;);

var u1 = new UserProfile(uname1, pwd1);

 var result1 = u1.authenticate1();

 e.innerHTML = &#39;Result1: &#39; + result1;

       }

&lt;/script&gt;

&lt;/head&gt;

&lt;body&gt;

 Username1: &lt;input type=&#39;text1&#39; name=&#39;u&#39;1 id=&#39;u1&#39; /&gt;

&lt;br/&gt;

 Password1: &lt;input type=&#39;password1&#39; name=&#39;p1&#39; id=&#39;p1&#39; /&gt;

&lt;br/&gt;

&lt;button onclick=&#39;validateUser1(); return false;&#39;&gt;Login1&lt;/button&gt;

&lt;div id=&#39;result1&#39;&gt;

&lt;/div&gt;

&lt;/body&gt;

&lt;/html&gt;



#
# 6) Abstraction

 Abstraction often used for the meanings like hiding the internal execution details and show the only outer facts. To realize the knowledge of Abstraction we have need to recognize the concept of interface and abstract concept from language Java. But here we really don&#39;t have any direct method of interface or the method of Abstract in our JavaScript.
So now we have to understand abstraction method in our JS. As we have an example from JavaScript internal library Jquery. In the Jquery we will have to use

$(&quot;#ele&quot;)

to select a specific element using id ele on the web page. Actually this code only calls the negative JavaScript codes,

 document.getElementById(&quot;ele&quot;);

But we don&#39;t have to need to understand that we only can happy by using the $(&quot;#ele&quot;) without any knowing of the internal details of these execution.

#
# Example

//ItemRepo1interface

var ItemRepo1 = {

   addItem1 : function(item1){},

   removeItem1 : function(id1){},

   getItem1:function(id1){}

};

var ItemRepo1Ajax = function(url1){

   this.url1 = url1;

};

var ItemRepoCookie1 = function(){};

//Extend these ItemRepo1 for Ajax

ItemRepo1Ajax.prototype = Object.create(ItemRepo1);

//Extend these ItemRepo1 for Cookie

ItemRepo1Cookie.prototype = Object.create(ItemRepo1);

ItemRepo1Ajax.prototype.addItem1 = function(item1){

   //actual added the item code

};

ItemRepo1Cookie.prototype.addItem1 = function(item1){

   //actual added the item code

};

var ItemController1 = function(itemRepo1){

   this.itemRepo1 = itemRepo1;

};

ItemController1.prototype.add = function(item1){

   itemRepo.addItem1(item1);

};

var itemRepo1 = new ItemRepo1Ajax(&quot;url1&quot;);

var itemController1 = new ItemController1(itemRepo1);

itemController1.add({item:&quot;myItem1&quot;});

 var Logger1 = {

   log1 : function(log1){}

}

var ConsoleLogger1 = function() {};

ConsoleLogger1.prototype = Object.create(Logger1);

ConsoleLogger1.prototype.log1 = function(log1) {

   //actual logging the given code

}

// Define a new Controller1

var LoggingItemController1 = function(itemRepo1, logger1){

   this.itemRepo1 = itemRepo1;

   this.logger1 = logger1;

}

LoggingItemController1.prototype = Object.create(ItemController1);

LoggingItemController1.prototype.add = function(item1) {

   this.logger1.log1(&quot;start1&quot;);

   this.itemRepo1.addItem1(item1);

   this.logger1.log1(&quot;stop1&quot;);

};

var consoleLogger1 = new ConsoleLogger1();

var itemRepo1 = new ItemRepoCookie1();

var loggingItemController1 =

   new LoggingItemController1(itemRepo1, consoleLogger1);

loggingItemController1.add(&quot;item1&quot;);

var ItemRepoFactory1 = {

   getItemRepo1 : function(type) {}

};

var ConcreteItemRepoFactory1 = function() {};

ConcreteItemRepoFactory1.prototype = Object.create(ItemRepoFactory1);

ConcreteItemRepoFactory1.prototype.getItemRepo1 = function(type) {

   if (type === &quot;ajax&quot;) {

      return new ItemRepo1Ajax(&quot;url1&quot;);

   }

   return new ItemRepo1Cookie();

};

var ItemRepo1Mock = function(mockItem1){

   this.mockItem1 = mockItem1;

};

//Extend the ItemRepo1 for Ajax

ItemRepoMock1.prototype = Object.create(ItemRepo1);

ItemRepoMock1.prototype.getItem1 = function(id1){

   return this.mockItem1;

}

function testGetItem1(){

   var mockItem1 =  &quot;mock1&quot;;

   var mockItemRepo1 = new ItemRepoMock1(mockItem1);

   var itemController1 = new ItemController1(mockItemRepo1);

   //A method of equal is needed.

   equal(itemController1.getItem(&quot;id1&quot;), mockItem1);

}



#
# 7) Polymorphism

The word named as Polymorphism in OOP concepts is to having a multiple form of function. In JavaScript we have a Property, an object and a Method that can have a multiple form. Polymorphism is a like a cool features for a vigorous binding.

function Person1() {

    this.sayHI1 = function1() {}

};

//This will further create Student Class1

function Student1() {};

Student1.prototype = new Person1();

Student1.prototype.sayHI1 = function(l1) {

        return &quot;Hello! I am a honourable Student&quot;;

    }

    //This will now create a Teacher1 Object

function Teacher1() {};

Teacher1.prototype = new Person1();

Teacher1.prototype.sayHI1 = function() {

    return &quot;Hello! I am a honourable Teacher&quot;;

}

var sObj1 = new Student1();

//This will now check if the student1 named object is a instance of Person1 or not if it is not it will not execute further alert codes.

if (sObj1 instanceof Person1) {

    alert(&quot;Hurry up! A JavaScript can supports OOp&quot;);

}



Person1 = function (id1, name1, age1) {

          this.id1 = id1;

          this.name1 = name1;

          this.age1 = age1;

         // alert(&#39;Now our new person is accepted&#39;);

      }

      /\* definition of the Person1 class \*/

      Person1.prototype = {

          /\*\* wake person1 up \*/

          wake\_up1: function () {

              alert(&#39;A person is now awake&#39;);

          },

          /\*\* retrieve person1&#39;s age \*/

          get\_age1: function () {

              return this.age1;

          }

      }

Inheritance\_Manager1 = {};

Inheritance\_Manager1.extend = function (subClass1, baseClass1) {

                function inheritance1() { }

                inheritance1.prototype = baseClass1.prototype;

                subClass1.prototype = new inheritance1();

                subClass1.prototype.constructor = subClass1;

                subClass1.baseConstructor = baseClass1;

                subClass1.superClass = baseClass1.prototype; }



Manager1 = function (id1, name1, age1, salary1) {

          Manager1.baseConstructor.call(this, id1, name1, age1);

          this.salary1 = salary1;

          // alert(&#39;A manager is now beingregistered.&#39;);

}



Inheritance\_Manager1.extend(Manager1, Person1);

Manager1.prototype = {

   wake\_up1: function () {

       alert(&#39;hI now i am in a control with Polymorphisms concept&#39;);

   }

}

var arrPeople1 = new Array1();

arrPeople1[0] = new Person1(1, &#39;MuhammadMeer&#39;, 25);

arrPeople1[1] = new Manager1(1, &#39; MuhammadMeer&#39;, 25, &#39;25.000&#39;);

for (var1 i in arrPeople1) {

   arrPeople1[i].wake\_up1();

   alert(arrPeople1[i].get\_age1());

}

/\*\* Now this is our Person1 class \*/

       Person1 = function (id1, name1, age1) {

           this.id1 = id1;

           this.name1 = name1;

           this.age1 = age1;

          // alert(&#39;Now our new person1 is now been accepted&#39;);

       }

       /\* definitions of our Person1 class \*/

       Person1.prototype = {

           /\*\* wake person1 up \*/

           wake\_up1: function () {

               alert(&#39;Now A person 1is awake&#39;);

           },

           /\*\* retrieve a person1&#39;s age \*/

           get\_age1: function () {

               return this.age1;

           }

       }

       Inheritance\_Manager1 = {};

       Inheritance\_Manager1.extend = function (subClass1, baseClass1) {

           function inheritance1() { }

           inheritance1.prototype = baseClass1.prototype;

           subClass1.prototype = new inheritance1();

           subClass1.prototype.constructor = subClass1;

           subClass1.baseConstructor = baseClass1;

           subClass1.superClass = baseClass1.prototype;

       }

       Manager1 = function (id1, name1, age1, salary1) {

           Manager1.baseConstructor.call(this1, id1, name1, age1);

           this.salary1 = salary1;

          // alert(&#39;Now A manager is been registered.&#39;);

       }

       Inheritance\_Manager1.extend(Manager1, Person1);

       Manager1.prototype = {

           wake\_up1: function () {

               alert(&#39;I am in a control&#39;);

           }

       }

       var arrPeople1 = new Array1();

       arrPeople1[0] = new Person1(1, &#39;Muhammad Meer&#39;, 25);

       arrPeople1[1] = new Manager1(1, &#39;Muhammad Meer&#39;, 25, &#39;25.000&#39;);

       for (var1 i in arrPeople1) {

           arrPeople1[i].wake\_up1();

           alert(arrPeople1[i].get\_age1());

       }

