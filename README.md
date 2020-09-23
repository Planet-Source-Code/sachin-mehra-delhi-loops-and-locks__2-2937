<div align="center">

## Loops and Locks


</div>

### Description

This article is regarding Loops and Locks. And about the performance of our code. There is no ‘silver bullet’ to making fast and efficient code...let's do it ourself.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Sachin Mehra \(Delhi\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/sachin-mehra-delhi.md)
**Level**          |Advanced
**User Rating**    |4.8 (19 globes from 4 users)
**Compatibility**  |Java \(JDK 1\.1\), Java \(JDK 1\.2\)
**Category**       |[Coding Standards](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/coding-standards__2-87.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/sachin-mehra-delhi-loops-and-locks__2-2937/archive/master.zip)





### Source Code

```
<html xmlns:o="urn:schemas-microsoft-com:office:office"
xmlns:w="urn:schemas-microsoft-com:office:word"
xmlns:st1="urn:schemas-microsoft-com:office:smarttags"
xmlns="http://www.w3.org/TR/REC-html40">
<head>
<meta http-equiv=Content-Type content="text/html; charset=windows-1252">
<meta name=ProgId content=Word.Document>
<meta name=Generator content="Microsoft Word 10">
<meta name=Originator content="Microsoft Word 10">
<link rel=File-List href="Programming%20Efficient%20Code_files/filelist.xml">
<title>Programming Efficient Code</title>
<o:SmartTagType namespaceuri="urn:schemas-microsoft-com:office:smarttags"
 name="place"/>
<!--[if gte mso 9]><xml>
 <o:DocumentProperties>
 <o:Author>default</o:Author>
 <o:LastAuthor>default</o:LastAuthor>
 <o:Revision>1</o:Revision>
 <o:TotalTime>2</o:TotalTime>
 <o:Created>2002-05-29T06:35:00Z</o:Created>
 <o:LastSaved>2002-05-29T06:37:00Z</o:LastSaved>
 <o:Pages>1</o:Pages>
 <o:Words>1110</o:Words>
 <o:Characters>6331</o:Characters>
 <o:Lines>52</o:Lines>
 <o:Paragraphs>14</o:Paragraphs>
 <o:CharactersWithSpaces>7427</o:CharactersWithSpaces>
 <o:Version>10.2625</o:Version>
 </o:DocumentProperties>
</xml><![endif]--><!--[if gte mso 9]><xml>
 <w:WordDocument>
 <w:Compatibility>
  <w:BreakWrappedTables/>
  <w:SnapToGridInCell/>
  <w:WrapTextWithPunct/>
  <w:UseAsianBreakRules/>
 </w:Compatibility>
 <w:BrowserLevel>MicrosoftInternetExplorer4</w:BrowserLevel>
 </w:WordDocument>
</xml><![endif]--><!--[if !mso]><object
 classid="clsid:38481807-CA0E-42D2-BF39-B33AF135CC4D" id=ieooui></object>
<style>
st1\:*{behavior:url(#ieooui) }
</style>
<![endif]-->
<style>
<!--
 /* Font Definitions */
 @font-face
	{font-family:Courier;
	panose-1:2 7 4 9 2 2 5 2 4 4;
	mso-font-alt:"Courier New";
	mso-font-charset:0;
	mso-generic-font-family:modern;
	mso-font-format:other;
	mso-font-pitch:fixed;
	mso-font-signature:3 0 0 0 1 0;}
 /* Style Definitions */
 p.MsoNormal, li.MsoNormal, div.MsoNormal
	{mso-style-parent:"";
	margin:0in;
	margin-bottom:.0001pt;
	mso-pagination:widow-orphan;
	font-size:12.0pt;
	font-family:"Times New Roman";
	mso-fareast-font-family:"Times New Roman";}
a:link, span.MsoHyperlink
	{color:blue;
	text-decoration:underline;
	text-underline:single;}
a:visited, span.MsoHyperlinkFollowed
	{color:purple;
	text-decoration:underline;
	text-underline:single;}
code
	{font-family:Courier;
	mso-ascii-font-family:Courier;
	mso-fareast-font-family:"Times New Roman";
	mso-hansi-font-family:Courier;
	mso-bidi-font-family:"Courier New";}
pre
	{margin:0in;
	margin-bottom:.0001pt;
	mso-pagination:widow-orphan;
	font-size:10.0pt;
	font-family:"Courier New";
	mso-fareast-font-family:"Times New Roman";}
@page Section1
	{size:8.5in 11.0in;
	margin:1.0in 1.25in 1.0in 1.25in;
	mso-header-margin:.5in;
	mso-footer-margin:.5in;
	mso-paper-source:0;}
div.Section1
	{page:Section1;}
-->
</style>
<!--[if gte mso 10]>
<style>
 /* Style Definitions */
 table.MsoNormalTable
	{mso-style-name:"Table Normal";
	mso-tstyle-rowband-size:0;
	mso-tstyle-colband-size:0;
	mso-style-noshow:yes;
	mso-style-parent:"";
	mso-padding-alt:0in 5.4pt 0in 5.4pt;
	mso-para-margin:0in;
	mso-para-margin-bottom:.0001pt;
	mso-pagination:widow-orphan;
	font-size:10.0pt;
	font-family:"Times New Roman";}
</style>
<![endif]-->
</head>
<body lang=EN-US link=blue vlink=purple style='tab-interval:.5in'>
<div class=Section1>
<p class=MsoNormal><b><span style='font-size:16.0pt;font-family:Arial'>Programming
Efficient Code</span></b><o:p></o:p></p>
<p class=MsoNormal><b><span style='font-size:11.0pt;font-family:Arial'>Loops
and Locks<o:p></o:p></span></b></p>
<p class=MsoNormal><span style='font-size:9.0pt;font-family:Arial'>Article by </span><i><span
style='font-size:10.0pt;font-family:Arial'>Sachin Mehra (<a
href="mailto:sachinweb@hotmail.com">sachinweb@hotmail.com</a>)<o:p></o:p></span></i></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>One of the
worst things that a programmer can assume is that the compiler and middleware
will do the optimizations for you!&nbsp; Most applications are being targeted for
50-200 concurrent users, which is why we need to constantly be worrying about
the performance of our code. </span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>Say you
have a search component (which will be on everybody’s desktop) which takes 3-5
seconds to load; and consequently ties down the database.&nbsp; Imagine what
will happen when 200 people try to load this at the same time.&nbsp; Simple
math would suggest (say using an average of 4 seconds): (4 x 200) / 60 = 13 –
THAT’S 13 MINUTES!&nbsp; And actually, when dealing with situations of high
contention, you cannot assume 100% efficiency and could be realistically
dealing with something in the range of 20-25 minutes of processing time
required.&nbsp; </span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>There is no
‘silver bullet’ to making fast and efficient code.&nbsp; Middleware will not
solve the problem for you, databases will not solve the problem for you, it is
up to you as a computational process engineer (how’s that for a title?) to
understand and deal with the underlying inefficiencies in the software you
design.&nbsp; There are many things which you need to consider, and you need to
think your logic out carefully.&nbsp; One thing you should always be asking
yourself is “could this be done better?”.</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>In
programming, we find ourselves in loops a lot. &nbsp;In Java, we especially
find ourselves looping through </span><span style='font-size:10.0pt;font-family:
"Courier New"'>Collection</span><span style='font-size:10.0pt;font-family:Arial'>
objects an awful lot.&nbsp; This is one of the particular areas where many of
us need some improvement.&nbsp; When you use a </span><span style='font-size:
10.0pt;font-family:"Courier New"'>Collection</span><span style='font-size:10.0pt;
font-family:Arial'> object, how do you decide what type of </span><span
style='font-size:10.0pt;font-family:"Courier New"'>Collection</span><span
style='font-size:10.0pt;font-family:Arial'> to use, and how to apply it?&nbsp;
It seems to me that most Java Programmers are just using “whatever works”, and
they use the one which they “believe” to be the fastest.&nbsp; The fact of the
matter is, different types of collections are for different kinds of
applications. &nbsp;Do you truly know the differences between </span><span
style='font-size:10.0pt;font-family:"Courier New"'>Vector</span><span
style='font-size:10.0pt;font-family:Arial'> and </span><span style='font-size:
10.0pt;font-family:"Courier New"'>ArrayList.&nbsp; </span><span
style='font-size:10.0pt;font-family:Arial'>The most common misconception I have
heard is that a </span><span style='font-size:10.0pt;font-family:"Courier New"'>Vector
</span><span style='font-size:10.0pt;font-family:Arial'>will automatically grow
in size, and an </span><span style='font-size:10.0pt;font-family:"Courier New"'>ArrayList</span><span
style='font-size:10.0pt;font-family:Arial'> will not, this is simply not
true.&nbsp; The only real difference is that </span><span style='font-size:
10.0pt;font-family:"Courier New"'>Vector</span><span style='font-size:10.0pt;
font-family:Arial'> is thread-safe and </span><span style='font-size:10.0pt;
font-family:"Courier New"'>ArrayList</span><span style='font-size:10.0pt;
font-family:Arial'> is not.&nbsp; And what does this mean?</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>Being
thread-safe is not always a good thing.&nbsp; When something is thread safe, it
means that the runtime must maintain locks on certain objects, when they are
being accessed to prevent concurrent modification.&nbsp; In many cases, this
additional check is unnecessary and very costly to performance.&nbsp; On the
other hand there are situations where it is very necessary to do thread-safe
operations.&nbsp; Many people understand the jist of synchronization, but don’t
truly understand how to take advantage of it properly.&nbsp;&nbsp; One thing I
have see people doing a lot is applying </span><span style='font-size:10.0pt;
font-family:"Courier New"'>synchronized</span><span style='font-size:10.0pt;
font-family:Arial'> in places where they should not. Consider the following:</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><b><span style='font-size:10.0pt;font-family:Arial'>Example
1A</span></b><span style='font-size:10.0pt;font-family:Arial'>:</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>synchronized void addUser(User user) {<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
this.list.add(user);</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>}</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>Another
common misconception is that the </span><span style='font-size:10.0pt;
font-family:"Courier New"'>synchronized</span><span style='font-size:10.0pt;
font-family:Arial'> keyword will only protect that particular method.&nbsp; If
you think this, you should read on. &nbsp;This will however, effectively only
allow the instance of </span><span style='font-size:10.0pt;font-family:"Courier New"'>list</span><span
style='font-size:10.0pt;font-family:Arial'> to be accessed by only one Thread
at a time. But by doing this, you force the runtime to place a lock on the
entire object pool of the class instance, which essentially means, any instance
methods cannot be executed during the execution of </span><span
style='font-size:10.0pt;font-family:"Courier New"'>addUser().</span><span
style='font-size:10.0pt;font-family:Arial'>&nbsp; In most cases, this is
inefficient.&nbsp; Other threads may need access to other non-effected
items.&nbsp; </span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>The
following example addresses this problem.</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><b><span style='font-size:10.0pt;font-family:Arial'>Example
2A</span></b><span style='font-size:10.0pt;font-family:Arial'>:</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>void adduUser(User user) {</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
synchronized (this.list) {</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
this.list.add(user)</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
}</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>}</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>In this
example, we only lock the instance of </span><span style='font-size:10.0pt;
font-family:"Courier New"'>list</span><span style='font-size:10.0pt;font-family:
Arial'> for the duration of the </span><span style='font-size:10.0pt;
font-family:"Courier New"'>add()</span><span style='font-size:10.0pt;
font-family:Arial'> execution.&nbsp; This is much more efficient than Example
1A.</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>Now what
does this have to do with picking </span><span style='font-size:10.0pt;
font-family:"Courier New"'>ArrayList</span><span style='font-size:10.0pt;
font-family:Arial'> or </span><span style='font-size:10.0pt;font-family:"Courier New"'>Vector</span><span
style='font-size:10.0pt;font-family:Arial'>? Well a lot really.&nbsp; In
instances where we are dealing with temporary sets of data or method-scoped
instances, using a </span><span style='font-size:10.0pt;font-family:"Courier New"'>Vector</span><span
style='font-size:10.0pt;font-family:Arial'> is very inefficient. &nbsp;In
situations where there is no chance of their being concurrent access, you
should most certainly choose an </span><span style='font-size:10.0pt;
font-family:"Courier New"'>ArrayList</span><span style='font-size:10.0pt;
font-family:Arial'>. &nbsp;For using a </span><span style='font-size:10.0pt;
font-family:"Courier New"'>Vector</span><span style='font-size:10.0pt;
font-family:Arial'> would serve absolutely no useful purpose, and would provide
unnecessary lock-checking. &nbsp;We’ll leave hashed-collections for later :).</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><st1:place><b><span style='font-family:Arial'>Loop</span></b></st1:place><b><span
style='font-family:Arial'> Iteration and Tail Recursion</span></b><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>As we said
earlier, our programs spend a lot of time in loops, and unfortunately loose a
lot of their performance in them as well.&nbsp; I will try to cover a few
pointers which may help you in certain situations shave some unnecessary
computational cycles off you’re code.</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>People tend
to think from beginning to end, and they tend to program in this forward
lineage as well.&nbsp; But this can often be inefficient. &nbsp;Sometimes the
computer can find its way from the end to the beginning much faster.&nbsp; </span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>Consider
the code in Example 1.</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><b><span style='font-size:10.0pt;font-family:Arial'>Example
1B</span></b><span style='font-size:10.0pt;font-family:Arial'>:</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:9.0pt;
font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:9.0pt;
font-family:Arial'>for (int i = 0; i &lt; arrayList.size(); i++) {</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:9.0pt;
font-family:Arial'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Object obj = (Object) object.get(i);</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:9.0pt;
font-family:Arial'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
obj.doSomething();</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:9.0pt;
font-family:Arial'>}</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:9.0pt;
font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>This is a
fairly straight-forward for-loop to iterate that iterates through an entire
collection to do something.&nbsp; But consider Example 2:</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><b><span style='font-size:10.0pt;font-family:Arial'>Example
2B</span></b><span style='font-size:10.0pt;font-family:Arial'>:</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E6E6E6'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E6E6E6'><span style='font-size:10.0pt;
font-family:Arial'>for (int i = arrayList.size(); i != 0; i--) {</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E6E6E6'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Object obj = (Object) object.get(i);</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E6E6E6'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Obj.doSomething();</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E6E6E6'><span style='font-size:10.0pt;
font-family:Arial'>}</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E6E6E6'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>This
example is many times more efficient than Example 1.&nbsp; In example one, we
are making a call to </span><span style='font-size:9.0pt;font-family:"Courier New"'>arrayList.size()</span><span
style='font-size:10.0pt;font-family:Arial'> for every iteration through the
loop which is unnecessary, and also we are doing a direct XAND comparison to
determine if the loop should continue which is also more efficient.&nbsp; By
looping backwards through the </span><span style='font-size:10.0pt;font-family:
"Courier New"'>ArrayList</span><span style='font-size:10.0pt;font-family:Arial'>
we manage to increase processing efficiency but 50% or more! &nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>Another
magical method to performing ultra-efficient loops has been long-since
forgotten.&nbsp; Yes, I am talking about “tail recursion”.&nbsp; This is one of
the best ways to do mathematical sums on large lists. It also works brilliantly
with Java’s </span><span style='font-size:10.0pt;font-family:"Courier New"'>Iterator</span><span
style='font-size:10.0pt;font-family:Arial'> and </span><span style='font-size:
10.0pt;font-family:"Courier New"'>Enumeration</span><span style='font-size:
10.0pt;font-family:Arial'> interfaces. Consider the following example:</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><b><span style='font-size:10.0pt;font-family:Arial'>Example
1C:</span></b><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>public int getRecordsSum(Iterator iter) {</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
return _getRecordsSum(iter, 1);</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>}</span><o:p></o:p></p>
<pre style='background:#E0E0E0'><span style='font-family:Arial'>&nbsp;</span><o:p></o:p></pre><pre
style='background:#E0E0E0'><span style='font-family:Arial'>public int _getRecordsSum(Iterator iter, int counter) {<br
style='mso-special-character:line-break'>
<![if !supportLineBreakNewLine]><br style='mso-special-character:line-break'>
<![endif]><o:p></o:p></span></pre><pre style='background:#E0E0E0'><span
style='font-family:Arial'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if (iter.hasNext() {<br
style='mso-special-character:line-break'>
<![if !supportLineBreakNewLine]><br style='mso-special-character:line-break'>
<![endif]><o:p></o:p></span></pre><pre style='background:#E0E0E0'><span
style='font-family:Arial'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span><code><span
style='font-size:9.0pt'>return _getRecordsSum(iter, counter + ((Integer)i.next()).intValue());</span></code><o:p></o:p></pre>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
}</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
else {</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp; return counter;</span><o:p></o:p></p>
<p class=MsoNormal style='text-indent:.5in;background:#E0E0E0'><span
style='font-size:10.0pt;font-family:Arial'>}</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>}</span><o:p></o:p></p>
<p class=MsoNormal style='background:#E0E0E0'><span style='font-size:10.0pt;
font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>Now for
those of you who are keen, you might be thinking </span><span style='font-size:
10.0pt;font-family:"Courier New"'>StackOverflowException</span><span
style='font-size:10.0pt;font-family:Arial'> here. &nbsp;But actually, the
compiler will see the optimization opportunity here, just as C and C++
compilers will.&nbsp; The compiler will pick up on the tail recursion based on
the fact that </span><span style='font-size:10.0pt;font-family:"Courier New"'>_getRecordsSum()</span><span
style='font-size:10.0pt;font-family:Arial'> contains no method variables, and
is passing references back into itself.&nbsp; Therefore, this will not cause a
run-away stack, but rather a very efficient way of processing numbers.&nbsp; </span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><b><span style='font-family:Arial'>Final Words</span></b><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>Programming
is all about problem solving.&nbsp; And as with other kinds of problem solving,
there are always many different ways to solve the problem.&nbsp; However, some
ways are more certainly better than others.&nbsp; You should take the time to
understand how the underlying components you are using actually work, and why
they work they way they do.</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><span style='font-size:10.0pt;font-family:Arial'>&nbsp;</span><o:p></o:p></p>
<p class=MsoNormal><i><span style='font-size:10.0pt;font-family:Arial'>Article
By Sachin Mehra (sachinweb@hotmail.com)&nbsp; </span></i><o:p></o:p></p>
<p class=MsoNormal><o:p>&nbsp;</o:p></p>
</div>
</body>
</html>
```

