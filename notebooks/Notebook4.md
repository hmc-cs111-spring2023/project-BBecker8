# Design notebook entry

## Last week's critique

"I looked over the error handling code and I liked how readable the parser was to find when errors were being thrown and what the error would look like for the user. My only suggestion for your error handling would be what was mentioned in our discussion to also add some feedback when users put in valid inputs so they can understand that their input went through without error."

"I liked your description of the issues you were experiencing and the approach you took to start resolving them. I looked through the code linked here and it does look like a lot of effort to try to parse through JSON requests to use the API so I hope it does not require too much more work to get functioning!"

"I like how well your DSL has come together including the new interface with error handling progress this week, it made it seem much more concrete to see what users will be interacting with and how they will be able to work through any issues with their inputs."

I will address the above critiques of last week's notebook. Firstly as we discussed in class I did end up sending the user a success message when they have successfully updated the spreadsheet. This lets the user know That the spreadsheet was updated and that They are good to enter in their next line. Secondly, Although my original JSON file looked a bit messy it had a lot of the functionality that I needed, this allowed me to swiftly finish up the API side of my dsl. Thirdly, Thanks for all the positive feedback through this project. 



## Description

This week I did a few things. First I finished implementing the API for Spreadsheets.com. This included a post/update/delete functionality. Also I added in a new game and edit past game features. Next I worked on making sure that there were no errors with the language and the interface/API. This involved setting up a test file to test all possible inputs. 
Lastly, I thought it would be nice to show another general application for this DSL, so I built an additional interface/parser to add a Play by play functionality.

Implementing The API to spreadsheets.com was not an easy task. As we saw last week I ran into many errors with the implementation of the google sheets API. However, lucky spreadsheets.com was not as difficult. I began by building a function that could post JSONArrays to the spreadsheet. This Array would include the content of a single Game (playtypes, players, and stats). This also involved building a mini parser from Hashmap to JSON. Afterwards, I was able to post to the API. I needed A way to update upon a new user input. This included building a delete/update function. Now I call it a delete/update because essentially it was easier to grab information from Spreadsheets.com and keep it in a JSON format than it was to build a JSON structure to post. Basically I use a get request to get a JSONArray of all the row id from the spreadsheet. Then I pass that into a delete function that deletes every currently used row in the sheet. That way when the User makes another input we can delete the content of the original sheet and then use the post request to send an updated version of the game.  ([code to API](https://github.com/hmc-cs111-spring2023/Bbecker8-Artifact/blob/main/my-dsl/app/src/main/java/my/dsl/API/SpreadsheetApi.java))


Along with the interface and API I wanted the ability for the user to add a new game and to edit a past game. This involved editing the interface such that the user could now say “Start New Game: game name” and it builds a new spreadsheet with the API. Also they could say “Edit Past Game: sheet#” to move to an already existing spreadsheet. sheet# is defined in my documentation as well as when the user first uses the interface. Basically the leftmost sheet is number 1 and the right most sheet is n being the number of sheets you have. This process involved making a global game variable in the interface such that you could update the current game you are adding players into. And also involved updating the http request in the API since each spreadsheet changed the http request we had to update the url such that the sheet you are editing matches the game you are editing. ([code to interface](https://github.com/hmc-cs111-spring2023/Bbecker8-Artifact/blob/main/my-dsl/app/src/main/java/my/dsl/Interface/App.java)) ([code to API](https://github.com/hmc-cs111-spring2023/Bbecker8-Artifact/blob/main/my-dsl/app/src/main/java/my/dsl/API/SpreadsheetApi.java))

After this, I worked to straighten out my code. I added documentation and comments as well as wrote a new test file that would stream a line from a file into the API. After running the test I figured out that there were a few commands that were not working. After some debugging I was able to quickly fix those errors in various locations of the project. ([code to tests](https://github.com/hmc-cs111-spring2023/Bbecker8-Artifact/tree/main/my-dsl/app/src/test/java/my/dsl))

After all of this, there were two features that I still wanted to have. The first was averages across multiple games or within game team stats. I realized that adding this in would probably take all my free time up this week and next so I decided that my functionality and my current spreadsheet which was my initial goal would be good enough. The second feature that I wanted to show/ add was the ability to forecast a live play by play. I did not know of any API’s for play by play usage or streaming so I built a small interface that pops up when you press a button on the original interface. This interface includes a scrollable label. Next I would need to build an additional parser such that when the user inputs “P 11 12y 13 TD” the interface would pop up “Player 11 threw for 12y to player 13 and the result was a TD”. The parser that I built mocs the structure of my original parser but instead it focuses on string building. This went relatively smoothly and I had no problems with it (see my plan for the parser below). ([code to interface](https://github.com/hmc-cs111-spring2023/Bbecker8-Artifact/blob/main/my-dsl/app/src/main/java/my/dsl/Interface/App.java)) ([code to parser](https://github.com/hmc-cs111-spring2023/Bbecker8-Artifact/blob/main/my-dsl/app/src/main/java/my/dsl/Parser/PlayByParser.java)) 

<img width="699" alt="Screen Shot 2023-04-20 at 3 40 20 PM" src="https://user-images.githubusercontent.com/97985236/233501887-670b2e00-05ec-4933-86f5-8e31e0d7dd89.png">


## Questions

**What is the most pressing issue for your project? What design decision do
you need to make, what implementation issue are you trying to solve, or how
are you evaluating your design and implementation?**

Nothing. I have finished my DSL. For future work I may work on adding in game average features. All that I have left is to make the video. 

**What questions do you have for your critique partners? How can they best help
you?**

N/A

**How much time did you spend on the project this week? If you're working in a
team, how did you share the work?**

10 hours

**Compared to what you wrote in your contract about what you want to get out of this
project, how did this week go?**

Compared to my contract I have surpassed everything that I wanted to do. All that I have left is to make the video. 
