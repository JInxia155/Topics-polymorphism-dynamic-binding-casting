Download Link : https://programming.engineering/product/topics-polymorphism-dynamic-binding-casting/

# Topics-polymorphism-dynamic-binding-casting
Topics: polymorphism, dynamic binding, casting
Problem Description

Please make sure to read all parts of this document carefully.

Ahoy matey,

The year be 1700. A group of pirates recently acquired a computer from the British Navy (just go with it)

in a surprise raid on a British fort. Despite their affinity for tea, the British had recently installed Java on

the computer before it was plundered by the pirates. The pirates, being business savvy as they are, have

offered a contract worth one-thousand doubloons to you to help modernize their logistical systems. You

choose to ignore the ethical issues of piracy for those sweet, sweet doubloons and the opportunity to

apply your polymorphism, dynamic binding, and casting knowledge to a real-world problem.

Solution Description

Create files Loot.java, Coin.java, Sugar.java, Plunderable.java, and Ship.java. You will be creating several

fields and methods for each file. Some classes will inherit from other classes, and some will implement

an interface. Follow the instructions, paying close attention to keywords, to determine what extends

and implements what.

Loot.java

This class represents the spoils gained from plundering a ship or fort. Loot is an abstract class.

Variables:

All variables must not be allowed to be directly modified outside the class in which they are declared,

unless stated otherwise:

double value – the monetary value of an item.

Constructor(s):

Constructor that takes in value and ensures that the value of the item is greater than 0.

Otherwise, value should be set to the default amount.

No-argument constructor that sets value to 0.

Methods:

All methods in this class should be public, unless stated otherwise:

Getter and setter for value. We want both to be public since the value of a piece of loot might

change based on supply and demand.

toString

o This method should properly override Object’s toString method.

o This method should return “A piece of loot worth {value}”

THIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZEDTHIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZED.

equals

o This method should properly override Object’s equals method.

o Two Loot objects are equal if they have the same value.

Coin.java

This class represents a piece of loot in the form of a coin.

Variables:

All variables must not be allowed to be directly modified outside the class in which they are declared,

unless otherwise stated in the description of the variable.

boolean heads – whether the coin is heads up.

int yearMade – the year the coin was manufactured. yearMade must be in the range [0,

1700]. If not, set it to 1700.

String material – the material the coin is made of (e.g., gold, silver, etc.).

Constructor(s):

A constructor that takes in value, heads, yearMade, and material.

o You may assume that the value passed in for material will be valid.

A constructor that takes in heads and yearMade.

o Sets value to (3000 – yearMade) / 100.

o Defaults material to “Gold”.

Reuse code if possible.

Methods:

All methods must have the proper visibility to be used where it is specified they are used.

toString

o This method should properly override Loot’s toString method.

o It should return a String in the following format:

“A {material} coin made in {yearMade}. Heads side is up:

{heads}.”

equals

o This method should properly override Loot’s equals method.

o Two Coin objects are equal if they have equal value, yearMade, and material.

o Hint: How can you reuse code by using Loot’s equals method?

Sugar.java

This class represents the valuable cash crop of sugar as loot, a frequently pirated commodity.

Variables:

All variables must not be allowed to be directly modified outside the class in which they are declared,

unless otherwise stated in the description of the variable.

double amount – the amount of sugar

double sweetness – the sweetness of the sugar. It must be in the range [0, 100].

THIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZEDTHIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZED.

Constructor(s):

A constructor that takes in amount and sweetness.

o You may assume that the value passed in for amount will be valid.

o If sweetness is not within the acceptable range, set it to 0.

o After determining the appropriate sweetness above, the value of the sugar should

be determined by its amount multiplied by its sweetness.

Methods:

All methods must have the proper visibility to be used where it is specified they are used.

toString

o This method should properly override Object’s toString() method.

o It should return a String in the following format:

“A pile of sugar of size {amount} and sweetness {sweetness}.”

equals

o This method should properly override Loot’s equals method.

o Two Sugar objects are equal if they have the same value, amount, and sweetness.

o Hint: How can you reuse code by using Loot’s equals method?

Plunderable.java

Plunderable is an interface which is implemented when an object can be plundered.

Methods:

bePlundered

o This method takes no parameters and should not be implemented in Plunderable. When

implemented, it should return an array of Loot objects, representing what the object

plundered had on hand.

Ship.java

This class represents a ship on the high seas with cargo on board. Ship implements Plunderable.

Variables:

All variables must not be allowed to be directly modified outside the class in which they are declared,

unless otherwise stated in the description of the variable.

Loot[] cargo – the cargo a ship has aboard. Initially, this array should be of length 10.

double totalCargoValue – the total value of the cargo on the ship. You should

continually update this whenever cargo is added or removed.

String name – every ship needs a good name, and these are no exception.

Constructor(s):

A constructor which takes in a name and sets cargo’s length to the value specified above.

o You may assume that the value passed in for name will be valid.

A no-argument constructor that defaults name to “Black Pearl”.

THIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZEDTHIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZED.

Methods:

All methods must have the proper visibility to be used where it is specified they are used.

toString

o This method should properly override Object’s toString method.

o It should print the following:

“A ship called {name} with cargo {cargo[0]}, {cargo[1]}…,

which has a total value of {totalCargoValue}.”

o Only slots in the array that have something in them should have their values displayed.

o Round totalCargoValue to 2 decimal places in the returned String.

addCargo

o This method takes in a Loot and adds it to the first available slot in the array.

Additionally, don’t forget to update the totalCargoValue of the ship.

o If there are no slots left in the array, create a new array with twice the length, copy

over the cargo, and add the new cargo according to the previous rule.

removeCargo

o This method takes no parameters and removes and returns the Loot in the first

occupied slot in the array. Don’t forget to update totalCargoValue.

o If the array is empty, return null.

removeCargo

o This method takes in a Loot and iterates through the array, checking if that item is on

the ship. If the item is found, remove and return it. Don’t forget to update

totalCargoValue.

o If the item is not found, return null.

o Note: Check for object equality, not reference equality when determining if an item is in

the array.

bePlundered

o Overrides bePlundered from the Plunderable interface.

o Returns an array of the Loot objects in the ship’s cargo and sets all the items in the

array to null.

▪ The returned array should have the exact length needed to store all of the

plundered items. You should not simply return the cargo field.

o E.g., If a ship with 3 coins is plundered, you should return an array of 3 coins and that

ship’s cargo should be empty afterwards.

o This method should also account for the totalCargoValue’s changes.

Checkstyle

You must run Checkstyle on your submission (To learn more about Checkstyle, check out cs1331-style-

guide.pdf under the Checkstyle Resources module on Canvas.) The Checkstyle cap for this assignment is

20 points. This means there is a maximum point deduction of 20. If you don’t have Checkstyle yet,

download it from Canvas → Modules → Checkstyle Resources → checkstyle-8.28.jar. Place it in the same

folder as the files you want to run Checkstyle on. Run Checkstyle on your code like so:

$ java -jar checkstyle-8.28.jar yourFileName.java

Starting audit…

Audit done.

THIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZEDTHIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZED.

The message above means there were no Checkstyle errors. If you had any errors, they would show up

above this message, and the number at the end would be the points we would take off (limited by the

Checkstyle cap). In future assignments we will be increasing this cap, so get into the habit of fixing these

style errors early!

Additionally, you must Javadoc your code.

Run the following to only check your Javadocs:

$ java -jar checkstyle-8.28.jar -j yourFileName.java

Run the following to check both Javadocs and Checkstyle:

$ java -jar checkstyle-8.28.jar -a yourFileName.java

For additional help with Checkstyle see the CS 1331 Style Guide.

Turn-In Procedure

Submission

To submit, upload the files listed below to the corresponding assignment on Gradescope:

Loot.java

Coin.java

Sugar.java

Plunderable.java

Ship.java

Make sure you see the message stating the assignment was submitted successfully. From this point,

Gradescope will run a basic autograder on your submission as discussed in the next section. Any

autograder test are provided as a courtesy to help “sanity check” your work and you may not see all

the test cases used to grade your work. You are responsible for thoroughly testing your submission on

your own to ensure you have fulfilled the requirements of this assignment. If you have questions about

the requirements given, reach out to a TA or Professor via the class forum for clarification.

You can submit as many times as you want before the deadline, so feel free to resubmit as you make

substantial progress on the assignment (submit early and often). We will only grade your latest

submission. Be sure to submit every file each time you resubmit.

Gradescope Autograder

If an autograder is enabled for this assignment, you may be able to see the results of a few basic test

cases on your code. Typically, tests will correspond to a rubric item, and the score returned represents

the performance of your code on those rubric items only. If you fail a test, you can look at the output to

determine what went wrong and resubmit once you have fixed the issue.

The Gradescope tests serve two main purposes:

Prevent upload mistakes (e.g. non-compiling code)

Provide basic formatting and usage validation

THIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZEDTHIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZED.

In other words, the test cases on Gradescope are by no means comprehensive. Be sure to thoroughly

test your code by considering edge cases and writing your own test files. You also should avoid using

Gradescope to compile, run, or Checkstyle your code; you can do that locally on your machine.

Other portions of your assignment can also be graded by a TA once the submission deadline has passed,

so the output on Gradescope may not necessarily reflect your grade for the assignment.

Allowed Imports

To prevent trivialization of the assignment, you may not import any classes for this assignment.

Feature Restrictions

There are a few features and methods in Java that overly simplify the concepts we are trying to teach or

break our auto grader. For that reason, do not use any of the following in your final submission:

var (the reserved keyword)

System.exit

System.arraycopy

Collaboration

Only discussion of the assignment at a conceptual high level is allowed. You can discuss course concepts

and HW assignments broadly, that is, at a conceptual level to increase your understanding. If you find

yourself dropping to a level where specific Java code is being discussed, that is going too far. Those

discussions should be reserved for the instructor and TAs. To be clear, you should never exchange code

related to an assignment with anyone other than the instructor and TAs.

You MAY NOT use code generation tools to complete this assignment. This includes generative AI tools

like ChatGPT.

Important Notes (Don’t Skip)

Non-compiling files will receive a 0 for all associated rubric items

Do not submit .class files

Test your code in addition to the basic checks on Gradescope

Submit every file each time you resubmit

Read the “Allowed Imports” and “Restricted Features” to avoid losing points

Check on Ed Discussion for a note containing all official clarifications and sample outputs

It is expected that everyone will follow the Student-Faculty Expectations document, and the Student

Code of Conduct. The professor expects a positive, respectful, and engaged academic environment

inside the classroom, outside the classroom, in all electronic communications, on all file submissions,

and on any document submitted throughout the duration of the course. No inappropriate language is

to be used, and any assignment, deemed by the professor, to contain inappropriate, offensive

language or threats will get a zero. You are to use professionalism in your work. Violations of this

conduct policy will be turned over to the Office of Student Integrity for misconduct.
