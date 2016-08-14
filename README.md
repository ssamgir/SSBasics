Willupdate later
The Beginner’s Guide to Objective c

Perhaps my own experience with the Objective-C programming language will sound familiar to you. I grew up in a world of dots, semicolons, and curly braces that are known around the programming world as the familiar syntax of JavaScript, Java, C#, and many other programming languages. “Objective-C can’t be that hard” I thought. And then I looked at my first Objective-C code and I thought, “What is this hot mess? WHY ARE THERE SO MANY SQUARE BRACKETS?” Okay, let’s step back a moment. Spoiler alert: It isn’t that hard to learn Objective-C (and I’ve grown to love it). It is the main programming language used to write apps for the iPhone and iPad, and it is incredibly flexible and powerful and is actually very similar in many ways to other more popular programming languages.

Source: TIOBE Programming Community Index for
August 2013 – http://www.tiobe.com/index.php/content/paperinfo/tpci/index.html
Despite my initial fears, I read some documentation, looked at some code, tried out my own, and asked smart people silly questions. But it brought me back to an enlightened viewpoint that is sometimes easy to forget: “Language doesn’t matter.” In programming, the language we use is just the syntax, just the details about how we want to control the computer. The concepts of what we are actually doing: loops, conditionals, using variables, etc., are all the same from one language to the next. When learning a different language we just need to learn the specific words and symbols we need to use to command the machine. All that aside, Objective-C is a great first language to learn, too. Below you will find a guide for getting started with Objective-C for iOS development which will help as a learning aid for how to program in Objective-C or as a quick reference if you already know another language.
Objective-C the Programming Language
As you might guess from its name, “Objective-C” is based on the C programming language, with lots of object-oriented features added. It was originally developed in the early 1980s but has really gained in popularity with the rise of iOS. Let’s address some common questions and fears about Objective-C.
C? C++? C#? What gives?
Objective-C isn’t the only popular language derived from C. First came C++, which was originally named “C with Classes.” The idea was to bring classes and other object-oriented features to C, and C++ became popular because of its combination of the power of C with the benefits of an object-oriented approach. C# was created by Microsoft to take C++ even further down the object-oriented road. At first it was quite similar to the massively popular language called Java, though they have since diverged in features despite sharing a nearly identical core syntax. The nice thing about all these languages derived from C is that a lot of the basic syntax is the same. Variables are often declared and used in the same way, and important keywords and symbols are usually repeated as well.
What’s all this “object-oriented” business about?
To borrow from my post about Java for Android:
An object-oriented language is one that is built around the concept of objects. In the physical world, take a look around the room and think of each thing as an object. For example, on my desk right now I have a mug. As an object, its name is mug and it has properties about it like its color and how much liquid it will hold. Object-oriented languages allow us to define objects like mugs and access their properties in our code. We can also send messages to objects, so for my mug I might want to know Is it empty? We can then create and manipulate all sorts of objects to do different things in our app. For example, we can use the Camera object to take a photo. The Camera object represents the physical camera on an iPhone, but in a way that we can interact with in code.
 

The isEmpty message for this mug object will return NO!
But what about these square brackets? This code looks like garbage.
Objective-C maintains all the same syntax and features of C. The object-oriented features that were added were done so in the model of Smalltalk, in which we send messages to objects (more on these later) in this manner:
mug makeEmpty
(The makeEmpty message is sent to the mug object.) In Objective-C we simply surround such actions with square brackets:
[mug makeEmpty]
What may seem like an arbitrary collection of brackets at first will, with time and practice, make sense as a mechanism for organizing code around these object-oriented concepts that were added as a thin layer on top of the world of C code.
C + stuff you can do with square brackets = Objective-C!
Okay, but I don’t wanna manage my memory!
You don’t have to. Sort of. In iOS 4.0, Apple introduced a concept called ARC (Automatic Reference Counting) which took much of the mundane pain of memory management away from Objective-C programming. In older iOS code you will see many retain and release messages passed to objects, but in projects that use ARC, these messages are handled automatically by the compiler. The code ends up looking a little more like code you might find in languages that manage memory automatically, like Java. But it’s still important to understand how memory is allocated, used, and released in an iOS program if you want it to operate smoothly and efficiently and avoid app crashes. For more details about memory management in Objective-C, check out this iOS Foundations stage about ARC.
Components of the Objective-C Programming Language
Let’s talk about the code itself. At its most basic level, programming is really about working with data. There are all sorts of types of data we will need to use that range in complexity from simple things like numbers and yes/no values, up to more complex things like pictures or player information for a game.
Basic Data Types
Some of the more common data types we use in Objective-C include:
int – An integer value, i.e. a whole number (no decimals) that includes zero and negative numbers.
float – A floating point value that includes as many decimal places as it can hold. Because the decimal place can change, or float, its important to know that these values may technically be imprecise. When precise decimals are needed, like for currency, we should use the NSDecimalNumber data type.
BOOL – Short for “boolean”, this is a 1-bit “true” or “false” value that can only be in one of those states. The C language (and hence, Objective-C) treat 0 as “false” and 1 as “true”. As such, the following keywords can be used to represent true/false values: YES/NO, TRUE/FALSE, true/false, 1,0.
char – A single character, such as the letter A or the symbol “#”. Note that lowercase and uppercase characters are different, so “a” and “A” are two different characters.
NSString – String data is a bunch of characters strung together to make text, like a banner strung up at a party.
NSNumber – This class is a lightweight “wrapper” class that gives object-oriented features to the primitive number types mentioned above (among others).
The first four data types in the list above, int, float, BOOL, and char, are scalar (non-object) data types, which means that they are relatively simple and straightforward. The word “primitive” is also used to describe this type of data, as it is not as advanced as Object data types. Other scalar data types include short, double, and long. For more information about basic data types in Objective-C, check out Objective-C 2.0 Data Types. NSString and NSNumber begin with capital letters because they are more complex data types. They are actually objects, and the naming convention in Objective-C is that object names should start with a capital letter. An object is different than a primitive data type because it has more complex properties and methods available to it, whereas the primitive data types are limited and straightforward. For example, we can send a message called length to an NSString object, and the NSString will tell us how many characters are in the text. The int data type does not respond to any messages like that. You might also be wondering why NSString and NSNumber start with the letters “NS” instead of being named String and Number. Objects are defined in class files (more on classes in Part 2), and all classes that get used in Objective-C get loaded into the same place, which means that classes with the same names can cause problems. To try to avoid the same names, Objective-C adopted the convention of adding a 2 or 3 letter prefix to class names to indicate where they come from. “NS” comes from NeXT and the NeXTSTEP Computer, which was the company Steve Jobs founded after being forced out of Apple in the 80s.
Variables
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
Stay Tuned
There is a lot to cover for even the basic syntax and concepts of Objective-C, so stay tuned for upcoming posts about things like classes, messages/methods/functions, conditionals, and loops! If you want to try some of this out yourself in the browser, check out Build a Simple iPhone App, which includes some exciting Code Challenges to get some practice with Objective-C. You might also like Objective-C Basics, our newest course on learning Objective-C.


code
iOS
iphone
make an app
objective-c
programming
programming language
variables
14 Responses to “The Beginner’s Guide to Objective-C: Language and Variables” 


Joshua Pinter on March 28, 2016 at 10:01 am said: 
As always Ben, great job. You’re a natural teacher with a deep understanding of the subject matter.
You taught me the basics of Android a couple years ago and won’t you imagine my delight when I see now you’re teaching me some Obj-c! 
Reply 
Ben Jakuben on March 28, 2016 at 11:45 am said: 
Thanks so much! And thanks for your notes on the other post: I’ll update it soon. We released updated courses on Objective-C that are really well done by Gabe Nadel, so be sure to check those out, too. We also have a workshop comparing Objective-C and Swift, with more on the way. 
Reply 
業界最高峰のブランドコピー 激安、コピーブランド、スーパーコピーブランド(N級品)通販専門店!ブランドコピー,コピーブランド,スーパーコピーブランド,ブランドコピー 激安,偽物ブラン on November 14, 2015 at 2:26 pm said: 
コピーカルティエ時計，コピーオメガ時計，コピーその他時計の專門店ロレックス、ウブロをはじめとした、様々なスーパーコピー時計の販売?サイズ調整をご提供しております。
業界最高峰のブランドコピー 激安、コピーブランド、スーパーコピーブランド(N級品)通販専門店!ブランドコピー,コピーブランド,スーパーコピーブランド,ブランドコピー 激安,偽物ブランド、偽物のバッグ、腕時計、財布など激安で買える！全部のスーパーコピー販売品物のなかで私達のブランド激安が一番有名です http://www.ooowatch.com/tokei/zenith/index.html
Reply 
JoeyBB on October 8, 2013 at 2:27 am said: 
The analogies you have used are so effective in teaching beginners like myself the basics of IOS programming. I have read a number of books, but none of them are as effective as yours. I am now a fan of your work. Please keep me posted of all your work!
Reply 
Webmaster Blog on August 19, 2013 at 5:46 am said: 
Its like you read my mind! You seem to know so much about this, like you wrote the book in it or something. I think that you can do with a few pics to drive the message home a bit, but instead of that, this is excellent blog. A fantastic read. I’ll certainly be back.
Reply 
Bendog24 on August 19, 2013 at 9:28 am said: 
Thank you, and thanks for the tip! I will try to include more photos in my next post. 
Reply 
janyen on August 17, 2013 at 3:28 am said: 
Wow. Thanks for this excellent guide  reptiles puzzles
Reply 
Noodle on August 16, 2013 at 3:09 am said: 
I am grateful to have read the entire article, since I shall be commencing my iOS Development Training next week. I have read tons of articles prior to the training, I must say yours is one that simply makes a newbie to the language understand the basics. Way to go, Ben. I am a C#.Net/VB.Net programmer and I think Objective C isn’t that difficult – yet.
Reply 
Bendog24 on August 16, 2013 at 8:39 am said: 
Thanks so much! That’s exactly how I am trying to write this series. Stay tuned for more, and good luck!
Reply 
Laura Ferrel on August 15, 2013 at 10:46 am said: 
Wow, today I cam across this guide too for beginners: http://ios-blog.co.uk/tutorials/objective-c-guide-for-developers-part-1/ – This must just be one of those days where I need to stop thinking about developing and actually start coding 
Reply 
Bendog24 on August 15, 2013 at 11:25 am said: 
Another great find! I’ll reference that other blog post in the future, too. And today is definitely a great day to start coding!
Reply 
iOS-Blog on August 16, 2013 at 8:49 am said: 
We just got a ping back that you posted this here. I’m glad you find the tutorial useful. And I agree with the author, today is a great day to start coding. Get to it  This tutorial is great too. 
Reply 
Alex on August 15, 2013 at 10:12 am said: 
Great Post!
Reply 
Bendog24 on August 15, 2013 at 10:19 am said: 
Thanks! Stay tuned for at least two more to follow about Objective-C. 
Reply 


Leave a Reply

 
Name *
 
Email Address (will not be published) *
 
Website

 
 
Want to learn more about iOS? 
iOS is the operating system that powers iPhones and iPads. Learn the language, tools and frameworks to build interactive apps on the iOS platform. 
Learn more 
Stay current
Sign up for our newsletter, and we'll send you news and tutorials on web design, coding, business, and more!
 




©2016 Treehouse Island, Inc. 

About • Careers • Blog • Affiliate Program • Terms • Privacy • Press Kit • Contact 






