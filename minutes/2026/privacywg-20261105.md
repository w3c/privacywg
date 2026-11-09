# Privacy Working Group, 5 November 2026

## Attendees

1. Nick Doty (CDT)

2. Sebastian Zimmeck (Wesleyan University)

3. Benjamin VanderSloot (Mozilla)

4. Ted Hardie (Invited Expert)

5. Bhavani Shankar Garikapati (Invited Expert)

6. Justin Brookman (Consumer Reports, invited expert)

7. Jeffrey Yasskin (Google Chrome)

8. Tara Whalen (W3C)

9. Pete Snyder (Brave)

10. David Pham (1Password)

11. Christine Runnegar (invited expert, Internet Society), joined at 1/2 hour

Apologies: 

- Joey Stanford

Chair: Nick Doty

Scribes: Bhavani Shankar Garikapati

# Agenda

## Introductions, Code of Conduct

Nick: Code of Conduct is not a weapon or a correction, it also sets out positive expected behaviors, like being honest, and seeking out and understanding diversity of opinions.

## GPC: TAG feedback and wide review

Notes: 

[Sebastian] Links:  https://github.com/w3ctag/design-reviews/issues/1265, [Seek wide review · Issue #138 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/138)

Accessibility, Architecture, Privacy and Security issues has been discussed. Tag group is satisfied with concerns, minor work pending like including position of GPC from Mozilla (in form).  Pending resolution like whether service workers should receive GPC (resolution pending).

[Justin Brookman] Service worker issue (which is already discussed)  is pending resolution. Do we need to have a wide review from privacy working group ? 

[Peter Snyder] So far no concerns on not having sending GPC signals to service worker. 

[Ted Hardie] : Wide review from privacy working group is not necessary, as this is artifact of the group itself.

[Nick Doty]: Can we open github issues for comments raised by Brian Kardell (2, 4 and 5) ?

[Jeffrey Yasskin] 2 issue is actually a bug, noted by Ehsan, from TAG review. If an extension changes the JavaScript property without a header, that would be a problem -- it would be inconsistent and make the user more fingerprintable. Spec should say that you must change both consistently.

[Sebastian] To open Github issue(s)

[Tara Whalen]. Privacy considerations needs to be documented. Address as one of our last incomplete steps before transition to Candidate Recommendation.

[Sebastian] Where should  Questionnaire needs to be filed ? 

[Nick] separate document is possible, but just a github issue with markdown comments.

[Tara Whalen] Make sure we have a clear privacy trail, that Privacy analysis is done.

[Sebastian] According to CCPA (california), all browsers need to implement GPC

[Justin] Clarification, need not be GPC, but some form of signal to allow for opt-out.

## Annual publications checkin:

- GPC, Working Draft, auto-publishing, last update September

- Mitigating Browser Fingerprinting in Web Specifications, Note, auto-publishing, no updates since last TPAC

- Self-Review Questionnaire: Security and Privacy, Note, *not* auto-publishing, no updates since last TPAC

Notes: 

- [Peter] Auto publishing can be fine, not much changes are expected.

- Considerations for Reviewing Differential Privacy Systems, Note Draft, auto-publishing, but no updates since initial publication

- [Nick] : We can review whether we can update our guidelines based on the recent work related to adversiting.

## TPAC report-backs on privacy-specific issues

Notes

[Nick Doty] : Any topics to discuss relevant to Privacy ?

[Jeffrey Yasskin]:  Start tracking accessibility properties that get locked by Privacy concerns, and look for innovative fixes. 

[Tara Whalen] : Need to have explainers for Policy people to understand our work. GPC is one such example. Topics related to age-assurance was discussed. 

Mini-workshop: [Mini-Workshop @ TPAC2026: Age Assurance · Issue #569 · w3c/strategy · GitHub](https://github.com/w3c/strategy/issues/569) (age assurance). Some of the work proposed here will be picked up in the Online Safety CG.

Private Advertising Technology WG met, minutes are here: [202610 PAT WG Minutes - Google Docs](https://docs.google.com/document/d/1aMsmlmZ1-YF3Ymosftx1irsFYpWkvnu0bViPwC49uus/edit?tab=t.0#heading=h.emacos7anbx5)

[Ben VanderSloot]: Agentic browsing use-case: A working group charter is formed, the Privacy and Security considerations might be of interest to this group. Bringing Privacy Pass to the web is something Google and Cloudflare are interested in. Link to chat: [web-drafts/explainer.md at main · Moderation-of-unLinkable-Endorsements/web-drafts · GitHub](https://github.com/Moderation-of-unLinkable-Endorsements/web-drafts/blob/main/explainer.md) 

[Nick Doty] : Renewed interest in protocol design related to Blueetooth, USB etc. There can be lot of new Privacy and Security issues with these new updates.

## Privacy Working Group charter ready for transition and AC review

[Tara Whalen] : Making minor changes to charter. Security Interest group asked us to include them for considerations. 

## Privacy reviews for specs and charters, in particular: proposed Agentic Web Working Group ([[wg/agenticweb] Agentic Web Group Charter · Issue #244 · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues/244))

- Ted Hardie to review SHACL.

- Pete to review CSS specs, and welcome co-reviewer.

- Agentic Web looking for feedback soon, so chairs will send any comments/items to flag/review.

## AOB

Next meeting is scheduled during the IETF week, so there may be a lot of conflicts. Otherwise, next meeting would be Thursday, December 3rd.
