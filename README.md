## Introduction
Toms is an absolute system for functional service. In this system, users do not need to
care about any configuration of infrastructure and only need focus on user business logic.
User can separate business logic from business data to make the business more general.
In the future, user can make their business to be productions on the toms business market.

Toms is a functional service infrastructure. There are five parts in it as following:

#### Language runtime.
There are three(will be more in the future) language runtimes now: JavaScript, Java and Golang.
Runtime executes, schedules, statistics and fragments user functions. User can invoke other functions
over language type. All the runtimes can be automatically divided at right time.

##### jsr
'jsr' is a condensed name of JavaScript runtime. In this runtime, we use v8 to make it.
It is different from NodeJS. NodeJS is a standalone JavaScript language. Jsr is a distribudted
runtime of JavaScript. In the jsr, we can fragment user function code and execute them on the
distribudted runtimes. And also users do not need to care about where the code was executed.
Jsr can hot-reload the user functions in a very short time.

It is mainly developed by C++ and use the bazel tool to build it. In this runtime, we use gRPC
to exchange message between services. For the JavaScript performance, we choose the v8 engine
for JavaScript runtime.

For more detail, go to [jsr](https://github.com/toms-less/jsr).

##### jar
'jar' is a condensed name of Java runtime. In this runtime, we use self-defined classloader
to hot-reload use functions. In the traditional Java application developing, user should package
all the code and deploy them to the target machines. This progress often take a long time,
and sometimes we only change one class of the application. In the jsr, we only reload the changed
class files and run them fastly.

For more detail, go to [jar](https://github.com/toms-less/jar).

##### gor
'gor' is a condensed name of Golang runtime. In this runtime, we use plugin feature of Golang to
load user functional logic.

For more detail, go to [gor](https://github.com/toms-less/gor).


#### Resource manager.
To make the goal that user need't care about configuration of infrastructure, we will build a schedule system.
In this system, we collect machine data by agent named 'applet' and dynamically schedule with lxc.

#### System function.
To make the goal of separating business logic from business data, we abstract the data with system function.
System function can be extended and developed ecologically.

#### Business configuration.
In the user business, there are a lot of configuration. But there are too many kinds of types and formats.
In the toms, we standardize configuration and make them can be separated from business logic.

#### User command line and dashboard.
To make user using toms conveniently, we offer command line and dashboard.

## Community
Now toms is developing and has not be released, there are a lot of things to do. If you are interested in toms,
please contact us by email [jingbing.csu@gmail.com](jingbing.csu@gmail.com). We hope you can join us to make it.