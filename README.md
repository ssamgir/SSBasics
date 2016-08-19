#Objective C Basics

# Contents
-	[Delegate](#Delegate)
-	[Data Types](#Data Types)
-	[Model View Controller Design Pattern](#Model View Controller Design Pattern)
-	[Properties](#Properties)
-	[UI Specific Elements](#UI Specific Elements)



###Delegate

###Let's assume an object A calls an object B to perform an action. Once the action is complete, object A should know that B has completed the task and take necessary action. This is achieved with the help of delegates.

###The key concepts in the above example are −

##*A is a delegate object of B.

##*B will have a reference of A.

##*A will implement the delegate methods of B.

##*B will notify A through the delegate methods.


###Data Types

>Type|Description
>-----|------------------------------------------------------------
>char|Typically a single octet (one byte). This is an integer type.
>-----|------------------------------------------------------------
>int|The most natural size of integer for the machine.
>-----|-------------------------------------------------------------
>float|A single-precision floating point value.
>-----|-------------------------------------------------------------
>double|A double-precision floating point value.
>-----|-------------------------------------------------------------
>void|Represents the absence of type.
>-----|-------------------------------------------------------------


#Model View Controller Design Pattern


![MVC](https://github.com/ssamgir/SSBasicsOfObjectiveC/blob/master/model-view-controller-diagram-no-arrows.png)

###View: The View is responsible for displaying the data on the screen from the Controller and receiving user gestures and relaying that back to the Controller.

###Controller: The Controller is responsible for updating and retrieving information from the Model and handles user interaction from the View.

###Model: The Model is responsible for retrieving the data from whatever data sources that powers the app (database, feeds etc).


###The Model View Controller design pattern also dictates how communication should function between the three roles.


This diagram below illustrates the rules:

![flow](https://github.com/ssamgir/SSBasicsOfObjectiveC/blob/master/model-view-controller-diagram.png)
###1. The View never directly sends or receives information to/from the Model.

###2. The Controller serves as the “middle-man” between the View and the Model

###3. The Model never communicates with the View.

So why do we have these communication rules?

##Nothing is going to blow up or crash if we don’t follow these rules however, by following the MVC design pattern and it’s communication rules, we’re “de-coupling” the different components as much as possible.

The idea is that, the more de-coupled things are, the easier it will be to:
##a) swap components in and out as needed because there are less intertwining relationships and dependencies
##b) easier to read, understand and thus solve any bugs that may crop up

If we didn’t follow the rules and had all the components communicating with every other component, it would be like sorting through a plate of spaghetti and you’re trying to trace the root of a bug.

The MVC pattern may seem very abstract to you right now but don’t worry because as we build more demo apps together, it’ll become increasingly apparent how our apps follow this software design pattern.

###Properties

*Properties are introduced in Objective-C to ensure that the instance variable of the class can be accessed outside the class.

The various parts are the property declaration are as follows.

Properties begin with @property, which is a keyword

It is followed with access specifiers, which are nonatomic or atomic, readwrite or readonly and strong, unsafe_unretained or weak. This varies based on the type of the variable. For any pointer type, we can use strong, unsafe_unretained or weak. Similarly for other types we can use readwrite or readonly.

This is followed by the datatype of the variable.

Finally, we have the property name terminated by a semicolon.

We can add synthesize statement in the implementation class. But in the latest XCode, the synthesis part is taken care by the XCode and you need not include synthesize statement.

It is only possible with the properties we can access the instance variables of the class. Actually, internally getter and setter methods are created for the properties.

For example, let's assume we have a property @property (nonatomic ,readonly ) BOOL isDone. Under the hood, there are setters and getters created as shown below.


##UI Specific Elements

1	 Text Fields -It is an UI element that enables the app to get user input

 

2 Input types - TextFields - We can set the type of input that user can give by using the keyboard property of UITextField.



3 Buttons It is used for handling user actions.

4	Label It is used for displaying static content.

5 Toolbar It is used if we want to manipulate something based on our current view.

6	Status Bar It displays the key information of device.

7	Navigation Bar It contains the navigation buttons of a navigation controller, which is a stack of view controllers which can be pushed and popped.

8	
Tab bar

It is generally used to switch between various subtasks, views or models within the same view.

9	
Image View

It is used to display a simple image or sequence of images.

10	
Scroll View

It is used to display content that is more than the area of screen.

11	
Table View

It is used for displaying scrollable list of data in multiple rows and sections.

12	
Split View

It is used for displaying two panes with master pane controlling the information on detail pane.

13	
Text View

It is used for diplaying scrollable list of text information that is optionally editable.

14	
View Transition

It explains the various view transitions between views.

15	
Pickers

It is used for displaying for selecting a specific data from a list.

16	
Switches

It is used as disable and enable for actions.

17	
Sliders

It is used to allow users to make adjustments to a value or process throughout a range of allowed values.

18	
Alerts

It is used to give important information to users.

19	
Icons

It is an image representation used for an action or depict something related to the application.
