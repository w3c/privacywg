# Privacy Working Group, 14 November 2025, TPAC


## Attendees 

1. Nick Doty (CDT)
2. Michael Kleber (Google Chrome)
3. Peter Snyder (Brave)
4. Mike Taylor (Google Chrome)
5. Ben VanderSloot (Mozilla)
6. Robert Liu (Google Chrome)
7.Julien Bataille (Rakuten)
8. Aram Zucker-Scharff (The Washington Post)
9. Anna Weine (Mozilla, observer)
10.Tara Whalen (W3C)
11. Lionel Basdevant (Criteo)
12. Thomas Prieur (Criteo)
13. Aloïs Bissuel (Criteo)
14. Maxime Vono (Criteo)
15. Tom Van Goethem (Google Chrome)
16. Sean Turner (PAT WG/CG - W3C IE - observer)
17. Will Bamberg (Open Web Docs, observer)
18. Florian Scholz (Open Web Docs, Docs CG chair, observer)
19. Ben Case (Meta)
20.Nicola Tommasi (Google Chrome)
21. Matthew Finkel (Apple WebKit)
22.Martin Dürst (IE, I18N IG chair)
23. Matt Dembski (Google Chrome)
24. Ari Chivukula (Google Chrome)
25. Nour Nabil (Google Chrome)
26.Isaac Foster (MSFT Ads)
27.
28.
29.
30.

Apologies: 



Chair: Nick Doty, Pete Snyder
Scribe: Ben

# Agenda

1. Introductions, Code of Conduct

https://www.w3.org/policies/code-of-conduct/


2. process

W3C AB

Tess speaking to us from Advisory Board

3. document status updates

* [Privacy Principles](https://www.w3.org/TR/privacy-principles/)

* [GPC](https://www.w3.org/TR/gpc/)

* [Mitigating Browser Fingerprinting](https://www.w3.org/TR/fingerprinting-guidance/)

* [Differential Privacy guidance](https://docs.google.com/document/d/1pE3p6TVsERPln00PLXj6j9rTdoG3PmiNHhv3NtXDtEU/edit?tab=t.0#heading=h.8174k9yshcu7)

* [credential-considerations](https://github.com/w3c/credential-considerations/blob/main/credentials-considerations.md)

* [permissions](https://github.com/w3c/adding-permissions)

4. any follow-ups from other TPAC sessions?

age assurance/restriction proposals

permissions

credentials

geolocation privacy/granularity

IP address privacy

privacy sandbox and what's next?

5. AOB

# Minutes

topic: Introductions. Name and affiliation of chairs given

topic: Process:

Tess: AB is trying to gauge appetite and pain points in process
    ... Focused on what gets in your way. 
    ... Don't want to take up too much of your time, so feel free to communicate later
    
Dan: we are here to hear from you
    ... this is the AB charm offensive. We want changes to be visible
    ... suggested topics: chartering, documents
    
Nick: members, any initial reactions?
    Room: none
    
Nick: How often is horizontal review a pain pont among the things you have heard this week?
    
Tess: Not in those words, but yes we have heard the lateness and delay is heard. But feedback
    ... is also self-contradictory
    
Dan: simplifying horizontal review is a theme. There is a disconnect between how we do work and 
    ... how W3C deals with work items
    
Nick: simplification is interesting. Late coming to a spec is bad for the reviewer as well. 
    ... We'd like to come in earlier and have a chance to do affect change
    
Pete: It makes it hard for us to get volunteers for reviews if their feedback is not heard or used
    
Tess: I know what you mean from the TAG design review experience
    
Nick: Formal objections have come up a lot in Privacy, to the charters of what we do and to substantive publications. They have slowed things down. 
    ... sometimes they are not resolvable, and so spending a long time and delay on just fundamental objection to our doing this work is frustrating.
    
Tess+Dan: agree
    
Dan: I've been taking a lot of notes. Brent Zundel (Process CG & AB) is going to be synthesizing them and finding areas to fix. Chime in as we go
    
Aram: Hopping around different pages for reviews is hard. A central place of the list of reviews, where they are, and who is doing them would be helpful. 
    
Tess: We have heard a lot about pain that might be tooling problems. I'd expect a key result would be shared tooling improvements. Resentment is heard, and is compounded by the quirkiness of each group. Uniformity of tooling may help with that too
    
Dan: One suggestion from other groups: more frequent, smaller chunk formal review. Web Apps PRs are consensus. Would it make sense to get review on every PR?
    
Pete: Some groups ask for 7 reviews at the same time. Sometimes things are out of date or we have other issues with document correctness
    
Nick: Assigning reviewers will be intense if we assign people for each PR.
    
Pete: if we went that direction, we'd need to assign reviewers to a Working Group who could then monitor updates in an ongoing way.
    
Ben: zooming out, Process is all there for a reason, every requirement written in tears, you don't know why it's like that until you experience the pain it was to addressed. outsiders don't understand what the Rec track means. general gripe on clarity of why the Process is there.
    
Tess: It'd be easy to remove something that causes problems inadvertently. We are being careful for that reason.
    
Dan: You also want things better explained?
Ben: Nods
    
Dan: we are looking to improve information architecture
    
Tess: Sorry for taking your time. This is the beginning of a conversation. Talk to the AB if you have any additional feedback
    
Dan: Whoever you feel comfortable talking to
    
Nick: Do you have a timeline for feedback?
    
Tess&Dan: Whenever.

(Via Martin D.)

Pointers to Internationalization review process: How to engage with the i18n WG for assistance and reviews (https://www.w3.org/International/reviews/projReview.html), Review comment tracker (https://w3c.github.io/i18n-activity/reviews/), Review Radar (https://github.com/orgs/w3c/projects/91/views/1)

topic: document status updates:
    
Nick: We do a few types of work. We have moved to autopublishing some of them. It's important to check in on them. Especially the guidance docmuents.
    
Nick: First, privacy principles! It is a Statement of the W3C, reflecting consensus. Congrats to those that participated. Does anyone on the TAG think we need to do more work? 
    
Room: silence (nobody from TAG present to comment)
    
Nick: The urgent work is to update other docuemnts to satisfy the principles.
    
    
Nick: Second, GPC!
    
Pete: GPC has some force in 13 states. Other states and countries are looking at using it too. There is a new law in California requiring implementation of a set of things that only includes GPC. We believe the normative sections are complete or nearly complete. Ancillary documents are seeing more changes. Overall, we think we are close to putting it forward for ???.
    
Nick: the last WG call went into more substative details on the docuemnt issues. Are we publishing the explainer as a Note? Is it hard?
    
Tara: It's not difficult to do. We just need a decision from the group, not even a consensus call. It can be a note or note draft
    
Nick: Great! 
    
Aram: Now seems like a good time to close long-standing issues #51 and #6. #6: structured fields. this requires a breaking change.
Room: silence
    
Aram: Closed! #51: should GPC support other privacy laws? If you want to support another signal, make another spec was the think we thought. Any objections? Pete?
    
Pete: No objection
    
Nick: I thought we agreed to add non-normative advice in the explainer to tell others looking that they should make a different signal and not overload GPC
    
Aram: Let's file that as an issue against the WG. Closing the bug with a note to this effect.
    
Michael: There are people on the queue. I'd like to talk about other laws. There are more laws coming. What does the room think we should do if the new version of GDPR in 3 months directly contradicts our group's statements and has incompatibility issues with other laws. How much flexibility should we have? "Go take a hike" is a valid position. Maybe it leads to many checkboxes. That seems bad. But we should have thoughts
    
Nick: Not sure how laws can contradict the spec? Do you mean that it would be incompatible, or wouldn't be helpful in exercising those legal rights?
    
Michael: Other legislative bodies saying that there are different requirements on the signal. Should we expect that any other global opt out would need a new signal? Do we want to relitigate this?
    
Nick: The non-normative explainer is a great way to handle some of this

Aram: GPC is a signal that you want to request the greatest privacy available to you under whatever law. If the EU says tomorrow that a global opt-out exherts rights under GPC. We would not need to change the spec for that. Other states have expressed that GPC works for their law. 
    
Isaac: What does "we" mean here? The work of this group or this header?
    
Michael: I am looking for a clear, forward-looking position of what we think we will do when privacy legislation changes in the future. Will we retain flexibility? Will we change GPC? Will we pick up a new signal? Will we ignore them? Three reasonable options. Doing nothing is kicking the can down the road.
    
Isaac: Is the goal to be responsive of specific legislation or "go into the most conservative consent mode possible" If we get it from a client in a jurisdiction, we flip into conservative mode. 
    
Aram: Maybe my interpretation is wrong. I imagine other specs. We don't update CSS to support the imagined future holodeck. But one day in the future if there is a holodeck we might. That isn't a thing we can really consider at this time for CSS in the same way we can't really consider an unpassed law right now for GPC. 
    
Michael: The law is available. Read paragraph 39. It's a draft.
    
Aram: How many drafts don't become law? These things might become real in the future, but we can't build things this flexibly immediately. 
    
Matt: I had similar concerns to michael. These issues are related. Not making structured fields means you are not willing to break things now. That means you are committed to handing future laws
    
Nick: Back on track: We cannot commit to what we will or won't do in all future cases.
    
Isaac: can you explain Paragraph 39?
    
Michael: Link to what I heard called a leaked draft: https://cdn.netzpolitik.org/wp-upload/2025/11/EU-Kommission-Digital-Omnibus-A-Data-Act-und-DSGVO.pdf
    ... I got my answer though. No answer now, but we can talk later. Let's move on

Martin: on earlier topic, re: process -  i18n does a lot of horizontal review. You could use some of their stuff.
    
Nick: I'm on the hook for advice on handing changes in the future. 

Next item: mitigating browser fingerprinting. This is a guidance document. Advice for spec authors and ourselves. There have been significant updates in the past year! Thanks are due to Tom from Mozilla! There are several issues that have not been addressed yet. Might take time for editors to get to, but help is welcome. Tom wanted help with client hints as a way to make entropy use more detectable. If you have experience, let us know
    
Nick: next topic Differential Privacy Guidance: came from the TAG/Jeffrey. DP is something we see more. Pete and some of his colleagues at Brave have written a draft explaining it to non-experts. We are publishing it as a Note Draft. 
    
Pete: Summary: I know there are outstanding suggestions. I am going to wait until we have a repo to track changes with.
    
Matt: Agree that having something to help reviewers is good. Differential Privacy is hard, and this group might not be the right group to review new differential privacy systems. 
    
Nick: We wanted guidance because we don't all have that expertise.
   
Michael: What is the process issue?
    
Tara: We are just changing the category of the document. Getting it together is one thing. Making a Draft Note is just a form of publication (document is not on Recommendation Track). Movement is before publication.
    
Michael: Sounds like publication isn't needed to get it into github. Just want to make sure a Note Draft is not a statement of consensus.
    
Nick: Note drafts are new!
    
Aram: I'm in favor of publishing it as a Draft Note. Thanks for the work.
    
Nick: Next is Credentials considerations. It's a merged document from me and Rick Byers (Chrome). It was messy to merge. We discussed working on a joint publication with the FedID WG about this. That group was concerned about the scope and their priorities of their spec. It's be useful to have published from us though. Kyle was interested in helping as well. This needs active work. Let me or Rick Byers know. File issues against the repo. We may bring it as a Draft Note when we have a draft
    
Nick: Finally, Permissions! We have a document giving guidance on adding a new permission, or advice on not adding one. There have been a lot of discussions on this front this week. Working with the TAG on this has been a topic of interest. 
    
Pete: It would be good to add guidance on how to handle permissions that affect multiple origins at the same time. e.g. Storage Access, iframes.
    
Nick: Adding an issue would be great
    
Last agenda item is updates to each other. TPAC is a place of communication. I have a placeholder here, feel free to add more. What work should we do?
    
Ben: Age Assurance breakout update: IAB/W3C age workshop happened Oct 7-9, had a debriefing on this to start with, then brainstormed about issues and possible solutions. Next day, Ben gave a proposal at WHATUP on signalling -- meta-tag approach, with name="rating" --got great feedback (esp from Aram) on what we might do. Signalling vs labelling; strong arguments for signalling.

Nick: there were some new ideas but not yet new proposal stage yet. Motivation has been child safety, involved abusive interactions online, what can we do to help? Age restriction has been floated as a solution, but maybe other approaches may be helpful, like mechanisms for reporting abuse, not just limiting access to web pages. This is a different approach to "safety" that we haven't yet discussed much. 

Any other sessions?

John: There is renewed interest in the better, privacy preserving FedCM spec


Nick: More context?

John: Federated logins. The original spec had the property that the identity provider did not learn where you logged in. That regressed. There is interest in trying to get it back in as a subset

Johann: Cookies breakout was fun. We are not removing 3pc. We talked about how to move forward on cookies. Probably need multi-year joint solutions. May need a new group for ongoing conversation and coordination, not just at TPAC each year. Two new proposals: origin-bound cookies and third-party-cookie-allow-list.

Ari: we want to add a header to allow a website to block third party cookies for itself. Defaults don't change

Johann: Cookie layering continues. RFC 6265bis is going to be published soon

Nick: Can someone summarize permissions breakouts?

Mike: Which thing in particular?

Nick: Any?

Mike: Element-based work is one we are considering. Prompts are either too loud or too quiet, We want to get a better signal of user intent. Constrained presentation element that gives the user a clue about real user intent. Louder prompts when you want them, and quieter when you don't. Other permissions are relevant. PWA install, camera. Presented to a couple of groups. There seems a broader pattern to improve user experience. Give feedback in WICG's repo PEPC. We may rename. 

Nick: also, something on research on rationales. 

Mike: Marian Harbach gave research on pre-prompts in page content. Grab the slides from that breakout.

Nick: Interesting breakout on geolocation privacy. Looked at old email discussions. May be more geolocation work coming, about coarse or different granularity.

Pascoe: Webauthn talked about "immediate mediation". Only show a dialog if there are credentials on the device. Leaks a bit. One proposal is to never return. Discussion ongoing.

Nick: that might be a more general problem shape.
... next meeting is Dec 4. Comment on the issue for the agenda!

https://github.com/w3c/privacywg/issues/18

