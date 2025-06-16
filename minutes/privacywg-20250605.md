# Privacy Working Group, 5 June 2025

## Attendees

1. Christine Runnegar (co-chair)

2. Nick Doty (CDT)

3. Benjamin VanderSloot (Mozilla)

4. Tom Ritter (Mozilla)

5. Tara Whalen (W3C)

6. Julien Bataille (Rakuten)

7. Lola

8. Nipuna Weerasekara

9. Aniketh

10. Lubna Dajani

11. Tom Van Goethem (Chrome)

12. Peter Snyder (Brave Software, co-chair)

13. Narseo Vallina

14. Gunes Acar

Apologies: 

Chair: Nick Doty

Scribe: Christine

# Agenda

1. Introductions, Code of Conduct

2. [GitHub - web-platform-tests/interop-privacy: Privacy Testing for WPT](https://github.com/web-platform-tests/interop-privacy) is working on review of [privacytests.org]([https://privacytests.org/](https://privacytests.org/)) @ChrisC 

Nick: Chris is unfortunately not available to present today. The project is a W3C effort (browser implementers, to test implementations of specs). Every year they look at areas where they could approve testing, and this year one area of focus is privacy interoperability. See website (above). We are trying to see which tests in that repo could become part of the privacy implementation testing. Some may be in specs, some may be just in implementations. Interest in doing an audit to see what could be moved to web platform tests. You can sign up in the Github issue to help. The second thing we could also see which of these are not in W3C spec but potentially could be, e.g. partitioning of state that may are not defined in our specs, but are implemented by browsers for privacy protections. Can do this by creating issues. Those are the two requests.

3. Privacy reviews:

    * Web Payments charter update / charter template updates

    * [Chinese Web Interest Group]([[ig/chinese-web] Chinese Web Interest Group re-charter · Issue #157 · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues/157))

Nick: new charter which led to focus on the chapter template

Pete: lightweight review, no concerns, but regarding the template, now we expect WG to fix privacy vulnerabilities not just document, but those expectations need to be mirrored in the charcter to avoid misunderstandings as to expectations. This group is using an older template, but the W3C should revisit the current template and update to current best practices and expectations. I will be looking at this over the next couple of weeks, invite others to help. Will close the review for these charters.

Jeffrey: happy to help review and iterate on charter template proposal

Christine: Pete, did you note what the Chinese Web Interest Group were focusing on?

Pete: no, was looking at specific elements of charter; Christine will look this up

Nick: There's an issue: [[template] Privacy should be mitigated, not just detailed · Issue #416 · w3c/charter-drafts · GitHub](https://github.com/w3c/charter-drafts/issues/416). I will also be looking at charter template 

    * [WebAuthn]([Web Authentication 2025-04-24 &gt; 2025-05-25 · Issue #162 · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues/162)) (@npdoty)

Nick: a lot of work (the review) because it is a massive spec. This version has relatively minor updates. The new features are still quite significant from a privacy perspective. Will discuss two here, still reviewing. The first is related origins. Many websites use a common authentication but have many different origins when you sign in (e.g. google.com and google.uk or google.com and youtube.com login). The idea was that if you are using a security key or web authentication key, the website wants it to be the same irrespective of which login. A website can specify which RP origin. A JSON file lists all the origins for which it is a common origin. The number of related origins is complex, at least 5, and everything that looks the same before the TLD counts as anything (e.g. google.anything), potentially a large number of strings that are part of the base origin.

Sounds like related party or first party sets proposed in other web features and specs. Password managers also have some of this functionality in place. Privacy issue because the user may not realise that when they login in one origin with a cryptographic unique identifer across all these origins. Don't think can be accessed silently, but not sure. Not discussed in spec.

Pete: Sometimes there are legal restraints (e.g. trademark), seems concerning can have anything.star ... could be sucking up other peoples' domains

Nick: spec does not say you can put .*, [insert]  it just doesn't count as a different label when the website does all these things

Nick: second one, getclientcapabilities with potential extensions to web authentication, to help RPs present a useful (or know in avdance) what are likely to be successful registration procedures (e.g. whether plug in a key). They acknowledge it is a fingerprinting risk. May be more than a fingerprinting risk depending on what "support" means, does it mean the software supports or the user has the device connected. They are aware of it, but there needs to be more detailed analysis. Common issue across specs revealing feature support and how that is used. Will be continuing review and will communicate on mailing list before going back to group.

    * update on Audio Playback Statistics (@pes10k)     

Pete: a new proposed feature, discussed a month ago, allow a site to understand compute pressure of audio and if frames are dropped. .Ther are two concerns. The first is practical, that the feature could be abused to get around partitioning protections. The second concern is that an extremely similar attack was fixed in another spec (compute pressure), and it would be harmful to getting groups to fix privacy issues if a group does a lot of work to solve a problem, only to have the same the nearly-same problem introduced months later in a new spec.

Pete: good reviews lead to more good reviews, very important to be persistent. A practical solution to mitigate the problem and for future. Will integrate, only call API is active frame or have the microphone permission. If you have the permission you can already do this. A great practical solution, but don't love the pattern that there is another spec that has the vulnerability so we are not going to fix it here.  

Nick: Jeffrey wrote a [section in the privacy principles on this issue]([Privacy Principles](https://w3ctag.github.io/privacy-principles/#information)). I suggest we write down somewhere that if this is the same risk as that,  if you fix A, you fix B. 

Pete: That makes sense. The group is planning to write something in the privacy considerations, not normative part of spec. Group is going great work, but your idea is good.

Ben: Putting the note as a backlink note in the spec whose privacy concerns you are relying upon.

Pete: can't make the group update the spec every time someone hangs something off their spec

Jeffrey: dependent group can send a PR to the microphone spec

Nick: maybe we will learn how to do this going forward   

    * volunteer needed: [DID 1.1]([Horizontal Review Request for DID v1.1 2025-05-17 · Issue #163 · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues/163))

    * volunter needed: [APA charter]([[wg/apa] Accessible Platform Architectures Group Charter · Issue #164 · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues/164))

    Nick asked for volunteers to review, can volunteer after the call too

4. localhost: further protections needed?

    * [https://localmess.github.io/](https://localmess.github.io/)

    Nick: examining a particular abuse - communication between web browser and native app, listening in on localhost - interested to see how we should be updating guidance for privacy, might give up context for other attacks or vulnerabilities on privacy

    Narseo: some orgs may be using localhost sockets to breach browser activities, other platforms could be also being abused - we don't want to discuss details of behaviours we have observed, but communications appear to have been used for a while, different platforms - may have occurred without using awareness, significant privacy leaks of user browser habits - only those sites with trackers involved, not all sites - users have to be logged in for this attack

    Gunes: what are the implications for web standards, of efforts to isolate domains, websites - this method of sending an identifier from website to native, bypasses client-side protections - so something to keep in mind for adversary model

    Nick: re: the different methods - you say communicating from website to native app, but seems some might be two-way communication, is that two-way communication required to be a threat, or is the one-way communication still of concern

    Narseo: through origin field can reveal which website has been browsed by user, using ... origin header in HHTP request, anyone listening could also obtain history of user. We have observed WebRTC and STUN, only from script to the native app (app was collecting and uploading to the cloud)

    Nick: why not an image rather than WebRTC or STUN

    Gunes: don't know, we can't say, found people complaining about these localhost calls, using WebRTC is more obscure ..

    Jeffrey: caveat, not working on the team, Chrome has some early work on permission control over the network ([GitHub - explainers-by-googlers/local-network-access: A proposal to restrict sites from accessing a users&#39; local network without permission](https://github.com/explainers-by-googlers/local-network-access)), if this existed not a problem, Apple does some on the OS level, not sure about iOS, people interested should participate

    Gunes: we did not have time to think about defenses, spent our time on researching the problem

    Pete: Jeffrey is the right approach; we put permission on localhost requests ([Localhost Resource Permission | Brave](https://brave.com/privacy-updates/27-localhost-permission/)), but because we are implemented off Chronium, we have some challenges if not explict, but hope to have that resolved soon

    Ben: Jeffrey, giving website owners visibility about what is happening on their wesbites is useful. Difficult to explain to users, a concern, but not a reason to do it. Need a broader investigation on how to convey semantics to users.

    Nick: Chrome has presented proposals in the past - explaining the permissions has been the really hard problem 

    Narseo: context re iOS, need 2 conluding elements for attack, platform is not the same as Android, still working on it, but iOS protections might explain why they were targeting Android, this kind of attack is possible because not considered in any threat model, has been considered a legitimate use, Brave has taken some precautions, but threat model missing. Re: adding a new permission, it is one way to go, more persistent solution, but when release risk of allowing local sockets, asking users for consent, maybe here

    Nick: aware of threat of localhost, but learning here about what they might learn, what they communicate out, here we look at what maybe could be done on web site, on webdev tools, need good transparency, raise as bug with browsers

    Jeffrey: worth figuring out

6. TPAC meeting planning

Nick: in November, in Japan, we need to notify how much time when need and when we prefer to meet, we typically do one shorter session for discussion of guidance, discuss documents, triage, but if there are other things we should include on the agenda, let us know

7. AOB
* next meeting date may be delayed by holidays. what do y'all think?

19 June - Juneteenth

3 July (day before 4 July)

Nick: don't plan meeting, do asynchronously work, meet 17 July, the week before IETF

# Queue
