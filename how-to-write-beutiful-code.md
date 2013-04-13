How to write beutiful code
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
has no idea what samba means...+They, or better yet(what is considered) the_"independent"_ school district
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

```
// Main pointer class -- pointer.c is current pointer, and pointer.p[*] are the pointers in it's array
class pointer {
  int p[0] = 0;
  int c = 0;

  // Simply appends a new int to pointer.p
  void addNewPointer() {
    pointer.p.append(0);
  }
}
```

If you're reading this, I haven't finished this chapter.

Chapter 2 - Organization
------------------------
I'm not entirely sure where I'm going with this, but I'll just start with some pointers on code organization.
By _organize your code_, I mean where you structer positions of sections of your code. This could be the order
you add stuff to your classes, where you define a bunch of const's, or when you use global variables over
class function return values. If you're a static programmer(HTML and javascript) then this wouldn't be of much
importance, though it would effect your css files.

- Keep your stuff that goes together, together! This isn't just advice, this is logic!
- Be consistant with how you apply something. If you use half return values, and half global variables, you're going to have a confusing time.
- If you reuse the same naming scheme on something (exa. goblinHealth, goblinDamage, goblinTrolololol) you should try to use classes. (exa. goblin.health() goblin.Damage())
- Header files are not evil, if you reuse sections of code multiple times, just use headers. They also allow for others to add their own sets of code.

### Naming
For example, lets say we have some thingy that has to variables, position x on the grid, and position y on the grid. We have a few options:

1. If we have x's and y's for multiple objects, use classes, then we decide on 2.
2. Minimalism (only with good documentation) will be `x` and `y` as the var names, though simplicity would be `posx` and `posy`
3. If we are using them as parameters in functions, for readability, you'd want to use `posx` and `posy`, or something of that nature.
4. If the situation you're naming in has the grid as a virtual one, and the postions are used for something where the names would be different, (exa. north-south and east-west) unless you're closed source, you'd be best with either documenting them with the names, or actually naming them as what they'll be used for.

If you're reading this, I haven't finished this chapter.
