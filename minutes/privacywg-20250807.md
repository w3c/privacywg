# Privacy Working Group, 7 August 2025

## Attendees

1. Nick Doty (CDT)

2. Tara Whalen (W3C)

3. Pete Snyder (Brave Software)

4.  Joey Stanford (Invited Expert)

5. Sebastian Zimmeck (Wesleyan University, Invited Expert)

6. Tom Ritter (Mozilla)

7. Don Marti (Raptive)

8. Ben VanderSloot (Mozilla)

9. Justin Brookman (Consumer Reports)

10. Michael Kleber (Google Chrome)

11. Chris Cuellar (Bocoup)

Apologies: 

Chair: Nick Doty

Scribe: Don Marti

## Agenda

1. Introductions, Code of Conduct

2. privacy reviews
- Web Authentication 2025-04-24 > 2025-05-25 w3cping/privacy-request#162

- IMSC Text Profile 1.3 (22 July 2025) w3cping/privacy-request#167
3. GPC
- Add user agent automation definition gpc#105

- Edit to spec to clarify scope gpc#107 (also 102 and 104)
4. differential privacy review guidance document
- [What To Expect When You're Inspecting Differential Privacy Systems - Google Docs](https://docs.google.com/document/d/1pE3p6TVsERPln00PLXj6j9rTdoG3PmiNHhv3NtXDtEU/edit)
5. AOB
- reminder about age-restriction workshop

- fingerprinting guidance update

## Notes

Nick: Not a big backlog of reviews, summarize agenda

### Privacy reviews

#### Web Authentication

[Web Authentication 2025-04-24 &gt; 2025-05-25 · Issue #162 · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues/162)

Could have been a quick review, but some new features with privacy considerations

Related origins concept: you have a keypair, sign a challenge to log in

Some sites want different origin but same account system so share key pairs

But that identity (log in with passkey) can be shared across sites, introduces the concept of a related origin

If string before tld is the same, can have 5 strings before the TLD (?)

google.TLD can be treated as the same with multiple TLDs, or log in to youtube.* with Google account

There is some potential for user confusion or tracking, some confusion about the concept of related domains

2nd area client capabilities: passkeys adding more features like using a different device (using a QR code or BT to pass info). Possible extensions in the future may enable the user agent to advertise capabilities and extensions supported. Could be a fingerprinting surface, reveal device details and what the user has set up and not just product and age. Could be clarified.

Cross origin iframes -- there might be an iframe for an auth vendor embedded in a site. This is ripe for user confusion because unclear what you are signing in to. This could be useful and also confuse users into providing a cryptographically unique identified across sites in unintended ways

User verification discouraged: site can tell UA not to prompt user when asking for passkey -- this indicates that sites can enable scrpts to do something without detection by the user (possibly without the site maintainer knowing)

Material to be added to privacy review issue, feedback welcome

Pete: Which issues will be filed as needs resolution?

Nick: Mostly framed as questions, need more info on implementation. Could be answered in a way that indicates it's not a problem. All of them need to be addressed.

Pete: related origins seems straightforwardly relaxing boundaries, no shared credentials across boundaries. Can file a special issue as needs resolution

Nick: Can open an issue with questions

Pete: Will open a parallel issue so that it can be tagged as needs resolution. UAs might have feature to share which passkey is being used. Can have different credentials but you need to do some work on the client side, but if sites are allowed to combine passkeys, hard for users to manage, could discourage use of passkeys, be a step backwards.

Nick: seems like work for credenial manager (browser)

Ben: Cross origin iframe problem -- if you have a cross origin iframe and it requests a passkey it gets a passkey that was used to log in at the top level in the past?

Nick: not clear, this is marked as a question

Ben: Needs to be clear if this is breaking a privacy boundary

Nick: top level site needs to set a permission for the iframe, explicit opt in from the top level site is useful. Not sure on details

Ben: are passkeys partitioned?

Nick: Partitioned? 

Michael Kleber: In Nick's description of related domains: country TLDs for google.TLD -- actually this is not relevant. New blog post:  [Here’s an update on our use of country code top-level domains.](https://blog.google/products/search/country-code-top-level-domains/) Google's use of country TLDs, now a thing of the past. Country code TLD pattern was a big deal 10 years ago but not a big deal now. 

Nick: google.* was not in the spec, but the spec states a recognizable string before a TLD but should not count toward the number of strings that can be combined (?) Lots of web sites are using this pattern. Are many sites moving away from cc TLDs?

Michael: I don't know whether it's a trend in general.  I think for Google it used to be technically important for latency and language, modern techniques do a better job.  I can't speak to anything like non technical branding issues

Pete: The 5 entry requirement is a floor not a ceiling, seems odd. 

Nick: Happens to be that implementers are using 5 as floor and ceiling

Pete: Section 5.11 says not that many more than 5 

Nick: Intended to be way more than 5 TLDs, 4 strings before the TLD

Pete: Confusing and novel: unlimited numbers of origins and seems very weird

Nick: number of origins can be in the thousands? Expected that clients will limit the number of strings before a registerable domain

Pete: can it be TLD plus 1? Examples

Nick: it's registerable domain, not eTLD+1, either using or avoiding PSL? Registerable concept (defined in whatwg html, I think)

Pete: Will follow up, not understanding the concept

Nick: need to follow up on details of domains

Pete: Related sites by a different name? Any text on how to recognize sites as related?

Nick: All have to refer to a single ID, avoid some problems of FPS/RWS. Relying party ID? Should follow up, will post to Slack about details, ask questions for the group

#### IMSC Text Profile 1.3

[IMSC Text Profile 1.3 (22 July 2025) w3cping/privacy-request#167](https://github.com/w3cping/privacy-request/issues/167)

Pete: markup and presentation for text intended to accompany videos. Caveat in privacy section, see these issues for discussion. We have argued about this for 7 years, no energy to continue in a bad pattern. Plan on documenting the concern. If someone has energy to work on it can share details. This version of the spec does not introduce novel privacy concerns.

Nick: Make sure issues are noted. Anyone else interested, let Pete know

Pete: will file an issue and see if anyone wants to pick it up

## GPC

Nick: up to date on privacy reviews, let's talk about GPC. Two PRs on the agenda: 

#### Add user agent automation definition

Ben opened 105 on automation

[Add user agent automation definition by bvandersloot-mozilla · Pull Request #105 · w3c/gpc · GitHub](https://github.com/w3c/gpc/pull/105)

Ben: to test GPC we need to tell browser automation to enable it, reflecting user choice. Helpful for testing. WebDriver process for adding an automation feature needs this.

Nick: Does this need to be in the spec too?

Ben: yes, typically in spec (not just WebDriver) Details are defined in the WebDriver spec. This is how I have seen it done, webDriver editors can correct if needed

Pete: examples of specs that include WebDriver info?

Ben: Will look up examples, add to notes

- [Navigational-Tracking Mitigations](https://privacycg.github.io/nav-tracking-mitigations/#bounce-tracking-mitigations-automation)

- [www.w3.org/TR/fedcm/#automation](http://www.w3.org/TR/fedcm/#automation) 

#### Edit to spec to clarify scope

[Edit to spec to clarify scope by j-br0 · Pull Request #107 · w3c/gpc · GitHub](https://github.com/w3c/gpc/pull/107)

[Pull requests · w3c/gpc · GitHub](https://github.com/w3c/gpc/pulls) {102, 104, 107}

Nick: clarify scope -- there are multiple PRs on this topic, Justin's is most recent and has general agreement that there is improvement

Justin: What is GPC specifically meant to convey? Encapsulating in 1 phrase can be challenging, originally California was do not sell, now do not share, other states have opt outs with other terms. Jeffrey had suggested other options in PR 102 and 104. The new PR is adapted from 104. Intended to opt out of cross context advertising. Michael would prefer to say "cross organization" But in some cases organizations might own multiple contexts, user expectations. Privacy Principles cover cross context, many laws use "cross organization". To make it clear, state it is not meant to stop tracking within a context. Could be added to the explainer. Edge cases where cross context tracking within organizations, we are close and can keep iterating on it. Also an issue on where within the text of the spec can be more clear. Would like to push PR 107 soon and discuss more clarifying language. Would be fine with finding places to make this more clear. As other states are enforcing, would be helpful.

Michael: Agree with everything Justin said, biggest difference between this and previous PRs is Justin still maintains two concepts, "cross context" and "cross organization", if I understand correctly those two as distinct phrases, cross context is what GPC would philosophically like to be about and cross organziation is what the specific laws address. I would be happy with just one phrase, but if we need to retain two then I would want to make sure that both of those terms have coherent definitions. We already have a good definition for one, but let's also make it clear that cross context is not trying to talk about a new notion that browsers need to introduce that is more restrictive than the hostname

Justin: meant to be a request to stop cross context, may be more expansive than cross org. California law goes a little further, closer to cross context, covers distinctly branded, other state laws mention cross org. If California wants to say that tracking across companies with common ownership + distinct branding then GPC is consistent, then that would be a change and might more consistency about cross-organizational scope. Clearly branded ecosystem -- not intended to limit info sharing across clearly commonly branded sites.

Nick: I like cross context, defined in Privacy Principles, but for explaining legal issues, cover cross organization where we do not necessarily have the concept. Explainer would be a good place to explain this.  Privacy principles also define same site recognition or same context recognition, could be added to state that GPC is not intended to affect or indicate any preference about same site/context recognition

Justin: Not just site specific. Even within a branded organization, not intended to limit data usage within that ecosystem.

Nick: consensus to merge, follow up with more discussion

Justin: will merge, and work on next steps in explainer and/or spec

## Differential privacy

Nick: General advice about differential privacy? When it comes up, what to do about it, how to evaluate it. Almost all of us are not experts on DP. Pete had written docs

Pete: Suggestions and guidance about how to review specs using DP in a way that doesn't require deep knowledge of DP but understand the promises it offers. Intended to highlight tradeoffs that DP systems must make. Goal is to -- because there are lots of ways to achieve DP -- people are looking for ways to compare systems e.g. Epsilon floors not helpful for understanding, like saying a system uses crypto, can obscure more than it helps. Without understanding the math how to understand the DP options. Could be important as reviewing systems. DP is one of an infinite number of mechanisms, 18 different decisions being made and all could have some implications. Can move this document into a repo or leave as is, or discusssion item.

Link: [What To Expect When You're Inspecting Differential Privacy Systems - Google Docs](https://docs.google.com/document/d/1pE3p6TVsERPln00PLXj6j9rTdoG3PmiNHhv3NtXDtEU/edit?tab=t.0#heading=h.8174k9yshcu7)

Nick: Reviewing PATCG specs I would find anything like this useful. Can check in at next call.

Pete: If of interest, not interested in extra PRs with too many details, the goal of the doc is to understand tradeoffs without having to be a domain expert.

## agews workshop

Nick: more items, first W3C and IAB are organizing a workshop on age based restrictions on content. Workshop scheduled for October in London. Call for position papers: write down ideas ahead of time so people can understand. Papers needed by tomorrow (8 Aug). Will be discussing privacy implications.

https://datatracker.ietf.org/group/agews/about/

## Fingerprinting guidance

Fingerprinting guidance: Tom has been writing PRs and looking for some reviews

Tom: PRs need feedback

Randomness [Expand the section on randomness and update it. by tomrittervg · Pull Request #76 · w3c/fingerprinting-guidance · GitHub](https://github.com/w3c/fingerprinting-guidance/pull/76)

Organization [Reorganize the Best Practices as described in #70 by tomrittervg · Pull Request #81 · w3c/fingerprinting-guidance · GitHub](https://github.com/w3c/fingerprinting-guidance/pull/81)

Pete: plan to give feedback

Nick: AOB? Next meeting Aug 21, will open issue for agenda items

# 
