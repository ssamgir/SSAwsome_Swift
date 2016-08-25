# Awsome Swift
Variables, Constants and Type Inference

In Swift, you declare variables with the “var” keyword and constants using the “let” keyword. Here is an example:


var numberOfRows = 30
let maxNumberOfRows = 100
1
2
var numberOfRows = 30
let maxNumberOfRows = 100
These are the two keywords you need to know for variable and constant declaration. You simply use the “let” keyword for storing value that is unchanged. Otherwise, use “var” keyword for storing value that can be changed.

What’s interesting is that Swift allows you to use nearly any character for both variable and constant names. You can even use emoji character for the naming:

Swift Variable Name in Emoji
Tip: You may wonder how you can type emoji character in Mac OS. It’s easy. Just press Control-Command-spacebar and an emoji picker will be displayed.
You may notice a huge difference in variable declaration between Objective C and Swift. In Objective-C, developers have to specify explicitly the type information when declaring a variable. Be it an int or double or NSString, etc.


const int count = 10;
double price = 23.55;
NSString *myMessage = @"Objective-C is not dead yet!";
1
2
3
const int count = 10;
double price = 23.55;
NSString *myMessage = @"Objective-C is not dead yet!";
It’s your responsibility to specify the type. For Swift, you no longer needs to annotate variables with type information. It provides a huge feature known as Type inference. The feature enables the compiler to deduce the type automatically by examining the values you provide in the variable.


let count = 10 
// count is inferred to be of type Int
var price = 23.55
// price is inferred to be of type Double
var myMessage = "Swift is the future!"
// myMessage is inferred to be of type String
1
2
3
4
5
6
let count = 10 
// count is inferred to be of type Int
var price = 23.55
// price is inferred to be of type Double
var myMessage = "Swift is the future!"
// myMessage is inferred to be of type String
It makes variable and constant declaration much simpler, as compared to Objective C. Swift provides an option for you to explicitly specify the type information if you wish. The below example shows how to specify type information when declaring a variable in Swift:


var myMessage : String = "Swift is the future!"
1
var myMessage : String = "Swift is the future!"
No Semicolons

In Objective C, you need to end each statement in your code with a semicolon. If you forget to do so, you’ll end up with a compilation error.

As you can see from the above examples, Swift doesn’t require you to write a semicolon (;) after each statement, though you can still do so if you like.


var myMessage = "No semicolon is needed"
1
var myMessage = "No semicolon is needed"
Basic String Manipulation

In Swift, strings are represented by the String type, which is fully Unicode-compliant. You can declare strings as variables or constants:


let dontModifyMe = "You cannot modify this string"
var modifyMe = "You can modify this string"
1
2
let dontModifyMe = "You cannot modify this string"
var modifyMe = "You can modify this string"
In Objective C, you have to choose between NSString and NSMutableString classes to indicate whether the string can be modified. You do not need to make such choice in Swift. Whenever you assign a string as variable (i.e. var), the string can be modified in your code.

Swift simplifies string manipulating and allows you to create a new string from a mix of constants, variables, literals, as well as, expressions. Concatenating strings is super easy. Simply add two strings together using the “+” operator:


let firstMessage = "Swift is awesome. "
let secondMessage= "What do you think?"
var message = firstMessage + secondMessage

println(message)
1
2
3
4
5
let firstMessage = "Swift is awesome. "
let secondMessage= "What do you think?"
var message = firstMessage + secondMessage
 
println(message)
Swift automatically combines both messages and you should the following message in console. Note that println is a global function in Swift to print the message in console.


Swift is awesome. What do you think?

You can do that in Objective C by using stringWithFormat: method. But isn't the Swift version more readable?

 
NSString *firstMessage = @"Swift is awesome. ";
NSString *secondMessage = @"What do you think?";
NSString *message = [NSString stringWithFormat:@"%@%@", firstMessage, secondMessage];

NSLog(@"%@", message);
1
2
3
4
5
NSString *firstMessage = @"Swift is awesome. ";
NSString *secondMessage = @"What do you think?";
NSString *message = [NSString stringWithFormat:@"%@%@", firstMessage, secondMessage];
 
NSLog(@"%@", message);
String comparison is more straightforward. In Objective C, you can't use the == operator to compare two strings. Instead you use the isEqualToString: method of NSString to check if both strings are equal. Finally, Swift allows you to compare strings directly by using the == operator.


var string1 = "Hello"
var string2 = "Hello"
if string1 == string2 {
    println("Both are the same")
}
1
2
3
4
5
var string1 = "Hello"
var string2 = "Hello"
if string1 == string2 {
    println("Both are the same")
}
Arrays

The syntax of declaring an array in Swift is similar to that in Objective C. Here is an example:

Objective C:


NSArray *recipes = @[@"Egg Benedict", @"Mushroom Risotto", @"Full Breakfast", @"Hamburger", @"Ham and Egg Sandwich"];
1
NSArray *recipes = @[@"Egg Benedict", @"Mushroom Risotto", @"Full Breakfast", @"Hamburger", @"Ham and Egg Sandwich"];
Swift:


var recipes = ["Egg Benedict", "Mushroom Risotto", "Full Breakfast", "Hamburger", "Ham and Egg Sandwich"]
1
var recipes = ["Egg Benedict", "Mushroom Risotto", "Full Breakfast", "Hamburger", "Ham and Egg Sandwich"]
While you can put any objects in NSArray or NSMutableArray in Objective C, arrays in Swift can only store items of the same type. Say, you can only store strings in the above string array. With type inference, Swift automatically detects the array type. But if you like, you can also specify the type in the following form:


var recipes : String[] = ["Egg Benedict", "Mushroom Risotto", "Full Breakfast", "Hamburger", "Ham and Egg Sandwich"]
1
var recipes : String[] = ["Egg Benedict", "Mushroom Risotto", "Full Breakfast", "Hamburger", "Ham and Egg Sandwich"]
Like NSArray, the Swift provides various methods for you to query and manipulate an array.

Simply use the count method to find out the number of items in the array:


var numberOfItems = recipes.count
// recipes.count will return 5
1
2
var numberOfItems = recipes.count
// recipes.count will return 5
In Objective C you use the addObject: method of NSMutableArray to add a new item to an array. Swift makes the operation even simpler. You can add an item by using the "+=" operator:


recipes += "Thai Shrimp Cake"
1
recipes += "Thai Shrimp Cake"
This applies when you need to add multiple items:


recipes += ["Creme Brelee", "White Chocolate Donut", "Ham and Cheese Panini"]
1
recipes += ["Creme Brelee", "White Chocolate Donut", "Ham and Cheese Panini"]
To access or change a particular item in an array, pass the index of the item by using subscript syntax just like that in Objective C.


var recipeItem = recipes[0]
recipe[1] = "Cupcake"
1
2
var recipeItem = recipes[0]
recipe[1] = "Cupcake"
One interesting feature of Swift is that you can use "..." to change a range of values. Here is an example:


recipes[1...3] = ["Cheese Cake", "Greek Salad", "Braised Beef Cheeks"]
1
recipes[1...3] = ["Cheese Cake", "Greek Salad", "Braised Beef Cheeks"]
This changes the item 2 to 4 of the recipes array to "Cheese Cake", "Greek Salad" and "Braised Beef Cheeks".

Dictionaries

Swift only provides two collection types. One is arrays and the other is dictionaries. Each value in a dictionary is associated with a unique key. If you're familiar with NSDictionary in Objective C, the syntax of initializing a dictionary in Swift is quite similar. Here is an example:

Objective C:


NSDictionary *companies = @{@"AAPL" : @"Apple Inc", @"GOOG" : @"Google Inc", @"AMZN" : @"Amazon.com, Inc", @"FB" : @"Facebook Inc"};
1
NSDictionary *companies = @{@"AAPL" : @"Apple Inc", @"GOOG" : @"Google Inc", @"AMZN" : @"Amazon.com, Inc", @"FB" : @"Facebook Inc"};
Swift:


 

var companies = ["AAPL" : "Apple Inc", "GOOG" : "Google Inc", "AMZN" : "Amazon.com, Inc", "FB" : "Facebook Inc"]
1
var companies = ["AAPL" : "Apple Inc", "GOOG" : "Google Inc", "AMZN" : "Amazon.com, Inc", "FB" : "Facebook Inc"]
The key and value in the key-value pairs are separated by a colon. Like array and other variables, Swift automatically detects the type of the key and value. However, if you like, you can specify the type information by using the following syntax:


var companies: Dictionary<String, String> = ["AAPL" : "Apple Inc", "GOOG" : "Google Inc", "AMZN" : "Amazon.com, Inc", "FB" : "Facebook Inc"]
1
var companies: Dictionary<String, String> = ["AAPL" : "Apple Inc", "GOOG" : "Google Inc", "AMZN" : "Amazon.com, Inc", "FB" : "Facebook Inc"]
To iterate through a dictionary, use the for-in loop.


for (stockCode, name) in companies {
    println("\(stockCode) = \(name)")
}
1
2
3
for (stockCode, name) in companies {
    println("\(stockCode) = \(name)")
}
You can also use the keys and values properties to retrieve the keys and values of the dictionary.


for stockCode in companies.keys {
    println("Stock code = \(stockCode)")
}
1
2
3
for stockCode in companies.keys {
    println("Stock code = \(stockCode)")
}

for name in companies.values {
    println("Company name = \(name)")
}
1
2
3
for name in companies.values {
    println("Company name = \(name)")
}
To access the value of a particular key, specify the key using the subscript syntax. If you want to add a new key-value pair to the dictionary, simply use the key as the subscript and assign it with a value like below:


companies["TWTR"] = "Twitter Inc"
1
companies["TWTR"] = "Twitter Inc"
Now the companies dictionary contains a total of 5 items. The "TWTR":"Twitter Inc" pair is automatically added to the companies dictionary.

Classes

In Objective C, you create separate interface (.h) and implementation (.m) files for classes. Swift no longer requires developers to do that. You can define classes in a single file (.swift) without separating the external interface and implementation.

To define a class, you use the class keyword. Here is a sample class in Swift:


class Recipe {
    var name: String = ""
    var duration: Int = 10
    var ingredients: String[] = ["egg"]
}
1
2
3
4
5
class Recipe {
    var name: String = ""
    var duration: Int = 10
    var ingredients: String[] = ["egg"]
}
Similar to Objective C, right? In the above example, we define a Recipe class with three properties including name duration and ingredients. Swift requires you to provide the default values of the properties. You'll end up with compilation error if the initial values are missing.

What if you don't want to assign a default value? Swift allows you to write a question mark (?) after the type of a value to mark the value as optional.


class Recipe {
    var name: String?
    var duration: Int = 10
    var ingredients: String[]?
}
1
2
3
4
5
class Recipe {
    var name: String?
    var duration: Int = 10
    var ingredients: String[]?
}
In the above code, the name and ingredients properties are automatically assigned with a default value of nil. To create an instance of a class, just use the below syntax:


var recipeItem = Recipe()
1
var recipeItem = Recipe()
You use the dot notation to access or change the property of an instance.


recipeItem.name = "Mushroom Risotto"
recipeItem.duration = 30
recipeItem.ingredients = ["1 tbsp dried porcini mushrooms", "2 tbsp olive oil", "1 onion, chopped", "2 garlic cloves", "350g/12oz arborio rice", "1.2 litres/2 pints hot vegetable stock", "salt and pepper", "25g/1oz butter"]
1
2
3
recipeItem.name = "Mushroom Risotto"
recipeItem.duration = 30
recipeItem.ingredients = ["1 tbsp dried porcini mushrooms", "2 tbsp olive oil", "1 onion, chopped", "2 garlic cloves", "350g/12oz arborio rice", "1.2 litres/2 pints hot vegetable stock", "salt and pepper", "25g/1oz butter"]
Swift allows you to subclass Objective-C classes and adopt Objective-C protocols. For example, you have a SimpleTableViewController class that extends from UIViewController class and adopts both UITableViewDelegate and UITableViewDataSource protocols. You can still use the Objective C classes and protocols but the syntax is a bit different.

Objective C:


@interface SimpleTableViewController : UIViewController <UITableViewDelegate, UITableViewDataSource>
1
@interface SimpleTableViewController : UIViewController <UITableViewDelegate, UITableViewDataSource>
Swift:


class SimpleTableViewController : UIViewController, UITableViewDelegate, UITableViewDataSource
1
class SimpleTableViewController : UIViewController, UITableViewDelegate, UITableViewDataSource
Methods

Swift allows you to define methods in class, structure or enumeration. I'll focus on instance methods of a class here. You can use the func keyword to declare a method. Here is a sample method without return value and parameters:


class TodoManager {
    func printWelcomeMessage() {
        println("Welcome to My ToDo List")
    }
}
1
2
3
4
5
class TodoManager {
    func printWelcomeMessage() {
        println("Welcome to My ToDo List")
    }
}
In Objective C, you call a method like this:


[todoManager printWelcomeMessage];
1
[todoManager printWelcomeMessage];
In Swift, you call a method by using dot syntax:


todoManager.printWelcomeMessage()
1
todoManager.printWelcomeMessage()
If you need to declare a method with parameters and return values, the method will look this:


class TodoManager {
    func printWelcomeMessage(name:String) -> Int {
        println("Welcome to \(name)'s ToDo List")
        
        return 10
    }
}
1
2
3
4
5
6
7
class TodoManager {
    func printWelcomeMessage(name:String) -> Int {
        println("Welcome to \(name)'s ToDo List")
        
        return 10
    }
}
The syntax looks a bit awkward especially for the -> operator. The above method takes a name parameter in String type as the input. The -> operator is used as an indicator for method with a return value. In the above code, you specify a return type of Int that returns the total number of todo items. Below demonstrates how you call the method:


var todoManager = TodoManager()
let numberOfTodoItem = todoManager.printWelcomeMessage("Simon")
println(numberOfTodoItem)
1
2
3
var todoManager = TodoManager()
let numberOfTodoItem = todoManager.printWelcomeMessage("Simon")
println(numberOfTodoItem)
Control Flow

Control flow and loops employ a very C-like syntax. As you can see above, Swift provides for-in loop to iterate through arrays and dictionaries. You can use if statement to execute code based on a certain condition. Here I'd just like to highlight the switch statement in Swift which is much powerful than that in Objective C. Take a look at the following sample switch statement. Do you notice anything special?


switch recipeName {
    case "Egg Benedict":
        println("Let's cook!")
    case "Mushroom Risotto":
        println("Hmm... let me think about it")
    case "Hamburger":
        println("Love it!")
    default:
        println("Anything else")
}
1
2
3
4
5
6
7
8
9
10
switch recipeName {
    case "Egg Benedict":
        println("Let's cook!")
    case "Mushroom Risotto":
        println("Hmm... let me think about it")
    case "Hamburger":
        println("Love it!")
    default:
        println("Anything else")
}
Yes, switch statement can now handle strings. You can't do switching on NSString in Objective C. You had to use several if statements to implement the above code. At last Swift brings us this most sought after utilization of switch statement.

Another enhancement of switch statement is the support of range matching. Take a look at the below code:


var speed = 50
switch speed {
case 0:
    println("stop")
case 0...40:
    println("slow")
case 41...70:
    println("normal")
case 71..<101:
    println("fast")
default:
    println("not classified yet")
}
// as the speed falls within the range of 41 and 70, it'll print normal to console
1
2
3
4
5
6
7
8
9
10
11
12
13
14
var speed = 50
switch speed {
case 0:
    println("stop")
case 0...40:
    println("slow")
case 41...70:
    println("normal")
case 71..<101:
    println("fast")
default:
    println("not classified yet")
}
// as the speed falls within the range of 41 and 70, it'll print normal to console
The switch cases now lets you check values within a certain range by using two new operators: "..." and "..<". Both operators serve as a shortcut for expressing a range of values. Consider the sample range of "41...70", the ... operator defines a range that runs from 41 to 70, including both 41 and 70. If we use the ..< operator instead of ... in the example, this defines a range that runs from 41 to 69. In other words, 70 is excluded from the range.

Should I Still Learn Objective C?

I hope this short tutorial gives you a very brief introduction of Swift. This is just the beginning of the Swift tutorials. We'll continue to explore the language and share anything new with you. Of course, we'll develop more detailed tutorials when Apple officially releases Xcode 6 and iOS 8 this fall. Meanwhile, if you want to further study the language, grab the free Swift book from iBooks Store.

Before I end this post, I'd like to take this chance to answer a common question after the announcement of Swift.

Should I continue to learn Objective C?

My view on Swift is it is the future of programming for iOS. Apple will continue to promote and add features to the language. As you can see in this tutorial, the syntax is more developer-friendly and it's easier for beginner to learn, particular for those who have scripting background. It will definitely encourage more people to learn iOS programming and build iOS apps. That said, I think Objective C will not disappear overnight and is here to stay for years. There are tons of apps and code libraries that are written in Objective C. It'll take time for developers to convert the code to Swift. As Xcode supports both Objective C and Swift, some developers may even keep the existing code in Objective C and only develop new library/app in Swift. Thus, I suggest you to learn both languages. If you can manage the fundamentals of Objective C, it'll be very easy for you to switch over to Swift as the two languages are quite similar. And it would definitely give you an edge over other Swift-only developers in the market.

What do you think about Swift? Leave me comment and share your thought.
