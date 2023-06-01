# SmartCalc v3.0

> При старте работы над проектом просим вас постараться хронометрировать время работы над проектом.
> По завершении работы над проектом просим вас ответить на два вопроса [в этом опросе](https://forms.gle/GmDeKHa7bJN3fKAo8)

Implementation of SmartCalc v2.0.

The russian version of the task can be found in the repository.

## Contents

1. [Chapter I](#chapter-i) \
   1.1. [Introduction](#introduction)
2. [Chapter II](#chapter-ii) \
   2.1. [Information](#information)
3. [Chapter III](#chapter-iii) \
   3.1. [Part 1](#part-1-implementation-of-smartcalc-v20) \
   3.2. [Part 2](#part-2-bonus-credit-calculator) \
   3.3. [Part 3](#part-3-bonus-deposit-calculator)


## Chapter I

![smartcalcv3.0](smartcalc3.0_subject.png)

Chuck was running late, so he was in a hurry and couldn't sit still. Only the occasional stern look from the cab driver in the rearview mirror humbled him each time.

*- “Could you go any faster, I'm in a hurry,“* Chuck said harshly.

*- “Young man, I'm going the maximum speed allowed here, and I'm not going to break the rules for no reason. Calm down, we're almost there. And you could have left the house earlier...“* Chuck skipped further lectures and switched back to his phone. Time was running out. \

Buildings, palm trees, and people with dogs flew by the window. California is usually hot this time of year, so many people were sunbathing on their lawns. But Chuck wasn't really interested in that; he glanced from time to time at the map and at the time on his phone, checking how much longer he had left to go. He didn't fly halfway across the country for sun, beach, and relaxation. His mission was to find answers to his questions, and some anonymous person had kindly agreed to provide them. Yes, the text message from him wasn't very informative: just an address, a time, and promises of answers, but Chuck felt that he was sure to get help here. He got as close to the truth as he could. The cab pulled up to a small square with three people standing there. Chuck's mind was spinning, "I hope I'm not too late, I hope I'm not too late. He shot out of the cab, dropping his bag on the ground. The driver shouted something to him, but at that moment another familiar voice caught Chuck's attention:

*- “Chuck?! And you're here, too?“* Eve said slightly surprised.

*- “Oh, hi, Eve! What a far-off place to meet. How small the world is! And what do you mean, here? Did you get that weird text message, too?“* Chuck seemed to be out of breath, constantly looking around for either potential dangers or something interesting. *“I hope I'm not too late.“*

*- “We all got this text here,“* John interjected. *“I'm John, this is Thomas.“*

*- “I'm Chuck. Never thought it would be such a mysterious meeting in the middle of nowhere,“* Chuck said in response, looking around.

*- “It's not exactly nothing here, though,“* Thomas replied. *“Until a few months ago there was a nice lively jazz club here, owned by the father of a good friend of mine. Who, as it turned out, was an acquaintance of John's. He was a colleague of yours, wasn't he? Except neither John nor I had heard from him in over three months. And the club... Well, you can see how it's turned out,“* Thomas looked sadly at the building.

*- “Where did you work?“* Eve asked John.

*- “A local division of SIS, John muttered back. Administration of network applications and configuration of computer hardware.“*

*- “Chuck and I are also from SIS. Different departments and the Eastern division, but still,“* Eve said thoughtfully. *“Where do you work, Thomas?"*

*- “Advanced Solutions Inc. Daughter of SIS, transferred there quite recently. I had to take a vacation to get here, but I was seriously worried about Seb, and apparently not for nothing. Turns out we're all related to SIS in one way or another.“*

*- “And not only to it, right, Eve? Chuck said. I've got some documents here that I think you might find interesting, so where are they...“* Who knows where this conversation would have gone if not for the simultaneous beeping and vibrating of smartphones in everyone's pockets that occurred at that moment.

>Greetings to all! I'm very happy that you were interested and were able to get to your destination right in time. You are gathered here for a reason and will indeed get all the answers. But only after a little test. There is one task that they liked to test me on. But now it's time to switch places a little bit. Prove that you are ready and able to handle the tasks ahead, and then I will answer all of your questions. A test with details is already waiting for you in your personal repositories. Please begin immediately. Thank you.
Chuck couldn't keep a slight smile off his face and whispered just one word:

*- “The Terminator...“*


## Introduction

In this project you’ll need to implement an extended version of the standard calculator in C++ in the object-oriented programming paradigm, implementing the same functions as the previously developed application in SmartCalc v1.0 project. In addition to basic arithmetic operations such as add/subtract and multiply/divide, you need to supplement the calculator with the ability to calculate arithmetic expressions by following the order, as well as some mathematical functions (sine, cosine, logarithm, etc.). Besides calculating expressions, it should also support the use of the _x_ variable and the graphing of the corresponding function. As for other improvements you can consider a credit and deposit calculator.


## Chapter II

## Information

Note that you should use *Dijkstra's algorithm* to translate expressions into *reverse Polish notation* to implement the calculator. You can find all the necessary information in the SmartCalc v1.0 project description to refresh your knowledge.

### MVC pattern

The MVP pattern has two components in common with MVC: the model and the view. But it replaces the controller with a presenter.

The presenter implements the interaction between the model and the view. When the view notifies the presenter that the user has done something (e.g., pressed a button), the presenter decides to update the model and synchronizes all changes between the model and the view. However, the presenter does not interact with the view directly. Instead, it uses an interface to communicate. This allows all components of the application to be tested individually afterwards.

### MVVM pattern

MVVM is a more modern update of MVC. The main purpose of MVVM is to provide a clear separation between the presentation and model layers. MVVM supports two-way data binding between View and ViewModel components.

The view acts as a subscriber to property value change events provided by the view model (ViewModel). If a property has changed in the view model, it notifies all subscribers about it, and the view, in turn, requests the updated property value from the view model. If the user interacts with an interface element, the view calls the corresponding command provided by the view model.

A view model is on the one hand an abstraction of a view, and on the other hand a wrapper of data from the model to be bound. In other words, it contains the model transformed to the view, as well as the commands the view can use to affect the model.

![](misc/images/MVC-Process.png)


## Chapter III

## Part 1. Implementation of SmartCalc v2.0

You need to implement the SmartCalc v2.0:

- The program must be developed in C++ language of C++17 standard
- The program code must be located in the src folder
- When writing code it is necessary to follow the Google style
- Classes must be implemented within the `s21` namespace
- Prepare full coverage of expression calculation modules with unit-tests using the GTest library
- The program must be built with Makefile which contains standard set of targets for GNU-programs: all, install, uninstall, clean, dvi, dist, tests. Installation directory could be arbitrary
- GUI implementation, based on any GUI library with API for C++17: Qt, SFML, GTK+, Nanogui, Nngui, etc.
- The program must be implemented using the MVC pattern, and also:
   - there should be no business logic code in the view code
   - there should be no interface code in the controller and the model
   - controllers must be thin
- Both integers and real numbers with a dot can be input into the program. You should provide the input of numbers in exponential notation
- The calculation must be done after you complete entering the calculating expression and press the `=` symbol.
- Calculating arbitrary bracketed arithmetic expressions in infix notation
- Calculate arbitrary bracketed arithmetic expressions in infix notation with substitution of the value of the variable _x_ as a number
- Plotting a graph of a function given by an expression in infix notation with the variable _x_ (with coordinate axes, mark of the used scale and an adaptive grid)
   - It is not necessary to provide the user with the ability to change the scale
- Domain and codomain of a function are limited to at least numbers from -1000000 to 1000000
   - To plot a graph of a function it is necessary to additionally specify the displayed domain and codomain
- Verifiable accuracy of the fractional part is at least to 7 decimal places
- Users must be able to enter up to 255 characters
- Bracketed arithmetic expressions in infix notation must support the following arithmetic operations and mathematical functions:
   - **Arithmetic operators**:
     | Operator name | Infix notation <br /> (Classic) | Prefix notation <br /> (Polish notation) |  Postfix notation <br /> (Reverse Polish notation) |
      | --------- | ------ | ------ | ------ |
      | Brackets | (a + b) | (+ a b) | a b + |
      | Addition | a + b | + a b | a b + |
      | Subtraction | a - b | - a b | a b - |
      | Multiplication | a * b | * a b | a b * |
      | Division | a / b | / a b | a b \ |
      | Power | a ^ b | ^ a b | a b ^ |
      | Modulus | a mod b | mod a b | a b mod |
      | Unary plus | +a | +a | a+ |
      | Unary minus | -a | -a | a- |
      >Note that the multiplication operator contains the obligatory sign `*`. Processing an expression with the omitted `*` sign is optional and is left to the developer's decision
   - **Functions**:
      | Function description | Function |
      | ------ | ------ |
      | Computes cosine | cos(x) |
      | Computes sine | sin(x) |
      | Computes tangent | tan(x) |
      | Computes arc cosine | acos(x) |
      | Computes arc sine | asin(x) |
      | Computes arc tangent | atan(x) |
      | Computes square root | sqrt(x) |
      | Computes natural logarithm | ln(x) |
      | Computes common logarithm | log(x) |

## Part 2. Bonus. Credit calculator

Provide a special mode "credit calculator" (you can take banki.ru and calcus.ru as an example):
- Input: total credit amount, term, interest rate, type (annuity, differentiated)
- Output: monthly payment, overpayment on credit, total payment

## Part 3. Bonus. Deposit calculator

Provide a special mode "deposit profitability calculator" (you can take banki.ru and calcus.ru as an example):
- Input: deposit amount, deposit term, interest rate, tax rate, periodicity of payments, capitalization of interest, replenishments list, partial withdrawals list
- Output: accrued interest, tax amount, deposit amount by the end of the term
