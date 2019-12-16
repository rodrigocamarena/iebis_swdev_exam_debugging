# iebis_swdev_exam_debugging
Somebody from administration wanted to create a random phrase generators and created the code that you can find in Main.java for this purpose.

The intention was to transform students email address to something similar but using slashes ("/") instead of dots ("."). Then he wanted to put a random word in front of the result to create weird sentences.

So for an email address like "john.doe.mis2016@ie.edu" the potential outputs should be one of the following sentences:

```
Your john/doe/mis2016@ie/edu
Four john/doe/mis2016@ie/edu
Tour john/doe/mis2016@ie/edu
```

So basically, every time that you run the code, one of these sentences should be printed in the console, but this is not happening since it seems there's something wrong in the code.

The intention is that these sentences appear with equal equiprobability, so if we would run the code 1000 times, the expected repetitions of each sentence should be close to 333 for each one. Obviously, we can not achieve exactly one third of the times with a random generator, but at least it would be close.

The problem is that nothing of this is happenning now.

Your goal is to fix the code changing the code as little as possible. Obviously we could make some new code that does the same. But that won't score, the goal here is to fix the actual code and find the bugs.

======================================================================

# Instructions
1. Execute the code and see how the outputs differ from the expected.
2. Read the code carefully and figure out what the author tried to do.
3. Then proceed to debug and spot in which points the code is not doing what it apparently does.
4. Looking to documentation online or in IntelliJ, or just using your intuition, fix the code so it performs the requested output.
5. Modify the Readme.md and mention which bugs you found, don't limit yourself to fix them. Explain what you found and why they are bugs.

# Instructions to get the code and present it
1. Up in the GitHub interface you will see a *Fork* button. Click it and choose your account. This will create a copy of this project on your GitHub account.
2. Go to your recently copied project (make sure your user name appear in front of the name of the project).
3. Clone your project into your workspace.
4. Make any modifications to fulfill the requirements in your workspace unsing IntelliJ.
5. Commit your changes.
6. Push it to origin: "git push origin".
7. Add "*Chezlui*" as a collaborator to your project.

## Rules to consider
1. You are free to use Internet to consult resources.
2. *Push any code before the deadline*. Any code presented after the deadline will be scored as 0. Better upload something early than a perfect solution late.
3. Scoring won't take into account any kind of working code. The goal is to spot bugs and fix them (obviusly this will transform the failing code into working code).

## Hints
There are basically 4 bugs in this code. You must spot the 4 of them in order to score all the points, but also be aware of your available time, it's better to upload 3 bugs than nothing.
Scoring criteria:
- 60%: Spot all the bugs
- 20%: Fix all the bugs and push the proposed solution to your repository online
- 20%: Explain the solved exercise in the README, in the best possible way

## Changes
1. We have added a double \\ where the "." so the email is printed correctly.
2. The bound of the random generater was 2. So, the last case (the one where the random number takes 2 as a value) could never be reached. We were generating numbers between 0 and 1. So, we have to put 3 as a bound so we can reach 2. 
3. In every case, we were creating the variable word with a determined letter. Nevertheless, this letter was passed through the Stringbuffer as a char instead of a String because the letter was passed through a simple quote **''** instead of a double **""**. That is why, the letter was never added to the email.
4. Finally, we were going through every single case because we were missing the break statement. By adding the break in every single case, whenever we entry in one case, the program reads the break statement and exit the switch without going to the rest of cases. 
