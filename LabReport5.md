# CSE 15L Lab Report 5 - Putting it All Together
By: Athena Taylor

***

## Part 1
* Initial Post
> Jane Doe
>   
> Hi!  
> I wrote a Java program that checks if two strings given as command line arguments are equal and a bash script that runs some test cases. However, the test case for two equal strings is failing, and I can't figure out why.
 Here's a screenshot:

![Image](lab-report-5-symptom.png)

> Could you help me figure out what the problem is?

* TA Response
> Athena Taylor  
>   
> Hi Jane.
> You'll have to post the contents of the Java file and your bash script otherwise I can't really determine what the problem is. However, if it's just the equals case that's failing, have you made sure you're comparing the actual strings and not their references?


* Student Follow-up
> Jane Doe
>
> You were right! I used the equals method to compare the strings instead of != and now all the test cases are working.

![Image](lab-report-5-success.png)


> Thank you!

* Setup Information
> File Structure

![Image](lab-report-5-file-structure)

> File Contents

> Command to Trigger Bug

```
bash tesh.sh
```

> Fix
> Change line 12 in StringChecker.java from `if(args[0] != args[1])` to `if(!(args[0].equals(args[1])))`


## Part 2
> I learned how to use the Java Debugger tool, which allows you to examine a Java program at any point during its runtime. I'm happy about this because it's quicker than manually writing print statements, which is what I was doing before.


