# Objective-C



## Method calls ('messages')

```objective-c
// This is pretty weird, but...

[object method]

[object method:argument]

// Nesting methods
// e.g. firstName + " " + lastName

[[firstName stringByAppendingString:@" "] stringByAppendingString:lastName];
=> returns @"John Olmsted"

// Multiple arguments:

[fullName stringByReplacingOccurrencesOfString:firstName withString:lastName]
=> returns @"Olmsted Olmsted"
```

## Strings

```objective-c
// Let's print something:

NSLog(@"Hello, world");    => "Hello, World."

// Note that the language is statically typed.
// Type is associated with variables:

NSString *firstName = @"John";

// Once we've defined the variable's type, we do not
// need to refer to it again, so long as we assign a value
// of the correct type:

firstName = @"Bob";

// String 'placeholders':

NSLog(@"Let's interpolate my name. It is %@.", firstName);
NSLog(@"They are %@ in the order they are %@.", @"replaced", @"defined");

/ Note that we have to use a different 'format specifier'
// to interpolate an NSUInteger into a string:

NSString *city = @"Berkeley";
NSUInteger cityLength = [city length];
NSLog(@"City has %lu characters", cityLength);    => "City has 9 characters"

// Method calls

[firstName description]    => returns @"John"

[firstName stringByAppendingString:lastName]    => returns @"John Olmsted"

[NSString stringWithFormat:@"%@ %@", firstName, lastName];
```


## Numbers

```objective-c
NSNumber *myAge = @28;

NSLog(@"%@", myAge);    => returns @28

NSUInteger myAge = @28;

// What's the difference between NSNumber and NSUInteger?

// NSNumber is an Objective-C type, and that's why the variable
// name `*myAge` is prefixed with an asterix at definition.
// NSUInteger is a C type, and no asterix is required.

// Converting between these types:

NSNumber *waterlooDate = @1815;
NSUInteger waterlooDateInt = [waterlooDate unsignedIntegerValue];
// or
NSUInteger waterlooDateInt = [waterlooDate intValue];

// Unfortunately this means that you get weird problems like this:

NSNumber *four = @4;
NSNumber *six = @6;

// This throws an error because `*` is a C operation, and these are
// Objective-C types:
NSNumber *twentyFour = four * six;    => Error!

// To use a C operation, we need Objective-C types:

NSUInteger four = @4;
NSUInteger six = @6;

NSUInteger twentyFour = four * six;
```


## Arrays

```objective-c
NSArray *fruit = @[@"banana", @"apple", @"kiwi"];

fruit[1];    => returns @"apple"

// Arrays are immutable objects!
fruit[3] = @"orange";    => This throws an error.
```


## Dictionaries

```objective-c
NSDictionary *myInfo = @{
  @"First Name": @"John",
  @"Last Name": @"Olmsted",
  @"Age": @28
};

myInfo[@"First Name"];    => returns @"John"
```


## Classes

```objective-c
// Let's objects without object literal notation:

NSString *emptyString = [NSString string];
NSArray *emptyArray = [NSArray array];
NSDictionary *emptyDictionary = [NSDictionary dictionary];

// Using alloc/init
// `alloc` allocates memory for the object, `init` actually creates it:

NSString *emptyString = [[NSString alloc] initWithString:@"I'm aliiiiive!"]

// Other handy ways to uses class methods ('messages') to create objects:

NSString *fullName = [NSString stringWithFormat:@"%@ %@", firstName, lastName];
```


## Control Flow

```objective-c
// This part is a little weird:

BOOL thisIsTrue = YES;
BOOL thisIsFalse = NO;

if (condition) {

} else if (condition) {

} else {

}

// Some conditionals:

myInt < 3
myInt > 10
[myString isEqualToString:@"applesauce"]

// Switch statements:

switch (animal) {
  case @"dog" : {
    NSLog(@"woof!");
    break;
  }
  case @"cat":
  case @"tiger":
  case @"lion" : {
    NSLog(@"meow!");
    break;
  }
  case @"goblin": {
    NSLog(@"wharblarg!");
    break;
  }
}
```
