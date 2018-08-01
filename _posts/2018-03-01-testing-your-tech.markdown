---
layout: post
title:  "Why is testing software so important?"
date:   2018-03-01 19:29:58 +0100
categories: long software testing
---

Only 52% of people believe technology in the public sphere has been properly tested. This stat was revealed during CRITICAL Software’s recent ‘Test Your Tech’ campaign where a public opinion survey was conducted. It’s pretty astounding that half of us believe the tech we’re using has not been tested properly!

As a software engineer, I thought I’d share an inside look at the important role that testing plays in my field: the development of software. Stick with me and I’ll share what testing is, why it’s important and some of the potential consequences of neglecting this fundamental step.

---
<br>

What is software testing and why do we do it?
===

Due to the inherently complex nature of software, it’s incredibly easy for humans to make mistakes when designing and developing systems. Testing something you’ve made might seem like an obvious thing to do, but when it comes to software, unfortunately this is sometimes taken for granted.

For those out there who aren’t familiar with software development, here’s a quick overview. Software testing is a very broad term, but for our purposes today, it refers to the practice of ensuring software conforms to an expected standard. The ‘piece’ of software you are testing and the standard to which it is measured both depend on the type and level of testing in question.

Different methods fall under different categories, some of which are only relevant at certain times during the software development lifecycle. 

**Static** testing consists of utilising automated testing tools to verify that source code, requirements and design documents adhere to certain standards. This is usually carried out by software developers or autonomous tools as part of the build process, falling under the heading of ‘verification testing’. This kind of testing is undertaken when the software itself is not executed (not actually running), hence the term ‘static’. An example of this is ‘syntax linters’: an automated tool that can check the code conforms to project conventions, such as class/method naming, tabs and spaces for indentation and so on.

With **dynamic testing**, source code is executed to validate functional behaviour (aka check it does what it’s meant to do) and analyse system performance with the intent of finding defects and areas needing improvement. Dynamic testing is performed at all levels, covering a broad scope and falling under the heading of validation.

Included in dynamic testing are other methods, such as black-box/white-box testing, however, I don’t want to concentrate on the different methods of testing too much, this is more of a broad introduction.

Static and dynamic are two examples of overall testing types, but included within these are many different levels of testing that can be carried out during a software build. Here are just a few to highlight the different levels:

Unit testing is a method in which small, individual units of source code are tested using a set of control data to confirm if they function as expected. These units are taken out of the context of their surrounding environment, and still expected to do their job. Imagine a function that calculates an employee’s monthly earnings. During testing, if an incorrect value comes back, the engineer might suspect a recent code change (one of the units of code) has broken something. These small bits of code usually come in the form of functions/procedures, classes or interfaces, and should work independently of the surrounding application.

Integration testing refers to the phase in which individual software modules are combined and tested as a group to ensure inter-compatibility: essentially ensuring everything gets along nicely. Completion of this phase enables the testing to evolve to system and user acceptance testing.

Acceptance testing comes once most other forms of testing have been completed and system testing has proven to be successful. Acceptance testing is conducted to determine if the initial software requirements have been met. This phase can be undertaken by the customer (or whomever has commissioned the software), allowing them to verify the system behaves as expected.

Another option for acceptance testing is to have software tested independently by a third party. This is common practice in safety-critical domains such as space and aerospace, though less common in other just-as-critical areas. According to the Test Your Tech survey results, it’s clearly important to the consumer as well: 90% of people said that independent testing by experts is important in assuring them that tech is reliable.

In fear of rambling on too much about the different types of testing, I’ll leave it there for now. I have by no means covered all methods, levels or areas of software testing, as I just wanted to give a brief overview. Testing is (or should be!) integral in every part of the software development lifecycle and should be considered just as important as the actual development work itself.

---
<br>

What are the consequences of not testing?
=======

Put simply, not testing software properly leads to serious problems. Not only will it cost more time and money to retrospectively fix uncaught defects, but, depending on the domain, it could have catastrophic financial, social or safety implications.

For our first example of ‘what testing might have prevented’, let’s talk space. In 1998, due to a difference in measurement units used by engineers working on the project, the Mars Climate Orbiter entered the Martian atmosphere at the wrong angle. No big deal, right? Well, a small mix-up between metric and imperial systems caused the $327.6 million spacecraft to disintegrate in the Red Planet’s upper atmosphere upon arrival. It’s a bad day when you’re left with a big bill and many wasted hours of hard work.

Let’s shift to finance. Online banking, apps and the like are big business and many people rely on them to make a huge number of transactions, 24/7, 365 days a year. When the system fails, it can spell disaster. A software glitch hit stock market firm Knight Capital right in the wallet recently when their trading platform started buying stock at market prices and selling at bid prices. This error caused losses of around 15% per share, made forty times a second for three hours before it was caught. Added up, it cost the company around $440 million.

An extreme, even more worrisome example is the 1983 Soviet nuclear early-warning system incident. During the height of the Cold War, the Soviet Air Defence Forces were using a satellite early-warning system to alert them of any nuclear strike launched by the USA, hoping it would give them enough time to retaliate. On 26th September, Stanislav Petrov was manning the station when the alert system went off, claiming five ICBMs had been launched and were on their way to the Soviet Union.

Petrov’s orders were to pass this up along the chain of command which would have ultimately resulted in a Soviet counter-attack, starting an all-out nuclear war, however, this didn’t happen. Petrov had been using the system for a while and knew there were problems with the software. He couldn’t believe the US would start a nuclear war with just five missiles. He and the other operators had been told if it were to happen it would likely be on a much bigger scale. Luckily for all of us, his hunch turned out to be correct: it was a false alarm.

It was later discovered the system had interpreted the sun’s reflection off of high-altitude clouds as five separate missiles hurtling their way towards the USSR. Introduced in the 1970s, the system had long been known to have problems. According to statements later made by Petrov, it had been rushed into service and felt ‘raw’. This is a good example of why reliable and exhaustive testing matters so much: the whole component responsible for identifying false positives (such as the sun’s reflection) needed rewriting as not every edge case was accounted for.

Admittedly, a lot has changed in software development and testing since then. However, severe, big-impact problems still arise today which can be attributed to lack of testing.

Earlier this year, the inhabitants of Hawaii were sent into a panic as they received a push notification on their smart phones warning them of an imminent missile strike. The message, “BALLISTIC MISSILE THREAT INBOUND TO HAWAII. SEEK IMMEDIATE SHELTER. THIS IS NOT A DRILL”, was broadcast to around 1.4 million people.

We now know this was a false alarm, but what went wrong this time? According to Vern Miyagi, the administrator of Hawaii’s Emergency Management Agency an employee pushed the wrong button on a shift change. Protocol says employees must test the system is working as expected when changing shifts and this time the wrong button was pressed. In this case, the system technically worked as expected but the user interaction clearly needed some alteration. Functionally, there was no problem, but why did the system allow the employee to press the wrong button in the first place, causing bedlam throughout the Pacific State?

This could be seen as failure to conduct rigorous user testing before the system went live, or even an oversight in the static testing phase (if there was one). There must have been design documents detailing the two buttons. Shouldn’t this eventuality have been picked up during the static review of design documentation?  When testing user interactions with software, it is always said ‘test for every eventuality’. No matter how stupid it might be, you should always test assuming the user will do it.

These cases highlight the need for extensive testing at different levels and at different parts of the development lifecycle. Fortunately, the above examples did not result in lives lost, but sadly there are plenty of examples where things have gone badly wrong.

Probably one of the worst, but lesser-known examples relates to healthcare. Therac-25 was a radiation therapy machine that used x-ray and electron beams to kill tumours in cancer patients. In its short service life, this machine was responsible for killing four people and leaving two with lifelong injuries. Between June 1985 and January 1987, six patients were exposed to massive doses of radiation, sometimes 100 times more than prescribed. The crux of the problem was discovered by a staff physicist at a clinic in Tyler, Texas. He noticed that most of the incidents happened when a certain technician was on duty. It turned out that this operator was very familiar with the system, so would go through the process of selecting the treatments more quickly than her colleagues would.

By selecting the ‘x-ray’ function, then selecting ‘electron mode’ within 8 seconds, this fast-fingered technician was unknowingly causing the machine to enter an ‘unknown’ state. Put simply, the machine wasn’t designed to cope with different users’ operational speeds. This hadn’t been found before as testing had previously been carried out in a meticulous manner, meaning the user’s timing hadn’t been factored in. This machine had a number of flaws – such as the entire system design being incorrect, little to no timing analysis or unit testing, plus over-use of old software by an inexperienced programmer –  and stands as a sad example of negligence when it comes to testing.

Like most things, testing software has a cost in terms of time and money. For companies who don’t mind taking big risks, saving on these two valuable resources – both of which are inevitably ‘tight’ in any software project – could be seen as a worthwhile gamble. Part of the problem is that testing doesn’t necessarily deliver instant gratification. With development of new features, it's easy to see the results of the time and effort put in by developers: after a week you might be able to use a new form, or a new API will be available. There’s a tangible return for your money. With testing, this isn’t necessarily the case, but that doesn’t make it any less important.

It’s also true that testing requires a high level of expertise to do well. That’s probably why 95% of people say that when testing is done correctly, they feel confident they can rely on the tech they use.

The fact that testing is important is undeniable. The key is finding the right balance between risk and speed of development. The secret is to invest in high-quality testing right off the bat. Do it right first time and you don’t have to fix things later. Risk-takers might spend less early on, but ultimately, hidden flaws will cost a great deal in the long run, potentially taking more than just money.

Sometimes, all it takes is one missed typo to cause unthinkable consequences; from where I’m standing, proper testing is a small price to pay for tech that’s safe and sound.