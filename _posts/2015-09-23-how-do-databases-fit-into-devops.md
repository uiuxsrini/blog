---
title:  "How Do Databases Fit Into Devops ?"
date: 2015-09-23 12:45:17
---

“How do DBAs fit into a DevOps world?”

If we look at how the roles and responsibilities break down, it looks like DBAs are simply Ops specialists. Does that mean that database developers and DBAs should be blended in a single DBDevOps team? Having two flavours of DevOps team running side-by-side on the same overall application feels like a poor compromise, but are databases special enough to warrant it?

Alternatively, does this mean that the DBA dissolves into just another Ops facet of the overall team? Given the amount of specialist training and knowledge we so often see invested in DBAs, it’s hard to imagine how a team could be high-performing without some degree of specialization when it comes to managing data. This could be the straw that breaks the Full-Stack Engineers back, or it could be that you can actually get a very long way before you have to dip into the skills of a true specialist. I’m sure that, like so many questions, the answer is “It depends”


Either way, the fact that we’re even talking about Database Lifecycle Management (and uttering sentences which include both “database” and “DevOps”) suggests that software engineering as a whole is maturing at the pace of Moore’s Law, and starting to embrace the ideas that were obvious to W. Deming. Not only are we tackling these questions thoughtfully, but we’re also being more aware of the practices that have emerged in software engineering. As a result of that maturity, we’re also starting to see tools emerging which are actually fit to be used in a DevOps environment. In the case of databases, part of that is about treating them as stateful artifacts, and I particularly like Redgate’s SQL Lighthouse in this regard – a free little tool currently in beta for monitoring when database states drift.