# Password_Hashing_Assignment
I have written my test cases based on the requirements listed in the specifications. I try to breakdown test cases into the smallest pieces I can. I believe test cases should only have one reason for failing. This allows the QA person to report what is wrong as specifically as they can.

An example would be if I wrote a large case for all requirements in sending a POST for hashing the password. If all requirements listed for that call were one big case, then the test case would have failed for several reasons. The way I broke down the requirements into several test cases allows me to more accurately report my findings and makes it much easier for Devs to fix. The main issue is the malformed input response and due to that I am blocked in being able to test the other requirements. So I am more accurately reporting the other requirements as blocked and not as failures.

If this was a real world situation I would also build a Confluence page or something similar detailing the installation process and curl commands used. 

My feedback on the assignment overall would be that the main feature being a bug doesn’t seem like a real world scenario. My expectations would be that the Devs would not send out an application to be tested with the main feature being broken in such a manner. I would expect smaller items to be broken and not the main feature.

If this was in the pre-prod environment and being regression tested I wouldn’t expect to see the issues found. Main requirements for the application would/should have been caught before being shipped to pre-prod.

Overall this assignment was a good challenge for me and I learned things that I didn’t know before. I appreciate the opportunity and hope to hear your feedback soon.

Bug report #1

Title: User is receiving a Malformed Input error when trying to send a POST call to hash a password.

Prereq: Have Password Hashing App running

Steps: 
1. Send a POST call, ex. “curl -X POST -H "application/json" -d '{"password":"angrymonkey"}' http://127.0.0.1:8088/hash"
2. Wait for response

Results - Malformed Input error received

Expected Results - User should receive a job identifier response, 5 seconds after the password should begin to hash.

*This issue is blocking multiple other test cases.*


Bug report #2

Title: User is not receiving a 200 response when shutting down the program.

Prereq: Have Password Hashing App running

Steps:
1. Send a POST call, ex “curl -X POST -d ‘shutdown’ http://127.0.0.1:8088/hash”
2. Wait for 200 Empty Response

Results - No 200 response received. App does shut down

Expected Results - User should receive a 200 Empty Response before shut down is completed.
