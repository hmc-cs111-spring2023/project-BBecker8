# Design notebook entry

## Last week's critique
Here are the critiques from the previos weeks project ideas, I will adress each of them:

"I really appreciated that you went into detail on each goal. It showed you have a plan for each stage of the project. I know we discussed this in class but reiterating that it would be good to keep in mind what concerns you may have about things not getting done for each of these goals and what contingency plans you'll have if something does go wrong with that goal."
"I like that you clearly outlined your plan for each day of the week, I'd be cautious to ensure that you hold yourself accountable because while it is good to not have long blocks when you plan to work since missing one day isn't a huge setback. However, it could be difficult to get set up, and getting started each of these days could bite into your capacity for development."

I will address the two critiques above: Right now I don't see any delays or walls for my project. Everything that I have done thus far has been really smooth and I am a week or two ahead of schedule. I am a very detailed person so I tend to stick to a schedule with the addition of working on the project during my free time when I get bored. This week I found that I was getting work done early and I had a bunch of free time to just work on the project. As for moving forward I will keep in mind that I need to focus during my allotted hours for this project but I do not see time as an issue right now. This may change as errors start to show up but in the meantime I will keep chugging away at the project at my heart's content. 

"Great use of examples, this addresses my concern above about users not knowing programming principles. I really enjoy your explanation of your thought process here, I think it would be great to allow for both the more verbose and shorthand implementations such that users could use "P 11 20y 82", "Pass player number 11 for 20 yards to player number 82", and maybe even a combination of the two such as "Pass 11 20 yards 82" for cases where users may be able to remember some shorthand definitions but not all of them."
"I think that there are going to be many more design decisions to be made here than anticipated. An example of something you might have to consider in the future is statement order, so what if someone wants to say "20 yard pass to player number 82 from player number 11" or in shorthand form "20y P to 82 from 11"? I think testing out more ideas like this might require a significant amount of thinking which even if not all of them translate directly to code, make this project require more design decisions than the current estimate of primarily system implementations above."

I will address the two critiques above: Right now I plan on using a strict shorthand notation. The reason for this is so that I can use a regex pattern matcher as my parser, and because it should make error handling easier. Although your suggestion to have a combination sounds really nice and it did cross my mind, I think a narrowed scope for my language will allow me to get a functional project completed. More on the shorthand notation, the notation will follow the following format (playtype- a string or character uppercase or lowercase that must start out the string)(nameOrNumber - the name or number of a player, names must be a word where the first letter is capital and the rest lowercase, numbers can be any number 0-99)(numyards-this will be a number immediately followed by the letter y)(nameOrNumber2- same as previous)(outcome- a word in all caps representing the outcome of a play or an additional tag for a play). This strict structure will allow me to build a pattern matching regex expression. Also to note the fact that it may be harder for some users to learn, I plan on adding in a howto guide to the readme file as well as providing documentation on the language itself. There are not that many combinations of strings that a user can input so it should not be that difficult for a user to learn. 

## Description

I began the week early last Friday because I was bored. I began by building a chart that would represent most if not all combinations of strings/inputs for my language. This helped me to map out how an input would be parsed into groups via regex pattern(see image below). Next I built a class with a regex pattern and a file parser. The file parser reads one line from a text file and uses the regex pattern on the input string/line to determine if it fits the pattern. If it does it parses the words from that line into the five groups mentioned earlier and below. 
(playtype- a string or character uppercase or lowercase that must start out the string)
(nameOrNumber - the name or number of a player, names must be a word where the first letter is capital and the rest lowercase, numbers can be any number 0-99)
(numyards-this will be a number immediately followed by the letter y)
(nameOrNumber2- same as previous)
(outcome- a word in all caps representing the outcome of a play or an additional tag for a play)
This aspect of my project was pretty straight forward and had little to no hiccups except for some experimentation with the regex pattern (link to code here). Error handling for the parser has not yet been implemented but will be in the near future.
chart image:

<img width="602" alt="Screen Shot 2023-03-30 at 7 55 34 PM" src="https://user-images.githubusercontent.com/97985236/229011324-73a37a60-9a6c-4df1-becb-0fb27c6c819e.png">
                                                                 
<img width="609" alt="Screen Shot 2023-03-30 at 7 56 25 PM" src="https://user-images.githubusercontent.com/97985236/229011458-dc9f8c81-b94c-42b0-9ea6-41e305c15878.png">

image of possibe inputs:

<img width="233" alt="Screen Shot 2023-03-30 at 7 57 16 PM" src="https://user-images.githubusercontent.com/97985236/229011588-d87b5cbd-4055-46f5-9c0d-92ce86e1a7dc.png">

Continuing this week I got ahead by planning out and implementing the data structure that would represent a spreadsheet of a football game. I began by drawing up a layout of a hashmap with a possible representation of a player that may be stored within it (see images below). Then I wrote down some notes/drawings of things that I want to make sure get implemented with this data structure such as having the ability to update a player or add a player to the hashmap. (see images below). Next I began my implantation by building a game class. This class houses the hashmap that has a string key representing the type of play and an arraylist of players to be stored for each hash. This was straight forward and I had no problems. Next I began building an abstract parent class called player. The goal of this class is to hold all possible variables, methods, getters, constructors that may be used in a given player type (subclasses)(link to code here). This was straightforward but took some experimenting with the subclasses. Next I build a subclass for each type of player (9 total). Each subclass represents a different type of player and each type's constructor is slightly different (link to code here). But the creation of these classes went very smoothly. Next I worked on a method in the game class that would allow me to add a player to a specified hash given the string of the hash and the player to be added. The add method is very similar to the default add method but just tailored towards data structure and the player class. Finally to end the week I build a function called setPlayer that allows for specific attributes of a player to be updated. Say you wanted to update the number of yards a rushing player rushed for you could do so with this method. The challenge of this method was that each player type needed a slightly different implementation. Overall this was not hard but tedious. (link for code) 

Images of plan for data structure:

![IMG_8536](https://user-images.githubusercontent.com/97985236/229011899-63f02c5f-6cd8-45f6-b733-30941eff8a9f.jpeg)

![IMG_8537](https://user-images.githubusercontent.com/97985236/229011930-5868f4ad-4787-41de-8b9b-c768a75b8c80.jpeg)


## Questions

**What is the most pressing issue for your project? What design decision do
you need to make, what implementation issue are you trying to solve, or how
are you evaluating your design and implementation?**
My most pressing issue at this time is making sure that I have my repo set up correctly for java. As of right now I used a tutorial to set up a repo for all of my code and it runs. I am just not sure it is correct. The next problem will be working to build the bridge from my parser to the data structre aspect of my project. 

**What questions do you have for your critique partners? How can they best help
you?**
I do not have any questions at this time.

**How much time did you spend on the project this week? If you're working in a
team, how did you share the work?**
I spent about 9-12 hours this week on the project

**Compared to what you wrote in your contract about what you want to get out of this
project, how did this week go?**
This week went really well I basically completed my goals for week one and week 2. 
