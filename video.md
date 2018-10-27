#Disclaimer

The video presentation text may be slightly differnt than this text. Sometimes it is easier to write than it is to read

~~~~

# Make form processing simpler with Brian Kotek's FormUtils


## Goal

Have you ever had to work with HTML tables filled with rows and columns of data? If you have, you know that picking out all the data out of the form scope can be difficult. As a ColdFusion developer, I wish forms could submit arrays and structs.

Consider this table. It has four columns; each with names and five rows. ColdFusion does not make it easy process this data. I could make a bunch of form fields that look like this. They are all accounted for, but they are not easy to process.

Let's do a submit and see what we get back. As you can see what we are getting is nothing like the original. 

## Why is this is a problem

This data is not easy to loop over. It not easy to find values. It is just one long set of veriables. I would much rather have an array of structs like the original

## Let's fix that!


Brian Kotek to the rescue. In 2007, Brian was actively working on a tool call FormUtils. I have taken that and have updated it for ColdFusion 2016 and later. Let's take a quick look at what it can do and then dive into how use can use it on your projects.

First let's go to Github and get some code. The link to repository is. I will include a link below

Let's setup the local copy in ~/Sites/ColdFusion/FormUtils2018. You can put this in any directory you like. 

I am going to be using Ortus Commandbox to bring up the site. I do not need to put code into any particular directory. If you Google Ortus Commandbox, usually the link will show up. I will put a link below too.

Next, I am going to be using VS Code. VS Code is everywhere so you should have no trouble finding it.

## Let me tell you a little about why I like it

- It brings most of the activities associated with developement all in one place
- I can edit files and all the are color coded by purpose
- I can find and replace in whole directories
- I can instantly see the status of my files vs Github
- There extensions that make ColdFusion files look great
- It has a built in terminal. When used with CommandBox, I can start and stop ColdFusion Servers with ease
- It also looks very similar to Azure Data Studio.


I have downloaded the repository, I have installed Commandbox, I have installed VS Code, I am now ready to make things happen.

## VS Code


Let me start up VS Code and open the folder with FormUtils. All the files used in this presentation are present. You will note that there is a .server.json file. That is the file that is going to tell Commandbox everything it needs to know to get ColdFusion up and running. In VS Code, I am going to open the terminal.

Make sure you have navigated to the right directory. I am on MacOS, so I type pwd OK, things look good

Next, I type box. I then get the CommandBox prompt

Next I type install. I only have to do this once. The first time you do this, it can be slow because it has to get a copy of ColdFusion

Last, I type start. If I did everything right, ColdFusion comes up and index.cfm is shown on your default browser. index.cfm is the original page created by Brian Kotek. I like his example. You can use his example of even options that you can do with FormUtils.

## Run it!

Let's run a table example without FormUtils


Here is the same form, but let's look in the table to see what was created. We are making some rather complicated form names. These form names are exactly how we would access these variables if they were ColdFusion variables.

I am going to submit the form and them we need to do a little processing.

First we are going to instantiage a copy of FormUtils. If we were making a large application, we might tie this in the application scope or perhaps make it a service. We don't have an application.cfc or application.cfm, so we are not going to worry about that.

The next step is to run the "buildFormCollections" function. We are passing in form, but you may have a framework that has a more appropriate variable. I use FW/1 a lot, so I run this before rc is even setup.

You will not that "buildFormCollections" does not return back a variable. It has already updated form to the new format. Right here in my code you can see I am doing a <cfdump> of form.user. I am doing this because I don't want to work through the entire form scope. Keep in mind that form is a struct. I don't want to work though a bunch on keys in a struct, I want an array of structs.

Now let's run it with FormUtils

As you can see we have the exact same structure as when we started.

## Ta da!

Next steps

You should now be able have much cleaner data additional processing.

Thank you for watching.

Happy Coding

# Resources

https://www.adobe.com/products/coldfusion-family.html


https://github.com/jmohler1970/FormUtils


https://www.ortussolutions.com/products/commandbox


https://code.visualstudio.com/


## See it in action

https://www.youtube.com/watch?v=xraa933iOgQ

