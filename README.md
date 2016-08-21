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



Sent Items


Write


Fw: IOS
"SANDESH"<sandesh_samgir79@rediffmail.com> to you & 2 other(s)
Sun, 22 May 2016 11:45:16 





We have blocked some images in this mail for security. Click here to view the blocked images.



Note: Forwarded message attached

-- Original Message --

From: "SANDESH"sandesh_samgir79@rediffmail.com on Sun, 22 May 2016 11:04:05 +0530
To: "sandeshsamgir "sandesh.samgir@adp.com
Subject: IOS


Get your own FREE website, FREE domain & FREE mobile app with Company email.  
Know More >

iPhone Interview Questions and Answers 



1. What is @interface?

- It’s a keyword used to declare the Class.





2. What is @implementation?

- It’s a keyword used to define the Class.





3. Garbage collector in iPhone?

- iOS 5.0 has got the ARC ( Automated reference counting ).  Objective C does not have a garbage collector rather it uses the reference counting algorithm to manage the memory. This was the developers task until Apple launched iOS 5.0. Again if you are targeting iOS 4.0 or earlier , ARC is no more a choice for you .



4. What is delegate?

- Delegate is an object that handles the events happening on an object. To do that delegate has to follow a protocol specifying the task it is going to handle .





5. What is @synthesize?

- We use @synthesize to generate getters and setters automatically from compiler. We declare properties and then generate getter and setter method by using @synthesize.





6. What are the features of iOS 5.0 ?

- https://developer.apple.com/technologies/ios5/





7. What is nonatomic ?

- nonatomic and atomic are related to multithreading environment .

 - If a property has an attribute as “nonatomic” that means multiple threads can modify that property concurrently.

- If the attribute is “atomic”, the threads would be given access atomically.

-  So “Atomic” is thread safe while “nonatomic” is thread unsafe.

- Atomic drastically hampers the performance so until and unless not needed you should never go for atomic attribute. ‘nonatomic ’ will do in most of the cases.





8. What are the delegate methods of MKMapView ?

- Check the MKMapViewDelegate in the Documentation. If you don’t have Xcode with you then search on Google.





9. What are the important delegate methods of NSXML parser?



-DidStartElement

-FoundCharecters

-DidEndElement

-FoundError







10. What is @dynamic and any place where it is used ?

- It tells compiler that getter and setter are not implemented by the class but by some other class .

- May be super class or child class .



Example – Core Data

-       The Managed object classes have properties defined by using @dynamic.





11. What is @property?

- It is a keyword used to declare a property.



12. What is data source?

- The datasource is an object that implements the required datasource protocol that is needed to create a complex control.

Ex UITableView is a view that needs a datasource object to which will help building the table. Often it’s the controller that is displaying the table view. The protocol that dataSource object ( mostly controller it self) has to implement is “UITableViewDataSource” .



13. What is model view controller?

- MVC is a Design pattern .

Model stands for the database  object which will manage all the database transaction .

- View stands for the UI i.e. the UI visible to the user. User will be interacting with the view.

- Controller is an object who handles the view events and also render the database changes to the UI. In short , it bridges the interaction between Modal and View.







14. what is @ protocol?

- @protocol is a keyword used to define a protocol. A protocol is a set of method declarations defining specific purpose. It only lists out the methods prototype , the actual implantation would be provided by the class that implements /  follows the protocol.





15. what is id?

- id is a generic reference type. The variable declared using id data-type can hold any object. Most of the methods that returns an object has ‘id’ as return type. Ex – init.



16. Explain memory management?

- Most of the object oriented languages have the Garbage Collector .  All the objects are allocated on the heap memory. The Garbage Collector is a thread that runs periodically to check all the objects, which are no more being referenced from the program. Garbage collector then de-allocates all these unreferenced objects on the Heap. In this environment programmer does not need to worry about de-allocating the objects explicitly.



In Objective – C we don’t have garbage collector. ( Note: Its available from iOS 5.0 only). So in this environment we have to explicitly take care of allocation and deallocation of all the objects in our program.  And to manage this Objective C uses ‘reference counting’ algorithm as the memory management algorithm. 



Reference Counting: In this algorithm every object keeps track of it owners ( I,e reference variables from the program ) . No of owners is represented by the property retainCount declared in NSObject. If this retainCount goes to ‘0’ the object gets deallocated automatically.  We never call dealloc method on any object explicitly.





17. what is retain and release?

- retain and release are two method defined in NSObject . - -

- These methods are related to Memory Mangement .

- retain method when called increases the retainCount by 1.

- release method when called decreases the retainCount by 1





18. what is dealloc?

- dealloc method is called on an object to actually deallocate the memory for that object. ( We should never call dealloc directly )

- In reference counting environment when retainCount of an object reaches to ‘0’, the dealloc method is called on that object automatically to delete the memory space of the object .

- If the object is having some reference type variable holding other objects, then we should call release method on every variable in dealloc.

- If you override then [super dealloc] should be the last line in this method.





19. What is Autorelease pool?

-  Autorelease pool is like a container that holds the autoreleased objects .

- This pool is drained with every run-loop of the Application

- When the pool gets drained, autorelease pool sends a release message to all the objects it was holding.







20. What is Foundation Framework? Can you explain some classes from that?

- Foundation is one of the important frameworks in COCOA Touch.

- It contains the classes like  NSArray , NSString , NSObject etc .





21. What is the difference between NSArray and NSMutableArray?



* NSArray

-        is a static array

-       Once created you can not modify the array

-       Ex you can not add or remove the object in NSArray.



* NSMutableArray

-       is a dynamic array

-       You can add or remove the object dynamically.





22. Write a delegate method of the table view?

 - (void)tableView:( UITableView*)tableView didSelectRowAtIndexPath:(NSIndexPath*)indexPath





23. What are the delegate methods of NSURLConection?

- didReceiveResponse:

- didReceiveData:

- didFinishLoadingData:

- didFailWithError:





24. What is cocoa ?

- COCOA is a collection of frameworks used to write Applications for MAC OS X.





25. Singleton classes

- A singleton class is such a class from which no more that one instance can be created. So there will always be single instance created throughout the program.

Ex UIApplication.



Posted by rahul varma at 10:56
Email ThisBlogThis!Share to TwitterShare to FacebookShare to Pinterest


+2   Recommend this on Google
Labels: iphone interview questions, iPhone Interview Questions and Answers 

18 comments:
￼
1. Zia Shahid3 February 2013 at 15:38 good,can u plz add 
