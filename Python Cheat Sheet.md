---


---

<h1 id="python-3-–-mchens-quick-reference">Python 3 – mchen’s Quick Reference</h1>
<h2 id="data-types">Data types</h2>
<p><strong>Bitwise Operation:</strong><br>
count_of_1 = bin(integer).count(“1”)             #count number of 1s in binary representation of integer</p>
<p>XOR swap<br>
This algorithm works for integers only</p>
<pre><code>x = x ^ y
y = x ^ y
x = x ^ y
</code></pre>
<p>Strings:</p>
<p>s = “foo bar”<br>
s = ‘foo bar’<br>
s = r"c:\dir\new"                     # raw (== ‘c:\dir\new’)<br>
s = “”“Hello<br>
world”""<br>
s.join(" baz")<br>
n = len(s)<br>
“Ala ma {} psy i {} koty”.format(2,3)<br>
“Square root of 2 is equal to {:.2f}”.format(math.sqrt(2))</p>
<pre><code>&gt;&gt;&gt; import re
&gt;&gt;&gt; s = 'test1a'
&gt;&gt;&gt; re.findall('\d+', s) .   #returns a list
['1']    
</code></pre>
<p>Lists:</p>
<p>L = [1, 2, 3, 4, 5]<br>
L = [None]*size<br>
L[0]                                  # single position<br>
L[0:3]                                # the first three elements<br>
L[-2:]                                # the last two elements<br>
L[1:4] = [7,8]                        # substitute, add or remove as applicable<br>
L[::-1]                                 #reverse the list<br>
L[:-1]                                  #return everything except the last character/element safe way of removing that last character/element<br>
del L[2]                              # remove elements<br>
L.append(x)                           # x is a value<br>
L.remove(x)<br>
L.extend(L2)                          # or: L3 = L + L2<br>
L.pop()                               # simple stack (with append)<br>
L.sort()<br>
#list.sort() will manipulate itself, no return object<br>
L.sort(key=lambda x: x[-1]) will sort  <code>L</code>  by the last element.<br>
L.sort(key = lambda x: x[0]**2+x[1]**2)  <code>L</code> is . a list of lists, sort <code>L</code> by L[0]**2 + L[1]**2</p>
<pre><code>&gt;&gt;&gt; a = [[10, 4], [3, 5], [7, 1]]
&gt;&gt;&gt; a.sort(key=lambda x: x[-1])
[[7, 1], [10, 4], [3, 5]]
</code></pre>
<p>x in L                                # does L contain x?<br>
L.index(x)                            # index of the first occurrence<br>
[x*2 for x in L if x&gt;2]               # list comprehensions</p>
<p>Tuples:</p>
<p>x = 1,2,3<br>
x = (1,2,3)<br>
x[1]<br>
a,b,c = x</p>
<p>Dictionaries:</p>
<p>D = {‘f1’: 10, ‘f2’: 20}              # dict creation<br>
D = dict(f1=10, f2=20)<br>
D = collections.defaultdict(int)<br>
D = collections.defaultdict(list)<br>
D = collections.defaultdict(lambda : 0)</p>
<p><strong>Nested Dictionary</strong><br>
D = defaultdict(lambda: defaultdict(lambda: -1))<br>
or<br>
def nested_dict(self):<br>
return collections.defaultdict(self.nested_dict)</p>
<p>keys = (‘a’, ‘b’, ‘c’)<br>
D = dict.fromkeys(keys)               # new dict with empty values</p>
<p>for k in D: print(k)                  # keys<br>
for v in D.values(): print(v)         # values<br>
for k, v in D.items():                # tuples with keys and values<br>
list(D.keys())                        # list of keys<br>
sorted(D.keys())                      # return sorted list of keys</p>
<pre><code>&gt;&gt;&gt; dict = {3:20, 2:30}
&gt;&gt;&gt; print(sorted(dict.keys()))
[2, 3]
</code></pre>
<p>#sorted on Dictionary by key</p>
<pre><code>od = collections.OrderedDict(sorted(d.items()))
or od = sorted(D.items(), key=lambda x: x[0], reverse=True) 
</code></pre>
<p>#sorted on Dictionary returns a list of tuples<br>
*sorted_by_value = sorted(D.items(), key=lambda x: x[1], reverse=True) #Sort by value in reverse order<br>
*sorted_by_value = sorted(D.items(), key=lambda x: -x[1])<br>
*sorted_by_value = sorted(D.items(), key=lambda x: x[1][2])</p>
<pre><code>&gt;&gt;&gt; sorted(D.items(), key=lambda x: x[1][2])
[('item2', [8, 2, 3]), ('item1', [7, 1, 9]), ('item3', [9, 3, 11])]
&gt;&gt;&gt; sorted(D.items(), key=lambda x: x[1])
#sorted on dict returns a list of tuples. sorted_dict = [(1, 3), (2, 2), (3, 1)]
&gt;&gt;&gt; [x[0] for x in sorted_dict][:2]
[1, 2]
</code></pre>
<p>Count of occurrence of values larger than or equal to 2:</p>
<pre><code>a = sum(1 for i in dict.values() if i &gt;= 2)
</code></pre>
<p>D = {}<br>
D[(1,8,5)] = 100                      # 3D sparse matrix<br>
D.get((1,8,5))<br>
D.get((1,1,1), -1)<br>
Nested Dictionary</p>
<pre><code>nested_dict_func = lambda: collections.defaultdict(dict)  
nested_dict = nested_dict_func()
</code></pre>
<p>List cannot be used a key of dictionary, but we can convert it to tuple</p>
<pre><code>dict[tuple(sorted(s))].append(s)
</code></pre>
<p>Sets:</p>
<p>S = {1,3,5}<br>
L = [1, 3, 1, 5, 3]<br>
S = set(L)                            # set([1, 3, 5])<br>
if (3 in S):<br>
S1+S2, S1-S2, S1^S2, S1|S2</p>
<p>Matrix:<br>
Method 1: numpy.matrix.transpose</p>
<pre><code>&gt;&gt;&gt; a = np.array([[1, 2], [3, 4]])
&gt;&gt;&gt; a.transpose()
array([[1, 3],[2, 4]])
</code></pre>
<p>Method 2:</p>
<pre><code>Input:
[1,2,3],  
[4,5,6],  
[7,8,9]
for row in range(len(matrix)):  
    for column in range(row, len(matrix[0])):  
        matrix[row][column], matrix[column][row] = matrix[column][row], matrix[row][column]
Output:
[[1, 4, 7], 
[2, 5, 8], 
[3, 6, 9]]
</code></pre>
<p><strong>Tree</strong><br>
<img src="https://www.geeksforgeeks.org/wp-content/uploads/2009/06/tree12.gif" alt="enter image description here"><br>
Depth First Traversals:<br>
(a) Inorder (Left, Root, Right) : 4 2 5 1 3<br>
(b) Preorder (Root, Left, Right) : 1 2 4 5 3<br>
© Postorder (Left, Right, Root) : 4 5 2 3 1</p>
<p>Breadth First or Level Order Traversal : 1 2 3 4 5</p>
<h2 id="loops">Loops</h2>
<p>for x in range(6):                    # 0, 1, 2, 3, 4, 5<br>
for x in range(1,6):                  # 1, 2, 3, 4, 5<br>
for x in range(1,6,2):                # 1, 3, 5</p>
<p>for k,v in D.items():<br>
print(“D[{}]={}”.format(k,v))     # D[f1]=10  D[f2]=20</p>
<p>L = [1, 3, 5]<br>
for i,v in enumerate(L):              # (index,value)<br>
for x,y in zip(L1,L2):                # returns tuples<br>
for i in sorted(set(L)): print(i)     # sorted set from a list<br>
for x in reversed(L1):</p>
<h2 id="functions">Functions</h2>
<p>def foo(arg1, *args, **dic):<br>
“”"Example documentation string.</p>
<p>This function does not do anything special.<br>
“”"</p>
<h1 id="arg1-is-a-positional-argument">arg1 is a positional argument</h1>
<h1 id="args-is-a-list">args is a list</h1>
<h1 id="dic-is-a-dictionary-of-named-arguments">dic is a dictionary of named arguments</h1>
<p>def foo(a,b,c=0):<br>
L = [1, 2, 3]<br>
foo(*L)                               # unpacking a list of arguments<br>
D = {‘a’: 10, ‘b’: 20}<br>
foo(**D)                              # unpacking a dictionary of arguments</p>
<p>foo.<strong>doc</strong>                           # the docstring</p>
<h2 id="inputoutput">Input/output</h2>
<p>Printing:</p>
<p>str(x)                                # human readable representation<br>
repr(x)                               # interpretable representation</p>
<p>File access:</p>
<p>f = open(“test.txt”, “w”)             # r / r+ / rb / rb+ / w / wb<br>
f.write(“Ala ma kota\n”)<br>
f.close()</p>
<p>for line in open(“test.txt”): print(line, end="")</p>
<p>L = open(“test.txt”).readlines()      # returns a list of lines</p>
<p>Exclusive access:</p>
<p>f = os.fdopen(os.open(“test.txt”, os.O_WRONLY|os.O_EXCL), “w”)</p>
<p>Input:</p>
<p>x = raw_input("Name: ")<br>
for line in sys.stdin: print(line)</p>
<p>String buffers:</p>
<p>from StringIO import StringIO<br>
buf = StringIO()<br>
sys.stdout = buf<br>
print(“Hello”)<br>
x = buf.getvalue()</p>
<p>Error stream:</p>
<p>print(“Error!”, file=sys.stderr, flush=True)</p>
<p>Other file operations:</p>
<p>os.rename(from, to)                  os.remove(path)<br>
os.chmod(file, 0700)                 os.stat(file)</p>
<h2 id="special-names">Special names</h2>
<p><code>__name__</code></p>
<p>name of the file being run not imported</p>
<p>Typical usage:</p>
<p>if <strong>name</strong> == “<strong>main</strong>”:<br>
print("Do something)</p>
<h2 id="exceptions">Exceptions</h2>
<p>try:<br>
raise TypeError(“arg”)<br>
except (RuntimeError, NameError):<br>
pass                              # empty instruction (NOP)<br>
except:<br>
info = sys.exc_info()<br>
print(info[0])<br>
print(info[1])<br>
traceback.print_tb(info[2])<br>
raise<br>
else:<br>
…                               # no exception but before finally<br>
finally:                              # on the way out<br>
…                               # unhandled exc, release resources</p>
<h2 id="object-oriented-programming">Object-oriented programming</h2>
<p>class Person:<br>
ID = 0                            # static variable<br>
def <strong>init</strong>(self, name, age=0):<br>
<a href="http://self.name">self.name</a> = name<br>
self.age  = age<br>
<a href="http://Person.ID">Person.ID</a> += 1<br>
<a href="http://self.ID">self.ID</a> = <a href="http://Person.ID">Person.ID</a><br>
def lastName(self):<br>
return self.name.split()[-1]<br>
def <strong>str</strong>(self):<br>
return “{}({},{})”.format(self.<strong>class</strong>.<strong>name</strong>,<br>
<a href="http://self.name">self.name</a>, self.age)</p>
<p>class Worker(Person):<br>
def <strong>init</strong>(self, name, position, age=0):<br>
super().<strong>init</strong>(name, age)<br>
self.position = position<br>
def <strong>str</strong>(self):<br>
return “{}({},{},{})”.format(self.<strong>class</strong>.<strong>name</strong>,<br>
<a href="http://self.name">self.name</a>, self.position, self.age)</p>
<p>bob = Worker(“Bob Smith”, “developer”, 25)<br>
print(bob)</p>
<h2 id="useful-apis">Useful APIs</h2>
<p>Queues:</p>
<p>Q = collections.deque([10,20,30])<br>
Q.append(40)<br>
Q.popleft()</p>
<p>Pickling:</p>
<p>f = open(“myobj.dat”, “w”)<br>
pickle.dump(x, f)<br>
f = open(“myobj.dat”, “r”)<br>
x = pickle.load(f)</p>
<p>Databases:</p>
<p>conn = sqlite3.connect(“data.db”)<br>
c = conn.cursor()<br>
c.execute(“SELECT * FROM employees”)<br>
for row in c:<br>
print(row[0])<br>
conn.commit()<br>
conn.close()</p>
<p>db = shelve.open(“file”)<br>
db[“x”] = y<br>
db.close()</p>
<p>CGI:</p>
<p>form = cgi.FieldStorage()<br>
print(“Content-type: text/html\n”)<br>
print(cgi.escape(form[“user”].value))</p>
<p>HTTP Server:</p>
<p>srvraddr = ("", 8080)                 # my hostname, portnumber<br>
srvrobj  = BaseHTTPServer.HTTPServer(srvraddr,<br>
CGIHTTPServer.CGIHTTPRequestHandler)<br>
srvrobj.serve_forever()</p>
<p>URLs:</p>
<p>conn = urllib.urlopen(“<a href="http://localhost:8080">http://localhost:8080</a>”)<br>
reply = conn.read()</p>
<h2 id="environment">Environment</h2>
<p>Encoding:</p>
<p>#!/usr/bin/python3</p>
<h1 id="coding-latin-2---">-<em>- coding: latin-2 -</em>-</h1>
<p>Windows – use  <code>.pyw</code>  extension to run the script (with GUI) without a console window.</p>
<p>Paths:</p>
<p>PYTHONPATH<br>
export PYTHONSTARTUP=~/.pythonrc.py</p>
<p>Module  <code>sys</code>:</p>
<p>sys.argv      sys.stdin       sys.stdout      sys.stderr<br>
sys.path      sys.platform    sys.version</p>
<p>Processes (module  <code>subprocess</code>):</p>
<p>res = subprocess.call([“hostname”,"-f"], stderr=subprocess.DEVNULL)<br>
res = subprocess.call(“ps axu | grep ^root”, shell=True)<br>
output = subprocess.check_output([“mycmd”, “myarg”],universal_newlines=True)</p>
<p>Module  <code>os</code>:</p>
<p>os.pathsep    os.sep          os.pardir       os.curdir       os.linesep<br>
os.startfile(“index.html”)<br>
os.popen(“ps ax”).readlines()<br>
os.listdir("/usr/local")              # [‘bin’, ‘etc’, …]<br>
os.glob("*.txt")                      # [‘test.txt’, ‘out.txt’, …]</p>
<p>Module  <code>os.path</code>:</p>
<p>os.path.split("/usr/bin/go.sh")       # (’/usr/bin’, ‘<a href="http://go.sh">go.sh</a>’)<br>
os.path.join("/usr/bin", “<a href="http://go.sh">go.sh</a>”)     # ‘/usr/bin/go.sh’<br>
os.path.splitext("/usr/bin/go.sh")    # (’/usr/bin/go’, ‘.sh’)<br>
os.path.abspath("…/bin/go.sh")       # ‘/usr/bin/go.sh’<br>
os.path.isfile(“<a href="http://go.sh">go.sh</a>”)</p>
<p>Module  <code>os.environ</code>:</p>
<p>os.environ.get(“PYTHONSTARTUP”)</p>
<p>Directories:</p>
<p>for (dir, subdirs, files) in os.walk("/tmp"):<br>
for f in files: print(f)</p>
<h2 id="functional-programming">Functional programming</h2>
<p>f = lambda x: x+10                    # creates an anonymous function<br>
f(5)                                  # returns 15<br>
L = [1, 4, 7]<br>
for x in filter(lambda i: i&lt;5, L):    # returns [1, 4]<br>
for x in map(lambda: x: x*2, L):      # returns [2, 8, 14]</p>

