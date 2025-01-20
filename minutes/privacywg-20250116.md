# Privacy Working Group meeting - 16 January 2025

## Attendees

- Nick Doty (CDT, PrivacyWG co-chair)
* Tara Whalen (W3C)
- Philippe Le Hegaret (W3C)

- Tom Ritter (Mozilla)

- Justin Brookman (Consumer Reports)

- Peter Snyder (Brave, PrivacyWG co-chair)

- Sebastian Zimmeck (Wesleyan University)

- Michael Kleber (Google Chrome)

- Lola Odelola (invited expert)

- Mike West (Google Chrome)

- Jeffrey Yasskin (Google Chrome)

- Benjamin VanderSloot (Mozilla)

- Christine Runnegar (Privacy WG co-chair, invited expert)

- Johann Hofmann (Google Chrome)

Apologies: 

- 

Chair: Nick Doty

Scribe: Mike West

## Agenda

### 1. Introductions, Code of Conduct

[Positive Work Environment at W3C: Code of Conduct](https://www.w3.org/policies/code-of-conduct/)

[Introductions, going around the room]

Trying w3.org etherpad!

### [Mitigating Browser Fingerprinting]([GitHub - w3c/fingerprinting-guidance: What is browser fingerprinting and how should specification authors address it.](https://github.com/w3c/fingerprinting-guidance))

    * status update, ready to start publishing as Working Group Note?

    Editor's draft: [Mitigating Browser Fingerprinting in Web Specifications](https://w3c.github.io/fingerprinting-guidance/)

Nick Doty: There's a Privacy IG note. Somewhat out of date. Might be worth updating the ED, fixing some bugs, etc. Is this ready to publish this as a WG Note? Do we have the right issues? Volunteers?

Christine: Was an IG note first, I second bringing it into this group, publishing FPWD.

Tom: I volunteer to help, support adoption. Randomization, for instance, could be improved as well as updating references

Nick: Implementer experience in the recent past might indeed change some of our recommendations. Would be ideal to bring that into the document.

Pete: I volunteer as well.

Nick: Great. Also separate threads with folks not on this call who might be able to help. Other issues? Are we ready to publish as a group Note?

Pete: Motion to publish.

Nick: Happy to autopublish? Hopefully it'll improve as we work through each issue, and since not recommendation track, should be fine. Open PRs to make that work from plh?

plh: I can update the PR and work the magic to get this published.

Tom: Is it best to start an issue with suggested text, or just send PRs?

plh: Make sure there's an issue that describes the problem you're fixing, and then send PRs with text suggestions.

Nick: There might already be issues, so look through them. I think I'm hearing that we want to adopt/improve this document, and we want to autopublish it.

[Everyone ~loudly agrees]

Nick: PRs are great for randomization specifically, thanks Tom. Also talk with Matt F. at Apple.

### Privacy reviews: in progress or help needed

#### [WebRTC amendments]([WebRTC: Real-Time Communication in Browsers](https://www.w3.org/TR/2024/REC-webrtc-20241008/#proposed-amendments))

Pete: I gave this an initial read, I think it would be helpful to do a full review. I'm happy to work with anyone who wants to do that, would prefer not to take the lead on it.

Lola: Would someone be up for walking me through how to do a review?

Pete: Perfect, done.

[It's a plan.]

[for reference on reviews, from plh: [privacywg/howto-conduct-a-privacy-review.md at main · w3c/privacywg · GitHub](https://github.com/w3c/privacywg/blob/main/howto-conduct-a-privacy-review.md)]

#### [Verifiable Credentials prior to Rec transition]([Final Review Request of seven (7) W3C VCWG Specifications · Issue #153 · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues/153))

Nick: This is a transition to REC for a batch of documents. My understanding is that there aren't many changes from when we reviewed at CR. I'll look at this with Kyle (Brave).

#### Charters

plh: Are we interested in looking at the following charters?

    * Web Fonts   [[wg/webfonts] WebFonts Working Group Recharter · Issue #486 · w3c/strategy · GitHub](https://github.com/w3c/strategy/issues/486)

    * Timed Text [[wg/ttwg] Timed Text Working Group Charter · Issue #487 · w3c/strategy · GitHub](https://github.com/w3c/strategy/issues/487)

    * Web Machine Learning [[wg/webmachinelearning] Web Machine Learning Working Group Charter · Issue #488 · w3c/strategy · GitHub](https://github.com/w3c/strategy/issues/488)

    * Web Payments Security IG [[ig/securepay] Web Payment Security Interest Group Charter · Issue #491 · w3c/strategy · GitHub](https://github.com/w3c/strategy/issues/491)

plh: We're reasonably up to date on the ML work. Fonts is less clear to me. Again, just reviewing charter, not the specs.

Pete: I looked at each of these, except Payments. They looked fine. I don't think they need a deeper review. Also: Timed Text seems to have generated their diff backwards, which was confusing.

Nick: Folks should feel free to follow those links, but doesn't seem like we should assign anyone.

### GPC

Nick: Three PRs and one issue if we have time:

#### [privacy and security considerations]([Issue 84 privacy and security considerations by SebastianZimmeck · Pull Request #89 · w3c/gpc · GitHub](https://github.com/w3c/gpc/pull/89))

Sebastian: There was already a privacy considerations section. I polished that. For security considerations, I added one sentence: "There are no known security impacts of the features in this specification." Privacy is substantively unchanged: exposing the user preference divides users into two groups, etc. Debated including private mode, had a discussion with Pete, decided not to do that.

Lola: Did anyone look at the security impacts here?

Sebastian: I looked through the review document, went through all the items, and none seemed to apply.

Pete: Security & Privacy questionnaire. [Self-Review Questionnaire: Security and Privacy](https://www.w3.org/TR/security-privacy-questionnaire/)

Nick: Useful to talk about correlation between signals. I wonder whether we should give guidance about not having many similar signals that can be independently configured. Setting GPC and DNT separately, for instance.

Pete: Good point. I suggest not putting that in the GPC document, but in the fingerprinting guidance doc. Thinking back to TPAC about generating a taxonomy of fingerprinting concerns.

Lola: DNT wasn't successful, GPC aims to improve on it. Any advice for browsers/web app developers on deprecating DNT and just using GPC?

Nick: Interesting question, not yet answered.

Jeffrey: Browsers are already moving towards deprecating DNT. Not much action needed. Also, to Pete's point: we should put the advice in both places. General advice, and pointing back to it in specific cases.

Ben: Firefox shipped GPC, trying to navigate the impedence mismatch between the two. We've removed the DNT checkbox, thinking through what to do with it and GPC.

Nick: From a fingerprinting perspective, it doesn't matter whether it's set to something constant or not there at all.

Ben: Our experience is that users touching one would almost always touch the other as well.

plh: We have a deprecated note on our DNT website. Perhaps we should more strongly point to GPC?

Nick: I think we're saying: I should open an issue on the fingerprinting guidance about multiple controls: deprecate or correllate signals like DNT. and an issue/PR on the GPC spec.

plh: DNT is not a REC, working group Note because abandoned.

Nick: Sure. We'd update that doc once we have something else recommended.

plh: We don't have to wait.

Sebastian: All this sounds good to me. Should we do this work in the current PR, or a new PR for the new issue?

Nick: Sebastian's PR is an improvement, we should merge it. I'll open the issue and send out a small PR.

Jeffrey: Reading process: we don't have a way to recind a note. CR can turn into "discontinued drafts", I don't think we have the same for Notes.

plh: We can put a label on the DNT note, that's the right thing for web developers. Not talking about changing the content, just putting a warning on it. Strictly speaking, the team doesn't need this WG to approve that but we'd like the input here.

Nick: I think there are people using DNT. Not sure I'd say "Go away, don't look at this document." There are reliance impacts.

plh: we'll run by the group the warning we'd like to put at the top. We can tweak it.

Ben: Within the last year or two, a German court did uphold DNT, so there are reliance interests.

[Tara: adding reference -- potentially this case?: [German court affirms legal significance of 'Do Not Track' signals in LinkedIn case | Digital Watch Observatory](https://dig.watch/updates/german-court-affirms-legal-significance-of-do-not-track-signals-in-linkedin-case)]

Nick: There are steps there, leave it to plh to come back.

#### [overriding consent]([Update Explainer to add new 6.4 (Consent to Track Notwithstanding a Universal GPC Signal) by j-br0 · Pull Request #88 · w3c/gpc · GitHub](https://github.com/w3c/gpc/pull/88))

Justin: GPC goes out to the world, but perhaps there's a side agreement to override it. Laws have implications here on the ways you can ask, etc. Resolution to put language into the explainer, tweaked the PR a bit. Have also added some language to the spec itself in response to feedback. Again, matter of state/other law about when you can get a side agreement. Two states recognized GPC since we last met: 4 states in the US, all doing things in slightly different ways for better or worse. Happy to further revise guidance as folks wish.

Nick: Positive reviews on GitHub.

Michael Kleber: My comment is not really about side agreements, but the wording: there's a new section in this PR: title is "consent to track", first line is "do not sell or share preference", first line of explainer is "sold or shared or used for targeted advertising". Different interpretations of GPC: long standing issues 51, 52, focused on being more clear about one interpretation. Would be helpful to keep one way to describe the signal and use it consistently. Different meaning in different locations might make this difficult: 4 different states, 4 interpretations? So, for this particular PR (88), would be ideal to have fewer new statements of what GPC means.

Nick: It's come up sometimes that we're using a shorthand, it would be good to be consistent.

Justin: Text I was adding wasn't related to this particular problem. I hear what you're saying, though. There's nuance. I think it would be tedious to say every single time that it's "sold or shared or cross-context targeted advertising". I do want to be clear and precise. I don't have a fix right now, but happy to take it as an action item. Probably should come back to the broader issues. This PR addresses the side agreement issue, I'd like to merge it, and separately deal with the concern you're raising.

Michael Kleber: We could change the section name in this PR, as it seems like an ambiguity we could address here. "Consent to Use Data" might be better, as it avoids making GPC be about "tracking" and not the other things.

Christine: Readability is important. Perhaps we can define it carefully in one place, and reference that throughout, perhaps as "the preference".

Nick: "Consent notwithstanding"? Consent needs to be quite specific, but we don't have to say what you're consenting to in the title of the section.

Justin: "Consent to disregard GPC"? "Consent notwithstanding" is vague... Don't feel strongly, could live with it's poetry. But "disregard GPC" might be good enough. Happy to work through this offline.

Nick: "Consent to share notwithstanding". But maybe we just let the editor edit. My impression is that we support the PR modulo this concern, editors can take care of that.

#### [ready to start publishing the Explainer?]([Rename explainer by j-br0 · Pull Request #90 · w3c/gpc · GitHub](https://github.com/w3c/gpc/pull/90))

Nick: Should we publish the explainer?

Justin: I think we agreed to have legal discussion in the explainer. Also: is "explainer" the right word. "Legal and Implementation Considerations Guide guide"? Right now, the links within the spec are broken, still pointing to old repository. I think W3C staff wanted some other repository? Where should this guide live?

Ben: It may be useful to put a minimal explainer in place once we move the Guide elsewhere.

[Jeffrey pointed to TAG explainer guidelines: [Explainers](https://tag.w3.org/explainers/)]

plh: Depends on Justin and Sebastian. Easiest to have one repo per document. Two goals: if the document is useful enough to be linked from the spec, we should make it a stand-alone thing. Second thing, we could move the legal guidance there rather than continuing to update the specification. I'd recommend multiple repositories, that seems easier, but up to the editors.

Jeffrey: It sounds like the idea is to make the Guide a Group Note.

Nick: Yes, that's what we've discussed previously. A separate document that can be cited.

Jeffrey: Making it a note means we need consensus on the document. I think we'd want to ask lawyers to review it. Draft Note is fine, of course, doesn't require consensus. But puts us on track to ask for more formal review. Probably a good idea. Also: separate repository means that PR Preview works, everything else handles multiple documents in one repo fine.

Nick: Draft Note? Sounds reasonable to me as text we can refer to.

Sebastian: Sounds good to me. One consideration: if we have a draft note, does that put us on track towards a real note? As for lawyers, we should have an idea of what that review would look like before committing to go that route.

plh: I don't think we need lawyers to review this document. Hard to get answers. Should invite comments, certainly.

Jeffrey: This will require consensus, which means Google as an entity will need to agree, will ask lawyers internally.

Justin: This is an informal document. Explainer. "Here's the deal. There are legal issues." We're not going to give universal overviews of what GPC means in various jurisdictions. Leaving this as an unofficial "Hey, if you're new, these are the general legal authorities. Go talk to lawyers."

plh: We're linking to this doc from the spec?

Justin: Yes, we are.

plh: Do we want people to look at the doc or not?

Aram: Why would it be markdown linked from the doc, or an explainer that's rendered into HTML, make it less likely that people look at it than a formally published note.

plh: Notes reference from the doc carry more weight.

Aram: Do you feel that it would be a blocker to getting the REC advanced if it links to something other than a formal note?

plh: Maybe? Hard to predict.

Aram: Until someone comes to us and says "We can't advance this because this link isn't a Note.", we should resist changing its status.

Nick: Running out of time.

Christine: Let's postpone what kind of document this is, let's instead get happy with the content. Happy to help with the doc.

Nick: PR that tries to change the name of the doc. Now we have questions about whether this is legal advice. Editor says no. I think that's the answer we want. Getting reviews on the PR, positive on that. Not legal advice. Do need to figure out the document status, will do that later.

#### if time, [handling private browsing mode]([Private mode/incognito · Issue #34 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/34))

[Didn't get to this, look at it offline!]

See you Feb. 6th!
