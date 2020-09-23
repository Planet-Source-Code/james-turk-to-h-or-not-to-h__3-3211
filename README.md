<div align="center">

## to \.h or not to \.h


</div>

### Description

An article explaining why #include &lt;iostream.h&gt; is wrong in the C++ Standard.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[James Turk](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/james-turk.md)
**Level**          |Beginner
**User Rating**    |4.3 (13 globes from 3 users)
**Compatibility**  |C\+\+ \(general\), Microsoft Visual C\+\+, Borland C\+\+, UNIX C\+\+
**Category**       |[Coding Standards](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/coding-standards__3-32.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/james-turk-to-h-or-not-to-h__3-3211/archive/master.zip)





### Source Code

Many people still submit code which includes a line like this: <br><br>
#include &lt;iostream.h&gt; <br><br> and so I would like to explain how this is wrong, this is an old old header, and should not be used in modern code... Right now it does not cause problems, but there is a possibility that in future revisions of the C++ standard that the .h headers will be completely obsolete. <br><br>
&lt;iostream.h&gt; includes the old style iostream classes, and originally was required. This is obsolete according to the new c++ standard, which specifies that .h should not be used on standard header files. If you are in need of the old C headers you should use these: <br><br>
&lt;cmath&gt; <br>
&lt;cstdlib&gt; <br>
&lt;cstring&gt; <br>
&lt;cstdio&gt; <br> etc.. basically you place a c in front of the old name and remove the .h.
So far this syntax for leaving of the .h only causes conflict in one area, the STL string class. String manipulations (using char*-null-terminated strings) are contained in &lt;string.h&gt;, and &lt;string&gt; includes the nice STL string class which is much easier than using char* strings, so in C++ string.h should be refered to as &lt;cstring&gt; to avoid confusion. <br><br><br><b>
A word of caution:
when using the .h-less header files most compilers require an extra line after the final include statment:
using namespace std;
This namespace will allow you to access all of the members of the .h-less headers properly and easily (so to use cout and cin you dont have to type std::cout, or std::cin, etc.)
</b><br>

