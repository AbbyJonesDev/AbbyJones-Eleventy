---
title:  "iOS Development on Udacity - Week One"
date:   2015-10-30
summary: ""
tags: 
  - iOS
  - Xcode
  - Swift
  - Learning to Code
---
I started Udacity's <a href="https://www.udacity.com/course/intro-to-ios-app-development-with-swift--ud585" target="_blank">Intro to iOS Development with Swift</a> course this past weekend. I can't believe how much I've learned in just a few days. Our last assignment for Lesson 3 is to write a blog post about what we've learned so far.  It would take way too long to write it all up, but here are some of the cool things I learned about XCode.

The instructor, Kunal Chawla, gave us an overview and then got us right into using the IDE, explaining more features as they became relevant.  It seemed overwhelming before, but now I feel comfortable navigating the basic areas/features of the program.
<ul>
  <li>Four Main Areas
<ul>
  <li>Navigator - For viewing the file tree and navigating to different parts of the app</li>
  <li>Editor - For viewing and editing storyboards and code</li>
  <li>Utility Area - For viewing, editing, and adding properties and elements in a GUI format</li>
  <li>Debugger - For debugging...  It's at the bottom of screen below the other three areas</li>
  <li>Icons - At the top of each area are a series of icons for accessing many different types of information or options in each category.  This can be a little overwhelming, but it's becoming easier to remember and navigate quickly to the ones we've used the most often.</li>
  <li>Toggling - Icons on the far right side of the main toolbar (at the top) can be used to quickly toggle different areas open or closed, so you can manage your screen real estate and have more room for what you need to see the most at the moment.  The next set of icons to the left let you toggle between modes in the editor pane so you can see just the storyboard, the storyboard plus the view controller, or...  (There are probably other helpful variations, but those are the two we've used so far.)</li>
</ul>
</li>
  <li>Drag and Drop
<ul>
  <li>The bottom part of the Utility area has icons for four different libraries - File Templates, Code Snippets, Objects, and Media.  So far, we've only worked with Objects from this area.</li>
  <li>In the Objects section, scrolling down reveals UI elements such as Buttons that can be dragged and dropped into the Storyboard to create layouts.</li>
  <li>Dragging an element to a specific place doesn't necessarily mean that's where it will show up on the screen.  Constraints can be set in several ways to place the element at a particular location: using the Size Inspector in the Utility area, clicking the Align or Pin icons at the bottom of the Editor area while viewing the Storyboard, or clicking and dragging the element in the Storyboard to bring up a menu.</li>
</ul>
</li>
  <li>Click and Drag
<ul>
  <li>Clicking and dragging a UI element in the Storyboard brings up the Constraints menu</li>
  <li>UI elements can also be clicked and dragged into the View Controller in the Assistant Editor to create Outlets and Actions.
<ul>
  <li>Actions are functions that control what happens when a user interacts with the UI element</li>
  <li>Outlets create connections between UI elements and variables that can be used to manipulate the UI element through code.  (For example - a button might need to be hidden after a user clicks on it.  Creating an outlet allows you to reference the button in an action and make it invisible.)</li>
</ul>
</li>
</ul>
</li>
  <li>Simulator
<ul>
  <li>Clicking the Play button at the top-left side of the screen builds the app and launches it in iOS Simulator. It's pretty slick how quickly it works.</li>
  <li>Any errors pop up in the Debug area at the botton of the Xcode screen.</li>
  <li>You can set breakpoints in your code and use the debugger area to step through your code while it runs in the simulator. (I learned this by accident. Took me a minute to figure out why my code had mysteriously stopped running...)</li>
</ul>
</li>
</ul>