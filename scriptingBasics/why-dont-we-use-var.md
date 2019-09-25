---
id: 266
title: 'Why don&#8217;t we use &#8220;var&#8221; in C# and Unity?'
parent: Scripting Basics
layout: post
categories:
  - Scripting Basics
---
You can use &#8216;var&#8217; all you want! Lets avoid it because it can be misleading and confusing. There is a difference between what var does in C# (implicit typing) and what beginners _may think_ var does in C# (loose typing). 

When we declare variables in Unity, almost always, they are explicitly typed. That means we are describing exactly what kind of variable it is.

<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">int num = 10;</pre>

This is an Integer, because I used &#8220;int&#8221; to say as much. int num = &#8220;banana&#8221;; would throw a compiler error. 

Every once in a while, somebody discovers on some example code that C# has a &#8220;var&#8221; keyword.

<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">int num1 = 10;
var num2 = 20;</pre>

&#8216;var&#8217; in C# lets use implicitly typed variables. Everything is the same (this example, num2 becomes an int), but we don&#8217;t have to figure out the typing. 

That looks similar to JavaScript, and is useful! Now you don&#8217;t have to remember what type your variable is, you can just declare it with var! Neat!

Problem is that the way Javascript and C# work are slightly different. 

C# is still a &#8220;strongly typed&#8221; language, and variables declared with &#8220;var&#8221; will get turned into their appropriate types (as determined by the compiler). This is &#8220;implicitly typed&#8221; as opposed to &#8220;explicitly typed&#8221;. We just let the compiler figure that part out for us when we use var. The variable is still &#8220;strongly typed&#8221;.

JavaScript, on the other hand, is a &#8220;loosley-typed&#8221; language. It&#8217;s not the same thing as implicitly figuring out the what the type is, the compiler treats the variable differently. Read more about what those differences are [here](https://en.wikipedia.org/wiki/Strong_and_weak_typing).

## So &#8230; why don&#8217;t we use Var?

Clarity. In contexts where those learning Unity have come from other (loosely typed) languages, the use of &#8216;var&#8217; can be misleading. C# is strongly typed, typing the variables ourselves never hurt anyone. Letting the compiler determine the type is a nice shortcut but makes example code harder to understand &#8211; the programmer still needs to know the type.

Letting the compiler choose the type can lead to some optimizations, there can technically be an small advantage there. Not a large enough one to listen to any dogmatic &#8220;you should always use var&#8221; proclamation, I believe understandable code is more important than these advantages.

To prevent confusion and make example code more readable, I don&#8217;t use &#8216;var&#8217;. A lot of C# programmers are unaware of var, and I don&#8217;t think the advantage is strong enough to be worth confusing them.

You, now knowing the differences between strongly-typed and weakly-typed languages, and between explicit and implicit typing, are now free to use var in your code all you want! 

Read more in the C# documentation:

  * [Implicitly Typed Local Variables](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables)
  * [Implicitly Typed Arrays](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/arrays/implicitly-typed-arrays)
  * [var](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/var)