How to write beautiful code
==========================

So, this is a stupidly written, dumb, __unedited__, and fairly lazy book on how to make your code look awesome and be readable by other people!

Anyways...This book is written in [markdown](http://daringfireball.net/projects/markdown/). And well, even though I'm not too familiar I like it's minimalism.
So...This book won't really have much structer too it, I'm just going on a post by post style, or however it ends up...

Chapter 1 - Documentation
-------------------------
So I'm L8D. I don't have much to say for myself when it comes to a degrees, major projects, or _internetz_
popularity, but I'm writing this anyway for bothexperience, and to share my hopefully helpful knowledge.
I usually work with c++, python, javascript, some java, and brainfuck(and delvs\[del-vis\], my
own derivative of brainfuck). I and a few other coders consider me a minimalistic one. I like
to keep my code clean, simple, and almost all of my coding design has been inspired in some way by the
[suckless](www.suckless.org/philosophy) philosophy.

I use vim, I am an avide vim user, and I use markdown + raw text file to make the majority of my rich
text documents. Though, for public school computer purposes I end up having to use google docs. Though
I do not support google much, I'd rather use that than trust my school's samba server when the head IT
has no idea what samba means...+They, or better yet(what is considered) the _"independent"_ school district
has a serious SQL injection problem.

### Back to documentation.
I guess my second best feature is documentation. I read a lot a coders attempt at documenting
their code...eugh! Sometimes I see things that dumb the code down to _normz_ level, and others only use
direct references to _what is considered_ common coding knowledge. Neither of these are useful.

In difference to the typical answer of _"The best would be a balance between the two"_. __NO!__ bad boy!
In my opinion, the best approach to code documentation includes notes on:

- What a function or set of code does.
- Usage for a set of code or function.
- Notes on something in the code, like deprecation, legacy, needed changes, or suggestions.
- Step by step explanation of a complicated process, or code that is gibberish(which is what this book hopes to prevent!).

Example for a function to add a new var to an array in C++:

    // Main pointer class -- pointer.c is current pointer, and pointer.p[*] are the pointers in it's array
    class pointer {
      int p[0] = 0;
      int c = 0;

      // Simply appends a new int to pointer.p
      void addNewPointer() {
        pointer.p.append(0);
      }
    }

This is how I would document my code:

    // Convert the 0-2 values of port's status to readable words
    string checkStatus(int bay, char n) {
      int lvlnum =  bays[bay].lvl(n);
      switch(lvlnum) {
        case '0':
          return "Off";
          break;
        case '1':
          return "Charging";
          break;
        case '2':
          return "Active";
          break;
        // If it's 3 or above, return 'Unknown'.
        default:
          return "Unknown";
    }

Simple enough, the code itself is readable enough to not have many comments, though spacing can go a long way:

    // Convert the 0-2 values of port's status to readable words
    string checkStatus(int bay, char n) {

      int lvlnum =  bays[bay].lvl(n);

      switch(lvlnum) {

        case '0':
          return "Off";
          break;

        case '1':
          return "Charging";
          break;

        case '2':
          return "Active";
          break;

        // If it's 3 or above, return 'Unknown'.
        default:
          return "Unknown";
      }
    }

Doesn't that just look elegant? The whole naming thing I'm not too sure about, I just created those for examples...


If you're reading this, I haven't finished this chapter.

Chapter 2 - Organization
------------------------
I'm not entirely sure where I'm going with this, but I'll just start with some pointers on code organization.
By _organize your code_, I mean where you structure positions of sections of your code. This could be the order
you add stuff to your classes, where you define a bunch of const's, or when you use global variables over
class function return values. If you're a static programmer(HTML and javascript) then this wouldn't be of much
importance, though it would effect your css files.

- Keep your stuff that goes together, together! This isn't just advice, this is logic!
- Be consistent with how you apply something. If you use half return values, and half global variables, you're going to have a confusing time.
- If you reuse the same naming scheme on something (exa. goblinHealth, goblinDamage, goblinTrolololol) you should try to use classes. (exa. goblin.health() goblin.Damage())
- Header files are not evil, if you reuse sections of code multiple times, just use headers. They also allow for others to add their own sets of code.

### Naming
For example, lets say we have some thingy that has to variables, position x on the grid, and position y on the grid. We have a few options:

1. If we have x's and y's for multiple objects, use classes, then we decide on 2.
2. Minimalism (only with good documentation) will be `x` and `y` as the var names, though simplicity would be `posx` and `posy`
3. If we are using them as parameters in functions, for readability, you'd want to use `posx` and `posy`, or something of that nature.
4. If the situation you're naming in has the grid as a virtual one, and the positions are used for something where the names would be different, (exa. north-south and east-west) unless you're closed source, you'd be best with either documenting them with the names, or actually naming them as what they'll be used for.

If you're reading this, I haven't finished this chapter.

Chapter 3 - Style
-----------------
This is what this entire book was supposed to be about. Coding style. Spacing, mark positioning, comment locations, indentation, etc.
Every coder should have their own coding style, though most of the ones who are working with a team or
for a company, know you have to stick to their coding style. If you're developing your own project, or at
least can use your own style, this chapter is for you.

### Minimalism
My style of coding is like this:

    #include <iostream>
    using namespace std;

    int main(int argc, char * argv[]) {
      cout << "You suck!" << endl;
      return 0;
    }

Some of it is just because of how vim automatically spaces things, other parts is the style of code
is what I saw when I learned it. Another style of code could be something like:

    #include <iostream>
      using namespace std;

    int main ( int argc, char * argv[] )
    {
      cout << "You suck!\n";
      return (0);
    }

Notice the difference?
I aim to keep the parts of code that need to be seen obvious, and I minimize the others. Using a few shortcuts like the `return 0;` to keep it looking minimal.
I do keep the `}` as a separate line with equal indentation to it's origin so the origin can be found, though as opposed to the second
example I gave, I kept the `{` on the origin line because it was unnecessary. Also, I prefer to use `endl` over a `\n` because doesn't
obscure it's surrounding text, and if you're printing multiple lines, it works as a good separator. I could've done something like:
`cout<<"You suck!"<<endl;`
But how readable is that? Especially with fonts that make `<` and `>` look like crap.

### Rules

1. __ALWAYS BE CONSISTANT WITH YOUR CODING STYLE__. But, part of your coding style could be _dynamic_ and be different depending on different things.
2. If you want to have self-documenting code, then try to write it that way. Not just how you do something, but spacing and style can also deeply effect the human-readability of code.
3. Never be redundant with variable names. Try to be at least simple, but keep it understandable. If you want to be minimal, make sure it's obvious and well-documented.

Chapter 4 - I don't know yet
----------------------------
This chapter is for my sister who is a css+html web dev, she wanted me to explain universal syntax and syntax shortcuts for stuff in many languages.

So. I'm going to start with javascript, since that is by far the most common embedded and web programming language.
Here is a sample peice of javascript, really standard:

`document.write("<p>Blah</p>");`

And now I'll break it down, and this is applicatable to many languages.

Whenever you see a word/name with `()` following it (exa. `write("asdf")`) it means it is a function, and what goes inside the '()'s are the arguements for the function.
`function(arguements)`
Whenever you see a '.' in between two names(of variables, not to be mistaken for string joining) it means it is inside a class. So `document.write()` is using the 'write'
function from the 'document' class.
`class.something`
And last, you have the semicolon, which in most languages means it's the end of the intruction. In actuality though, in javascript `document.write();` is actually using
document as a file name, and it's uses the file method(which is a function applicable to a certain variable type) 'write' to append that to the html page. But you don't
nessicarily have to know that because that is the only instance where you'd practically write to mem files.

As an explanation to earlier where I talked about using `return 0;` over `return(0);`, because return is both a function and an instruction itself, so it allows spaced arguements.
Whereas also there is a `return0;` instruction only in modern compilers. For the pupose of quickly exiting.
