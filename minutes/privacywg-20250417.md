# Privacy Working Group, 17 April 2025

## Attendees

- Tom Ritter (Mozilla)

- Sebastian Zimmeck (Wesleyan University)

- Tara Whalen (W3C)

- Nick Doty (CDT)

- Jeffrey Yasskin (Google Chrome)

- Pete Snyder (Brave)

- Don Marti (Raptive)

- Ben VanderSloot (Mozilla)

- Chris Needham (BBC)

- Joey Stanford (Invited expert)

- Aram Zucker-Scharff (The Washington Post)

- Christine Runnegar (co-chair, invited expert)

- Justin Brookman (Consumer Reports, invited expert)

- Chris Cuellar (Bocoup)

- Lola Odelola (Invited Expert)

- Johann Hofmann (Google)

- David Pham (Washington Post)

Apologies: 

- Michael Kleber

Chair: Nick Doty

Scribe: Sebastian, Ben

## Agenda

### Introductions, Code of Conduct

### Fingerprinting

- I'll fix the reference issue but before the Ephemeral Fingerprinting section is merged, does anyone want to [advocate for a particular name]([Add references for Ephemeral Fingerprinting by tomrittervg · Pull Request #74 · w3c/fingerprinting-guidance · GitHub](https://github.com/w3c/fingerprinting-guidance/pull/74#issuecomment-2741117639))?

Tom Ritter: Merge in a week if there are no concerns.

Nick Doty: I think it is great that we came up with a new name, "ephemeral fingerprinting". I liked the "transient" correlation.

Christine Runnegar: Ephemeral already has a specific meaning in different contexts, so it may be preferable to use another term, e.g. "Transitory correlation" or a similar term may be good.

Nick: The danger of using "ephemeral" is that it may be misleading. If other people have comments on names, put it in GitHub. I will put my suggestion in there as well. Let us wait a week, and then we can go ahead.

- Structure for the Randomization [additions]([Expand the section on randomness and update it. by tomrittervg · Pull Request #76 · w3c/fingerprinting-guidance · GitHub](https://github.com/w3c/fingerprinting-guidance/pull/76#issuecomment-2767082811)).  It feels like this is going to be a new subsection under Mitigations with somewhere between 1-3 new BPs.  Does that sound about right to people?

Tom: It may get longer. There are a number of details. I will work on the words and shift them around. If people have preferences on the best practices, I welcome that.

Pete Snyder: Let me know, and I am happy to help.

Tom: Thanks, I am happy to write lots of words, and you can improve the structure. 

Pete: Sounds good.

Nick: Since Tom and Pete, you looked into this in detail but it sounds quite difficult and extended, can we proactively give best practices to spec authors?

Tom: It may be awkward to tell spec authors to fuzz things

Pete: ...

Nick: We want to make it for spec authors. That may limit your scope a bit.

Jeffrey Yasskin: We actually give some guidance. That could be useful, for example, for canvas fuzzing. That helps both the implementers and the web developers.

Nick: I thought we recommended rounding?

Jeffrey: We did, but even rounding may be effective. We can round a bit more granularly, and that may have the intended effect.

Nick: I would be for giving this advice. I am happy to look at that, whether that is in this or another section. Anything else on randomization?

Tom: I go towards truncating. You can also jitter up or jitter down from a randomly chosen midpoint - but this might be in the weeds

Jeffrey: This would be the right document to consider those variations and what we should recommend.

Nick: We did not even explain mathematically when we first started writing that mitigation into specs. That seems like something to improve.

Aram Zucker-Scharff: I understand what is being said here in terms of noise. That has value in itself. It is not possible for us to remove every single fingerprinting surface. Adding noise is not perfect, but we should not discount it. The adversarial relationship we have is that we always create work for fingerprinters if we do our job correctly.

- Feedback on [Issue 70 about re-organizing]([Adjust the organization of BPs and split one into two. · Issue #70 · w3c/fingerprinting-guidance · GitHub](https://github.com/w3c/fingerprinting-guidance/issues/70))

Tom: Issue 70 has sat for a while. If I get a chance, I will open a PR. Not sure if silence means reluctant consent or something else.

Nick: I assigned myself. I look at this one. You can look at the PR.

### GPC

- [Give UAs more help in establishing user intent · Issue #52 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/52) 

- [Clarify scope of GPC by j-br0 · Pull Request #99 · w3c/gpc · GitHub](https://github.com/w3c/gpc/pull/99)
* [Weak requirements language · Issue #35 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/35)

Nick: Let us talk about GPC. Justin, can you talk about the issue raised and the proposed resolution?

Justin Brookman: We can talk about what the user agent needs to do. This is tricky because in different jurisdictions it can mean different things. There is also no guidance given on UI in specs. It is not meant to solve all problems. I wrote a PR to address the issues. I added some language to the main spec. On the user agent side, we point to being flexible. It should not be rocket science. There is already something in there. I added some more. It is not appropriate for us to say how exactly implementers should go about this. Michael Kleber said on Slack to share some thoughts on GitHub. I am happy to hear other thoughts.

Jeffrey: I defer to Michael on speaking for Google. One thing is that we should think about what GPC means in different jurisdictions.

Justin: That is already in the spec in various places. Adding more would be probably too much. What is missing?

Jeffrey: It may also need to include in which jurisdiction the browser and/or the site is running in.

Nick: I thought you wanted to indicate that browsers may want to let their users know.

Jeffrey: My first issue is about what browsers may need to show users. If that is what the group decides, that is fine. Michael may disagree with that. But then we should talk about how the browser makes that decision.

Nick: It sounds you are not concerned that GPC can have various impacts that the browser might explain to the user, based on what sites feel they need to do to comply with user preference.

Jeffrey: It seems that the group has moved along already. So, I will not keep bringing this up again.

Justin: I worry about over-prescribing but if you have some middle ground, I am happy to address it.

Jeffrey: It is just a worry; I am not insisting.

Aram: When it comes to including this type of stuff in the spec is that not every user agent in every jurisdiction has the same responsibilities. For example, in some jurisdictions you may be able to turn on GPC by default. So, beyond the fact that we generally do not want to prescribe UI, given the differences, it is even more important to not prescribe in the spec. The spec may otherwise even get wrong.

Don Marti: The UI issue may be a difficult situation because the browser may be bundled with an OS, the user may be an employee of a company with an enterprise managed browser, a family device, or follow a path to install a browser that includes text and videos explaining the browser's privacy features. Putting in too much detail about the UI could cause some issues so I agree with Justin.

Lola: Echo Jeffrey's point. Spec doesn't need to say what is to be said, but that something should be said. But I've heard good counter-arguments

Ben: echo Aram, overspecifying UI is fraught with issues. Clarity why we would even specify UI anyway -- don't want deep undermining of the signal by browsers, as in the historical case of IE and DNT. Lightest possible touch to achieve that goal is probably right.

Nick: Editors, that was a lot of opinions. Do you have a direction?

Justin: I'd like to hear from Michael. We agree that we don't want to be overprescriptive, but we are sympathetic to the counterargument. The PR isn't what Jeffrey asked for, so let's keep talking about it.

Nick: The other thing I wanted to talk about is communicating to the regulator who may be communicating to their constituents that there is a single switch to turn on every privacy feature. This other issue?

Justin: this is an older issue, but is covered by the same discussion.

Nick: Testability is a challenge. 

Ben: WebDriver command could solve it pretty simply

Nick: Maybe we need an issue, I'll file it after this call.  *** action for npdoty

### Privacy reviews / follow-ups

* WebAudio

* Verifiable Credentials

* Web Neural Network API

#### WebAudio

Nick: WebAudio Playback Statistics API

Aram: Reviewed them, along with the S&P consideration. Provide more info about latency and skipped frames in audio. Can adjust bitrate, pause the stream, or provide analytics as a result. Fingerprinting risk in CPU loading to be detected by audio lag. However the issue already exists in the audio spec. They find it unlikely an attacker would stress the CPU to fingerprint, which is incorrect in my experience. 

Nick: Is this ephemeral fingerprinting / transient event correlation from overloading the device and noticing the lag simultaneously in 2 windows.

Aram: Yes, and device fingerprinting. The ephemeral bit is harder because of cross-site isolation.

Jeffrey: Ephemeral fingerprinting described here is actually a message  channel and security folks tend to research this quite a bit. This could end up being a security vulnerability, not just responding to external events, but something the attacker can control and communicate between contexts.

Aram: Yes.

Nick: The mitigations may be different, depending on what the attack is

Pete: Is this API trying to convey the degree of stress on the CPU? Compute Pressure API is something we already reviewed. Also, architecturally better. Maybe they could adopt some of the same mitigations from Compute Pressure.

[Compute Pressure API notes a "timing attack" which is the transient event correlation risk that we were discussing, and "cross-site covert channel" which is the message channel risk that we were discussing. Just noting for coming up with consistent language in our guidance across specs.]

Aram: Not directly CPU pressure. It is a proxy. Reemphasize that this adds no new information to the platform. Noising drastically reduces the utility of the platform.

Pete: I think this is downstream from compute pressure.

Aram: This is useful to have even with Compute Pressure API existing. The spec approach is good, and nice to have on the specific audio element.

Pete: Do they need so many datapoints?

Aram: It seems like it from their explainer and spec. Specifically the number of dropped frames and multiple plays. Maybe some minimization could be done.

Ben: If this isn't adding new information that can't already be obtained, then it seems reasonable, because making it easier for intended purpose while not increasing entropy of the platform.

Aram: Output latency can theoretically measure everything, but with a higher level of difficulty. Making it easier does still increase fingerprinting risk. Another point: much of their concern is about messaging between contexts. But it is a fingerprinting surface. And the Audio API is being used for fingerprinting. It is worth considering the information added. The spec should note that it is a fingerprinting risk

https://fingerprint.com/blog/audio-fingerprinting/

Related to performance varying across devices and browsers. 

Christine: Analysis is: it does somewhat increase the risk of fingerprinting because it makes it easier. It is a useful feature. How do we reconcile these, or can we mitigate it?

Aram: I'm stumped. No clear mitigation. Maybe a deeper conversation on clamping rounding and noise, but the information is already available. Mitigations seem to reduce the utility

Here is the review we did of the (seems to me) very related Compute Pressure API.  I think we should insist on (at the very least) the same mitigations the Compute Pressure API incorporated to be added here

[Compute Pressure API 2023-02-07 · Issue #113 · w3cping/privacy-request · GitHub](https://github.com/w3cping/privacy-request/issues/113)

In particular this area which, like Jeffrey mentioned, is not so much a fingerprinting concern, but a covert channel issue:

https://github.com/w3c/compute-pressure/issues/197

Lola: Sometimes we have to weigh up the risk. I would encourage everyone to think about who benefits from this the most. If the people who are going to benefit from this are earlier on the list (need reference) it might be useful.

Aram: It makes it much easier for developers to make a good audio experience on the web. And the additional fingerprinting risk is low. This seems like a reasonable tradeoff.

Lola: Including the risk as part of the design review is a good shout. Also allows documentation to be stronger. Documentation CG exists. Documentation is a mitigation.

Chris: I know media application development. There is utility here. This is not the <audio>, but is about music mixing applications. This granularity is needed for these applications. Think about jamming with other musicians.

Nick: Use cases can drive mitigations too. we could consider how it would be useful for some specialized cases but something has gone wrong if we see it running on every website.

Aram: Thank you for the perspective on use contexts

#### Verifiable Credentials

Nick: I'm still looking at Verifiable Credentials. Will share on list, still reviewing, but looks like they've clearly documented the privacy risks and mitigations, but the potential uses and risks are very broad.

#### Web Neural Network API

Christine looked at the Neural Network API, will share either on-list or next call.

[adjourned] - See you May 1
