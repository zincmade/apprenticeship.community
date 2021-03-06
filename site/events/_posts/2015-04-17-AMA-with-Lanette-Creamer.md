---
title: Ask-Me-Anything with Lanette Creamer
start-time: 2015-04-21T18:00:00-07:00
end-time: 2015-04-21T19:00:00-07:00
layout: event
---
Lanette Creamer shared her extensive passion and experience with software testing during her AMA with the Apprenticeship Community.

{% include bio-lanette-creamer.md %}

The full AMA with Creamer follows, edited for content, clarity and style.

###[kmanion](https://twitter.com/kmanion): I don’t actually understand what you do. How would you define software testing?###

Yes! I do a ton of [agile testing](http://en.wikipedia.org/wiki/Agile_testing) currently. This can be something as simple as verifying a replaced word in one dialog box, and as complex as identifying a missing requirement at the very last rendered page as a result of something far upstream in an end to end test. I’ve got a few examples from today that might help. First, I learned that if you pasted in unsupported text styling from outside our application, it appears nicely on screen, but at output time, you get a mess of untranslated HTML tags at the very end, making the content unreadable. To best serve the team, I need to figure out why that happens, where it happens, and convince others that it would be better to strip out everything we don’t support up front rather than fight a losing battle against “every possible element and type of styling on the web.”

Secondly, I do some very simple tests. One example is sorting. Did the list toggle both ways, contain all of the same content but in a different order? Yes or No? Those are more the automated checks that I might script validation for.

I’d estimate 80% of the testing I do is tool assisted. Mostly I use software to help me get further information about results, understand why and how things are failing, and demonstrate the information better to others. The communication is the most difficult part of my work. I’m used to the technical challenges.

###[mattpolito](https://twitter.com/mattpolito): I was going to ask if you were automating the tests but since you answered that … How are you automating that kind of work?###

There are two main ways. So far, I’m using [Python](https://www.python.org/) to seed our database with content that I need, to perform loops, and to do some comparison and kick off other tools. One example was to seed data to test lazy loading. I’m using [Paw](https://luckymarmot.com/paw) to test the restful APIs with [JSON](http://json.org/) objects across environments. We do have some [Selenium](http://www.seleniumhq.org/) tests, but for some reason they picked [Java](https://www.java.com/) (which I hate). Most of them don’t validate due to a serious lack of consistency in naming due to where we are in the project (Not released to anyone yet). I think that is a common situation with UI-driven automation, but hopefully more Selenium soon. For now, more Paw and Python.

###[aurynn](https://twitter.com/aurynn): What’s been the biggest resistance you’ve seen to adding more testing, automated and not, and how have you overcome that resistance?###

Wow. Let me just say the biggest issues are political and not technical. At times, I’ve overcome resistance by sending my ideas through other people, and luckily I have a few allies. 

I am used to working at all technology companies for the past 15 years. When you join the corporate world it can be shocking to adapt to the political realities sometimes. Our best SDET (Software Design Engineer in Test) made a ton of automation four months ago and no one cared. One of the developers automated one tiny test without validation, but since the directors liked it, endless praise resulted. Marketing is very important. Was that at all helpful? I do think that more automation will be possible now that one thing is seen as important, but getting to that point was difficult.

It has been said repeatedly “Testing will never be an impediment to development.” I think to that value, we’ve adhered. I believe it is a risky strategy, but it isn’t my call. I’d prefer it if quality *were* an impediment to proceeding, at least where our customers are concerned, but I think working with devs to quickly fix only severe issues could find a good balance.

My favorite thing to do with bugs is to just quickly validate in person. I’ve done 3-15 bug fixes per hour using pairing in this way.

###[kmanion](https://twitter.com/kmanion): You mentioned a difference between working at "all technology companies" and joining “the corporate world”. Could you elaborate a bit on that?###

When I’ve worked at companies like Adobe, Silicon Publishing, or other places where software delivery is the primary product, it seems like there is more basis in research and reason. I’ve encountered more politics, old fashioned thinking, command/control legacy, and difficulty doing what helps most with software delivery the few times I’ve worked in IT projects for larger companies that primarily sell other products. This was also true at a coffee company in Seattle, when I worked on an IT project.

###[kmanion](https://twitter.com/kmanion): I wanted to ask about the difference between working for large and small organizations, but it sounds like you've seen more of a difference between "software" and "not-software" companies.###

Yes! There is a huge difference in size as well. When I worked at Adobe there was much more specialization across areas and products. When I worked on “The Creative Suite” it was more cat herding to get the needed specialists than knowing everything myself. The amount of expertise on products was especially deep. 

Contrast that with when I was the first ever tester at Silicon Publishing. I was testing for 5 projects and 15+ developers by myself at first, which considering our limited process, was much more about making testing possible than doing it all myself. 

The developers were amazing. The CEO was very focused on delivery to users. There was no time for politics as delivery to the client was the top thing at all times. I was seriously lucky that my desire to try new things was a match there. I never got bored. If I had any crazy idea, they allowed it. I even wrote a client facing feature at one point. Trust me, I’d have *never* written a client facing feature at Adobe.

The large company is better for stability, benefits, not going crazy when you come back from vacation. The small company is better for collaboration and learning new things outside of your role.

###[Zee](http://www.zeespencer.com/): What would you say is the primary difference between agile and traditional testing?###

That is a tough one, because I felt like the testing I did at Adobe in 2000 was more agile than some “agile” projects are now. The big difference, for me, is that you write tests for the features selected iteratively, you test those in the sprint, and then you test them with other features after integration.

My favorite agile projects include “collaboration” which means instead of a separate bug database, we collaborate and turn around fixes very quickly, either from a wiki page, checklist, in person meeting, or anything besides writing out bugs in a database that sit there getting moldy and are later triaged way after we’ve all moved on.

I see there are mostly two kinds of agile projects: 1. The kind where user feedback informs the design (real useful agile) or 2. The kind where we pretend we can represent the end user, and find out later how wrong we are (I don’t see how this is better than [waterfall](http://en.wikipedia.org/wiki/Waterfall_model)).

As a tester, I’m very good at isolating the cause of a problem if I know it is important to the user. I am not psychic though, so I can’t actually *be* the customer for any company. I am still a technical person, so I can’t pretend to be a new user in the same way that an actual new user is. I’m on my computer most of the day, every day. I try to use real content whenever I can, in a real environment. Sanitization causes missed problems.

I wanted to share what I think the biggest misconception is about testing? Is that ok?

The biggest misconception about software testing is that we mainly find code defects that programmers should have known about.

Most of what we do is identify requirements that were missed, or where integration has gone in ways that we did not anticipate. Larger system issues, performance, security, usability, and other -ilities.

I like to say that I’m paranoid so that everyone doesn’t need to be (as much). Black hats *are* out there, and if you let a user do something, they could. We even find bugs in the tools and external code used. It isn’t usually the fault of one developer when we find an important issue. 

It’s just new information, and now we can decide what to do earlier. I feel pleased when I save someone an awful day by preventing problems. It isn’t because I believe anyone is or is not a bad developer. Quality is a team effort. That means that the unconsidered is a risk to everyone. Testing is for risk identification so decisions can be made by the team. Blame assignment is inappropriate.

###[krystyna](https://twitter.com/Wimsy113): How important would you say pairing is to testing?###

It is vital if you want more than one person to be able to test an area, if you want bugs fixed and verified with maximum efficiency, or if you want any “non-primarily testers” to learn how to help with [Exploratory Testing](http://en.wikipedia.org/wiki/Exploratory_testing) or to even do a quick sanity check. Testing skill is spread by practice and pairing. I think the books are less effective for most people. Can you test without pairing? Of course. Should you? If you have no other alternative only.

I paired today for 30 minutes with the newest employee who is a project manager. She said she learned more in the walkthrough than in the past two days.

###[kmanion](https://twitter.com/kmanion): I’ve seen you say you are extremely passionate about testing. How did you discover and build a career around your passion?###

That is hilarious and a bit of a long story. I was working as a shift manager at a charity bingo parlor (Big Sisters Bingo in Renton, WA), when I got into a serious car accident. I wanted to work during the day, so I took a temp contracting job at an outsource company that I got after getting a high score on a test for Pagemaker tech support. I promised myself I’d quit if I hate working with “those nerd guys”.

It turns out that I loved it, and 2 months later I got promoted to being a 2nd tier support person. I really had a knack for hypnotizing people with my voice (side hobby). Anyhow, I was in classes to do tech support for Windows 2000 for Microsoft when I had the chance to interview for a temp job testing InDesign at Adobe. I despised my first 2 weeks testing.

I was about to quit when I went off of the boring script and found dozens of bugs. I’ve been testing in the way that it works (unscripted, more than just happy paths) ever since. Even in 2000 I interviewed against about 50 people to get my first job. I think it is more difficult for self taught people to get their first role now. I got the job because the developers insisted. The developers know much faster than others who is finding useful and actionable bugs. I think they should have more clout in hiring decisions.

###[nathanael](https://twitter.com/cnnct2you): What advice would you give someone who is just getting started as a novice tester?###

Better educated and more experienced people applied. The difference was the communication with developers and coworkers. This can not be stressed enough. It isn’t about the bugs you find. It is about understanding the business value.

I’d suggest they stop reading books and start testing more. Weekend testers, open source, automate something (anything). Experience is worth much more than theory.

The biggest mistake I see are people following tutorials to the letter, getting grades, but learning nothing useful. They still can’t code anything. They still can’t test. I think we can do better to help people get practical experience.

###[kmanion](https://twitter.com/kmanion): We've got two minutes. Any final thoughts?###

On diversity, I hope to get more ideas from other people to learn what has worked for them. We have a chance to stand up to people who would rather rate an entire person on a scale of 1-10 on their work performance without context. As a group, technical people are more powerful than is currently recognized, and we can insist on respectful treatment for more people. We all deserve to be treated with respect, even if situations are difficult.

*Lanette Creamer will be presenting a workshop at [Agile Roots 2015](http://www.agileroots.com) in June.*
