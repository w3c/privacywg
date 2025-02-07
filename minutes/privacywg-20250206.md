# Privacy Working Group meeting - 6 February 2025

## Attendees

- Nick Doty (CDT, PrivacyWG co-chair)

- Pete Snyder (Brave, PrivacyWG co-chair)

- Tom Ritter (Mozilla)

- Christine Runnegar (co-chair, invited guest)

- Tara Whalen (W3C)

- Stalgia Grigg (Bocoup)

- Chris Cuellar (Bocoup)

- Sebastian Zimmeck (Wesleyan University, invited expert)

- Jeffrey Yasskin (Google Chrome)

- Chris Needham (BBC)

- Joey Stanford (invited expert)

- Justin Brookman (CR, invited expert)

- Johann Hofmann (Google Chrome)

- Aram Zucker-Scharff
  
  

Apologies: 

* none
  
  

Chair: Nick Doty

Scribe: Jeffrey Yasskin

## Agenda

### Introductions, Code of Conduct

[Positive Work Environment at W3C: Code of Conduct](https://www.w3.org/policies/code-of-conduct/) - Please get consent before adding transcription bots.

[Introductions, going around the room]

Trying w3.org etherpad (for second time, has been stable so far)

### Privacy reviews:

#### WebRTC (thanks Pete and Lola),

    [WebRTC API 2024-10-12 &gt; 2025-01-31 · Issue #152 · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues/152)

Pete: Review mostly done by Lola. The changes are odds-and-ends. No serious privacy concerns. 2 non-blocking concerns:

    1. Default about WebRTC over global or local connections. Seems to have changed; will follow up.

    2. Additional complexity on the platform: can pass channels between workers. Not as broad as I'd initially thought, but it's a new annotation in the WebIDL space. Is the complexity needed? Not a privacy concern, but rather about platform complexity.

Pete: Will work with Lola to file issues after the meeting.

#### Verifiable Credentials (pending Kyle and Nick)

    [Final Review Request of seven (7) W3C VCWG Specifications · Issue #153 · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues/153)

Nick: 7 CRs trying to go to PR. Want re-reviews. Not large changes, but some changes. We haven't gotten to this review, but they're hoping to go to PR in Feb. 

Jeffrey: There were privacy issues on the previous CR; this would be a good time to check they're fixed.

Nick: AI for me.

#### New request on WebAudio Playout Statistics

[Playout Statistics API for WebAudio 2025-01-31 &gt; 2025-03-01 · Issue #154 · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues/154)

Christine: I had a quick look. Early stage, but the TAG has asked the group to get a privacy review. They've done the self-review, but haven't written Privacy & Security Considerations. I'm not an expert in this technology. From a glance, could be fingerprinting issues. Would be good for someone to look closer. First suggestion is to contratulate on doing the Questionnaire, then ask them to write the Considerations, with pointers for things to look at.

Aram: Volunteer! I'm familiar with the underlying WebAudio technology.

Tom: Is it fine to leave a drive-by comment?

Nick: Absolutely.

Jeffrey: It's sometimes unclear to groups whether reviews are individual or group consensus, so make that clear, but please do send individual reviews.

Nick: It's useful to bring it back for discussion. No formal calls for consensus.

### Global Privacy Control:

#### Quick summary of PRs

Justin: 6 open PRs: [Pull requests · w3c/gpc · GitHub](https://github.com/w3c/gpc/pulls). I'll cover 5.

* #88: If you have specific consent, can sometimes disregard GPC. We're almost done. One outstanding comment about adding the Legal Guide to the biblio.

* A year ago we created the explainer as an FYI talking about the purpose and intersections with laws. We discussed renaming this to the Legal and Implementation Considerations Guide. PR changes name. We'd talked about turning this into a Note, which has some meaning within W3C. Discussion last time indicated we should leave it as an informal reference for now. Should review and close.

Christine: Changing the name to "Legal and Implementation Considerations Guide"?

Justin: Yes.

Christine: "Legal Issues and Implementation Considerations Guide"?

Justin: Will talk with other editors.

Nick: The PR now has text saying that it's not legal advice, right?

Justin: Yes.

* Jeffrey created a PR to enable PR-Preview. None of the editors are familiar, but don't know enough about it.

Jeffrey: should be enough to enable it. in every PR that changes the particular document, it will create links to preview the change with a diff view. also helps catch issues with formatting.

* #95: Update legal changes: goal of having this document is to update as legal guidance comes out over time. 2 more states said GPC has legal meaning in those states, so added a sentence saying that. Pointed to guidance from those states. 

    * [private mode issue]([Private mode/incognito · Issue #34 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/34)) / [pr]([Update Legal and Implementation Considerations Guide to reference private browsing/incognito mode. by j-br0 · Pull Request #96 · w3c/gpc · GitHub](https://github.com/w3c/gpc/pull/96))

Justin: Long-standing issue. If I turn on Incognito, how does that affect GPC? General sense is that it depends on the UA. We don't dictate the UI. I added a couple sentences to the Legal and Implementation Considerations Guide saying that if it seems appropriate, you can send it.

Christine: Text looks fine to me. Wondering whether we should or shouldn't add something like "browsers should explain whether their private browsing mode does or doesn't send the signal." Encourage browsers to be transparent. Could confuse users otherwise. Users might assume both directions otherwise.

Justin: Different states have different requirements. E.g. Colorado says you have to say something in the documentation. A lot of Incognito mode pages have legalese which people may not read.

Sebastian: Did you have browser UI in mind? 

Christine: I don't want to say how it should be implemented. But since we're saying it could be implemented differently, add a short note about being transparent with users about how it's implemented in this context, as a reminder. 

Justin: I'll add a sentence, and people can review.

Nick: Part of why this came up, and why we recommend why all people consider how the feature should work in Private Browsing Mode, is to thing about whether this might disrupt Private Browsing by saving local state, or needing some other user consent step. We should say we think we don't have any issues like that. And also that UAs might think they should send GPC in private browsing mode, and we're not expressing an opinion on that.

Justin: Yes.

### Mitigating Browser Fingerprinting:

Nick: Tom has stepped up with issues and PRs. Thank you! 2 PRs worth looking at.

    * quick summary of PRs

    [Pull requests · w3c/fingerprinting-guidance · GitHub](https://github.com/w3c/fingerprinting-guidance/pulls)

Tom: 1: General wordsmithing emphasizing that fingerprinting is a threat, and removing ambiguous language from 10 years ago. CSS-based fingerprinting. Changes that happened over time.

Tom: 2: Ephemeral fingerprinting: that independent tabs can correlate your session by monitoring events that are happening at the same time (e.g. a webcam was plugged in). Explaining that this threat model isn't usually a concern, and we're mentioning it here. And some open issues.

Nick: I've reviewed modernization, and Mike West reviewed ephemeral fingerprinting. I think we can go ahead and merge them.

Jeffrey: we know how to solve ephemeral fingerprinting by only sending events when the tab has focus

Tom: feel like that's usually correct, but not certain. refers to "visible"

Jeffrey: could be more specific than "visible". will review and coordinate with TAG documents.

Tom: Issue #70: suggesting that we split a best practice. Want people's general thoughts.

[Adjust the organization of BPs and split one into two. · Issue #70 · w3c/fingerprinting-guidance · GitHub](https://github.com/w3c/fingerprinting-guidance/issues/70)

Pete: I'll also review open issues

Jeffrey: Make Tom an editor?

Nick: Sounds reasonable. Tom, are you willing?

Tom: Sure. I also owe a PR about randomization.

### Confirming publication decision

Nick: We sent a call for consensus on the mailing list. Mark Nottingham raised questions for auto-publishing and approval. A couple meetings ago, we talked about using auto-publication, so people who go to the TR get the latest content, without separate calls for consensus. We do get reviews. And as a backstop, we should look at every document as a group, to make sure editors and reviewers haven't gotten us going down the wrong track. Wanted to check with this group if we think that's right.

Jeffrey: more serious group out of consensus issue is that documents get out of date.

Chris N: Per W3C process, editors are required to reflect group consensus. As PRs get merged, they should be in a state where they reflect consensus.

Nick: Are we formalizing the step of getting consensus. Editors take direction from the group, get people to review PRs. Suggesting that we don't need a formal call for consensus.

Nick: I think we have support for that. Will ask to publish and auto-publish. And we can also continuously revise this. If PRs are getting merged that we don't like, we can change this at any time. Chairs welcome people raising concerns.

### AOB

Nick: Bocoup: Interop process?

Chris C: Bocoup has been participating in Interop for some years; helped get it going. Relevant to this group is that there's a new Investigation Area in the privacy sphere in Interop 2025. Interop is the process where browser vendors prioritize increasing interoperability of various features across the web. Arduous consensus process each year. Lots of discussion, then a vote. This year there was a championing process, and Bocoup championed the Privacy investigation. Announcement next week. That means a way for folks to propose guidance for browser vendors on how to include test coverage for privacy features. Goal is to ensure that browsers implement privacy features in an interoperable way. It's an investigation because we're not entirely sure what tests to write.

Nick: Haven't talked as much about testing in this group as perrhaps we should.

Jeffrey: Sent an email about TAG design principals, called "Privacy design principals for web protocols" . What should we do about it? Seems like "Privacy Principles" document can replace it, but would be good to get more thoughts.

Nick: We ought to at least direct people looking at the earlier document (which is not being worked on) to "Privacy Principles" (which is being worked on). That document was largely a reference/version of RFC 6973, which is another useful reference.


