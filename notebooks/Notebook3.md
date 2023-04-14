# Design notebook entry

## Last week's critique

“Thanks for the description of the issue and the link to the changes, I think it's important especially in these reflections to make sure you describe even things you get stuck on as it shows that effort was put in during that time, which is really important for a project like this where time sinks can be detrimental to your progress.”


“Yeah, if you're trying to run a Java app in codespaces, it can be tricky. I see that you have a .devcontainer.json file that should be set up for Java. We can try to debug it together in class on Wednesday, or during office hours!”


“I reviewed some of the files in this folder to look over how your player position classes are set up and I better understand why much of the code was previously described as tedious and how a call like the one you provided above functions. One recommendation I would make would be to rename some of the 'set' methods as 'add' methods (i.e. setINTs => addINTs) as it seems these methods just add to the current count. I don't think this really affects the outcome of what users will be interacting with but it is just a minor detail that could clarify what these functions do.”


“One note I would have is that your StringGrouping.java file contains if(groupsMatcher.matches()) which works to prevent errors but it seems like nothing happens if a user inputs a string that doesn't match the regex pattern so I would recommend adding an else case which lets users know they've made an error”


“The "run" play could also be referred to as a "rush"”


I will address the previous comments from last week. Firstly, I hope you don’t mind the rant but most of this week's notebook will consist of the many many errors I ran into. Secondly, I went into office hours and prof Ben was able to provide me with a layout that has the capabilities of running a java app with java fx. This really helped this week and I appreciate the help from him. Thirdly, to address the set vs add. I can see how just looking over the code you may find that these functions are more related to an add feature function. However in my mind they are more of a set/update function. For the time being I will keep them as a set function title but might change them later. Also they do not really affect the user so like you said it is not at the top of my list. Fourthly, This week I added in error handling so the part of the code if(groupsMatcher.matches()) is actually more relevant now. Also when I worked with regex last summer during my internship that is how we used it so its kinda a habit. Lastly, wow I cannot believe I did not think to use rush. I added that in Thanks!!


## Description

This week was a lot of setup with codespaces and dependencies however I was glad to get some stuff done with error handling and setting up the java.app on codespaces. Moreover, I struggled a ton with trying to get an API working.

To start the week I began by adding in error handling. The user now has a workable interface that allows the user to know when the language that they used is not up to par. If there are parts of their input that are not correct they will receive a message stating that _____ part of their input was wrong and also a provided solution for it. The solution aspect is very similar to what I will provide as documentation. ([link to interface](https://github.com/hmc-cs111-spring2023/Bbecker8-Artifact/blob/main/my-dsl/app/src/main/java/my/dsl/Interface/App.java)) ([link to error message files](https://github.com/hmc-cs111-spring2023/Bbecker8-Artifact/tree/main/my-dsl/app/src/main/java/my/dsl/Interface)) ([link to example error handling](https://github.com/hmc-cs111-spring2023/Bbecker8-Artifact/blob/main/my-dsl/app/src/main/java/my/dsl/Parser/StringGrouping.java)).

Next I began working on the implementation of the API. I really wanted to use the google sheets API. After talking with prof Ben I found out that codespaces does not allow API usage to google sheets. However, I should be able to run the project on my own computer through VScode. But this also had its own problems. I had everything set up to test the google sheets api including test code that should have worked, and all of the extra google sheets set up. The set up for google sheets required me to make a google project and set up some keys for it. Avast when running in VScode I did not have maven or gradle or docker set up on my computer. And sadly to get these set up I would need to install brew. After installing brew I found out that I need other requirements on my computer and sadly my computer wont update enough to get the required resources. So after all this set up and testing for proper dependencies I hit a wall that I simply cannot get through. But this sad tail does have a better ending.

After some sleep I figured that there must be another online sheet like resource that uses simple http requests. And after some research light got shed on spreadsheet.com and their open API. Now the easy part of using spreadsheet.com and their api Is that I can send http requests with no hassle. The challenge of using spreadsheet.com is that they require their input of data to be in JSON. Now if you have no background in JSON this gets very confusing. Luckily I do have some background. The challenges that now lay ahead of me are converting my pre-existing data structure into JSON. I spent the rest of the week experimenting with different strategies to do so. I will provide a file that has some of my test code for this. It is very rough and unorganized. But I believe I have found and made some methods that will be able to get the job done. Next week I will plan on finalizing this aspect and making the code and the inputs into the sheet look nice. ([example code not yet in project](https://github.com/hmc-cs111-spring2023/Bbecker8-Artifact/blob/main/.devcontainer/Examplecode))


## Questions

**What is the most pressing issue for your project? What design decision do
you need to make, what implementation issue are you trying to solve, or how
are you evaluating your design and implementation?**

The most pressing issue for me now is working to turn my pre-existing data structure into JSON.


**What questions do you have for your critique partners? How can they best help
you?**

I don’t have any question at this time

**How much time did you spend on the project this week? If you're working in a
team, how did you share the work?**

I spent roughly 10 hours this week

**Compared to what you wrote in your contract about what you want to get out of this
project, how did this week go?**

At this point I think I am still a week ahead of where I said I was going to be but I have some extra thought on extra things that I want to achieve in this project. 

