---
layout: post
title: "Self-documenting code in perspective"
date: 2018-05-24
---

For while, I've been meaning to write down my observations on documentation and its impact on a codebase. Speaking strictly anecdotal, throughout my career I've stumbled across a contrarian reality about documentation. Almost no developer wants or will document their code, citing their code is well document. *Just read the source* - They would answer when asked: Are there any docs on this? Moreover, in other instances or teams adding comment blocks to your code would be frowned upon.

By contrast, in school, professors teach and praise well documented code. But what exactly is well document code? Does adding long winded descriptions in block comments on your classes and methods suffice? Or, Is it creating a wiki page for that library you just wrote?

To me, documentation used to mean all of the above. It meant documenting classes in description blocks, params of untyped languages, and of course writing wikis. However, after some time in the industry, I've grasped what other developers meant by *self-documenting code*.

Self-documenting code is really a product of the realities of software engineering. In the real world, teams sprint towards coding business requirements. They do so often and iteratively as requirements and needs change with time. For said reasons, its logical to conclude that you, as a a developer, should not invest time writing long winded comment blocks or large wikis on a feature or section of code that will change rapidly tomorrow. Seasoned engineers know this and, to safe guard their time, they make sure they write readable source code.

This could be one of the reasons **python** is so [loved](https://insights.stackoverflow.com/survey/2018/) among developers. Python provides an english-like syntax that lends itself well to reading.

Since developers will spend more time [reading code than writing it](https://www.goodreads.com/quotes/835238-indeed-the-ratio-of-time-spent-reading-versus-writing-is). It seems only logical then that the documentation portion of the task be left to reading the source code and not opening up a different file. That is to say, the source code should be most, if not, all you need to understand what the code is doing. This is an art form in itself. Why? Because writing self-documenting code involves the one thing developers are notoriously bad at: [naming things](http://hilton.org.uk/blog/why-naming-things-is-hard). Given than naming things is hard, writing self-documenting code can be as well.

Below I'll illustrate visually the impact of self-documenting code in **Java**. Before, I get asked, I chose **Java** because its a strong & statically typed wide spread mainstream language. Note, that if self-documenting code is is important for statically typed languages like **Java**, its even more important on dynamically typed languages. Specifically, because these types of languages (i.e. **JavaScript**, **Python**) usually do not expose their type system to the programmer which provides useful information about your program. Thus, putting even more pressure, in my opinion, to name things clearly and structure your code correctly.

Compare the following snippets of code and decide which one would you rather encounter when reading code.

**Not Self-documenting:**
~~~ java
...
class Person {
  int age;
  String name;
}

/**
 * Provides functionalities for manipulating collections of people
 */
final class Utils {
  static final int AGE = 18;
  /**
  * Retrieves the names of people who are adults.
  * @param list List of people of all ages
  * @return A list of adult names
  */
  static List<Person> filterAdults(List<Person> list) {

   List<Person> names = new ArrayList<>();
   for (Person p : list) {
     if (p.age >= AGE) { // Check if age is/over 18
      names.add(p);
     }
   }
   // return adults found
   return names;
  }
}
~~~
The above in plain english would read:
*"I have a Utils class which has a AGE variable set to eighteen. Also, a static function which filters adults from a list of persons. I declare a variable named names. I iterate over the list of person's named list and call it p. If p's age is greater than or equal to variable AGE, then I add it to the names list. Return names"*

Notice how the code does not flow like an english paragraph largely because of poor naming choices. Additionally, notice how the code contains inline comments to clarify pieces of code that, given a proper name or using a different code structure, would've been evident.

**Self-documenting:**
``` java
...
class Person {
  static final int ADULT_AGE = 18;
  int age;
  String name;

  boolean isAdult() {
    return age >= ADULT_AGE ? true : false;
  }
}

final class PeopleUtils {
  static List<Person> filterAdults(List<Person> people) {

   List<Person> adults = new ArrayList<>();
   for (Person person : people) {
     if (person.isAdult()) {
       adults.add(person);
     }
   }

   return adults;
  }
}
```
Instead, the example above reads very much like english.

In plain english this code would read:
*"I have a PeopleUtils class that contains a static function which filters people if they are adults."*

`filterAdults` reads as:
*"I have a function that takes a list of people. I create an empty adults list. I iterate over each person, if the person is an adult I add it to adults. Return adults."*

As you can see from the above the subtle naming changes make a different in how one goes about reading the code.

The fact that I moved the check of wether a person `isAdult` to the `Person` class, not only makes for a good separation of concern, but also allows for readable code since method names provide a description as to what the code is doing. Consider also the benefits of working with an ever changing large code base and what the information the type system can provide you with. Would you rather have the type system tell you that there is something wrong in `isAdult method`? or in `line 20 if statement xyz etc.`?
Also, pay close attention to variable names. When reading the code I did not have to pause and say that each person of the list is called `p`, because its named `person` so its evident. This was not possible in the previous example because I chose to name the variable `p` and therefore had to account for that when reading, as `p` is not very descriptive. Lastly, notice that because good variable and class names were used I did not need comments of any kind to clarify the intent of the code.

Of course using **Java 8 and greater** features I could've ended up with even more concise code. However, I wanted to illustrate my point with an apples to apples comparison.

**Even more concise & self-documenting**
```java
...
class Person {
  static final int ADULT_AGE = 18;
  int age;
  String name;

  boolean isAdult() {
    return age >= ADULT_AGE ? true : false;
  }
}

final class PeopleUtils {
  public List<Person> filterAdults(List<Person> people) {
    return people
      .toStream()
      .filter(person -> person.isAdult())
      .collect(Collectors.toList());
  }
}
```

From previous comparisons, we can derive how to write self-documenting code.
  1. Use descriptive class names such to avoid having to comment on of the class to understand its purpose
  2. Use descriptive and evident local and instance variable names. Try not to use short and cryptic names, but also avoid verbose names.
  3. Use functions / methods names as an opportunity to describe clearly the intent of the block of code in it. This will pay off dividends when using said function later on, as it will read as english instead of math or logic.
  4. Organize and structure in way that separates concerns into logical code blocks.
  5. Follow code formatting conventions for your respective programming language.

Now, as a English as a Second Language (ESL) speaker myself, writing readable source code can be a two step approach as one thinks in a different language and translates words. Although, I mostly think in English now a days, when writing / reading code, speaking can sometimes still take the virtual machine approach xD. Nevertheless, the more you practice and pay attention to phenomenon that is naming things in english, the better you will get. English is the [official computing language](https://en.wikipedia.org/wiki/English_in_computing) and therefore is critical you learn the basics such that it translates to your code. Specially, if you intend to work in the U.S. labor market.

In summary, writing self-documenting code frees you, as a the author of code, from requiring excessive documentation blocks in your files, if any at all. That is not to say that comments should never be used. However, self-documenting code can save you time energy when maintaining code as it would read closer to English. Further, it does not mean you have to away with wikis. But, they can be left for more high level functionality aspects of a system. I've outlined steps that will steer other developers into hopefully writing more readable source code.
