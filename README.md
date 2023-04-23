Download Link: https://assignmentchef.com/product/solved-assignment-2-simple-query-search-retrieval-services
<br>
<u>Aim</u>

The objectives of this assignment includes:

<ul>

 <li>Learning about <span style="color: #ff0000;">process communication via sockets</span></li>

 <li>Apply the concepts learnt by developing a client-server program simulating a country search directory services</li>

</ul>

<u>Background</u>

This assignment requires you to develop a client-server application using socket programming to simulate a simple ‘query’ search and info retrieval service. The characteristics are as follows:

<u>Server</u>

Upon startup, the server program will read in a list of country data from a text file ‘countries.txt’, and store them in some data structure (e.g. array). Please refer to <strong>Appendix A</strong>, for a description of the fields in each line of record. <strong>Appendix B</strong> shows a sample of the contents in ‘countries.txt’ file.




After storing all the country data records, the server program will then create a socket, bind it to an address, goes into an <u>infinite loop</u> to listen for and accept a connection request.

Upon receiving a connection request, the server is to <u>create a new child process</u> to handle the client’s query. The child process will exit only when client indicates it is done searching for info, and the connection is then closed. While the child process is handling a particular client’s query, the parent process should continue waiting and listening for other client’s request for connection.

<strong>Appendix C</strong> shows an example of the server started in the background, with a message to confirm the startup status.

<u>Client</u>

Upon startup, the client program will create a socket and initiate a connection to the server. Once connection is established, it will prompt user for input (i.e. the name of the country), before sending over client’s query.

Upon receiving server’s response, the client needs to handle 2 main situations:

<ul>

 <li>If the country’s data cannot be found, either because of mis-spelling in the query, or the country is non-existent, the client will output some error message to inform user</li>

</ul>




<ul>

 <li>If the country’s record is found, the client will display some info about the country. (e.g. in <strong>Appendix D</strong>, the country’s capital city, and currency code are shown. However, you are not limited to display only these 2 fields. In fact, you can display whatever pieces of information that is available in ‘countries.txt’ file read in by the server).</li>

</ul>

<ul>

 <li>Finally, <strong>Appendix E</strong> shows a simple simulation of multiple connections from 2 client programs started in 2 shell terminals. While it is difficult to demonstrate processing of multiple requests simultaneously (you need more than a pair of quick hands to do that), your server should be programmed in such a way to accept and handle at least two or more connections.</li>

</ul>

<u>Task Requirements</u>

<ol>

 <li>Please take some time to study the contents in <strong>Appendices A – E</strong> as they provide many useful information that could affect your program’s design, (e.g. how you should store each line of a country’s data as a record).</li>

</ol>

<ol>

 <li>Before you start developing your program, you should take some time to review the output, and expected behavior, plan for basic error handling and analyze the requirements of the client-server socket application.</li>

</ol>

<ol>

 <li>It is recommended that you come up with some basic table of technical requirements to document what you interpret to be desired functionalities of the program, before you proceed with program development.</li>

</ol>

<ol>

 <li>Once the program is completed and tested to be working successfully, you are highly encouraged to add on “new features” to the program that you feel are relevant to the tasks of country directory searching services. Additional marks may be awarded subject to the relevancy and correctness of the new functionalities.</li>

</ol>




<u>Deliverables</u>

<ul>

 <li>The deliverables include the following:</li>

</ul>

<ol>

 <li>The actual working client-server program (hard+soft copies), <strong><em><u>with comments on each file, function or block of code</u></em></strong> to help the tutor understand its purpose.</li>

</ol>

<ol>

 <li>A word document (hard+soft copies) that elaborates on:

  <ul>

   <li>(Interpreted) requirements of the client-sever program</li>

   <li>Diagram / Illustrations of program design</li>

   <li>Summary of implementation of each module in your program</li>

   <li>Reflections on program development (e.g. assumptions made, difficulties faced, what could have been done better, possible enhancements in future, <strong><em>what have you learnt</em></strong>, etc)</li>

  </ul></li>

</ol>

<ol>

 <li>A program demo/evaluation during lab session. You must be prepared to perform certain tasks / answer any questions posed by the tutor.</li>

</ol>




<ul>

 <li>IMPT: Please <strong>follow closely</strong>, to the submission instructions in <strong>Appendix F</strong>, which contains details about what to submit, file naming conventions, when to submit, where to submit, etc.</li>

</ul>

<ul>

 <li>The evaluation will be held during lab session where you are supposed to submit your assignment. Some time will be allocated for you to present / demonstrate your program during the session.</li>

</ul>

<u>APPENDIX A</u>

(Description of fields in ‘countries.txt’ file)




<table>

 <tbody>

  <tr>

   <td width="85"></td>

   <td width="94"><strong>Length</strong></td>

   <td width="108"><strong>Type</strong></td>

   <td width="425"><strong>Description</strong></td>

  </tr>

  <tr>

   <td width="85">Field 1</td>

   <td width="94">2</td>

   <td width="108">character</td>

   <td width="425">Top Level Domain (TLD) code</td>

  </tr>

  <tr>

   <td width="85">Field 2</td>

   <td width="94">variable</td>

   <td width="108">character</td>

   <td width="425">Country’s name</td>

  </tr>

  <tr>

   <td width="85">Field 3</td>

   <td width="94">2</td>

   <td width="108">character</td>

   <td width="425">Country’s code in FIPS104 standard</td>

  </tr>

  <tr>

   <td width="85">Field 4</td>

   <td width="94">2</td>

   <td width="108">character</td>

   <td width="425">Country’s code in ISO2 standard</td>

  </tr>

  <tr>

   <td width="85">Field 5</td>

   <td width="94">3</td>

   <td width="108">character</td>

   <td width="425">Country’s code in ISO3 standard</td>

  </tr>

  <tr>

   <td width="85">Field 6</td>

   <td width="94">variable</td>

   <td width="108">number</td>

   <td width="425">Country’s ISO number</td>

  </tr>

  <tr>

   <td width="85">Field 7</td>

   <td width="94">variable</td>

   <td width="108">character</td>

   <td width="425">Country’s capital name</td>

  </tr>

  <tr>

   <td width="85">Field 8</td>

   <td width="94">variable</td>

   <td width="108">character</td>

   <td width="425">Country’s region (e.g. Asia, Europe, etc)</td>

  </tr>

  <tr>

   <td width="85">Field 9</td>

   <td width="94">variable</td>

   <td width="108">character</td>

   <td width="425">Country’s currency name</td>

  </tr>

  <tr>

   <td width="85">Field 10</td>

   <td width="94">3</td>

   <td width="108">character</td>

   <td width="425">Country’s currency code</td>

  </tr>

  <tr>

   <td width="85">Field 11</td>

   <td width="94">variable</td>

   <td width="108">number</td>

   <td width="425">Country’s population</td>

  </tr>

  <tr>

   <td width="85"></td>

   <td width="94"></td>

   <td width="108"></td>

   <td width="425"></td>

  </tr>

 </tbody>

</table>

<u>APPENDIX B</u>

(Sample contents in ‘countries.txt’ file)

Note1 : Each field in the country’s record is delimited by the comma ‘ <strong>,</strong> ’ character

Note2 : Countries’ name can be MORE THAN one word!

<u>APPENDIX C</u>

(Server startup)

Note : ‘runServer’ is an executable shell script that executes the server program ‘css’. The ‘ps’ command verifies that the server program is started as a background process




<u>APPENDIX D</u>

(Sample output illustrating behavior of client program)







<u>APPENDIX E</u>

(Sample output illustrating multiple client connections)





