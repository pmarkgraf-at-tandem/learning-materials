# Mob Programming (AKA Ensemble Programming, AKA Software Teaming)

## Mobbing / Ensembling

* A software development approach where the whole team works on the same thing, at the same time, in the same space, and at the same computer.
  * Similar to pair programming where two people sit at the same computer and collaborate on the same code at the same time.
  * With mob programming, the collaboration is extended to everyone on a whole team!

## Strong Style

* Code only goes into the computer through someone else's hands
* One person is the Driver (Scribe)
  * Driver (Scribe) acts as a "smart keyboard", entering code/tests into the computer
  * Driver (Scribe) does not type their own ideas into the code/tests
* One person act as the Navigator
  * Navigator describes the code/tests to be written
  * Descriptions of code/tests should be at the Drivers level of abstraction
    * This might be at the code syntax level
      * "type a opening curly brace..."
    * This might be at the code structure level
      * "create a function that iterates through the input and ..."
    * This might be at the pattern level
      * "refactor these functions into a command pattern"
* Originally described by Llewelyn Falco
  * <https://llewellynfalco.blogspot.com/2014/06/llewellyns-strong-style-pairing.html>

## Roles and Rotation

* People within the mob take turns being the Driver and Navigator
  * Rotations are short, typically two or three minutes
    * Times should be set to make sure everyone stays engaged
    * If people are not paying attention, shorten the rotation time!
  * For our exercise, the person who is driving will be Navigator next
* The three main roles are:
  * Driver (Scribe - described above)
  * Navigator (described above)
  * Mobber
    * Those not driving or navigating (in the general case)
    * Responsible for being ready to carry on the idea of the previous navigators when their turn comes
      * Like in improv, mobbing leans on a "yes, and…" approach
      * Your work builds on the person before you
    * Be ready to answer questions and give suggestions, when asked
    * Doesn't interrupt when the navigator or driver is making an error
      * The other person will learn more, if they find the error themselves!
        * Don't "steal the learning"
* These are some good resources about Mob Programming roles:
  * <https://www.youtube.com/playlist?list=PLGME-VQ8iegjxFStr5EgOeXz6DxhGlvp3>
    * Especially the first three videos!
  * <https://github.com/willemlarsen/mobprogrammingrpg>
    * Driver: <https://github.com/willemlarsen/mobprogrammingrpg/blob/master/theDriver.pdf>
    * Navigator: <https://github.com/willemlarsen/mobprogrammingrpg/blob/master/theNavigator.pdf>
    * Mobber: <https://github.com/willemlarsen/mobprogrammingrpg/blob/master/theMobber.pdf>
* There are other roles that mobbers can take on to help the team
  * Researcher: hunts down information the team needs
  * The Nose: identifies opportunities for code improvement
  * Traffic Cop: helps the team build and keep to their agreed upon process
  * Rear Admiral: gives small hints to help coach the navigator
    * often useful with new navigators
    * the trick is to not give an answer, but gently nudge in the right direction

## end
