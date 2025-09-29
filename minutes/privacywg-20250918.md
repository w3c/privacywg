# Privacy Working Group, 18 September 2025

## Attendees

1. Nick Doty (CDT)

2. Joey Stanford (Invited)

3. Ben VanderSloot (Mozilla)

4. Pete Snyder (Brave)

5. Michael Kleber (Google Chrome)
   
   

Apologies: 

Charlie Harrison

Chair: Nick Doty 

Scribe: 

## Agenda

1. Introductions, Code of Conduct [Positive Work Environment at W3C: Code of Conduct](https://www.w3.org/policies/code-of-conduct/)

2. differential privacy doc (@pes10k @michaelkleber)

Pete: wording fixes on ambiguous language. Adding some text on epsilon and what role it plays in the system, along with a warning to not just latch on to that single number. Grateful for the feedback on Slack.

Current version of document:

[Considerations for Reviewing Differential Privacy Systems (for Non-Differential Privacy Experts) - Google Docs](https://docs.google.com/document/d/1pE3p6TVsERPln00PLXj6j9rTdoG3PmiNHhv3NtXDtEU/edit)

Pete: might be nice as a group note just so that it's in the W3C workspace. Just need to see if there's consensus in this group to adopt.

Kleber: suggest following up with Charlie Harrison who has particular expertise and feedback.

Pete: would need to add other authors as W3C members.

Nick: continue asynchronously, can check if we want a call for consensus on the privacywg mailing list

3. fingerprinting update (randomization @pes10k @tomrittervg)

completed Nick's review, reorganizing, now merged. Tom has been doing work on randomization. Pete will schedule his review of this.

4. privacy reviews 
- Screen Orientation (@bvandersloot-mozilla )

API to read the screen orientation and get event updates when the orientation changes, or locking the screen orientation, especially for full-screen web apps. Can also learn the "natural orientation" of the screen. Can learn how the user's display is configured. Some data might be leaked in a way you might not immediately expect. Privacy and security considerations describe different potential mitigations against fingerprinting: limits on sending of change events or not revealing the "natural orientation'" -- these are mitigations that MAY be done.

Filing issues on normative text mitigations (should/must, rather than may). Can probe whether the user allows website to lock orientation; should lock only when fullscreen. Also some issues on clarity, pre-lock conditions.

Pete: previously looked at folded screen API, Device Posture. Does this API have any reference to that?

Nick: ephemeral fingerprinting and firing events simultaneously in different frames/windows that can be used to correlate activity across contexts

Ben: gating on "visibility", but not entirely sure

Pete: do we have consistent terminology on top-level/focused/visible?

Ben: only top level is in the document to tease out the minimal scope

- DAPT

Pete: dubbing audio descriptions for ttml. Part of larger set of specs about subtitle/transcripts going along with media.

Nothing particularly privacy-relevant or new, so no notable concerns.

- WebAuthn (update)

Nick: not partitioned, using the same passkey when a cross-origin embedded iframe triggers a credential request.

Pete: there is some information present to help address partition-related

Nick: but these items are not intended to be utilized for partition-related protection. There maybe a significant privacy concern here because you may end up logging in with a passkey for a different, but related, account. Group thinks it's up to the browser to communicate this difference clearly.

Bi-directional, both the parent site and the child site have to be involved. But no hard requirement that an origin only appear in one.

Pete: unique security-relevant concept of an origin label (the name before the TLD). Doesn't seem like the right place for it.

- triage / closed out reviews

Pete: chairs looked at several charters and didn't notice larger issues: JSON-LD, Web and AI Interest Group (very early in its process), PNG, DID and DID-Methods, IMSC Profile

5. charters:
- WebExtensions

Very privacy relevant, but also novel -- not web sites but installed. Probably nothing special needed for the charter.

Standardizing existing surface area and APIs that are already implemented.

6. GPC (tentative)

Some PRs being worked on in github.

Nick to follow up with editors to see the plan for any outstanding issues before we move to next stage for the Rec track and explainer documents.

7. AOB

# 
