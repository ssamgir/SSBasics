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
