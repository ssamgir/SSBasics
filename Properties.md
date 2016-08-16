#Properties

*Properties are introduced in Objective-C to ensure that the instance variable of the class can be accessed outside the class.

The various parts are the property declaration are as follows.

Properties begin with @property, which is a keyword

It is followed with access specifiers, which are nonatomic or atomic, readwrite or readonly and strong, unsafe_unretained or weak. This varies based on the type of the variable. For any pointer type, we can use strong, unsafe_unretained or weak. Similarly for other types we can use readwrite or readonly.

This is followed by the datatype of the variable.

Finally, we have the property name terminated by a semicolon.

We can add synthesize statement in the implementation class. But in the latest XCode, the synthesis part is taken care by the XCode and you need not include synthesize statement.

It is only possible with the properties we can access the instance variables of the class. Actually, internally getter and setter methods are created for the properties.

For example, let's assume we have a property @property (nonatomic ,readonly ) BOOL isDone. Under the hood, there are setters and getters created as shown below.

-(void)setIsDone(BOOL)isDone;
-(BOOL)isDone;
