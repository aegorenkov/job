# Hello there
This page is here to allow you to see code samples without getting lost in the resources that I share with friends and students.
Aside from those random resources, my GitHub is relatively empty since I write most of my code on enterprise servers that are not open to the public. 

# Code samples

**Propensity Score Matching algorithm implementation in Python and NumPy**

[Main matching code](https://github.com/aegorenkov/PropensityScoreMatching/blob/master/PropensityScoreMatching/__init__.py)

[Project repository](https://github.com/aegorenkov/PropensityScoreMatching)

I needed to use statistical matching in the web, but the standard routines in R were too slow. It took 72 hours to do a match on the required data size. There are good proprietary implementations out there, but none that can be used in the web. So I made my own that could run the match within a second.

The code takes on several dependencies and several shortcuts to reduce development time since it was written under a deadline to serve as a prototype. This is not meant to be a public library.

# Writing samples

**Article for Medium**

[How to ask questions data science can solve](https://towardsdatascience.com/how-to-ask-questions-data-science-can-solve-e073d6a06236)

First article for Medium. I want to write many more of these, but it cuts into my programming study time.

**Dimensionality Reduction Guest Lecture**

[Dimensionality Reduction](https://github.com/aegorenkov/job/blob/master/dimensionality_reduction_solutions.ipynb)

This is a copy of an interactive lecture that serves as an intro to dimensionality reduction. I wrote this notebook, but I borrow a few concepts from other instructors. Generally, there is little time to prepare and typos are nearly unavoidable.

# Web apps and side projects

**Interactive cheatsheet**

[Pandas cheatsheet](http://www.codefluently.com/pandas/)

A simple mobile friendly site written in Ionic which is composed of Angular2 and TypeScript. The idea is that cheatsheets quickly become hard to navigate and could be greatly improved with information retrieval. All Pandas code and descriptions are written by me. No business case here, just a side project that gives me exposure to modern web frameworks.

*What made it interesting:*
- It's a simple application, but I have not done much Angular2 or Ionic work.

*Lessons learned:*
- ES6 and TypeScript seem to be going in a good direction, I might have to do more front-end work.
- Angular2 apps are huge even after tree-shaking and gzip.

**Codefluently App**

[Codefluently](http://www.codefluently.com/cfapp/) (Under the practice section in the menu).

A lightweight interface for fill in the blank coding challenges for beginning programmers. What is interesting is that the difficulty of the questions adapts to the apparent ability of the user. You need two points of inference, any time two users get a question wrong, then it's more likely the question is difficult. Any time a student gets a question wrong, then it's more likely that the student's ability is over-estimated. 

*What made it interesting:*
- What really makes this an interesting problem is that you need to be able to update the machine learning algorithm asynchronously between many mobile users with an unstable internet connection and a central server. This challenge is highly relevant to mobile apps "How do we simultaneously model individual and crowd behavior?", but in most cases you do not need realtime performance and can allow the server to use stale information. Another way to think about it is distributed machine learning, but instead of using a cloud server, you use the client's device.

*Lessons learned:*
- I spent time doing user-testing, which reminded me just how difficult it is to make an effortless UI.
- Even simple user-centric product apps have endless amounts of interesting problems to deal with, many of which mix software engineering and statistics.
- Glicko2 is a very cool algorithm and I had a chance to translate an implementation into TypeScript.

**Forest target and evaluation tools**

[Media Announcement](https://servirglobal.net/Global/Articles/Article/1397/servir-applied-sciences-team-developing-tool-to-evaluate-effectiveness-of-fores)

[Tools](http://www.rff.org/research/collection/targeting-and-evaluating-forest-conservation-latin-america)

Two tools for prioritizing and evaluating forest policy. These aren't pretty; The 2000s era interface was actually a requirement. I did maintenance on the prioritization tool and full stack development on the evaluation tool.

*What made it interesting:*
- The tech is surprisingly non-trivial and requires very flexible schemas to allow user to upload and merge data. The I/O requirements were a strain as well. Leaflet.js was very popular at this time and everyone who suggested it never stopped to think how long it takes to render 50,000 DOM nodes as specified in the requirements. (HINT: The browser crashes.)

*Lessons learned:*
- How to take a database query from minutes to seconds. This involved using prepared queries to influence the queryplan, which can't be overridden in PostgreSQL. This also involved rewriting SQL to make query plans more obvious, making sure table statistics update at the right time, schema denormalization to reduce page reads, tuning to make sure key tables stay in RAM, and a much more careful use of indexes.
- A variety of GIS tools, particularly GeoServer, GeoDjango, and PostGIS.
- The power of a well placed LRU cache.
