# Prefixbox Test

## Short questions

- What is a package? How do you define a package? We use packages to organize the the files of the application.
- What is a constructor? When is it executed? The constructor is responsible to "create" an object. It's executed when we instantiate an object.
- How do you implement inheritance in Java? With abstract classes and interfaces.
- How do you prevent someone to inherit from a class? 
- What is a final variable? Where you can assign value to final variables? 
- Specify the available access modifiers in Java and briefly explain them
- Briefly explain the mechanism of exception handling When we want to do something, and we expect that it may be go wrong, we should tell the program what to do when that error happens.
- What is the difference between an abstract class and an interface?
- What is the difference between Comparator and Comparable?
- How Iterable and Iterator interface works? What methods need to exist in a
class that implements them? What is their relation to for loops?

## Programming tasks

You can write your solutions in any language, you can even write pseudo code or
using only your own words.
The point is not to make a perfectly running application, the point is the way
you think!
Don't worry if you miss a semicolon or some parantheses.
You might use the Java stream API for your solutions but none of the exercises
require them

### Palindrom

Write a function which decides whether a text is palindrom(It's the same whether
you read it forwards or backwards). E.g.: abba, rotator, stats.
You might assume that the input string is not null, the length is greater than
1 and less than one million. **Strive for the low memory complexity!**

Example:

```java
public boolean isPalindrom(String input) {
    StringBuilder back = new StringBuilder();
    boolean palidron =false;
    for (int i = (input.lenght()-1); i > -1; i--) {
        back.append(input.get(i));
    }
    if (input.equals(back.toString()) == 0){
        palidron = true;
    }
    return palidron;
}

isPalindrom("alma"); //false
isPalindrom("görög"); //true
```

### Find The Duplicate

You have an array that contains strings. Every item in the array is
unique except one which is present in the array exactly twice.
Write a function which finds the string that is present twice in the array.
You might assume that the input array is not null, the length is greater
or equal to 2 and less than one million. **Strive for the low time complexity!**

Example:

```java
public String findTheDuplicate(String[] input) {
    String str = "";
        for (int i = 0; i < input.length() ; i++) {
            for (int i = 0; i < input.length() ; i++) {
                if (input.get(i) == input.get(j) {
                    str = input.get(i);
                    break;
                }
            }
        }
        return str;
}

String[] fruitBasket = new String[] { "apple", "banana", "coconut", "durian",
"banana", "elderberry", "fig", "grapefruit" };
findTheDuplicate(fruitBasket); //should return banana
```

### Count The Words

You have a long string that has some meaning on a real language. For example a
whole novel in a single string.
Write a function that counts the occurence of each word inside the string and
writes them to the output in the following format: `word: number of occurences`
You might assume that the input is not null and not empty. The order of the
words on the ouput does not matter.
The solution might be case insensitive, you don't have to differentiate
bwetween capital and non-capital letters.
The punctuation marks and line endings are not part of the words!

Example:

```java
public void countTheWords(String crazyLongString) {

}

String boci = "Boci, boci tarka, se füle, se farka.";
countTheWords(boci);

//Output:
//boci:2
//tarka:1
//se:2
//füle:1
//farka:1
```

### What Is The Output

What is the output of the following Java application? Explain your solution!

```java
package com.mycompany.myproject;

public class Person {
    public String firstName;
    public String lastName;

    public Person(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }  

    @Override
    public String toString() {return this.firstName + " " + this.lastName;}
}

public class Main {
    public static void main(String[] args) {
        int i = 0;
        String s = "apple";
        Person p = new Person("Jonh", "Doe");

        doSomething(i, s, p);

        System.out.println(i);
        System.out.println(s);
        System.out.println(p);
    }

    public static void doSomething(int i, String s, Person p)
    {
        i = 5;
        s += "banana";
        p.lastName = "Rambo";
    }
}

```

## SQL

- What is the PRIMARY KEY?
- What is the difference between CLUSTERED INDEX and NONCLUSTERED INDEX?
- There is a table called `Employees`. Let's assume that the columns exist
and they have the right data type.
What is going to happen if we execute the script and we destroy
the database connection during the execution? What are the possible problems
that might occure?

```sql
BEGIN TRANSACTION

UPDATE Employees
SET Salary = Salary * 1.1
WHERE
    Salary < 250000
    AND IsActiveEmployee = 1
```

## Web and HTTP

- Specify the existing HTTP request methods and describe their usage!
POST - it's usualy for creating data on the server, GET - it's used to request data from the server, UPDATE - for updating data on the server, DELETE - for deleting data from the server
- What are the groups of HTTP response status codes? Write an example for each group!
200-299 Everithing went fine.
300-399 Redirecting
400-499 Something was wrong with the request.
500-599 Server errors
