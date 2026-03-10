# Privacy Working Group, 5 March 2026


## Attendees 

* Peter Snyder (Brave)
* Joey Stanford (Invited)
* Benjamin VanderSloot (Mozilla)
* Bhavani Shankar Garikapati (Invited) 
* Ted Hardie
* Sebastian Zimmeck (Wesleyan University)
* Michael Kleber (Google Chrome)
* Nick Doty (CDT)



Apologies: 



Chair: Nick Doty
Scribe: Pete Snyder

# Agenda

    Introductions, Code of Conduct

# pass-through APIs

Nick: There are some APIs where there isn't much specified in the API/spec itself, and most of the logic and important bits are "passed through" and blind to the API

Benjamin: This came up with the DID Resolution review. The spec defines some common behavior and infrastructure, but the different kinds of resultion can do a lot of out of spec stuff (anything from just passing throgh numbers, to connecting to diff servers). I tried to note this in the review. Its difficult to review too because of"hiding the ball" kinds of 

Pete: We also have similar kinds of concerns with the credtential behaviour (e.g. datatypes specified in a registry). The less stuff that is being reviewed the less the PWG sees, the harder it is for the WG. We can miss privacy protections for the platform. It really does matter where this behaviour is defined. 

Nick: On the credential API, rather than having a registry they are going to have two specs elsewhere. Still, this is a good example. If you can say for the reviewer "oh the privacy stuff is here and you don't have to worry about the rest of the details". I think there has been a trend of design for purpose APIs. One way to avoid the open-endness, [is to document it] it becomes easier to see the implications for privacy and give feedback / draw conclusions. Let's do more design for purpose things so we have less confusion and abuse. The idea is to intentially allocate the responsibility for clarity. 

Ted: I agree,  Two ways to look a things: 1. define a minimum level of behavior for any of the kinds of the behaviors that could happen w/in this API, or 2. require more detail and be clear about whats reviewed and meets privacy standards for different of those sub-behaviors. 

Ben: I tried to do route 1 in Ted's terms, so giving minimum acceptable behaviors for the DID review (Scribe: did i get this right?)

Nick: For the credenital methods, the group seemed like it was going to go route #1 (using Ted's options), but the group ended up not doing that. So, there risk in trusting groups when they promise to add protections and conditions in the future.

Ben: meta-requirement of noting that any method/implementer should have its own privacy review

Pete: I'm trying to think through strategies. I'm cautious about broad minimum standards. The main lever we have is formal objections. If we are making promises for the future we lose the lever. It will be hard to guarentee / enforce privacy respecting behaviour. I plan to formally object to bad things a general practice, and not to forward thinking things that would happen in the future. i.e. review actual behaviours. 

Nick: 1) We should have the transparency (about where the privacy decisi. 2) We are going to set some basic conditions to get in (and we have some concerns about how that works). 3) fully specified purpose where we can fully evaluate the privacy implications.

Pete: 6 ot 7 years ago the web pattern at W3C was less strict. It was more common to suggest vs require.We have gotten better as a community and we should be proud about that. If we insist on things for the future we risk losing some of that progress.

Nick: We have options. We are learning from this. Should we write this down? Will someone write some of this down?

Pete: I have an informal document about how to do a privacy review. I can add some suggestions to it [based upon the above]. 

The document for suggestions on how to review a soec.  My (Pete's) suggestion is to add a note here, that reviewers should object when they see this pattern: https://github.com/w3c/privacywg/blob/main/howto-conduct-a-privacy-review.md

Nick: We also have a self-review questionaire. Do we have a good question for groups to trigger some thoughts about having additional reviews?

Ben: Do privacy properties of this review depend upon an additional spec?

Ted: Is the privacy properties novel to the API? Are they any use in the API? Pete's point is to tell people "dont' use this pattern at all but instead make it design for purpose". Some people want the flexibility. We could tell them if you use ...  we should tell them it has to be knowable and what the use of the API properties are going to be. If you need this broad API, then here is what you need to do as well. Make this part of the advise or survey or both.

Pete: There is a TAG design principles doc. Ted, I take your point. There are groups that need this flexibily as well as problem spaces. I want to push this to the absolute so we don't give up the little process power we have to push for change. We can't formally object if a group deviates from principals but we can if they deviate from the APIs.

Ted: The API needs to have some additional properties. We are saying avoid them at all but if you must do it the API must have something that has inspectability. Then we can object. We have to have an API surface to object upon. 

Nick: Pete to take action to do a privacy questionaire. For the self-review, we can open an issue. If Pete can open an issue we can all contribute to it. 

Joey: support minimum baseline idea, but also need that flexibility in APIs sometimes. need to have the ability to label things as privacy resolution needed, so need some power to direct.

# working group charters for review

Nick: We haven't brought these up frequently although we often mention it. Do we want to make any changes to this? Any perspectives? Often these do not have any specific privacy details. However, it might also be times to talk about privacy in the area. 

Pete: Performance WG in which we had a long and fruitful conversation about APIs. It's gone quiet. Their charter just came up. Thought might be a point to reengage. Are they not working on things much or [are we missing anything]?  In regards to CSS, we had a number of issues that were filed 5+ years ago that have not been resolved (e.g. fingerprinting).  A rechartering opp would help get the group to commit to address our issues. 

Joey: forcing function to address lingering issues.

Nick: related issue is that we have open needs. We have topics come up a number of times with different proposed solutions. It's not encapsulated on a single spec. We need to address broader issues.  e.g. we should try to make telemetry a more general issue. [aka abstracting / extracing these to a general problem]. This might take the format of a request for a deliverable vs an issue to address. Perhaps at charter time, we ask "is this now a good time to address this privacy issue?"

Joey: charter that comes up, scan through past open issues and put a call for feedback to the Privacy WG to identify items, maybe general issues that might cross multiple specs/groups. if it's cross-cutting, an opportunity to spin up a sub-group where we collectively address a more nuanced challenge; not every group will have the same perspective.

Pete: The pattern we have today is if the chair has any issue. If reviewing charters appeals to anyone we can pull more people into a fast-review circle. There's not a huge need. Please let us know. We'd love for you to help. I like the idea of automating the process of looking for open issues. I'll take the action to see if this can be automated.


https://github.com/w3cping/privacy-request/issues?q=is%3Aissue%20state%3Aopen%20label%3Acharter

# wide review for GPC

https://github.com/w3c/gpc/issues/138

Nick: We need to send out requests for internationalization, accessibility, security, etc. A design review needs to go to the TAG. We should do the TAG request sooner than later.  The TAG may have feedback on various topics. I suggest we get to this one first but ask for reviews generally.

Seb: I need to know exactly what I need to do and then I'm happy to go do it. I don't know how to reach out them (github, email,etc)

Pete: I'm happy to help you with that.

Seb: Offline you can point me to a starting point.

Nick: It is all github templates at this point. We can also ask Jeffrey. They will have feedback. Back to the review above, some has questionaires. We need to do some of them in order to get an effective review. Editors please get started with that. They should be fairly easy to answer. 

# AOB

Pete: We have a review request for mathml and ccs select. Are any of these of interest to anyone? It would be great if we have volunteers.

Shankar: I can do the mathML one.

Next call in two weeks but it conflicts with the IETF. We may still have that call and an agenda gathering issue.
