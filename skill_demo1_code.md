## Template for CSE15L Skill Demo 1

1.
git clone https://github.com/ucsd-cse15l-f22/skill-demo1

2.
javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java
java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore TestDocSearch

3.
Line14: change to "1391"

4.
javac DocSearchServer.java Server.java
java DocSearchServer 4000

5.
http://localhost:4000/search?q=biomed
http://localhost:4000/search?q=cse

6.
ssh cs15lfa22xx@ieng6.ucsd.edu
git clone https://github.com/ucsd-cse15l-f22/skill-demo1

7.
javac DocSearchServer.java Server.java
java DocSearchServer 2333

http://ieng6-2xx.ucsd.edu:2333/search?q=biomed
http://ieng6-2xx.ucsd.edu:2333/search?q=cse

8.
Change line 47: f.getName().contains()

9.
javac DocSearchServer.java Server.java
java DocSearchServer 4000

http://localhost:4000/search?q=rr74
http://localhost:4000/search?q=rr73

10.
scp ./DocSearchServer.java cs15lfa22xx@ieng6.ucsd.edu:~/skill-demo1/

javac DocSearchServer.java Server.java
java DocSearchServer 4000

http://ieng6-2xx.ucsd.edu:2333/search?q=rr74
http://ieng6-2xx.ucsd.edu:2333/search?q=rr73


Ieng6 Format:
cs15lfa22pn@ieng6.ucsd.edu

Vim Editing:
vim skill-demo1
i
ESC
:wq