# Week 9 Lab Report by Gabriel Renslow

# `Part 1 - Debugging Scenario`

Student: Hi teacher I have a problem with my code. It's not working.

Screenshot:
```
float c = 0;
bool on = false;
while(1) {
  c++;
  if (c==5) {
    on = true;
  }
}
```
Directory: lib\fart.java

Commands:
```
javac fart.java
java fart
```

Tutor: Let me see the code. *opens code*
Tutor: It looks like you have an infinite loop. You put a 1 in the while loop. Change it to the boolean you made, "on".
Student: Thank you! I'll try it right now!
Student: It works thank you so much!!!

Screenshot:
```
float c = 0;
bool on = false;
while(on) {
  c++;
  if (c==5) {
    on = true;
  }
}
```

# `Part 2 - Reflection`

One thing I learned this half of the quarter that I thought was really interesting was learning ow to run .sh files. I didnt really know what they were used for before but now I know that they are used to run bash commands. I was hoping we'd learn how to run bash commands via a file and YIPPEE we did.
