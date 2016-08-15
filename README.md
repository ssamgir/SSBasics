## Basic Data Types

```
Some of the more common data types we use in Objective-C include

* int -   An integer value, i.e. a whole number (no decimals) that includes zero and negative numbers.

* float -  A floating point value that includes as many decimal places as it can hold. Because the decimal place can change, or float,            its important to know that these values may technically be imprecise. When precise decimals are needed, like for currency,            we should use the NSDecimalNumber data type  

* BOOL  Short for “boolean”, this is a 1-bit “true” or “false” value that can only be in one of those states. The C language (and               hence, Objective-C) treat 0 as “false” and 1 as “true”. As such, the following keywords can be used to represent true/false           values: YES/NO, TRUE/FALSE, true/false, 1,0

* char   A single character, such as the letter A or the symbol “#”. Note that lowercase and uppercase characters are different, so            “a” and “A” are two different characters

* NSString – String data is a bunch of characters strung together to make text, like a banner strung up at a party

* NSNumber – This class is a lightweight “wrapper” class that gives object-oriented features to the primitive number types mentioned              above (among others)
```
The first four data types in the list above, int, float, BOOL, and char, are scalar (non-object) data types, which means that they are relatively simple and straightforward. 

The word “primitive” is also used to describe this type of data, as it is not as advanced as Object data types.

Other scalar data types include short, double, and long. For more information about basic data types in Objective-C, check out Objective-C 2.0 Data Types. NSString and NSNumber begin with capital letters because they are more complex data types.

They are actually objects, and the naming convention in Objective-C is that object names should start with a capital letter. 

An object is different than a primitive data type because it has more complex properties and methods available to it, whereas the primitive data types are limited and straightforward. 

For example, we can send a message called length to an NSString object, and the NSString will tell us how many characters are in the text. 

The int data type does not respond to any messages like that. 
You might also be wondering why NSString and NSNumber start with the letters “NS” instead of being named String and Number. 

Objects are defined in class files (more on classes in Part 2), and all classes that get used in Objective-C get loaded into the same place, which means that classes with the same names can cause problems.

To try to avoid the same names, Objective-C adopted the convention of adding a 2 or 3 letter prefix to class names to indicate where they come from. “NS” comes from NeXT and the NeXTSTEP Computer, which was the company Steve Jobs founded after being forced out of Apple in the 80s.

#Variables
In programming, a variable is basically a container used to hold data. The data itself can be anything from a simple number to the lyrics and metadata about a song. When we create a variable in Objective-C, we usually specify what kind of data it will hold. This is known as statically typing the data. Blocks of memory in the computer are allocated as the “container” to hold the data, and we store a reference to that container with a name that we provide. “Static typing” means that the type of data each variable (or container) will hold is declared up front. So for example, if a variable is supposed to hold a number, we need to say so, and we wont be allowed to put something else like a letter in it. Variables that are statically typed will be checked before the program even runs, and well be presented with an error if we forget to declare a type of data or declare the wrong one. Okay, let’s finally take a look at some code! Here’s an example of declaring a scalar variable and assigning some data to it:  The line above is a statement that declares a variable named favoriteNumber that holds int (integer number) data. We then assign this variable the value 24. In essence, it puts the value 24 in the container named favoriteNumber. Later in code we can use the container’s name to get the data we put inside it.
The first word in a variable declaration is the data type, which tells us what kind of data the variable will hold.
The second word is the name of the variable, which can be anything you want following a few conventions. Variable names must not contain any spaces or special characters; they can only have letters, numbers, and underscores. They must not start with a number, though.
The equals sign (=) is an operator, meaning it performs a specific operation for us. This is the assignment operator, meaning that we use it to assign values to variables. In this example it is assigning the integer value on the right (#4) to the variable favoriteNumber on the left (#2).
The number in green is the int value we are working with. int numbers are positive or negative whole numbers with no decimal parts, just like this example.
Finally, the last character in this line is the semicolon, which is used to finish this statement. Semicolons in Objective-C are like periods in sentences: we use them to indicate when were done saying something. Every statement in Objective-C must end with a semicolon (note that a statement may be displayed on multiple lines for better readability).
Things get slightly more complicated with object variables, though:  The parts of this statement numbered 1-5 are the same. The data in this case is text (which is surrounded by double quotes).
The asterisk (*) can be a little confusing. This is not part of the variable name. It can be placed anywhere between the data type and the variable name, so the following are all equivalent: 
NSString* title;
NSString * title; 
NSString *title;
The * symbol is actually an operator that is used to de-reference a pointer. De-what a what now? Pointers are pretty much what they sound like. They “point” to a location in memory where the actual data is stored. That location in memory is the true container that holds the data. Pointers are a part of regular C and are used because they are more efficient. When we use pointers in our programs, we only need to store and copy a simple pointer, which is really just an address for a space in memory. It’s a relatively small piece of data. If we instead had to store and copy the data being pointed to, we might very quickly run into problems of not having enough memory. For example, it’s much more efficient to simply point to the location for a large video file and use that pointer multiple times in code than to actually have to use all the data of that large video file every time we access it in code. Okay, so back to the asterisk: what does it mean to de-reference a pointer? It simply means that we obtain the value stored in the memory where the pointer is pointing to.
The “at” symbol (@) plus text inside double quotes make up an “NSString literal”. As someone who used Strings in other programming languages first, this was confusing to me. The @ symbol is used in a few places in Objective-C, and basically it’s a way to signal that whatever it’s attached to is special to Objective-C and not part of regular C. This is important when the computer compiles Objective-C code. NSString objects are different than the counterparts used in C, so that’s why the @ symbol appears before the first double quote.
One Last Thing: Static vs. Dynamic Typing
Remember a moment ago when we talked about Objective-C being a statically-typed language, meaning that “the type of data each variable (or container) will hold is declared up front?” Well, that’s sort of true, but doesn’t describe the whole picture. I don’t want to overload this post with details about the language, but it’s important to mention that Objective-C is also a dynamic language, which means that some parts of our code can be extended and modified while our apps are running (i.e. after they’ve already been compiled). One example is the use of the generic data type called id. id can be used to represent any kind of data type. It’s the most generic form of specifying data; it simply stands for an “identifier” that is used to reference data. This type of dynamic typing allows for increased flexibility in how we code certain things. In iOS, we often see id used for methods that are tied to controls on the screen, like:
- (IBAction)save:(id)sender;
This is the declaration of a method, which we’ll talk about in an upcoming post. But notice that the sender parameter is of type id. This allows some flexibility in that our app doesn’t care if the sender is a button or an image or whatever else we might want to use to trigger this action.
