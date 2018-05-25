---
layout: post
title: "How to survive technology changes"
date: 2016-06-02
---
As part of the IT/Technology organization you've probably encountered some software terminology which you do not understand. This is normal. Technology evolves faster than we can digest it. However, in order to do our jobs effectively we need to keep our knowledge always fresh with the latest. How can we do that? How can we really thrive in a field where buzzwords like cloud and devOps are the norm? The answer is life long learning. Yes, when you decided any of these career tracks (Computer Science, Engineering, Information Systems, or any [STEM](https://en.wikipedia.org/wiki/Science,_technology,_engineering,_and_mathematics) related degree) you committed yourself to learning for the rest of your life. Sounds scary? It is. For as long as you work in a technology related field you will have to be on your toes learning the latest.

Now that I've made it sound so scary, I will share the secret to staying above water in our field. It's actually pretty simple: **Categorize**!

For every buzzword or new concept thrown your way you must either fit it in a category or create a new one for it. This way you can associate what it is with what you already know! A simple example we all know is: Integrated Development Envrionments (IDEs). We all love Eclipse and some of people use NetBeans. Could you swap if you were required to? Probably. You might have to find your way around it, but you definetly know that for every feature on Eclipse there is one exactly or similar in Netbeans. Why didn't you freakout about it? You knew what category they belonged to!

Perhaps the most important aspect for this technique to work are definitions and vocabulary. If you do not know the definition of a category in a theoretical and practical way you will fail at mapping words or concepts to it. This is obvious. So, before proceeding associate a word, concept or tool with a category please do your best to understand the categories themselves. It is to say, if you do not know what a Integrated Development Environment is, than you will not be able to associate Eclipse & NetBeans to it.

That being said, I will proceed to provide a list full of categories and some technologies that fall under each one. It is not an exhaustive list. But this will get your though the day here at IT.

I encourage the reader to find the differences between some of these categories as some might be very subtle. For example, a common misconception is to say that Amazon Web Services and Google App Engine are the same thing. No. They are listed under different categories for a reason. The main differentiator between the two is that PaaS provide a managed/maintained environment layer to which users can *push onto* their application and have it run with little to none configuration. Google App Engine and Heroku are examples of such providers. In contrast, IaaS generally provide a raw "bare metal" or "bare minimun" host machine for the user to configure and use. AWS can provide you with many [EC2](https://en.wikipedia.org/wiki/Amazon_Elastic_Compute_Cloud) instances (linux virtual machine), but its up to the user to configure, maintain and do what he/she wants with it.

Another common mistake is to fail to distinguish between a **framework** and a **library**. Even experienced developers might fail to tell you the difference. In layman terms, a framework calls the user's to code in order to achieve a result. That is to say, you as the user of a framework need to fill in the blanks required by the framework for the overall program to run. By contrast, a library is essentially many functions and objects packaged together that you can use in your program at your own discretion. See the categories section for examples.

Stay sane my friends, categorize!

--------------------------------------------------------------------------------------------------------------------------------
**Software Development Methodologies**: Agile, Waterfall

**Programming Language**: Java, Python, Groovy, JavaScript, C#

**Run-time platform**: JVM, .Net's CLR

**Platform as a Service (PaaS) Provider**: Heroku, Google App Engine, Cloud Foundry

**Infrastructure as a Service (IaaS) Provider**: Amazon Web Services, Digital Ocean

**Version Control System**: Git, Subversion, CVS

**IDE & Editors**: Netbeans, Eclipse, Intellij, Sublime Text, Atom

**Build Tools**: Ant, Maven. Gradle, SBT, GruntJS

**Continuous Integration Server (CI)**: Travis CI, Jenkins, Bamboo

**Library**: JQuery, ReactJS, com.google.gson.Gson, java.util.Math

**Frameworks**: AngularJS, Spring, Play

**Unit Testing Framework**: JUnit, Mockito, QUnit, Mocha

**UI Testing Framework**: Selenium

**Template Engine**: Jade, Freemarker, Mustache, Velocity

**Static File Server (a.k.a HTTP Server a.k.a Web server)**: Apache HTTP, NGINX

**Servlet Container + Web Server**: Tomcat, Jetty, Glasshfish, Weblogic

**Object Relational Mapper**: Sequelize, Hibernate, Mongoose

**Storing data**: Relational database (SQL), NoSQL database, In Memory Cache

**Relational Database**: MySQL, PostgreSQL, OracleDB, Informix, MariaDB

**NoSQL Database**: MongoDB, Cassandra

**Memory Cache**: Redis

**Data Transfer Formats**: JSON, XML

**Client-side program**: A program that communicates with a server-side program and requests (usally over the internet) resources from it.

**Server-side program**: A program that provides a client program with resources (data or files) usually over the internet.

**Server**: Used interchangegably between a physical hardware machine that hosts software across the internet, and a server-side program.

**WebService**: A server-side program that can comunicate with client software via some protocol: HTTP or SOAP

**Buzzwords**: DevOps, IoT, Cloud

**DevOps**: Generally people refer to DevOps as an organization's strategy to have the same people of program a software system perform the deployment, mantainance, monitoring, scaling, debugging, and re-deploying it themselves.

**IoT**: Generally refers to the trend of having everyday "dumb" devices such has stoves and refrigerators connect to the internet and be able to communicate with a serverside program.

**Cloud**: Widespread adjetive used to market any software that happens to be accessible over the internet. When applied to a software system in particular it generally means that the system runs independently of the number of underlying phyical server machines that host its software. Thus, its "cloud enabled".
