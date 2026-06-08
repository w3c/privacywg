# Privacy Working Group, 21 May 2026

## Attendees

1. Nick Doty (CDT)

2. Pete Snyder (Brave Software)

3. Ted Hardie (Invited Expert)

4. Christine Runnegar (co-chair, invited expert)

5. Sebastian Zimmeck (Wesleyan University, invited expert)

6. Benjamin VanderSloot (Mozilla)

7.  Justin Brookman (Consumer Reports, invited expert)

8.  Bhavani Shankar Garikapati (Invited Expert)

9. Matt Reynolds (Google)

10. Don Marti (Invited Expert)

11. Joey Stanford (invited) - Tardy

12. Alvin (Google)

13. Lola Odelola (Invited Expert)

14. James Rosewell (Movement for an Open Web)

15. Chris Needham (BBC)

Chair: Nick Doty

Scribe: Sebastian, with Shankar

# Agenda

## 1. Introductions, Code of Conduct

- Nick: All meetings held under W3C code of conduct. Everyone who participates is treated fairly and with respect. Let us know if there is an issue. For those who are new, feel free to introduce yourself. 

## 2. Privacy Reviews

- #### [MathML](https://github.com/w3c/mathml/issues/576)
  
  [@gbshankar](https://github.com/gbshankar): No blocker, but big scope than MathML Core that should be acknowledged in the document.  Privacy and Security Considerations should explicitly cover Full-only features rather than relying on MathML Core: especially intent, broad href, external annotation src, mglyph, and Content MathML identifiers.

- #### WebTransport follow-ups
  
  [@hardie](https://github.com/hardie) [@pes10k](https://github.com/pes10k): Notes from the meeting: [Notes - Privacy WG review of WebTransport - Google Doc](https://docs.google.com/document/d/1-2q6a8_qWlSVVEIj1l3U87HZRNvgGNICVLplF6xW4lI/edit?tab=t.0)
  
  Three issues were filed by the Web Transport folks.:
  
  - Pooling should require a strong secondKey in fetch's network partition key (fetch tracker)
  
  - Should WT pool with non-WT requests?
  
  - Pooled stats counters persist across session boundaries
  
  Ted: Peter and I met with the Web Transport folks and took the notes above. Seems it is progressing well. We can close out the issues once we know more. I also reached out to Will Law to work out the pooling issues that belong to the IETF..
  
  Nick: Transport session being keyed to pooling?
  
  Pete: On that specific questions, I am not sure if there would be consensus. Fixing the issue upstream would be ideal. Also, as a process matter, we should close out our issue. It is a tracking issue for a todo queue. So, it can be closed. The substantive issues live in the spec repo. They will be kept alive.

- #### [Open review requests](https://github.com/w3cping/privacy-request/issues)
  
  Nick: Speaking on the list of open issues, [Issues · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues). Looks like we can close out the transport protocol issues soon. We are also loooking for volunteers at the RDF working group. They have some updates. If anyone has experience or is interested, we are looking for volunteers there.

## 3. [Approximate Geolocation]([Approximate Geolocation: Permissions Model Comparison · w3c/geolocation Wiki · GitHub](https://github.com/w3c/geolocation/wiki/Approximate-Geolocation:-Permissions-Model-Comparison))

    @marcoscaceres @nondebug: 

Nick: There are specific revisions in progress now, following up on discussion of approximate geolocation ongoing for many many years. They are looking for input on permissions.

Matt: Approximate location as opposed to precise location. Question is how to structure the permissions and whether those should be visible to websites. This would enable the website to make decisions on their end. Protecting the users privacy vs functionality is the challenge that we want to resolve now. 

Ben: Exposing only the one permission, i.e., less information (passively) is the stronger option.

Matt: The scenarios are where sites rely on approximat location without the abiilty to verify that the platform already has the approximate location.The other situation is that there could be a delievery driver needing the precise location.

Ben: In the first case is this a question of no precise geolocation should ever not touch my JavaScript question?

Matt: Yes.

Ben: The latter one is what I am more concerned about.

Pete: My memory from several years back is that there was float 50% accurate, for example.

Matt: We would rather rely on the capabilities of the platforms, and generally you have a Boolean switch.

Nick: I have been talking about approximate location for some time. If we can use platform APIs, I get it. The issue is whether we can deploy it. This is an advantage in terms data minimization. The permission question is also an issue I raised in 2015:

- [Privacy concern with being able to discern that a permission is granted · Issue #52 · w3c/permissions · GitHub](https://github.com/w3c/permissions/issues/52)

- Querying a permission before asking for it, has some privacy implications. Users would not notice that that is happening. I do not think we should have the query functionality. Having more granularity is more harmful. Although, we should get rid of it, we should not make it more granular.

Joey: The webkit model is the better choice. Any script on the page can call that location and sites can chose the privacy-preserving tier. There is an on-change gap, which is solvable. Sites can just recall the API. Should have some normative guidance for randomizing the coordinates to prevent active inference attacks.

Nick: Fuzzing model may also be relevant.

Lola: How does the web user understand the difference between precise and approximate location? How to differentiate for the end user?

Matt: Visual representation with smaller and bigger circle similar to what is on Android.

James: How is risk of abuse assessed?

Matt: What do you mean?

James: What risk of abuse is a concern, and how to determine ...

Matt: For example, frequency of location estimates can become an issue. The attacker should not be able to overcome the lack of precision by querying multiple times.

James: Attacker mostly security and not privacy?

Matt: Both.

James: No major method of assessing abuse?

Matt: Not that I am aware.

Christine: Generally, it can be very difficult to estimate what exactly will be abused in terms of privacy. Also, is it even detectable? There are a number of technically informed non-profit groups that try to discover how potential security and privacy vulnerabilities are being abused in the wild. E.g., a group looked at earlier version of WebRTC that leaked the local IP address and demonstrated how that protocol was being abused by websites. Similarly with security risks. It is very difficult to have prescribed procedure for assessing the abuse. The risks posed by vulnerabilities is hard to estimate. The best we can do is to idenfity potential vulnerabilities and how they might be exploited, encourage research on how they are or may be exploited. This group is about mitigating the privacy risk in Web standards. 

James: Confirmation of not having one particular measure.

Nick: How should we handle this going forward?

Matt: We are going to bring this back to the spec reviewers.

Nick: Please feel free to let us know if there is more need for review. 

Ted: Is there an alternative for visually impaired?

Matt: Yes.

Nick: I think we have some useful academic research on geolocation fuzzing and potential abuses. that might not be a single value or number, but we have plenty of detail if we want to read and analyze it in the specs.

- threat analysis of GEOPRIV would be one place, RFC 3694: https://datatracker.ietf.org/doc/rfc3694/



4. 

## 4. GPC

 [Does the GPC Support Resource apply to origins or sites? · Issue #113 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/113)

 Justin: GPC has optional Well known resource, does it apply to domain, site, origin. We believe Origin makes sense. We are not changing the meaning of existing definition. 

Joey: origin-scoped semantics is correct choice, we will have issues with domain, where subdomain is compromised. 

- [Define the header value parser · Issue #114 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/114)

Peter: How much detail spec should provide on parsing the header. All spec are outside w3c.  Doesn't seem ideal. Looking for TAG guidance.

Lola: Can check with other TAG members, and get back on Friday.

Nick: definitely fine to reference (normatively) IETF and WHATWG specs if that seems the easiest.

Lola: comparision to other normative references?

Pete: just seemed especially detailed, maybe more than is necessary, or logistical concern about links breaking or not being maintained.

Ben: should be able to define it as structured field integer 1, with an easy link into that RFC, with header serialization/deserialization. just works as an integer with value 1 given the deployment/historical reasons.

Pete: just curious if there's a W3C best practice.

## 5. AOB

Next meeting likely to be June 4th or 18th, depending on agenda items.



---
