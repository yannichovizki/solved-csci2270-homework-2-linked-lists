Download Link: https://assignmentchef.com/product/solved-csci2270-homework-2-linked-lists
<br>
<h1></h1>

OBJECTIVES

<ol>

 <li><strong>Create, traverse, add and delete nodes to a linked list </strong></li>

 <li><strong>Transmit messages through in a linked list </strong></li>

 <li><strong>Get practice implementing classes </strong></li>

</ol>

<strong> </strong>Background

In the Lord of the Rings trilogy, there is a scene where a warning beacon is lit in the towers of Minas Tirith, which is seen by a second beacon, prompting them to light their own fire which a third beacon sees, and so forth. This was a rapid means of communication in the days before telegraphs were invented. In this assignment, you’re going to simulate a communications network using a linked list. Each node in the list will represent a country and you need to be able to send a message between nodes from one side of the world to the other.

<h2>Building your own communications network</h2>

You will be implementing a class to simulate a linear communication network between countries. There are three files in Moodle containing a code skeleton to get you started. <em>Do not modify the header file or your code won’t work in Moodle!</em> You will have to complete both the class implementation in CountryNetwork.cpp and the driver file main.cpp.




The linked-list itself will be implemented using the following struct (already included in the header file):

<table width="629">

 <tbody>

  <tr>

   <td width="629"><strong>struct</strong> <strong>Country </strong><strong>{ </strong><strong>    </strong><strong>string</strong> <strong>name</strong><strong>;         </strong><strong>// name of the country </strong><strong>    </strong><strong>string message;</strong><strong>     </strong><strong> // message this country has received </strong><strong>    </strong><strong>int</strong> <strong>numberMessages</strong><strong>;  </strong><strong>// no. of messages passed through this country </strong><strong>    </strong><strong>Country *next;</strong><strong>      </strong><strong> // pointer to the next country </strong><strong>}; </strong></td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<h2><u>Class Specifications</u></h2>

The <strong>CountryNetwork</strong> class definition is provided in the file <em>CountryNetwork.hpp</em> in Moodle. <em>Do not modify this file or your code won’t work on Moodle! </em>Fill in the file <em>CountryNetwork.cpp</em> according to the following specifications.

<strong>Country* head; </strong>

<ul>

 <li>Points to the first node in the linked list</li>

</ul>

<strong>CountryNetwork(); </strong>

<ul>

 <li>Class constructor; set the head pointer to NULL</li>

</ul>

<strong>bool isEmpty(); </strong>

<ul>

 <li>Return true if the head is NULL, false otherwise</li>

</ul>

<h3>void insertCountry(Country* previous, string countryName);  <em>// Beware of edge cases</em></h3>

<ul>

 <li>Insert a new country with name <strong>countryName</strong> in the linked list after the country pointed to by <strong>previous</strong>.</li>

 <li>If <strong>previous</strong> is NULL, then add the new country to the beginning of the list.</li>

 <li>Print the name of the country you added according to the following format:</li>

</ul>

<table width="577">

 <tbody>

  <tr>

   <td width="577">// If you are adding at the beginning use this: cout &lt;&lt; “adding: ” &lt;&lt; countryName &lt;&lt; ” (HEAD)” &lt;&lt; endl;// Otherwise use this: cout &lt;&lt; “adding: ” &lt;&lt; countryName &lt;&lt; ” (prev: ” &lt;&lt; previous-&gt;name &lt;&lt; “)” &lt;&lt; endl;</td>

  </tr>

 </tbody>

</table>

<h3>void deleteCountry(string countryName); <em>// Beware of edge cases</em></h3>

➔ Traverse the list to find the node with name <strong>countryName</strong>, then delete it. If there is no node with name <strong>countryName</strong>, print <em>“Country does not exist.”</em>

<h3>void loadDefaultSetup();</h3>

➔ First, delete whatever is in the linked list using the member function <strong>deleteEntireNetwork</strong>. Then add the following six countries, in order, to the network with <strong>insertCountry</strong>: “United States”, “Canada”, “Brazil”, “India”, “China”, “Australia”

<h3>Country* searchNetwork(string countryName);</h3>

➔ Return a pointer to the node with name <strong>countryName</strong>. If <strong>countryName </strong>cannot be found, return NULL







<h3>void deleteEntireNetwork();</h3>

➔ If the list is empty, do nothing and return. Otherwise, delete every node in the linked list and set <strong>head </strong>to NULL. Print the name of each node as you are deleting it according to the following format:

cout &lt;&lt; “deleting: ” &lt;&lt; node-&gt;name &lt;&lt; endl;

<strong>             </strong>After the entire linked list is deleted, print:

cout &lt;&lt; “Deleted network” &lt;&lt; endl;

<strong> </strong>

<h3>void transmitMsg(string receiver, string msg);</h3>

<ul>

 <li>Traverse the linked list from the head to the node with name <strong>receiver</strong>. For each node in this path (including the head), set the node’s <strong>message</strong> to <strong>msg</strong> and increment the node’s <strong>numberMessages</strong> If the list is empty, print “Empty list” and exit the function. If the node is not present, print “Country not found”.</li>

 <li>As you traverse the list, at each node report the message received and the number of messages received using the following cout: (See the end of this document for example output)</li>

</ul>

cout &lt;&lt; node-&gt;name &lt;&lt; ” [# messages received: ” &lt;&lt; node-

&gt;numberMessages &lt;&lt; “] received: ” &lt;&lt; node-&gt;message &lt;&lt; endl;

<strong> </strong>

<h3>void printPath();</h3>

<ul>

 <li>Print the names of each node in the linked list. Below is an example of correct output using the default setup. (Note that you will <strong>cout &lt;&lt; “NULL” </strong>at the end of the path)</li>

</ul>

== CURRENT PATH ==

United States -&gt; Canada -&gt; Brazil -&gt; India -&gt; China -&gt; Australia -&gt; NULL ===

<ul>

 <li>If the network is empty then print <em>“nothing in path”</em></li>

</ul>

<strong> </strong>

<h2><u>Main driver file</u></h2>




Your program will start by displaying a menu by calling the <strong>displayMenu</strong> function included in main.cpp. The user will select an option from the menu to decide what the program will do, after which, the menu will be displayed again. The specifics of each menu option are described below.

<h3>Option 1: Build Network</h3>

This option calls the <strong>loadDefaultSetup</strong> function, then calls the <strong>printPath </strong>function. You should get the following output:

<table width="623">

 <tbody>

  <tr>

   <td width="623">adding: United States (HEAD) adding: Canada (prev: United States) adding: Brazil (prev: Canada) adding: India (prev: Brazil) adding: China (prev: India) adding: Australia (prev: China)== CURRENT PATH ==United States -&gt; Canada -&gt; Brazil -&gt; India -&gt; China -&gt; Australia -&gt; NULL ===</td>

  </tr>

 </tbody>

</table>

<h3>Option 2: Print Network Path</h3>

Calls the <strong>printPath</strong> function. Output should be in the format below:

<table width="624">

 <tbody>

  <tr>

   <td width="624">// Output for the default setup== CURRENT PATH ==United States -&gt; Canada -&gt; Brazil -&gt; India -&gt; China -&gt; Australia -&gt; NULL===<strong> </strong>// Output when the linked list is empty== CURRENT PATH == nothing in path===</td>

  </tr>

 </tbody>

</table>

<h3>Option 3: Add Country</h3>

Prompt the user for two inputs: the name of a new country to add to the network, <strong>newCountry</strong>, and the name of a country already in the network, <strong>previousCountry</strong>, which will precede the new country. Use the member functions <strong>searchNetwork</strong> and <strong>insertCountry</strong> to insert <strong>newCountry </strong>into the linked-list right after the node with the country name

<strong>previousCountry</strong>.

<ul>

 <li>If the user wants to add the new country to the head of the network then they should enter “First” instead of a previous country name.</li>

 <li>If the user enters an invalid previous city (not present in the linked list), then you need to prompt the user with the following error message and collect input again until they enter a valid previous country name or “First”:</li>

</ul>

cout &lt;&lt; “INVALID country…Please enter a VALID previous country name:” &lt;&lt; endl;

<ul>

 <li>Once a valid previous country name is passed and the new country is added, call the function <strong>printPath</strong> to demonstrate the new linked-list.</li>

</ul>

For example, the following should be the output if the linked-list contains the default setup from option (1) and the user wants to add Colombia after Brazil:

<table width="672">

 <tbody>

  <tr>

   <td width="672">Enter a new country name:ColombiaEnter the previous country name (or First):Brazil  adding: Colombia (prev: Brazil)== CURRENT PATH ==United States -&gt; Canada -&gt; Brazil -&gt; Colombia -&gt; India -&gt; China -&gt; Australia -&gt;NULL===</td>

  </tr>

 </tbody>

</table>

<h3>Option 4: Delete Country</h3>

Prompt the user for a country name, then pass that name to the <strong>deleteCountry </strong>function and call <strong>printPath</strong> to demonstrate the new linked-list.

For example, the following should be the output if the linked-list contains the default setup from option (1) and the user wants to delete Canada:

Enter a country name:

Canada

== CURRENT PATH ==

United States -&gt; Brazil -&gt; India -&gt; China -&gt; Australia -&gt; NULL ===

<h3>Option 5: Transmit Message</h3>

Prompt the user for two inputs: a message to send, and the name of a country to receive the message <em>(Hint: use <strong>getline</strong> in case there are spaces in the user input)</em>. Pass the message and country name to the <strong>transmitMsg</strong> function. <em>Don’t forget to add a newline after the message is collected, and before the output is printed. This is done for better readability.</em>

For example, the following should be the output if the linked-list contains the default setup from option (1) and the message “bom dia” is sent to “Brazil”:

<table width="624">

 <tbody>

  <tr>

   <td width="624">Example 1:Enter name of the country to receive the message:BrazilEnter the message to send:  bom dia United States [# messages received: 1] received: bom diaCanada [# messages received: 1] received: bom diaBrazil [# messages received: 1] received: bom dia</td>

  </tr>

 </tbody>

</table>




If the user then decides to transmit the message “ni hao” to “China”, the output will be:

<table width="624">

 <tbody>

  <tr>

   <td width="624">Example 2:Enter name of the country to receive the message:ChinaEnter the message to send:  ni hao<strong> </strong>United States [# messages received: 2] received: ni haoCanada [# messages received: 2] received: ni haoBrazil [# messages received: 2] received: ni haoIndia [# messages received: 1] received: ni haoChina [# messages received: 1] received: ni hao</td>

  </tr>

 </tbody>

</table>




If the user then decides to transmit the message “Sushi” to “Japan”, the output when the country is not present will be:

<table width="624">

 <tbody>

  <tr>

   <td width="624">Example 3:Enter name of the country to receive the message:JapanEnter the message to send: Sushi</td>

  </tr>

 </tbody>

</table>




Country not found




<strong> </strong>

<h3>Option 6: Clear network</h3>

Call the <strong>deleteEntireNetwork </strong>function. For example, deleting the default network should print:

<table width="624">

 <tbody>

  <tr>

   <td width="624">Network before deletion== CURRENT PATH ==United States -&gt; Canada -&gt; Brazil -&gt; India -&gt; China -&gt; Australia -&gt; NULL=== deleting: United States deleting: Canada deleting: Brazil deleting: India deleting: China deleting: Australia Deleted networkNetwork after deletion == CURRENT PATH == nothing in path===</td>

  </tr>

 </tbody>

</table>

<h3>Option 7: Quit</h3>

Print the following message:

cout &lt;&lt; “Quitting… cleaning up path: ” &lt;&lt; endl;

Then call <strong>printPath</strong>, followed by <strong>deleteEntireNetwork</strong>. Now, check if the network is empty using <strong>isEmpty</strong>. If it is, print:

cout &lt;&lt; “Path cleaned” &lt;&lt; endl;

Otherwise, print:

cout &lt;&lt; “Error: Path NOT cleaned” &lt;&lt; endl;




Finally, print the following before exiting the program:

cout &lt;&lt; “Goodbye!” &lt;&lt; endl;

<strong> </strong>













<strong><u>Appendix:</u></strong>

<strong> </strong>

<h4>● CountryNetwork::insertCountry()</h4>

○ cout &lt;&lt; “adding: ” &lt;&lt; countryName &lt;&lt; ” (HEAD)” &lt;&lt; endl;

○ cout &lt;&lt; “adding: ” &lt;&lt; countryName &lt;&lt; ” (prev: ” &lt;&lt; previous-

&gt;name &lt;&lt; “)” &lt;&lt; endl;




<h4>● CountryNetwork::transmitMsg()</h4>

○ cout &lt;&lt; “Empty list” &lt;&lt; endl;

○ cout &lt;&lt; “Country not found” &lt;&lt; endl;

○ cout &lt;&lt; sender-&gt;name &lt;&lt; “ [# messages received: ” &lt;&lt; sender&gt;numberMessages &lt;&lt; “] received: ” &lt;&lt; sender-&gt;message &lt;&lt; endl;

<h4>● CountryNetwork::printPath()</h4>

○ cout &lt;&lt; “== CURRENT PATH ==” &lt;&lt; endl;

○ cout &lt;&lt; “nothing in path” &lt;&lt; endl;

○ cout &lt;&lt; ptr-&gt;name &lt;&lt; ” -&gt; “;

○ cout &lt;&lt; ptr-&gt;name &lt;&lt; ” -&gt; “;

○ cout &lt;&lt; “NULL” &lt;&lt; endl;

○ cout &lt;&lt; “===” &lt;&lt; endl;




<h4>● main()</h4>

○ cout &lt;&lt; “Enter name of the country to receive the message: “&lt;&lt; endl;

○ cout &lt;&lt; “Enter the message to send: ” &lt;&lt; endl;

○ cout &lt;&lt; endl;

○ cout &lt;&lt; “Enter a new country name: ” &lt;&lt; endl;

○ cout &lt;&lt; “Enter the previous country name (or First): ” &lt;&lt; endl;

○ cout &lt;&lt; “INVALID(previous country name)…Please enter a VALID previous country name!” &lt;&lt; endl;

○ cout &lt;&lt; “Quitting…” &lt;&lt; endl;

○ cout &lt;&lt; “Invalid Input” &lt;&lt; endl;

○ cout &lt;&lt; “Goodbye!” &lt;&lt; endl;







<h3><em>Instructors: Zagrodzki, Ashraf, Trivedi</em></h3>

<h4>● displayMenu()</h4>

○ cout &lt;&lt; endl;

○ cout &lt;&lt; “Select a numerical option:” &lt;&lt; endl;

○ cout &lt;&lt; “+=====Main Menu=========+” &lt;&lt; endl;

○ cout &lt;&lt; ” 1. Build Network ” &lt;&lt; endl;

○ cout &lt;&lt; ” 2. Print Network Path ” &lt;&lt; endl;

○ cout &lt;&lt; ” 3. Add Country ” &lt;&lt; endl;

○ cout &lt;&lt; ” 4. Delete Country ” &lt;&lt; endl;

○ cout &lt;&lt; ” 5. Transmit Message ” &lt;&lt; endl;

○ cout &lt;&lt; ” 6. Clear Network” &lt;&lt; endl;

○ cout &lt;&lt; ” 7. Quit ” &lt;&lt; endl;

○ cout &lt;&lt; “+———————–+” &lt;&lt; endl;

○ cout &lt;&lt; “#&gt; “;


