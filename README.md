Download Link: https://assignmentchef.com/product/solved-ista-130-programming-assignment-10-classes
<br>
<strong>1.0)  RPG COMBAT (100 POINTS) </strong>

<strong> </strong>

<h1>1.1)  DETAILS</h1>




In this assignment you will write a program to simulate combat for a simple Role Playing Game (RPG).  The game will have a single type of character, the Fighter.  Each individual Fighter will have an integer value called “hit points” that represents his/her current health (the amount of damage he/she can sustain before death).

The program will simulate combat between two Fighters.  Combat will be divided into rounds.  During each round each combatant will make one attempt to strike the other.  Determining which Fighter attacks first in a round is important because the first attacker might kill his opponent before the opponent has a chance to attack him.




In table top RPG’s, the order of attacks is often determined by rolling dice.  For example, each combatant rolls a six-sided die.  The higher roller attacks first . The lower roller attacks second if he is still alive.  We’ll use random numbers to simulate the rolling of dice.  In the event of a tie, we’ll consider the attacks to occur simultaneously (i.e. the Fighters attempt to strike each other at the exact same moment).  During a simultaneous attack both Fighters will get to attack even if one (or both) is (are) killed during that round.




We’ll use a random number to determine whether an attack attempt is successful or not. Each successful attack will inflict damage on the opponent.  To simulate damage, we’ll reduce the opponent’s hit points by another random number.  When a Fighter’s hit points are reduced to 0 (or less than 0) he is considered to be dead.




Combat rounds will continue until one (or both) combatants are dead.  Create a new file called “rpg.py”.  In the file:




<ul>

 <li>Write a class called <strong>Fighter</strong>. Inside the class:</li>

</ul>




<ul>

 <li>Write an initializer method called <strong>__init__ </strong>that takes 2 parameters: self</li>

</ul>

(all of your methods will have this as the first parameter), and name (a           string, the name of a fighter).  The initializer method will:




<ul>

 <li>set a name attribute to the value of the name parameter.</li>

 <li><sup>set a </sup>hit_points attribute to 10 (i.e. all fighters begin life with 10 hit points.)</li>

</ul>




<ul>

 <li>Write a method called <strong>__repr__</strong> that takes one parameter: self. The method returns a string showing the name and hit points of the instance in the following format:</li>

</ul>

Bonzo (HP: 9)







<ul>

 <li>In this example “Bonzo” is the Fighter’s name and he currently has 9 hit points.</li>

</ul>




<ul>

 <li>Write a method called <strong>take_damage</strong> that takes two parameters: self (the Fighter instance that calls the method), and damage_amount (an integer         representing the number of hit points of damage that have just been inflicted on     this Fighter):</li>

</ul>




<ul>

 <li>The method should first decrease the hit_points attribute by the                 damage_amount.</li>

</ul>




<ul>

 <li>It should next check to see if the Fighter has died from the damage:</li>

</ul>




<ul>

 <li><sup>A </sup>hit_points value that is zero or less indicates death. In that case print a message as shown in the following example:</li>

</ul>




tAlas, Bonzo has fallen!




<strong>–</strong> In this example the Fighter’s name is “Bonzo”




<ul>

 <li>Otherwise print a message as shown in the following example:</li>

</ul>




tBonzo has 5 hit points remaining.




<strong>–</strong> In this example the Fighter’s name is “Bonzo” and he has 5 hit points left over after the damage.




<ul>

 <li>This method returns nothing.</li>

</ul>




<ul>

 <li>Write a method called <strong>attack</strong> that takes two parameters: self (the Fighter instance that calls the method), and other (another Fighter instance being attacked by self)

  <ul>

   <li>The method will print the name of the attacker and attacked in the         following format:</li>

  </ul></li>

</ul>




Bonzo attacks Chubs!




<ul>

 <li>Next determine whether the attack hits by generating a random integer             between 1 and 20.  Use the randrange function from the random                module to get this number.  A number that is 12 or higher indicates a hit*:</li>

</ul>




<ul>

 <li>For an attack that hits:</li>

</ul>




<ul>

 <li>Generate a random integer between 1 and 6 (use randrange) to represent the amount of damage inflicted by the attack. Do not use the from random import randrange syntax.  randrange works like range, not like randint (think about the upper bounds you choose).</li>

</ul>




<ul>

 <li>Print the amount of damage inflicted as in the following                                       example:</li>

</ul>




tHits for 4 hit points!




<ul>

 <li>Invoke the <strong>take_damage</strong> method on  the  victim  (i.e. on      other), passing  it  the amount of damage inflicted.</li>

</ul>




<ul>

 <li>For an attack that misses, just print the following message:</li>

</ul>




tMisses!




<ul>

 <li>This method returns nothing</li>

</ul>




<ul>

 <li>Write a method called <strong>is_alive</strong> that takes one parameter: self (the</li>

</ul>

Fighter instance that calls the method).

<ul>

 <li>The method returns True if self has a positive number of points, False</li>

</ul>




<ul>

 <li>Outside of the class write a function called <strong>combat_round</strong> that takes two parameters. The first is an instance of Fighter.  The second is another instance of Fighter.</li>

</ul>




i.)  The function determines which of the two fighters attacks first for the round by  generating a random integer (use randrange) between 1 and 6 for each fighter:

<ul>

 <li>If the numbers are equal:</li>

</ul>




<ul>

 <li>Print the following message:</li>

</ul>




Simultaneous!




<ul>

 <li>Have each fighter instance call his attack method on the other fighter (the first fighter in the argument list must attack first to make the test work correctly)</li>

</ul>




<ul>

 <li>If one number is larger:</li>

</ul>




<ul>

 <li>The fighter with the larger roll attacks first (by calling his attack method and passing it the fighter being attacked)</li>

</ul>




<ul>

 <li>If the second fighter survives the attack (call is_alive), he then attacks the first.</li>

</ul>




ii.)  This function returns nothing.




<ul>

 <li>In <strong>main</strong>:</li>

</ul>




<ul>

 <li>Create two instances of the Fighter class. The name of the first fighter must be Death_Mongrel; the second must be Hurt_then_Pain.</li>

</ul>




<ul>

 <li>Next repeat the following process until one (or both) fighters have been slain          (remember, a Fighter is dead when it has less than 1 hit point):</li>

</ul>




<ul>

 <li>Print the combat round number (start with 1) as shown in the following           example:</li>

</ul>




====================== ROUND 1 ======================




<strong><u>NOTE</u></strong><strong>:</strong> There are 19 equal signs on each side




<ul>

 <li>Print each Fighter’s information (remember how the <strong>__ repr__</strong>       method works). E.g.:</li>

</ul>




Bonzo (HP: 4)

Chubs (HP: 7)




<ul>

 <li>Use the input function to pause the program (like we did in our turtle           graphics programs) until the user presses enter.  Prompt the user with the             following message:</li>

</ul>




Enter to Fight!




<ul>

 <li>Use your <strong>combat_round</strong> function to simulate a single round of combat.</li>

</ul>




* For the curious:  The numbers are from Advanced Dungeons &amp; Dragons in which you roll a 20 sided die to determine a hit.  They assume the attacker is a 1st level Fighter swinging a club and the defender is wearing leather armor.




iii.)  Finally print a message indicating the battle has ended, followed by the  information for each of the Fighters, as shown in the following example:




The battle is over!               Bonzo (HP: 3)              Chubs (HP: -2)




<ul>

 <li>Adjust all of your output so that it looks pretty. See the example output below.</li>

</ul>




<ul>

 <li>Verify that your documentation makes sense and that you’ve added documentation to each of your functions.</li>

</ul>




<ul>

 <li><strong>Verify that your program works</strong></li>

</ul>




<ul>

 <li>Upload your file to the Program 10 dropbox folder on D2L</li>

</ul>

<h1>1.1)  EXAMPLE OUTPUT</h1>

<strong> </strong>

The following is an example of the output you might see when running this program:




<strong><u>NOTE</u></strong><strong>:</strong>  All indents are done by a single tab character




=================== ROUND 1 ===================

Bonzo (HP: 10) Chubs (HP: 10)  Enter  to  Fight!

Simultaneous!

Bonzo attacks Chubs!

Hits for 1 hit points!

Chubs has 9 hit points remaining.

Chubs attacks Bonzo!

Misses!




=================== ROUND 2 ===================

Bonzo (HP: 10) Chubs (HP: 9)  Enter  to  Fight!

Chubs attacks Bonzo!

Hits for 4 hit points!

Bonzo has 6 hit points remaining.

Bonzo attacks Chubs!

Hits for 3 hit points!

Chubs has 6 hit points remaining.




=================== ROUND 3 ===================

Bonzo (HP: 6) Chubs (HP: 6)  Enter  to  Fight!

Bonzo attacks Chubs!

Hits for 3 hit points!

Chubs has 3 hit points remaining.

Chubs attacks Bonzo!

Hits for 1 hit points!

Bonzo has 5 hit points remaining.




=================== ROUND 4 ===================

Bonzo (HP: 5) Chubs (HP: 3)

Enter  to  Fight!

Simultaneous!

Bonzo attacks Chubs!

Hits for 5 hit points!

Alas, Chubs has fallen!

Chubs attacks Bonzo!

Hits for 2 hit points!

Bonzo has 3 hit points remaining.




The battle is over!

Bonzo (HP: 3)

Chubs (HP: -2)




Here is a second example of running the program:




=================== ROUND 1 ===================

Bonzo (HP: 10) Chubs (HP: 10)  Enter  to  Fight!

Bonzo attacks Chubs!

Hits for 3 hit points!

Chubs has 7 hit points remaining.

Chubs attacks Bonzo!

Hits for 3 hit points!

Bonzo has 7 hit points remaining.




=================== ROUND 2 ===================

Bonzo (HP: 7) Chubs (HP: 7)  Enter  to  Fight!

Bonzo attacks Chubs!

Misses!

Chubs attacks Bonzo!

Hits for 4 hit points!

Bonzo has 3 hit points remaining.




=================== ROUND 3 ===================

Bonzo (HP: 3) Chubs (HP: 7)

Enter  to  Fight!

Simultaneous!

Bonzo attacks Chubs!

Misses!

Chubs attacks Bonzo!

Misses!




=================== ROUND 4 ===================

Bonzo (HP: 3) Chubs (HP: 7)  Enter  to  Fight!

Chubs attacks Bonzo!

Hits for 4 hit points!

Alas, Bonzo has fallen!




The battle is over!  Bonzo (HP: -1) Chubs (HP: 7)


