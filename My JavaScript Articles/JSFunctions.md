# 14 Essential Global Functions of JavaScript which every programmer should know

1. 1.
## encodeURI()


- Function Name:

# encodeURI()

- Syntax

encodeURI(uri)

- Function Description:

# A URI can be encoded in this function.This function can encode many special characters, except: , / ? : @ &amp; = + $ # (and encodeURIComponent() is used to encode these following characters).

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

- Example of encoding function:

When we have to encode a URI after encoding it:

var uri = &quot;my project.asp?name=ståll&amp;cars=showroom&quot;;
var ot = encodeURI(uri);

 The output of ot will be:

# my%20project.asp?name=st%C3%A5ll&amp;cars=showroom

1. 2.
## encodeURIComponent()


- Function Name:

### encodeURIComponent ()

- Syntax

encodeURIComponent(_uri_)

- Function Description:
- A URI Component can be encoded in this function.

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

- Example of Function:
- When we have to encode a URI after encoding it:

# var uri = &quot;https://xyz.com/my project.asp?name=ståll&amp;cars=showroom&quot;;
var res = encodeURIComponent(uri);

the output of ot will be:

### https%3A%2F%2Fxyz.com%2Fmy%20project.asp%3Fname%3Dst%C3%A5ll%26cars%3Dshowroom

1. 3.
## decodeURI()


- Function Name:

# decodeURI()

- Syntax

decodeURI(uri)

- Function Description:

# A URI can be decoded in this function.

- Supported Browsers:

### 1. Mozilla Firefox

###  2. Google Chrome

### 3. Safari

### 4. Microsoft Edge

### 5. Opera

- Example of decoding function:

When we have to decodea URI after encoding it:

var uri = &quot;my project.asp?name=ståll&amp;cars=showroom&quot;;
var ed = encodeURI(uri);
var dd = decodeURI(enc);
var ot = enc + &quot;&lt;br&gt;&quot; + dec;

 the output of ot will be:

# Encoded URI Form: my%20project.asp?name=st%C3%A5ll&amp;cars=showroom
Decoded URI Form: my project.asp?name=ståll&amp;cars=showroom

1. 4.
## decodeURIComponent()


- Function Name:

### decodeURIComponent ()

- Syntax

decodeURIComponent(_uri_)

- Function Description:
- A URI Component can be decoded in this function.

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

- Example of Function:
- When we have to decode a URI after encoding it:

# var uri = &quot;https://xyz.com/my project.asp?name=ståll&amp;cars=showroom&quot;;
var uri\_ed = encodeURIComponent(uri);
var uri\_dd = decodeURIComponent(uri\_ed);
var ot = uri\_ed + &quot;&lt;br&gt;&quot; + uri\_dd;

the output of ot will be:

# Encoded URI Form: https%3A%2F%2Fxyz.com%2Fmy%20project.asp%3Fname%3Dst%C3%A5ll%26cars%3Dshowroom
Decoded URI Form: https://xyz.com/my project.asp?name=ståll&amp;cars=showroom

1. 5.
## escape()


- Function Name:

# escape()

### Syntax

decodeURIComponent(_uri_)

- Function Description:

This function is Deprecated in version1.5.  we have to use the [encodeURIComponent()](https://www.w3schools.com/jsref/jsref_encodeuricomponent.asp)or  [encodeURI()](https://www.w3schools.com/jsref/jsref_encodeuri.asp)  instead of this.

The function **escape()** encodes any string.

Its benefit is to make any strings portable, so they can be transmitted through any network which is connected to any computer that can support the ASCII characters.

This function is used to encode any  special characters, with the limitation of: \* @ - \_ + . / characters.

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

- Example of Function:

When we have toencode any string:

# document.write(escape(&quot;do you need any help? Visit xyz.com!&quot;));

               the output will be:

# do%20you%20need%20any%20help%3F%20Visit%20xyz.com%21

1. 6.
##

## eval()


- Function Name:

# eval()

### Syntax

eval(_string_)

- Function Description:

       This function calculates any given strings and executes it as if it was a script code.

The eval() function calculates or executes an arguments.

If we have an arguments which is an expression,  eval() calculates these expressions. If these arguments is one or more JavaScript statements then eval() executes all the statements.

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

- Example of Function:

Execute JavaScript code

var a= 10;
var b= 20;
var c= eval(&quot;a\*b&quot;)+ &quot;&lt;br&gt;&quot;;
var d= eval(&quot;2+2&quot;)+ &quot;&lt;br&gt;&quot;;
var e= eval(&quot;x+17&quot;)+ &quot;&lt;br&gt;&quot;;
var ot = c + d + e;



  The output will be:

200
4
27



1. 7.
## isFinite()


- Function Name:

isFinite()

### Syntax

      isFinite(_value_)

- Function Description:

The isFinite() function defines whether a number is finite or not, or a legal number.

This is a special function which returns false value if the returned value is a NaN (Not-a-Number), +infinity or -infinity otherwise it returns atrue.

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

- Example of Function:

Check the number is a finite or a legal number:

var x = isFinite(123) + &quot;&lt;br&gt;&quot;;
var y = isFinite(-1.23) + &quot;&lt;br&gt;&quot;;
var z = isFinite(5-2) + &quot;&lt;br&gt;&quot;;
var a = isFinite(0) + &quot;&lt;br&gt;&quot;;
var b = isFinite(&quot;123&quot;) + &quot;&lt;br&gt;&quot;;
var c = isFinite(&quot;Hello&quot;) + &quot;&lt;br&gt;&quot;;
var d = isFinite(&quot;2005/12/12&quot;);

var out = x + y + z + a + b + c + d;

The output will be:

true
true
true
true
true
false
false

1. 8.
## isNaN()


- Function Name:

      isNaN()

- Syntax

       isNaN(_value_)

- Function Description:

The isFinite() function defines whether a number is finite or not, or a legal number.

This is a special function which returns false value if the returned value is a NaN (Not-a-Number), +infinity or -infinity otherwise it returns a true.

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

- Example of Function:
- Check  a value whether it is NaN:

isNaN(132)
isNaN(-7.23)
isNaN(5-6)
isNaN(0.0)

isNaN(0 / 0)
isNaN(&#39;13&#39;)

isNaN(&#39;NaN&#39;)
isNaN(&#39;Hello world&#39;)
isNaN(&#39;2015/12/12&#39;)
isNaN(&#39;&#39;)
isNaN(false)
isNaN(undefined)
isNaN(NaN)

1. 9.
## Number()


- Function Name:

      Number()

- Syntax

      Number(object)

- Function Description:

This function can convert an object&#39;s value into a numberthat will represent the object value.

If this value cannot be converted into a legal numbers, then NaN is returned.

.

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

- Example of Function:

It will  Convert the different objects value to their particular numbers:

var a = true;
var b = false;
var c = new Date();
var d = &quot;999&quot;;
var e = &quot;999 888&quot;;

var r =
Number(a) + &quot;&lt;br&gt;&quot; +
Number(b) + &quot;&lt;br&gt;&quot; +
Number(c) + &quot;&lt;br&gt;&quot; +
Number(d) + &quot;&lt;br&gt;&quot; +
Number(e);

The output of r will be:

1
0
1382704503079
999
NaN



1. 10.
## parseFloat()


- Function Name:

parseFloat()

- Syntax

     parseFloat(_string_)

- Function Description:

The function parseFloat() is that which parse any strings and in result it will return a number which is floating point.

Parse float function defines that if the very first character in the particular string is a number. If it is, it will parses the particular string till it extents the ends of the number, and it yield the number as a number, not as like a string.

- **Note1:**  this can return nly the very first number in the specified  string.
- **Note2:**  spaces of trailing and leading are allowed.
- **Note3:**  in result if we have a first character which cannot convert it into a number, then  it returns a NaN.

.

.

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

- Example of Function:

The example code is given below:

&lt;!DOCTYPE html&gt;

&lt;html&gt;

&lt;body&gt;

&lt;h3&gt;Click this button to parsinga multiple strings.&lt;/h3&gt;

&lt;button onclick=&quot;myFunction()&quot;&gt;submit&lt;/button&gt;

&lt;p id=&quot;myid&quot;&gt;&lt;/p&gt;

&lt;script&gt;

function myFunction() {

    var x = parseFloat(&quot;10&quot;) + &quot;&lt;br&gt;&quot;;

    var y = parseFloat(&quot;10.00&quot;) + &quot;&lt;br&gt;&quot;;

    var z = parseFloat(&quot;10.33&quot;) + &quot;&lt;br&gt;&quot;;

    var a = parseFloat(&quot;34 45 66&quot;) + &quot;&lt;br&gt;&quot;;

    var b = parseFloat(&quot;   60   &quot;) + &quot;&lt;br&gt;&quot;;

    var c = parseFloat(&quot;40 years&quot;) + &quot;&lt;br&gt;&quot;;

    var d = parseFloat(&quot;He was 40&quot;) + &quot;&lt;br&gt;&quot;;

    var k = x + y + z + a + b + c + d;

   document.getElementById(&quot;myid&quot;).innerHTML = k;

}

&lt;/script&gt;

&lt;/body&gt;

&lt;/html&gt;

The Output will be:

10
10
10.33
34
60
40
NaN

1. 11.
## parseInt()


- Function Name:

parseInt()

- Syntax

parseInt(_string, radix_)

**Function Description:**

The parseInt() function is to parse a particular strings and return any single  integer value of that.

There isradix parameters which is used to specify a numeral system that can be used, as example, we have a radix of hexadecimal mean 16 that specifiesthese number in the form of string which can be parsed from a single hexadecimal number to a particular decimal number.

If these radix parameters are omitted, JavaScript adopts the following:

- If the particular string initiates with &quot;0x&quot;, then the radix will be 16 mean hexadecimal.
- If the particular string initiates with &quot;0&quot;, then the radix will octal mean 8. And this feature is deplored.
- If the particular string initiates with any other values, then the radix will be decimal mean 10.

**Note1:**  we have only the very first number in the string which is returned!

**Note2:**  spaces of trailing and leading are allowed.

**Note3:**  in result if we have a first character which cannot convert it into a number, then  it returns a NaN.

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

- Example of Function:

The example code is given below:

&lt;!DOCTYPE html&gt;

&lt;html&gt;

&lt;body&gt;

&lt;h3&gt;Click this button to parsinga multiple strings.&lt;/h3&gt;

&lt;button onclick=&quot;myFunction()&quot;&gt;submit&lt;/button&gt;

&lt;p id=&quot;myid&quot;&gt;&lt;/p&gt;

&lt;script&gt;

function myFunction() {

    var a1 = parseInt(&quot;10&quot;) + &quot;&lt;br&gt;&quot;;

    var b1 = parseInt(&quot;10.00&quot;) + &quot;&lt;br&gt;&quot;;

    var c1 = parseInt(&quot;10.33&quot;) + &quot;&lt;br&gt;&quot;;

    var d1 = parseInt(&quot;34 45 66&quot;) + &quot;&lt;br&gt;&quot;;

    var e1 = parseInt(&quot;   60   &quot;) + &quot;&lt;br&gt;&quot;;

    var f1 = parseInt(&quot;40 years&quot;) + &quot;&lt;br&gt;&quot;;

    var g1 = parseInt(&quot;He was 40&quot;) + &quot;&lt;br&gt;&quot;;

    var h1 = parseInt(&quot;10&quot;, 10)+ &quot;&lt;br&gt;&quot;;

    var i1 = parseInt(&quot;010&quot;)+ &quot;&lt;br&gt;&quot;;

    var j1 = parseInt(&quot;10&quot;, 8)+ &quot;&lt;br&gt;&quot;;

    var k1 = parseInt(&quot;0x10&quot;)+ &quot;&lt;br&gt;&quot;;

    var l1 = parseInt(&quot;10&quot;, 16)+ &quot;&lt;br&gt;&quot;;

    var n1 = a1 + b1 + c1 + d1 + e1 + f1 + g1 + &quot;&lt;br&gt;&quot; + h1 + i1 + j1 + k1 +l1;

   document.getElementById(&quot;myid&quot;).innerHTML = n;

}

&lt;/script&gt;

&lt;/body&gt;

&lt;/html&gt;

The Output will be:

10
10
10
34
60
40
NaN

10
10
8
16
16

1. 12.
## string()


- Function Name:

string()

- Syntax

     String(_object_)

**Function Description:**

The function String() is a that which converts the particular value of an object to a specified string.

**Note:**  The String() function only returns a same value as like toString() of these individual objects.

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

- Example of Function:

The example code is given below:

&lt;!DOCTYPE html&gt;

&lt;html&gt;

&lt;body&gt;

&lt;h3&gt;Click this button to parsinga multiple strings.&lt;/h3&gt;

&lt;button onclick=&quot;myFunction()&quot;&gt;submit&lt;/button&gt;

&lt;p id=&quot;myid&quot;&gt;&lt;/p&gt;

&lt;script&gt;

function myFunction(){

    var a1 = Boolean(0);

    var a2 = Boolean(1);

    var a3 = new Date();

    var a4 = &quot;12345&quot;;

    var a5 = 12345;

    var result =

    String(a1) + &quot;&lt;br&gt;&quot; +

    String(a2) + &quot;&lt;br&gt;&quot; +

    String(a3) + &quot;&lt;br&gt;&quot; +

    String(a4) + &quot;&lt;br&gt;&quot; +

    String(a5);

   document.getElementById(&quot;myid&quot;).innerHTML = result;

}

&lt;/script&gt;

&lt;/body&gt;

&lt;/html&gt;

The Output will be:

false
true
Fri May 26 2017 11:29:03 GMT+0500 (Pakistan Standard Time)
12345
12345

1. 13.
## string()


- Function Name:

      string()

- Syntax

     String(_object_)

**Function Description:**

The function String() is a that which converts the particular value of an object to a specified string.

**Note:**  The String() function only returns a same value as like toString() of these individual objects.

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

- Example of Function:

The example code is given below:

&lt;!DOCTYPE html&gt;

&lt;html&gt;

&lt;body&gt;

&lt;h3&gt;Click this button to parsinga multiple strings.&lt;/h3&gt;

&lt;button onclick=&quot;myFunction()&quot;&gt;submit&lt;/button&gt;

&lt;p id=&quot;myid&quot;&gt;&lt;/p&gt;

&lt;script&gt;

function myFunction(){

    var a1 = Boolean(0);

    var a2 = Boolean(1);

    var a3 = new Date();

    var a4 = &quot;12345&quot;;

    var a5 = 12345;

    var result =

    String(a1) + &quot;&lt;br&gt;&quot; +

    String(a2) + &quot;&lt;br&gt;&quot; +

    String(a3) + &quot;&lt;br&gt;&quot; +

    String(a4) + &quot;&lt;br&gt;&quot; +

    String(a5);

   document.getElementById(&quot;myid&quot;).innerHTML = result;

}

&lt;/script&gt;

&lt;/body&gt;

&lt;/html&gt;

The Output will be:

false
true
Fri May 26 2017 11:29:03 GMT+0500 (Pakistan Standard Time)
12345
12345

1. 14.
## unescape()


- Function Name:

unescape()

- Syntax

unescape(_string_)

**Function Description:**

The function unescape() function which was condemned in JavaScript of the version 1.5 and UsedecodeURIComponent() or decodeURI()  instead.

This unescape() function is actually decode a particular encoded string.

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

- Example of Function:

The example code is given below:

&lt;!DOCTYPE html&gt;

&lt;html&gt;

&lt;body&gt;

&lt;script&gt;

var stg=&quot; you Need help? Visit xyz.com!&quot;;

var stg\_escape=escape(stg);

document.write(stg\_escape + &quot;&lt;br&gt;&quot;)

document.write(unescape(stg\_escape))

&lt;/script&gt;

&lt;/body&gt;

&lt;/html&gt;

The Output will be:

%20you%20Need%20help%3F%20Visit%20xyz.com%21
you Need help? Visit xyz.com!

#
# :Global Properties of JS:

#
## Infinity

- Property Name:

Infinity

**Property Description:**

The property Infinity is actually a numerical value that can represent a positive infinity.

The Property -Infinity is a numerical value that can representa negative infinity.

Infinity is shown when we have a particular number which exceeds the upper limit of a number which is a floating point, that is 1.797693134862315E+308.

-Infinity is shown when we have a number which exceeds the lower limit of a numbers which are floating point, that is -1.797693134862316E+308

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

- Example of Property:

The example code is given below:

&lt;!DOCTYPE html&gt;

&lt;html&gt;

&lt;body&gt;

&lt;h3&gt;1.797693134862315E+308 is the only limit of a number which is a floating point &lt;/h3&gt;

&lt;h2&gt;Click this submit button below.&lt;/h2&gt;

&lt;button onclick=&quot;myFunction()&quot;&gt;submit&lt;/button&gt;

&lt;p id=&quot;myid&quot;&gt;&lt;/p&gt;

&lt;script&gt;

function myFunction() {

    document.getElementById(&quot;myid&quot;).innerHTML =

    1.7976931348623157E+10308 + &quot;&lt;br&gt;&quot; +  -1.7976931348623157E+10308;;

}

&lt;/script&gt;

&lt;/body&gt;

&lt;/html&gt;

The Output will be:

### 1.797693134862315E+308 is the only limit of a number which is a floating point

## Click this submit button below.

submit

submit

Infinity
-Infinity

#
## NaN

- Property Name:

NaN

- Syntax:

Number.NaN

**Property Description:**

This NaN property is actually exhibit a &quot;Not-a-Number&quot; values. This specified property shows that a single value is not a legal numbers.

This specified property NaN is same as like a Number.Nan property which Use the isNaN() function to check whether if a value is a NaN value or not.

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

#
## undefined

- Property Name:

undefined

**Property Description:**

This property of undefined shows that a single variable is not assigned to a value.

- Supported Browsers:

### 1. Mozilla Firefox

###        2. Google Chrome

###        3. Safari

###        4. Microsoft Edge

###        5. Opera

- Example of Property:

The example code is given below:

&lt;!DOCTYPE html&gt;

&lt;html&gt;

&lt;body&gt;

&lt;h3&gt;Click this submit button to verify a particular variable is undefined.&lt;/h3&gt;

&lt;button onclick=&quot;myFunction()&quot;&gt;submit&lt;/button&gt;

&lt;p id=&quot;myid&quot;&gt;&lt;/p&gt;

&lt;script&gt;

function myFunction() {

    var a;

    if (a === undefined) {

        txt = &quot;a is undefined&quot;;

    } else {

        txt = &quot;a is defined&quot;;

    }

    document.getElementById(&quot;myid&quot;).innerHTML = txt;

}

&lt;/script&gt;

&lt;/body&gt;

&lt;/html&gt;

The Output will be:

### Click this submit button to verify a particular variable is undefined.

submit

submit

# a is undefined