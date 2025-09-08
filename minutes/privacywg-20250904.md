# Privacy Working Group, 4 September 2025

## Attendees

1. Nick Doty (CDT)

2. Tara Whalen (W3C)

3. Sebastian Zimmeck (Wesleyan University)

4. Benjamin VanderSloot (Mozilla)

5.  Charlie Harrison (Google Chrome)

6. Michael Kleber (Google Chrome)

7. Jeffrey Yasskin (Google Chrome)

8. Christine Runnegar (co-chair, invited expert)

Apologies: 

    * Pete

    * Joey

Chair: Nick Doty, with Tara as backup

Scribe: Christine

# Agenda

1. Introductions, Code of Conduct

2. Guidance or experience on cross-site data mechanisms (via w3ctag)

3. Differential privacy guidance

4. Fingerprinting status

5. GPC status check

6. Group charters for review

7. Open privacy reviews (geolocation update)

8. AOB

# Notes

1. Introductions, Code of Conduct

[Positive Work Environment at W3C: Code of Conduct](https://www.w3.org/policies/code-of-conduct/)

Nick gave an example of careful and sensitive sharing of educational material

2. guidance or experience on cross-site data mechanisms (via w3ctag)

Nick: TAG has been receiving reviews that raise these issues

Jeffrey:

Previous TAG discussion: [meetings/2025/telcons/08-11-minutes.md at gh-pages · w3ctag/meetings · GitHub](https://github.com/w3ctag/meetings/blob/gh-pages/2025/telcons/08-11-minutes.md#third-party-cookie-replacements-with-nick-doty)

- related website sets

- webauthn (related origins, the ability to authenticate with the same credential; also iframe login)

- Request Storage Access

- Fed CM

Jeffrey: how to do this well, what guardrails need to be in place for it to be appropriate, how can TAG inforce and escalate to this group

Nick: met with WebAuthn re: related origins, group is convinced the feature is needed, already in password managers work flow, not open to limiting feature, but useful to have more feedback on guidance/requirement re: ensuring that related websites are in fact related, there were some ideas in first party sets, we don't often have requirements on this, different from password manager case (acting for user)

We also heard that it will be up to the browser to inform users that data would be shared with two sites if use this feature, concerns about number of pop-ups/notifications that displayed to users, whether they read them

Does anyone have any ideas to contribute?

Jeffrey: request storage access is another e.g., where the only protection for the user is a permission; also anti-fraud considerations in this space, also FedCM UI might be effective, could be that different protections may be appropriate for different APIs

Ben: for WebAuthn and related websites - there is "at most one set" for each origin - doesn't work with request storage access API because e.g., Spotify embed might ask login to load full song or preview, so "belong to exactly one"" doesn't really work

Nick: could this be used by tracking network for pervasive cookie-style tracking? But another threat is that a user might try to log in and not realise that logging in links their accounts over two websites. On WebAuthn there is a cross-origin ability that can request passkey usage, it is not partitioned, log into embedded website and maybe they share more than users might expect

Lola: When we discussed in TAG, we agreed it might be helpful to have a label for these features when they pop up, would that still be useful? 

Nick: I still think a list would be useful, we should try to provide feedback on privacy considerations on a case-by-case basis, but hopefully also some general guidance when we learn what works and does not work

Lola: TAG wants to ensure that there is guidance, because we have received quite a few of these, perhaps as part of PING review, should come before or at the same time as TAG

Christine: security/privacy questionnaire could be one place for that guidance

Nick: hopefully the questionnaire is catching those kinds of cases. If not, it should be.

Lola: I can create a label on TAG side to track, after our face to face meeting

Nick: other ideas for guidance? Thanks to TAG for talking about the issue, please share your list with us for feedback and for developing more general advice

3. differential privacy guidance

Nick - Pete is not able to be here, there is a document that has received some feedback, we can discuss now or at a future call

Decided to move to a call when Pete can be available

4. fingerprinting status 

[GitHub - w3c/fingerprinting-guidance: What is browser fingerprinting and how should specification authors address it.](https://github.com/w3c/fingerprinting-guidance/)

Nick - there is a draft that Nick started editing, but now most of the work is being done by Tom. There are a couple of PRs that need review, Nick approved one re: minimising entropy or surface, distinguishing best practices. Pete is working with Tom on randomization for fingerprinting mitigation

5. GPC status check

Sebastian: not a lot to report - discussed the scope earlier, and we are close to converging on a solution

[Clarify scope of GPC by j-br0 · Pull Request #99 · w3c/gpc · GitHub](https://github.com/w3c/gpc/pull/99)

There is another small issue - [Weak requirements language · Issue #35 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/35) - the statement is not very meanginful, so a small tweak to refer to legal materials

At our next meeting, we will have suggestions for that issue.

Michael: [Edit to spec to clarify scope by j-br0 · Pull Request #107 · w3c/gpc · GitHub](https://github.com/w3c/gpc/pull/107) - was merged since we last talked, I think there was one thing we discussed in May that did not make it into the PR, is clarification needed? It is the cross-context ad targeting issue and to say explictly excludes same-site targeting - I think we had agreement on this in May, but I don't see this reflected in the PR

Sebastian: if I recall correctly, we discussed first bringing into PR and then make changes later on - we are on the same page, but I think this happened here - what is the best way forward? new comment? new issue?

Michael: you can make the call on how to track

Sebastian: Please add comment to PR 99

Michael: This is discussed in open Issue 94 [Consistency in use of sell/share/track/target terminology · Issue #94 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/94), I will comment there.

6. group charters for review

PNG Working Group Charter: [GitHub · Where software is built](https://github.com/w3cping/privacy-request/issues/171)

Tara: came in last week for review, includes improvements for high dynamic range, and potential to add metadata, needs a review

Christine: anytime possible addition of metadata, risks of fingerprinting and other privacy concerns, would need to be considered very carefully and should be recognised in the charter

7. open privacy reviews (geolocation update)

Screen Orientation: [Screen Orientation 2025-09-04 &gt; 2025-10-16 · Issue #173 · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues/173)

Christine: only mitigations seem to be MAY, could we find some privacy mitigations that could be implemented?

Ben: volunteers to review

Geolocation: [Geolocation 2025-09-01 &gt; 2025-10-02 · Issue #172 · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues/172)

Tara: looking for a reviewer

Christine: find a reviewer on #privacyreviews

8. AOB

Jeffrey: DID methods charter is open for review (reminder)

# 
