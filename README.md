# Programming as Conversation 2: The Case Statement

## Learning Goals

* Translate a `case` statement from `if...elsif...else...end`
* Write a `case` statement

## Introduction

A case statement is a powerful tool to test for performing _selection_, just
like `if...elsif...elsif...end`. They are used to test multiple conditions
against one value. They're just a nicer way to format a complex `if` with
multiple `elsif`s.

Not all languages have them! Python doesn't! It thinks that `if` and `else if`
are sufficient. But Ruby has them, so we'll learn to use them.

## Translate a `case` statement from `if...elsif...else...end`

Let's say we have a program that sets a `name` variable equal to a person's
name. Our program needs to execute certain code depending on what that person's
name is. 

```ruby
name = "Alice"

if name == "Alice"
  puts "Hello, Alice!"
elsif name == "The White Rabbit"
  puts "Don't be late, White Rabbit"
elsif name == "The Mad Hatter"
  puts "Welcome to the tea party, Mad Hatter"
elsif name == "The Queen of Hearts"
  puts "Please don't chop off my head!"
else
  puts "Whoooo are you?"
end 
```

As we can see, there's a lot of repetition here.

* We always test name
* We always compare with `==`
* We have the "none match" option stored in the `else` block

This is a pretty common _selection_ need. It's so standard, that the `case`
statement was created to cut down the typing, but do the same thing. Here it
is, but translated:

```ruby
case name 

  when "Alice" # translated: when name == "Alice"
    puts "Hello, Alice!"
  when "The White Rabbit"
    puts "Don't be late, White Rabbit"
  when "The Mad Hatter"
    puts "Welcome to the tea party, Mad Hatter"
  when "The Queen of Hearts"
    puts "Please don't chop off my head!"
  else 
    puts "Whoooo are you?"
end
```

Nice!

Now that we understand *when* to use a `case` statement in place of a series of
`if` and `elsif` statements, let's look at *how* to build a `case` statement
from scratch.

#### Step 1: Create a Value

A case statement starts with the `case` keyword followed by a value to test.

```ruby
case greeting
# ...
end
```

#### Step 2: Create the Conditions

Next, the `when` keyword is followed by a condition.

```ruby
case greeting
  when "unfriendly_greeting"
    #...
  when "friendly_greeting"
    #...
end
```

#### Step 3: Add the Code

The functionality that we wish to happen when the condition is met is placed on an indented line directly under the `when` line. Let's define the behavior:

```ruby
greeting = "friendly_greeting"

case greeting
  when "unfriendly_greeting"
    puts "What do you want!?"
  when "friendly_greeting"
    puts "Hi! How are you?"
end
```

## Example

In this example, we set the `current_weather` to `"raining"`. Next, we use
`when` statements to describe a list of possible matches. Since
`current_weather == "raining"` we'd expect this code to put `"grab an
umbrella"`.

```ruby
current_weather = "raining"

case current_weather
  when "sunny"
    puts "grab some sunscreen!"
  when "raining"
    puts "grab an umbrella"
  when "snowing"
    puts "bundle up"
end
```

## Conclusion

Now you have one more way of communicating _selection_ to Ruby, the `case`
statement. For simple values, use ternary. For an `if` with an `else` and maybe
an `elsif` use an `if`. For multiple cases, use a `case` statement.
