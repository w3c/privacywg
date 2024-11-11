# Privacy Working Group meeting - 7 November 2024


## Attendees 
- Pete Snyder (Brave, PrivacyWG co-chair)
- Nick Doty (CDT)
- Christine Runnegar (invited expert, Privacy WG co-chair)
- Tara Whalen (W3C, Team Contact)
- Michael Markevich (invited expert)
- Justin Brookman (Consumer Reports, GPC editor)
- Joey Stanford
- Chris Needham (BBC)
- Michael Kleber (Chrome)
- Don Marti (Raptive)
- Jeffrey Yasskin (Google Chrome)

Apologies: 
  
Chair: Nick, with Christine and Pete (in transit)

Scribe: Pete

## Agenda

### 1. Introductions, Code of Conduct

https://www.w3.org/policies/code-of-conduct/

introductions around the table :)

Nick: remidner that code of coduct requires and expects members to come with empathy,
…especially with difficult conversations and topics


### 2. Open privacy reviews

https://github.com/w3cping/privacy-request/issues

Nick: Group works by others coming to PrivacyWG with documents to reviews, usually as part of 
…: horizontal review. Current open review requests:

Pete: Verifiable Credentials documents. Kyle (from Brave) has done brief review and it looks
…: like the documents dont warrent a full review.

Nick: next, W3C vision statement

Christine: I did initial review before meeting, three notes
 - documents puts users first
 - privacy is a fundamental attribute
 - privacy and horizontal review are critical
 
I dont think further review is needed.
https://www.w3.org/TR/2024/NOTE-w3c-vision-20241018/

Nick: next, epub is requsting review. Changes are very minor from previous review, so
also suggest a full review is not needed

Nick: last, web assembly wants a review. Roy did a full review and left comments and issues
in the review. Additional reviews welcome.

Nick: No other open review requests

    
### 3. GPC (overview from editors and steps to publishing First Public Working Draft)

https://privacycg.github.io/gpc-spec/

Nick: WG charter lists GPC as a committed deliverable. Has gone through incubation through
PrivacyCG. GPC editors will now present the document, and then next process step will
be for a first public working draft (FPWD)

Justin: (giving overview of GPC) GPC came out of CCPA which included an opt-out
option for data being sold and shared. GPC is designed as a way to easily assert
that opt-out right. GPC is now legally enforced in CA. Other states (missed the number)
have and have announced they plan to recognize similar opt-outs broadly, and GPC specifically
(in the case of Colorado). The normative parts of the spec have been stable over the spec's
lifetime. Authors and implementors are nervous about major changes, but open to disucssion.

This was discussed at TPAC. Some concerns were:
 - opt-out is the wrong model: GPC isn't intended to endorse opt-out, or whether opt-out is the
   right model (GPC is silent on that)
 - US focused: GPC authors are talking with other jurisdictions, inc EU Berlin Group and
   other european stakeholders, and what GPC might mean in other places

Re FPWD, not my area of expertise but open to next steps on how to move forward.

Jeffrey: re process on FPWD, i think its ready now. I've filed issues for changes, but that
shouldn't block publishing the draft. Process wise i think its ready. See https://www.w3.org/policies/process/#RecsWD. It doesn't need consensus on the content, just an agreement that this is the starting point, which we agreed with the whole AC during the chartering process. Publishing is a little bit
urgent since other W3C documents (e.g., privacy principles) already mention GPC and we should
use a new WG URL

Aram: +1

Nick: Thank you Jeffrey, esp that FPWD does not mean that issues have been resolved or that
there is consensus

to team, do we need to move repo to request publication

PLH: i need a decision from PrivacyWG to public FPWD. Let me know now/asap if there are
concerns with moving repos or similar. Please make sure i have access to needed repos.

Also, can we make the document auto-publish (i.e., changes to the repo automatically re reflected
in public HTML version)

Aram: sounds good. autopublishing sounds good

Joey, Christine, Chris, Pete: +1 for fpwd and auto publication

PLH: should we move description of legal effects to another document, maybe a registry

Justin: spec currently has some references to current law. there is also an explainainer doc.
ther is also a PR to move more legal text into explainer. 

PLH: Can we publish explainer as a note from WG?

Aram: sounds good

PLH: Explainer-as-note would not need to come before FPWD

Chris: Can the note also be auto-publish? Since legal implications could change over time

PLH: yes

Nick: re other jurisdictions, i've been discussing with GDPR and UK experts. I think we should
reach out more. If people have other contacts or suggestions for who we should reach out to,
please let us know (esp outside of Europe)

Michael: I am worried about GPC meaning diff things in diff jurisdictions. Discussed in PrivacyCG
and issue seems to be getting worse. Current draft has internal contraditions. Current draft
says its not intended to limit first parties, but other sections re CO and CT contradct.
GPC means different things in different areas. Pulling the legal implications into a diff document
sounds like a good idea. We should make sure the W3C isn't seen as giving legal advice in this document.

However, what worries me is issues 51 and 52; if GPC is supposed to convey user intent,
then it needs to be clear what user intent is. Mozilla has a GPC option, but their text doesnt address
jurisdiction issue. Section 5.7 says browsers need to deal with explaining effect of GPC, and that sounds
maybe impossible.

Chris: re legal implications, there is a PR from Justin to move more text to explainier. I think we should
move all legal discussion to explainer document. I agree with what you were saying at the start re moving
legal language.

Michael: I think issues 51 and 52 cover

Nick: re requirements on user agents to represent user intent, many browser features are not well understood
by users. How do we deal with this issue (users dont understand features deelpy) elsewhere, and how could
it inform this feature?

Joey: GPC is implemented differently in different places (browsers, extensions, cookie banners, .well-known). Only the JS property seems browser-specifc to me in current spec. This could make
implementation difficult, maybe specificity would help (in terms of who and how implemneted). Also
might be helpful to understand what GPC does, minimally, on the current site.

Aram: We expect GPC could be implemented beyond browsers (e.g., smart TVs). Spec could potentially
cover such devices. 

Re what does the site do in response of GPC, spec can't mandate legal responses. But the technical details
of the header and JS property can be clearly defined (not sure i got this correctly)

Joey: I agree with pulling legal text into explainer. But, as a user, i still dont know what
happens when i enable or send GPC.

Aram: the "what will happen" parts make more sense in the explainer, but it depends on the developer
to implement GPC behavior

For example, accessiblility preferences or dark mode. The browser can indicate the request, but the
developer has to provide that experience; the spec doesn't define what a "dark mode experience"
would be. Implementors can provide guidance for how sites should or might respond to the request,
but the technical spec doesn't describe or define that. I think its beyond the scope of the spec
to specify what the developer receiving the signal should do.

Joey: I understand what you're saying, but the legal ramifications of the spec need further
clarification.

Nick: this is good, but lets move on. More issues please re Joey and Michael.

We can make sure future items get on future agendas (agenda+ tags on GitHub for example)

Our immediate issues and proposals are the below:

proposed: publish a FPWD based on the gpc-spec repo
proposed: auto-publish new Working Drafts based on merged updates
proposed: plan to publish explainer as a non-normative Draft Note, and set auto-publish as well

ask team to move repo to privacywg, and set up redirects
ask team to enable Echidna and auto-publication
ask team to notify / start wider review

chairs to send call for consensus


Justin: what to do with current PR to move text to explainer? do this before FPWD?

Jeffrey: dont block

PLH: do it after

Jeffrey: the explainer should start as a draft note, not a note; a note implies consensus

Christine: for future decisions, we should say something clear process wise, somethimng like
"there was consensus on the call, folks not on the call have X amount of time to object"

PLH: the speed of the W3C will make the above matter-of-fact automatically

Chris: from experiences in other groups, decisions can be made on the call, but consensus comes
after the call



### 4. Scheduling Privacy Working Group calls, closing Privacy IG, GitHub repositories

Nick: We've been calling 2x/month, but to get broader participation, we might want to add an Asia/Pacific time. Need to discuss that on the mailing list.

PLH: We need to close the IG, probably around Nov 19, which is 45 days after the start of this WG. If you haven't been able to join as an Invited Expert, keep working on that. We've been pretty relaxed so far.

PLH: We have a bunch of repositories in the privacy IG. Plan is to archive most of those. 1 will move to WG. Moving adding-permissions.

Christine: Nick wrote good text about adding permissions, and we think that should be a Group Note. We'll move it to the WG first. Guidance for spec writers.

PLH: Everything else will be archived. If we change our minds, it's possible to unarchive them.

Nick: That probably doesn't need any Decisions.


    
### 5. Other documents for Privacy WG

Nick: If we want to talk about the permissions document as a Note, or the explainer as a draft note, that should be on the agenda for a future call.

### 6. Open group charters for horizontal review

https://github.com/w3c/strategy/issues?q=is%3Aopen+label%3A%22Horizontal+review+requested%22+-label%3A%22Privacy+review+completed%22

Nick: The above link has charters that haven't yet gotten group feedback. Some open questions about CSS. Look at that link, and we'll get more feedback on future calls.
    
### AOB 

Nick: We'll meet again in 2 weeks.


Agenda items pushed to next call:

* privacy conversations at IETF Dublin)
* Other documents for Privacy WG