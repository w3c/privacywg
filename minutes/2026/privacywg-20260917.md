# Privacy Working Group, 17 September 2026

## Attendees

1. Nick Doty (CDT)

2. Beckett LeClair (invited expert)

3. Don Marti (invited expert)

4. Ari Chivukula (Google Chrome)

5. Ehsan Toreini (Samsung)

6. Joey Stanford (invited expert)

7. Ted Hardie (invited expert)

8. Chris Needham (BBC)

9.  Bhavani Shankar Garikapati (invited expert)

10. Peter Snyder (Brave)

11. Sebastian Zimmeck (invited expert, Wesleyan University)



Chair: Nick Doty

Scribe: Don Marti

## Agenda

### 1. Introductions, Code of Conduct

### 2. Privacy reviews

Chairs are doing triage of incoming privacy reviews

#### Attribution

Nick: Ben Case is not available for this meeting. The goal is to try to consolidate any feedback so that we can open issues or add on to existing issues so that the group can get all feedback from this group.

There is also a TAG review with comments, some of that might be relevant. Some comments from TAG and feedback from PATWG might be useful

Ted: Martin Thomson gave WG view on some things that we were raising. Doing feedback this late is problematic. Some other pieces are surprising and would be worth backing the TAG on them. TAG raised a question on the ability of the user to control signals. Intent is that browsers want to be able to differentiate based on these parameters, and do not expect setting by the individual. This is privacy-hostile and from a privacy POV that seems like a less than optimal choice, whether the browsers want to differentiate.

To get different behavior would have to switch browsers, not the level of choice we want to give users (Ted, can you correct)

Pete: also concerns about users being able to distribute the signal. If you choose to disable the API you are still sending reports. Common issue of users not being able to control the spec. My understanding on moving to issues is to summarize 3-4 issues we have open and we want to move into minutes

Additive vs non-replacement (maybe Ted to open)

Not being able to disable the behavior, user frustration and confusion (maybe Pete)

No recommendations for parameter values (maybe Nick)

Spec is un-implementable; requires that sites can never learn epsilon/parameters -- but if sites can drain "privacy budget" they will be able to learn when the budget is 0 -- more of a technical concern than a behavioral concern. (maybe Pete)

If there are things that are left out please add

Pete's initial go at issues to file / follow up on:

- additive vs replacement

- sending data even when users have disabled the signal like to cause confusion (at best) and / or anger

- spec does not give guidance on parameters

- implementability concern: spec says user agents MUST prevent sites from learning parametervalues, but if sites can knowingly drain the privacy budget, sites must be able to know (at some extreme) that the remaining value is "zero" / the budget has been exhausted

Nick: Ted, interested in parameter question. Martin's reply: doesn't expect users to be able to adjust epsilon. Not that users couldn't do that, but that if you're willing to modify your browser any user couild choose any epsilon. That's not actually a good ui to provide users, users don't know what they're getting. If I ask a family member what epsilon do you want they wouldn't understand the question. Bigger concern is whether it's set by browser or with user UI we haven't done enough to explain tousers what level of connection they're geting, or any different configuration of the differential privacy situation. Users would not understand this control or the level of protection they're gettting.

Ted: users need to understand what the browser is doing and whether they have control. Users never have a choice to turn this off full stop, the choice has been withdrawn. No way to manage what the actual parameters are going to be. If we don't tell the users what it does, telling the user to switch browsers is even less useful

If you can't say most privacy preserving/least privacy preserving with a slider you're telling them to swich browsers because of "epsilon" they don't understand. How to explain what this does and whether they should keep it. 

Nick: Shared concern, if users can't understand they find it hard to make a choice. Not good for users to have a slider

TAG feedback is that not being discoverable, sending nonsense values is better because user can't be coerced. Maybe there should be 2 different choices

Pete: Right now the spec collapses into 2 different cases, when the budget has been exhausted sending nonsense values is right

Sending nonsense values when user has disabled would be an infuriating option -- treating 2 cases differently separately should be [the way we think about this] ???

Nick: some users would like to be able to disable in a detectable way?

Pete: yes, the feature is not there

Ted: offer 3 choices: privacy budget = 0, turn off entirely, or let the browser set the parameters. I would prefer let the user set the parameters other than 0, but if these were available chces i'd feel better

Nick: even if TAG and WG want an undectable opt out there, feedback is that there should also be a detectable one.

Ehsan: I was involved in TAG review, adding to what Pete said letting users enable is a privacy breach itself. It can be used as a way for distinguishing users with more privacy concerns or whether if users are in private mode.  My understanding is that the room is not too concerned in the technical layer, most discussions are in usability layer, which is for all privacy-related APIs. But highlight the last paragraph that Martin said, on zero-sum. What the room thinks about that, that point was basically that it's a zero-sum game, not the best way to handle the situation? FIXME

Nick: zero-sum comment is kind of related to issue that Ted raised -- whether there's a benefit to doing this. Martin's argument is there's a benefit to doing this, not zero-sum. 

Don: my point is related to Martin T made in the TAG thread. "Something to help that industry" as in the ad industry. I also sat in on conversations on attribution tracking and drafts within the IAB tech lab. There is a substantial difference between the rest of the companies in the ad industry and what is in this particular proposal. This proposal is the view of not the ad industry but a few extremely large companies. I think a lot of the privacy math the proposal is throwing at the problem assumes there is an extremely large company/party with a privileged level of visibility into the industry - and then that [group] will dole out information to the other players. When we look at a proposal like this that is encoding this level of centralization, or requiring a large enough actor.

existing issue [link-to-do] on trying to avoid centralization in the development of privacy-preserving features

Nick: We're going to wrap this up so we can file issues. Trying to assign who can address each issue. Ted to open an issue?

Fully disabled vs. undetectable: Pete?

Parameter values: lack of recommendation or meaningfulness -- Nick can file, maybe Ted can add on

Pete has a separate issue on the threat of being able to detect epsilon

Don: I've been raising issues on these problems for so long, attending Community Group and Working Group as a member. feel tired of writing this up. If anyone wants to help communicate/translate what I have been writing in blogs, etc. I don't think this is last-minute feedback at all, as the comments have been raised throughout.

Ted: yes, I'm willing to work with Don on the centralization piece.

Nick: The result is not that everyone is going to be happy but we did assign homework

#### MCP

MCP: Nick to volunteer to write up one or two issues on that. Pete, can you help with others?

#### Triage and updates on charters and other review requests

Nick: we have verifiable credentials; make sure they have privacy considerations and not just threat model

Beckett: looking at Verifiable Credentials Data Model

(Nick: that's the core one to look at for the privacy implications for all of them, although I don't think they are requesting privacy reivew on that document right now)

Pete: request for reviewing a charter for the SVG group, in maintenance mode. Nothing being added that was privacy concerning, we closed that out. WebRTC charter also discussed, charter no concerns, closed out.

Nick: Manifest, anyone want to work on it w me?

Pete: Media WG registries

Chris: There are numerous registries, EME, MSE and Web Codecs. The review request is for  the registry itself, i.e., a review of what goes in and the criteria. Not looking for review of individual registry documents, but the registry itself. 

Pete: Criteria for registry do not mention privacy properties, before....how does group approach that?

Chris: I expect we would approach via the Privacy Considerations section in the the spec that pulls in the registry. Not clear if a particular registry entry would have privacy considerations in addition to the spec itself. Each registry entry could have its own Privacy Considerations, maybe?

Pete: A new image format might not have privacy concerns but some of the EME ones might. Make it clear what the privacy criteria are for being added

Chris: That is something we can figure out in the group.

Pete: When that is done we can review.

Chris: I will take a note to follow up. Thanks.

### 3. GPC

Sebastian: here is the tag link [WG New Spec: Global Privacy Control (GPC) · Issue #1265 · w3ctag/design-reviews · GitHub](https://github.com/w3ctag/design-reviews/issues/1265), we distributed the work a little bit. [Seek wide review · Issue #138 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/138) So in the GPC repo the roadmap and then we assigned the wide review tasks. Work distributed. On the TAG issue one question on GPC being exposed to worker navigator, but defined in top level context. Not clear how this works with service workers not tied to a top level browsing context. Pete has thought about this

Pete: As TAG notes we have a preference tied to a browsing context not to a party/origin.  [Global Privacy Control (GPC)](https://w3c.github.io/gpc/#preference-caching) So we have a conversation about how to address this, can get same intent by deleting section 3.2 which is non-normative, and have the preference apply per origin (PETE PLEASE CHECK) will review at next call.

Sebastian: that's the update, happy to take comments, or post an issue or a comment on the TAG issue.

Nick: Just lost Ari, if you open a PR tag him. We need an editor to review. ???

Ari's open PR: https://github.com/w3c/gpc/pull/152

Pete: will add to next GPC call

### 4. WG Charter

Nick: charter of this WG (2 y.o.) is expiring, so the process is for us to decide if we want to continue as a WG and update charter, then W3C AG will look at it and approve or not. Lots of positive feedback, no negative, on charter refinement. No changes to deliverables, will need to update timeline as we are past original timeline for GPC. We have a decision to enter Charter Refinement -- there is a GitHub issue. Suggestions on timeline welcome there, will ask for feedback from other groups. We have consensus not to make changes and continue work of the group. 

- charter: [CfC to proceed with Privacy WG charter refinement · Issue #26 · w3c/privacywg · GitHub](https://github.com/w3c/privacywg/issues/26)

- [[wg/privacy] Privacy Working Group Charter · Issue #572 · w3c/strategy · GitHub](https://github.com/w3c/strategy/issues/572)

### 5. TPAC

TPAC sessions coming up. No WG meeting, chairs will not be there but there will be breakouts and mini workshops.

Beckett: will be a conversation on age assurance. May be connected to Verifiable Credentials.

### 6. AOB

Nick: any other business?

Pete: there was a request for review from Verifiable Credentials, how to format and set a JSON schema. Unlikely to have privacy concerns, letting the group know in case anyone has concerns or wants to do a full review, otherwise can close out

Nick: Bluetooth, USB, serial devices access from web sites, incubated but no consensus so far. But some interest from other implementers: Mozilla, Google, Microsoft. There is a formal objection to adding those APIs and a question about where because some wanted to put it in a different WG. WHATWG to start a new work stream (?) for devices, which introduce a whole set of privacy and secrutiy issues. Not clear what devices can do or what the user is giving permission to. WHATWG does not have same privacy+ security process, but if anyone is interested in better reviews for those devices, that will be important and difficult work. Some think it can't be done properly; others think it can. Something to highlight for us but also an opportunity or obligation for someone who wants to improve the process for WHATWG this will be an important test case. How W3C bureaucracy affects this.

Joey: (in chat) Keep me in mind for the devices reviews as I've been involved in related work as of late



