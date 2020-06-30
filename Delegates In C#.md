# Delegates in C#

### What is Delegates in C#?
`The definition says a delegate is a reference type variable that holds a reference to a method/function with a specific parameter list and return type. A delegate is nothing but a type that is declared by the delegate keyword and acts as a type-safe function pointer.`

### Important Sticky  
- Delegates allow methods to be passed as parameters.
- Delegates are type safe function pointer.
- Delegate instances attach or detach a method at run time making it more dynamic and flexible to use.
- Delegates can invoke more than one method using the Multicast feature.
- Delegates are of reference types.

### Sample Code
<div class="dp-highlighter"> <div class="bar"></div> <ol class="dp-c"> <li class="alt"><span><span class="keyword">namespace</span><span>&nbsp;Delegates&nbsp;&nbsp;</span></span> </li><li><span>{&nbsp;&nbsp;</span> </li><li class="alt"><span><span class="keyword">&nbsp;&nbsp;&nbsp;public</span><span>&nbsp;</span><span class="keyword">delegate</span><span>&nbsp;</span><span class="keyword">void</span><span>&nbsp;myTestDel(</span><span class="keyword">string</span><span>&nbsp;Name);&nbsp;&nbsp;</span></span> </li><li><span><span class="keyword">&nbsp;&nbsp;&nbsp;class</span><span>&nbsp;Program&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;</span> </li><li><span><span class="keyword">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;static</span><span>&nbsp;</span><span class="keyword">void</span><span>&nbsp;Main(</span><span class="keyword">string</span><span>[]&nbsp;args)&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;</span> </li><li><span><span class="comment">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;//&nbsp;Normal&nbsp;Methos&nbsp;Call</span><span>&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;getName(<span class="string">"By&nbsp;Normal&nbsp;Method&nbsp;call&nbsp;-&nbsp;Abhishek&nbsp;Singh&nbsp;"</span><span>);&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;</span> </li><li class="alt"><span><span class="comment">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;//Method&nbsp;Call&nbsp;using&nbsp;delegates</span><span>&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;myTestDel&nbsp;del&nbsp;=&nbsp;<span class="keyword">new</span><span>&nbsp;myTestDel(getName);&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;del(<span class="string">"By&nbsp;Delagete&nbsp;call-Abhishek&nbsp;singh"</span><span>);&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;del.Invoke(<span class="string">"&nbsp;Using&nbsp;Invoke&nbsp;-&nbsp;Abhishek&nbsp;Singh&nbsp;"</span><span>);&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;del&nbsp;=&nbsp;<span class="keyword">new</span><span>&nbsp;myTestDel(getLocation);&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;del(<span class="string">"Mumbai"</span><span>);&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Console.ReadLine();&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}<br>&nbsp;&nbsp;</span> </li><li class="alt"><span><span class="keyword">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;public</span><span>&nbsp;</span><span class="keyword">static</span><span>&nbsp;</span><span class="keyword">void</span><span>&nbsp;getName(</span><span class="keyword">string</span><span>&nbsp;name)&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine(<span class="string">"My&nbsp;Name:&nbsp;"</span><span>&nbsp;+&nbsp;name);&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;</span> </li><li><span><span class="keyword">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;public</span><span>&nbsp;</span><span class="keyword">static</span><span>&nbsp;</span><span class="keyword">void</span><span>&nbsp;getLocation(</span><span class="keyword">string</span><span>&nbsp;location)&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine(<span class="string">"My&nbsp;Loc:&nbsp;"</span><span>&nbsp;+&nbsp;location);&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;</span> </li><li class="alt"><span>}&nbsp;&nbsp;</span></li></ol></div>

### What is Multicast Delegates ?
`Delegates can be used to assign multiple objects to one delegate instance meaning simply execute multiple methods in sequence meaning the delegate points to more than one function.
A Multicast delegates holds delegates of the same type in the list that, when called, get invoked in sequence.`
<ol class="dp-c"> <li class="alt"><span><span>myTestDel&nbsp;delmultiCast&nbsp;=&nbsp;</span><span class="keyword">new</span><span>&nbsp;myTestDel(getName);&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;</span> </li><li class="alt"><span>delmultiCast&nbsp;+=&nbsp;getLocation;&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;</span> </li><li class="alt"><span>delmultiCast(<span class="string">"Abhi"</span><span>);&nbsp;&nbsp;</span></span></li></ol>

`A Delegate instance can be pointed to by multiple methods using the += sign as stated above. Basically it adds the multiple methods to one delegate instance in the invocation list.`
### Sample Code :
<ol class="dp-c"> <li class="alt"><span><span class="keyword">namespace</span><span>&nbsp;Delegates&nbsp;&nbsp;</span></span> </li><li><span>{&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">public</span><span>&nbsp;</span><span class="keyword">delegate</span><span>&nbsp;</span><span class="keyword">void</span><span>&nbsp;myTestDel(</span><span class="keyword">string</span><span>&nbsp;Name);&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">public</span><span>&nbsp;</span><span class="keyword">delegate</span><span>&nbsp;</span><span class="keyword">void</span><span>&nbsp;TestMutliCast();&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">public</span><span>&nbsp;</span><span class="keyword">delegate</span><span>&nbsp;</span><span class="keyword">int</span><span>&nbsp;TestMutliCastint();&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">class</span><span>&nbsp;Program&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">static</span><span>&nbsp;</span><span class="keyword">void</span><span>&nbsp;Main(</span><span class="keyword">string</span><span>[]&nbsp;args)&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="comment">//&nbsp;Normal&nbsp;Methos&nbsp;Call</span><span>&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;getName(<span class="string">"By&nbsp;Normal&nbsp;Method&nbsp;call&nbsp;-&nbsp;Abhishek&nbsp;Singh&nbsp;"</span><span>);&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="comment">//Method&nbsp;Call&nbsp;using&nbsp;delegates</span><span>&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;myTestDel&nbsp;del&nbsp;=&nbsp;<span class="keyword">new</span><span>&nbsp;myTestDel(getName);&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;del(<span class="string">"By&nbsp;Delagete&nbsp;call-Abhishek&nbsp;singh"</span><span>);&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;del.Invoke(<span class="string">"&nbsp;Using&nbsp;Invoke&nbsp;-&nbsp;Abhishek&nbsp;Singh&nbsp;"</span><span>);&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;del&nbsp;=&nbsp;<span class="keyword">new</span><span>&nbsp;myTestDel(getLocation);&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;del(<span class="string">"Mumbai"</span><span>);&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="comment">//&nbsp;&nbsp;&nbsp;Mutlticast&nbsp;implementation&nbsp;with&nbsp;void&nbsp;return&nbsp;type</span><span>&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TestMutliCast&nbsp;delmultiCast&nbsp;=&nbsp;<span class="keyword">new</span><span>&nbsp;TestMutliCast(Method1);&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;delmultiCast+=Method2;&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;delmultiCast();&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="comment">//&nbsp;Mutlticast&nbsp;implementation&nbsp;with&nbsp;void&nbsp;return&nbsp;type</span><span>&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;myTestDel&nbsp;testMulti&nbsp;=&nbsp;<span class="keyword">new</span><span>&nbsp;myTestDel(getName);&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;testMulti&nbsp;+=&nbsp;getLocation;&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;testMulti(<span class="string">"Abhi"</span><span>);&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="comment">//&nbsp;Mutlticast&nbsp;implementation&nbsp;with&nbsp;int&nbsp;return&nbsp;type</span><span>&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TestMutliCastint&nbsp;intMulti&nbsp;=&nbsp;<span class="keyword">new</span><span>&nbsp;TestMutliCastint(Method3);&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;intMulti&nbsp;+=&nbsp;Method4;&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">int</span><span>&nbsp;i=&nbsp;intMulti();&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine(<span class="string">"Return&nbsp;Value&nbsp;is&nbsp;"</span><span>&nbsp;+&nbsp;i);&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Console.ReadLine();&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">public</span><span>&nbsp;</span><span class="keyword">static</span><span>&nbsp;</span><span class="keyword">void</span><span>&nbsp;Method1()&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine(<span class="string">"Delegate&nbsp;1st&nbsp;method&nbsp;called!!!!"</span><span>);&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">public</span><span>&nbsp;</span><span class="keyword">static</span><span>&nbsp;</span><span class="keyword">void</span><span>&nbsp;Method2()&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine(<span class="string">"Delegate&nbsp;2nd&nbsp;method&nbsp;called!!!!"</span><span>);&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">public</span><span>&nbsp;</span><span class="keyword">static</span><span>&nbsp;</span><span class="keyword">int</span><span>&nbsp;Method3()&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine(<span class="string">"Delegate&nbsp;3rd&nbsp;method&nbsp;called!!!!"</span><span>);&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">return</span><span>&nbsp;3;&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">public</span><span>&nbsp;</span><span class="keyword">static</span><span>&nbsp;</span><span class="keyword">int</span><span>&nbsp;Method4()&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine(<span class="string">"Delegate&nbsp;4th&nbsp;method&nbsp;called!!!!"</span><span>);&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">return</span><span>&nbsp;4;&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">public</span><span>&nbsp;</span><span class="keyword">static</span><span>&nbsp;</span><span class="keyword">void</span><span>&nbsp;getName(</span><span class="keyword">string</span><span>&nbsp;name)&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine(<span class="string">"My&nbsp;Name:&nbsp;"</span><span>&nbsp;+&nbsp;name);&nbsp;&nbsp;</span></span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;</span> </li><li class="alt"><span>&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">public</span><span>&nbsp;</span><span class="keyword">static</span><span>&nbsp;</span><span class="keyword">void</span><span>&nbsp;getLocation(</span><span class="keyword">string</span><span>&nbsp;location)&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine(<span class="string">"My&nbsp;Loc:&nbsp;"</span><span>&nbsp;+&nbsp;location);&nbsp;&nbsp;</span></span> </li><li class="alt"><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;</span> </li><li><span>&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;</span> </li><li class="alt"><span>}&nbsp;&nbsp;</span></li></ol>