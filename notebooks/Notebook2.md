# Design notebook entry

## Last week's critique

“I think it would be useful to ensure you have some documentation of this structure both for: 1) your own reference, which may allow you to reflect on what other use cases you may want in your design and 2) users writing in your DSL for the first time, it will allow them to have a template (and some example calls would be good) to look at when they are learning to write out commands in your DSL.”

“Let me know if you want to talk about the repo at all, or if there is something specific I can look at.”-Prof Ben

“I liked that you noted that the work was tedious despite not being complex, is there any way that you think you could have implemented these that would have been less tedious?”

I will address the three critiques above:

I agree. In the end I think that I will need some form of documentation for the language that shows different possibilities for each input group of the language as well as the general structure. I think I will plan to work on that near the end of the project term. Right now I want to focus on other aspects. 

To Prof Ben, I do think I may need some help with my repository. Although It has been working pretty well I ran into a problem this week when trying to implement a small interface for inputting my language. It turns out that codespaces does not know how to build a physical java application type interface without the proper setup in the repository or connections to a remote explorer. I would appreciate help with that sometime next week. 

Sadly I do not think I can simplify the tedious work that I had to do much more. You will see that there were some changes to the files for the player types this week. The changes allowed for simplification of various parts of the player types such as getting rid of the name aspect or adding simpler setters for each type. 


## Description

This week I worked on a few main things such as: building the bride from input to data structure through a parser, Implementing some sort of single line input either via a physical java interface or that being the command line, and looking over and simplifying the player type classes with individual setters per input type vs one big setter that sets all input types. 

I began the week by building a physical java interface for the system that would allow the user to input the language into a text box. This allowed me to easily test inputs and see if it was working properly. This went fairly smoothly until I tried to add a part to the language, this was a simple “start new game log” phrase that was evaluated in the interface portion of the code and created a new game. This would then allow the user to input the regular dsl language. However I kept getting a null pointer error and I could not figure out why because there were no null pointers being passed through. Eventually I figured out that when adding this extra piece of code to create a new game I was building a null game. I ended taking that portion out and it worked great from there on. I may end up going back and retrying something similar later. ([code here](https://github.com/hmc-cs111-spring2023/BBeckerArtifact/blob/main/src/Interface/TextInputInterface.java))

Next I started to simplify the player type classes with individual setters per input type vs one big setter that sets all input types. This was fairly straightforward, I got rid of alot of bulk in the abstract player class and allowed for each player type to be created with just the input of the players number instead of name and number and all the other components that each player has. Then I built setters for each player's unique inputs. This allowed me to write something similar to the following:
New PassingPlayer(playerOrNum).setYards(numYards).setINCs(outcome).setTDs(outcome).setINTs(outcome).updatePlayer();
This was useful because I was able to handle inputs that are the same across different methods. ([code here](https://github.com/hmc-cs111-spring2023/BBeckerArtifact/tree/main/src/Player))

Finally I built a parser that takes each part of the input language and utilizes the Game class add function to add a player into the data structure. This involved building code to determine what type of playtype each input from the user was. These functions are my is…() functions. They return a boolean value if the input matches a possible input string. This could be further simplified by using another type of parser but for now It works great. Next I worked on function that are designed to add the player to the game and return the game to the parser these function utilize the add function from the game class to add a new player to the data structure or if the player already exists update the stats by merging the players stats that were just created with the old ones. The individualized settlers for each player type came in really nice for this aspect. Finally I worked on some functions that would transform strings to numbers and parsing out yardage from a string. For example, if the user inputs 22y representing 22 yards the parser needs to transform that into just an integer number 22. ([code here](https://github.com/hmc-cs111-spring2023/BBeckerArtifact/blob/main/src/Parser/Parser.java))


## Questions

**What is the most pressing issue for your project? What design decision do
you need to make, what implementation issue are you trying to solve, or how
are you evaluating your design and implementation?**

The most pressing issue right now is to get my repo set up in a way that allows for me to build a physical interface for the user to input the language. I think this is the best way for the user to use my dsl and it's better than using a command line input. Also I will begin to work on error handling for the language next week and I think that this will best be presented to the user with such an interface. 


**What questions do you have for your critique partners? How can they best help
you?**

If anyone sees any possible ways of simplifaction in the code I would love to know?


**How much time did you spend on the project this week? If you're working in a
team, how did you share the work?**

This week I spent roughly 8 hours on the project. 


**Compared to what you wrote in your contract about what you want to get out of this
project, how did this week go?**

This week went well. I finished building the bridge from front to back and I am able to test almost all of the components of my language this way. I am way ahead of schedule and I plan to work on language arrow handling as well as starting to work on the API portion of the project. 
