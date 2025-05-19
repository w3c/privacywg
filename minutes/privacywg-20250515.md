# Privacy Working Group, 15 May 2025

## Attendees

1. Christine Runnegar (co-chair)

2. Justin Brookman (Consumer Reports)

3. Michael Kleber (Google Chrome)

4. Chris Cuellar (Bocoup)

5. Chris Needham (BBC)

6. Nick Doty (CDT)

7. Pete Snyder (Brave Software)

8. Sebastian Zimmeck (Wesleyan University)

9. Jeffrey Yasskin (Google Chrome)

10. Lubna Dajani (Alternet)

11. David Dabbs (Epsilon)

12. Benjamin VanderSloot (Mozilla)

13. Stalgia Grigg (Bocoup)

14. Ari Chivukula (Google Chrome)

15. Don Marti (Raptive)

16. Aram Zucker-Scharff (The Washington Post)

17. Tara Whalen (W3C)

Apologies:  none



Chair: Nick Doty

Scribe: Christine Runnegar

## Agenda

### Introductions, Code of Conduct

[Positive Work Environment at W3C: Code of Conduct](https://www.w3.org/policies/code-of-conduct/)

> Think of others’ needs from their point of view. Use preferred names, titles (including pronouns), and the appropriate tone of voice. Therefore, be formal and conservative in what you do and liberal in what you accept from others and acknowledge the contributions of your peers.     

No new introductions, today     

### Reviews

#### Web Neural Network API

-  [Web Neural Network API 2025-03-20 &gt; 2025-06-20 · Issue #156 · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues/156) @sandandsnow

Christine: a specification that we have reviewed before, just doing updates. two things to highlight:

    1. As a result of previous privacy review, device type preference. Application's preference for what kind of device is used for computation. In this iteration, the device type abstraction was removed to mitigate the issue we had identified.

    2. Highlighted changes to the API allow developers to probe feature support per operator, know in advance what is the optimal model architecture. 'Roughly' corresponds to the OS/browser version, so they don't believe it adds to the entropy. Feature support can be inferred from OS/browser version, but explicit method is more convenient for developers. Does include an extension point for privacy controls if that's needed in the future, in case the ecosystem became diversified. Doesn't create extra entropy at this point.

    Nick: WG tend to say no risk because it is what the browser supports anyway, but maybe we need something specific, so this is just a convenience method for browser and OS, does someone have suggested language

    Pete: Capability guidance is available, just because 1:1 correlation now, doesn't mean it will always be the case, concerned about the approach that is being taken, happy to work with the authors

    Jeffrey: Try to discuss this in info access in privacy principles, but lost the bit about 'it is okay if equivalent to the browser version', people should be looking at the document, and as needed send patches to privacy principles document

    Nick: Maybe we can figure out what needs to be said and then figure out where it needs to go

#### News: Privacy Principles Statement issued

    Tara: Privacy principles are a [statement]([Privacy Principles](https://www.w3.org/TR/privacy-principles/)) today, yay!

    Nick: Congrats! Quite useful to be able to cite things like this

    Pete: Relevant to see design principles [Web Platform Design Principles](https://www.w3.org/TR/design-principles/#device-apis)

#### WebAuthn

-  [Web Authentication 2025-04-24 &gt; 2025-05-25 · Issue #162 · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues/162)

Nick: We have a request for review of Level 3, not sure if we did a formal privacy review of earlier versions, but Privacy was part of discussions as it was developed, relevant to consider what is revealed when doing web authentication. (Nick provided an overview web authentication passkeys)

Questions about what can be revealed before a user goes through a ceremony, e.g., can I do a cross-device passkey? Also, consider privacy implications of attestations related to particular devices (e.g. which version of a security key), tells the site something about the maker and batch of the keys, which a user may not realise, attestation has been discussed but getclientcapabilities is quite new, also comes up in digital credential work (feature detection), Nick will review, does anyone else want to review?

Pete: Lots of things do passkeys that are not browsers, don't see how it can possibly map just on to UA

Nick: Maybe they want extensions, will add to review and share with the group

#### GPC

* [w3c/gpc#6]([Use HTTP structured field values · Issue #6 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/6))

Sebastian: issue about format of GPC header, namely, some people feel we have discussed sufficiently and reached the conclusion to keep the format as is, but others may not, so we wanted to bring it up here for explicit discussion in a WG call.

Nick: it looks like the editors closed issue, but one person raised concerns

Jeffrey: I continue to think that the structure of header is not quite right, see issue 51, if go that direction, take a different name, just a "1". think time to probably close issue 6, need a more complicated structure for support for other privacy laws

Pete: among us, our goal is not extensibility, just this (boolean, yes or no)

Justin: this has legal effect in lots of places now and have enforcement actions now, worry about changing structure radically, rather than whether the issue is extensibility or not

Ben: I agree with Jeffrey's assessment, a different name

Don: from a practical implementation point of view, for millions of users, for all but largest implementers, is a 50-state compliance program rather than 50 Jira tickets, extensibility looks like a time suck, keep header simple and manageable for small and medium sites

Nick: hearing that there is consensus to close 6 - would break compatibility with deployment, will add a note in Github, do we feel we need a consensus call on email?

Aram: large attendance today, I feel we can close it

Decision: close issue 6 (any objections can be raised on email)

* [w3c/gpc#103]([Meaning of `lastUpdate` for &quot;strange&quot; dates · Issue #103 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/103))

Sebastian: re: last update field, issue about the date in spec being 1997 when gpc did not exist; I didn't think too much about it, agree not a realistic date, but I would pick a date when gpc existed, to a time after gpc is created, we could write more substantively, limits to dates (which we allow and do not allow), not a big deal so don't need to write much

Aram: lastUpdate signals that it's when the file was updated, not a compliance argument about the status of the standard. implementers could make a mistake when updating the file, but it doesn't seem ambiguous.

Chris: text indicates more, that it does signal that future changes to GPC don't correspond to what the implementer is doing.

Aram: 'statement of support' is a reference to the JSON file being updated. not a spec need, just a potential implementation bug. could clarify that it's update to the JSON?

Chris: example should be changed. whether we should have versioning of the spec is separate future question.

Michael: bad text is copied and pasted from the example in the spec. [Global Privacy Control (GPC)](https://w3c.github.io/gpc/#gpc-support-representation) 

Aram: let's update the example to reflect a realistic date.

Nick: sometimes examples are wrong intentionally because we want people to fill in their data, not rely on what's in the spec.

Aram: we probably do want people to just use the current date from when they copied and pasted.

Ben: either build date, or 1970-01-01.

* [w3c/gpc#94]([Consistency in use of sell/share/track/target terminology · Issue #94 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/94)),  [w3c/gpc#102]([Align all descriptions of GPC to say it&#39;s meant to restrict sale and sharing of data. by jyasskin · Pull Request #102 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/102)), [w3c/gpc#104](https://github.com/w3c/gpc/issues/104) -- brief check-in

Justin: issue raised by Michael K about characterizing exact scope of GPC. 'do not sell or share' is the shorthand but could be interpreted in different ways. not possible to specify every scenario. but this issue was to use clear language in the spec.

Jeffrey has a couple PRs on this.

Justin: laws have referred to cross-context behavioral advertising. Jeffrey also had an alternative to refer to cross-organizational targeted advertising, which is more specific to Colorado. more consistent to what GPC would do, narrowed to what is in Colorado. some states have laws that go beyond organization -- distinctly branded websites owned by the same parent company would be opted out. could be an edge case for a state that has a global opt out law that does include opting out.

Jeffrey: pointer to state law that discussed branding (not currently mentioned in the spec/explainer)

Ben: 'organization' is ambiguous, because of parent company, branding, etc. ambiguity is probably a good thing because state laws will need to figure it out. Mozilla uses similar ambiguity in its language.

Michael: not hoping for precision about details of what GPC does, given the different laws in different states. unfortunate and painful but the world that we live in. my goal is for the browser giving a checkbox to the user is to help the user be somewhat well-informed when they make the choice that they do. give a basic coherent meaning for presentation to the user. we hope (as discussed in previous calls) that that could help guide regulators -- we can't tie regulators' hands, but clarity about what the user is told can make regulators know. don't need to specify the UI string, different browsers will choose different UI, but hopefully something similar in the spec. think this is different from discussion on issue 52. would like to pick something more specific and language that aligns with state laws, and then not change it in the future.

Aram: use definitions we use in privacy principles and other groups, cross-context and cross-site are defined. cross-organization would be new.

Michael: should tell the user what's accurate to the extent possible, so shouldn't make own definitions.

Aram: spec not speaking to the user, but the implementer. don't have to define user-facing language. light and dark mode is left up to implementers.

Nick trying to shorten long conversations.

Sebastian: could use shorter more general language (e.g., "claim right to opt out"). going deeper with more technical terms as they are used in laws is not going to help

Justin: edits to spec in 2022 were interpretations of law, editorial decisions reflected in explainer. if we took away all that language it would create more uncertainty. agreed on what it's trying to do, so engage to the extent we can.

Don: First Party Sets/Related Website Sets project. lots of problems with using 'organization' as a concept. will share links

Lola: while specifications traditionally written for implementers as key audience, not always exclusively the case. other people read them too, even though users don't read them. there is a documentation process for translating it for being comprehensible to users.

#### AOB

Agenda gathering issue, let's try to get items ahead of time so we know what will be discussed.

Continuing conversation on Slack and Github.
