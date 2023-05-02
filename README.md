Download Link: https://assignmentchef.com/product/solved-coen278-assignment-1
<br>
Define a string using either literal or “here document”, for example, the following variable “str” is defined with a “here document”

str = &lt;&lt;EOS

Facebook and its founder must release documents and electronic correspondence to a defense lawyer whose client has fled from criminal charges that he falsely claimed a majority ownership in the social media giant, a federal judge said Friday.

EOS

(you can also use %{ } to define string)

then write a method to calculate number of occurrence of any given word. if you pass 2 parameters, str and a string, then it will return number of occurrences of the string in str, if you just pass str, then it will return number of occurrences for every word in a hash for example:

if using above string:




count_word(str, “and”).     #. will return: 2

if the string is:




str = %{three, three, three}

count_word(str).                 #will return: {“three”=&gt;3}




<strong>Question 2.</strong>

Define an array of student record, for example,

students = [

{:firstname =&gt; “John”, :lastname =&gt; “LastnameJohn”,  :phonenumber =&gt; 123456789},

{:firstname =&gt; “Ken”, :lastname =&gt; “Lastnameken”,  :phonenumber =&gt; 456734244},

{:firstname =&gt; “Marisa”, :lastname =&gt; “lastnamemarisa”,  :phonenumber =&gt; 443234567},

{:firstname =&gt; “Ken”, :lastname =&gt; “Kenlastname”,  :phonenumber =&gt; 456734244}

]

write a method to be able to query student,







for example find all the record with firstname is ken:

search_students(students, firstname: “ken”), it will print:




First Name  Last Name      Phone#

Ken            Lastnameken  456734244 Ken            Kenlastname   456734244

you can also define a class to hold students record data and search method,  then pass the object to search_students()







<strong>Question 3. </strong> Write a class for compressing a string (remove duplicate word and be able to recover the original string). when you create an object of this class, you provide a string, then the object save the compressed result as the attribute of the  object. The compressed result will have two arrays:  an array for strings and an array for index (for recovering purpose). For example:  assuming the name of your class is Compress

to create an object, you can call like this:




obj = Compress.new(“i love you but do you love me”) then there will be two instance variables created inside the object to hold two values:

[“i”, “love”, “you”, “but”, “do”, “me”]            # no duplicate word (compressed)

[0, 1, 2, 3, 4, 2, 1, 5]      # index to the original array to  represent original string

Define a method to return the original string.

<strong>Question 4.</strong>  one of the method in Hash class is Hash#merge, it will merge two hashes. it’s format is like this:

merge(second_hash) → new hash merge(second_hash){ | key, val1, val2 | newvalue} → new hash

if no block is given, it merge two hashes, if there is duplicate key, the value of the “other_hash” will be used. if a block is given, the value for the duplicate key is determined by calling the block with the duplicate key, the value in first hash (val1), and the value in second hash (val2)




for example:

h1 = { “a” =&gt; 100, “b” =&gt; 200 } h2 = { “b” =&gt; 254, “c” =&gt; 300 }

h1.merge(h2)            #=&gt; {“a”=&gt;100, “b”=&gt;254, “c”=&gt;300} h1.merge(h2){|key, val1, val2| val2 – val1}

#=&gt; {“a”=&gt;100, “b”=&gt;54,  “c”=&gt;300} h1                      #=&gt; {“a”=&gt;100, “b”=&gt;200}

merge!() is the “dangerous” version of merge(), which will change the h1 to be the merged hash. re-open the class Hash, re-implement these two methods.

<strong>Question 5 </strong>

A template is a HTML file with Ruby code inside. The Ruby code is marked by &lt;% %&gt;. or  if a line start with %, then the whole line is ruby code




For example, the following is an template file:

&lt;%= simple_form_for @project do |f| %&gt;

&lt;%= f.input :name %&gt;

&lt;%= f.input :description %&gt;

&lt;h3&gt;Tasks&lt;/h3&gt;

&lt;div id=’tasks’&gt;

&lt;%= f.simple_fields_for :tasks do |task| %&gt;

&lt;%= render ‘task_fields’, :f =&gt; task %&gt;

&lt;% end %&gt;

&lt;div class=’links’&gt;

&lt;%= link_to_add_association ‘add task’, f, :tasks %&gt;

&lt;/div&gt;

&lt;/div&gt;

&lt;%= f.submit ‘Save’ %&gt;

&lt;% end %&gt;

Write a class, the object of this class has a template attribute and an instance method to “filter” its template, so that all ruby code are removed and filtered string is returned. You can define your string using either here document or normal string quotation %{ }  then create the object, then filter the template and return the filtered string.

[ assuming there is no nested case, for example,  &lt;% a  &lt;% b %&gt; c %&gt; ]

———

<strong>Requirement:</strong>

<ul>

 <li>Define your classes in each .rb file</li>

 <li>Write a main .rb file to require these .rb files, and write code to create object and call method and output results.</li>

 <li>Write comment</li>

 <li>Your program should do some data check, for example, in question 1, if str is empty. in question 2, if no match, print out “no match is found”.</li>

 <li>Use #! to make your main .rb program be able to run directly.</li>

</ul>