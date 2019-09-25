---
id: 219
title: Programming, Back To Basics
date: 2019-02-11T05:19:36+00:00
author: unity
excerpt: |
layout: post
guid: http://unity.hdyar.com/?p=219
permalink: /fundamentals/scripting-basics/programming-back-to-basics/
categories:
  - Scripting Basics
---
 

A refresher on what coding&#8230; is.

Basically, writing code, or coding, is generally the act of programming, which is the act of telling a computer what to do.

Code is text designed to be read both by humans and by machines. It&#8217;s a middle-ground. To become a programmer, you must learn how to think like the computer (or our game engine) is thinking, and what it is trying to do. It&#8217;s not anywhere as hard as most people make it out to be.

We will be writing code for Unity in C#. Unity supports both JavaScript and C#, and we won&#8217;t use Javascript. So let&#8217;s forget about it for now.

Unity projects can have lots and lots of code files. Any c# file in the assets folder will be considered part of the project, and may be used. I say &#8220;may&#8221; because that code may not actually _do_ anything, and may never get _executed._

## Five Things To Learn All At Once

We need to understand 4 programming concepts to start working in c# and Unity, and there&#8217;s no great order to learn them in. My advice is to learn them, then go back and learn them again, and the second time through things are going to start clicking a lot more.

  1. Code Execution/Code Flow
  2. Variables
  3. Functions
  4. Accessing Data/Functions/OO Theory
  5. Syntax.

I won&#8217;t cover syntax here in much detail. It will come with practice and time, and fixing errors until eventually you remember which things get capitalized and where the semicolons go. 

**Executing** code is when a computer reads the code, and follows it&#8217;s instructions. Most bits of code do one of two things: 

  1. It&#8217;s telling the computer to change how it is executing code. Like how Choose Your Own Adventure books tell you &#8220;Turn to page 35&#8221;. Code has lots and lots of things like that, that change the order and time various parts of code get executed.
  2. The computer changes the value of some data. 

That&#8217;s like, 99% of it.

### How Computers Execute Code

Computers execute code line by line. It starts at the top of the file, and goes down in order, one command at a time. Each line happening one after the next. It ignores comments, which are anything that happens after two slashes, and before a line break. Comments are just for use humans to read.

<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">int x = 2;//Define an integer, x, and set it to 2.
int y = x * 6;
int x = y - 1;
//What is x equal to?</pre>

In C#, each line of code &#8211; an individual command &#8211; tends to be ended either by a semicolon &#8220;;&#8221;, or by curly brackets &#8220;{}&#8221;. 

Semicolons, in c#, tell the computer that this command is finished, move on to the next line. 

Curly Braces (these things: {}) define the start and stop points of subsections of code. Basically, they are markers. Every line of code between the curly braces {like this} are grouped together.

We have lots of commands that changes order that the computer executes commands. I call this stuff &#8220;code flow&#8221;.  


<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">bool trueOrFalseVariable = false;

if (trueOrFalseVariable == true){
  DoSomething();
}else{
  BakeACake();
}

int i = 0;
while(i&lt;10){
  i = i + 1;
  ScreamIntoTheEmptinessOfSpace();
}
TheEnd();</pre>

The code above is all sorts of confusing new terms. But let&#8217;s just focus on the curly braces for now. There are three sets of them in the above code. The first one is after an if statement. If whatever is in the parenthesis is true, than code in the first set of curly braces (the &#8220;DoSomething(); function) will happen, otherwise the code in the second set (the &#8220;BakeACake();&#8221; function) will happen. The computer will skip the section it doesn&#8217;t run completely, and we define these sorts of sections curly braces.

In other words, curly braces are how we contain chunks of code.

The third set is after the while command. The while command will repeat whatever happens in it&#8217;s curly braces forever. Well, not quite forever, it will repeat it so long as what is in it&#8217;s parenthesis is true. In this case we see if the integer i is less than 10, and while that is true, we ScreamIntoTheEmptinessOfSpace(); We will do that 10 times first, i will be 0, then: 1,2,3,4,5,6,7,8, and 9. i will get set to 10, the _conditional_ inside of the parenthesis will stop being true, and we will finally move onto TheEnd();

## Variables

Variables store data for us. We have to be extremely specific when we tell C# what kind of data we are storing. C# is &#8220;strict&#8221;, it won&#8217;t make any assumptions and it will throw errors if we put the wrong data type in the wrong data holder. A number and a collection of words are just to different.

<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">int integer = 1;
int alsoValid;//</pre>

Luckily, errors tend to be descriptive enough with data mismatches that we can fix them pretty easily.

<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">float number = 2.34f;
string words = "double quotation marks are cool";
bool thisIsHelpful = true;</pre>

So how do we store information in C#? We need variables. Variables give us, the programmer, a useful name to refer to some information that we may want to change or check on. Like a player&#8217;s health, how much time has passed since we started a level, if the player is allowed to jump, and so on.

Variables give the computer a reference to data and let it know how to access and manipulate that data.

We define variables first by writing what **type** the data is: string, bool, int, float, double, and so on. Then we give it a name, something we will read and understand as humans. (Syntax note: use camelCase for variable names). Then we use a semicolon and boom. A variable is defined.

<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">int number;//now we have an integer variable called "number".
number = 4;//Now that it exists, we can set it to be equal to something.
int anotherNumber = 43;//We can also give it a value when we define (create) the variable. We do that a lot.</pre>

#### Different Kinds Of Numbers

Int is an integer, it&#8217;s whole numbers (and also negative numbers).

**float** is a way to store numbers with decimals. like 2.12. 

**double** is another way to store numbers with decimals.

_Note: we also have byte&#8217;s, decimal&#8217;s, long&#8217;s, sbyte&#8217;s short&#8217;s uint&#8217;s, ulong&#8217;s, and ushort&#8217;s. Just FYI there&#8217;s other ones too. You might use them if you need super optimized code. You don&#8217;t._

Behind the scenes, the computer is doing math with floats and doubles in different ways. Doubles are less precise than floats. They have their own advantages and disadvantages performance-wise. In general, we will use floats. **Basically, always use floats or int&#8217;s to store numbers.**

A number with just one decimal place (like 1.2) is by default a double. We can stick the letter f after it (1.2f) to let c# mean that we mean float.

<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">float 1.3;//may be an error.
float 1.3f;//not an error.</pre>

Yeah, since we almost always are using floats, this is annoying, but&#8230; deal with it. C# isn&#8217;t changing.

## Functions

A function is a set of code (curly braces incoming!) that we can give a name, and then whenever we say that name, it&#8217;s like shorthand for inserting all of the code at that spot. It&#8217;s re-usable code! 

<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">void SomeFunction(){
  Debug.Log("Hello!");
  Debug.Log("Lets pretend these three lines of code are complicated");
  Debug.Log("They aren't, but we can pretend");
}

SomeFunction();
SomeFunction();
SomeFunction();</pre>

The above code first _defines&nbsp;a&nbsp;function._

Then it _calls_ that function three times in a row.

A function is defined in four parts:

  1. The return type: void 
  2. The function name: SomeFunction
  3. Parameters. ()
  4. The code itself. {}

In C#, it&#8217;s good practice to write functions in [pascal case](http://wiki.c2.com/?PascalCase). &#8220;Good Practice&#8221; means do it because I said so.

When we use the function somewhere else in our code, I said it was like shoving all of the code in that spot. That&#8217;s only sort of true. It&#8217;s actually like, executing the code in the braces, and then replacing the function call with _whatever it returns._ Basically, it can pretend to be a variable, and return in.

Our return type is void. This means we don&#8217;t return anything. Yay! Moving on! Don&#8217;t forget to type void before the name of your functions that don&#8217;t return things.

## Accessing Data

Without getting into the nitty-gritty of object-oriented programming theory, let&#8217;s touch on at least one basic feature of OO theory: accessing data.

Every script we write is going to be a **class**. Every [component](http://unity.hdyar.com/fundamentals/what-are-components/) will be a class. I may need to store references to these components just like I need references to data (ie: variables). 

Remember how we have both Value properties and Reference properties in [components](http://unity.hdyar.com/fundamentals/what-are-components/)? These are just variables.

So we can create variables that store references to classes (usually components).

<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">Rigidbody rb;</pre>

Lets say I have a reference to the rigidbody (&#8220;rb&#8221; as I wrote above). That rigidbody has a variable called &#8220;velocity&#8221; which is this gameObject&#8217;s velocity.

To access this component, I can&#8217;t just use the variable &#8220;velocity&#8221; in my script. I need to get the velocity in the rigidbody class/script/component.

So I use a &#8220;dot&#8221; to access it.

Velocity is a Vector3, a class that has it&#8217;s own sub-properties (variables) that make it up. It has a variable called &#8220;magnitude&#8221; which is basically our total speed (regardless of direction). So to access it, I use the dot again.

The dot &#8220;digs in&#8221;, and it&#8217;s as if we were typing any variable in the script.

<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">Rigidbody rb;//assume this has been defined.
Debug.Log(rb.velocity.magnitude);</pre>

In real life, we may have some code that looks like this.

<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">public class NewBehaviourScript : MonoBehaviour
{
    Rigidbody rb;
    float maxSpeed = 20;
    void Start()
    {
        rb = GetComponent&lt;Rigidbody&gt;();//Make the reference equal to something! 
        //This will get the rigidbody component attached to the same gameObject that this component is attached to.
    }

    // Update is called once per frame
    void Update()
    {
        if(rb.velocity.magnitude &gt;maxSpeed){
            Debug.Log("Oh no! We going too fast!");
        } 
    }
}</pre>

We can also use the dot to get to functions. For example, the **Rigidbody** component has an **AddForce** function that &#8230; adds a force onto the ball.

The **Input** class is something Unity gives us to get player input. We don&#8217;t need a specific reference to, and it has it&#8217;s own properties and values. It has a function called &#8220;GetKeyDown&#8221; which is true for the frame we first press down the specified key.

<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">public class SimpleJumpExample: MonoBehaviour
{
    Rigidbody rb;
    float jumpForce = 10;
    void Start()
    {
        rb = GetComponent&lt;Rigidbody&gt;();//Make the reference equal to something! 
        //This will get the rigidbody component attached to the same gameObject that this component is attached to.
    }

    // Update is called once per frame
    void Update()
    {
        if(Input.GetKeyDown("space")){
            rb.AddForce(Vector3.up*jumpForce,ForceMode.Impulse);
        } 
    }
}</pre>

**Vector3** has a public variable called &#8220;up&#8221; which is just equal to a vector 3 that is 0 in the x and z axes&#8217; and 1 in the y axis (0,1,0). 

**ForceMode** has some data that the physics system can use to determine _how_ to add the force. Impulse is one that is instant and uses mass. If we wanted to slowly accelerate the thing (like a car&#8217;s gas petal), we might use ForceMode.Force.

See how we are using dot&#8217;s all over the place to get data that exists elsewhere?

## Public vs. Private

Sooooo there&#8217;s a catch. We can only get data from a variable from outside it&#8217;s own class (ie: by using a dot/a reference) if we say it&#8217;s okay. Public variables can be accessed outside of their **scope** while private ones cannot.

<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">int aNumber = 3;//private by default.
private anotherNumber = 4;//certainly private
public thisNumberRules = 200;//other components can access this number.</pre>

If we make a variable public, the unity inspector can also access and change it, and that&#8217;s how properties show up in the inspector!<figure class="wp-block-embed-youtube wp-block-embed is-type-video is-provider-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio">

<div class="wp-block-embed__wrapper">
</div></figure>