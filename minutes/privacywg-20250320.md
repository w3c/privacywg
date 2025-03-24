# Privacy Working Group, 20 March 2025

## Attendees

* Tom Ritter (Mozilla)
- Sebastian Zimmeck (Wesleyan University)

- Tara Whalen (W3C)

- Nick Doty (CDT)
* Jeffrey Yasskin (Google Chrome)
- Stalgia Grigg (Bocoup)

- Pete Snyder (Brave)

- Ari Chivukula (Google Chrome)
* Philippe Le Hegaret (W3C)
- Don Marti (Raptive)

- Michael Kleber (Google Chrome)



Apologies: 

- 

Chair: Nick Doty

Scribe: Sebastian

## Agenda

### Introductions, Code of Conduct

Nick: The meeting is held under the W3C Code of Conduct. You can talk to the chair as well. There is also an ombudsperson. People should follow the code of conduct and can report issues.

[Positive Work Environment at W3C: Code of Conduct](https://www.w3.org/policies/code-of-conduct/) 

### Report out / follow-ups from W3C North American Member meeting

Nick: W3C had a members meeting for North America. Gave overview of privacy that are happening across groups. One takeway is that there is some interest in proactively looking where the web platform has privacy gaps, what could we do about those, and what other products besides standards we can produce.

Nick: It may be useful to have principles or threat models in particular areas. We have privacy principles for the web, but they are more high-level. We may want to do something more concrete. For example, e-pub has some more details. Another topic was gaps. It would be useful to have impactful work by looking at the privacy principles and flesh out some of those.

Philippe: Potentially, every breakout group at the meeting was useful and could be addressed. see also [Mitigate Threats for Digital Credentials API: Episode II - Attack of... | W3C](https://www.w3.org/events/meetings/97790087-97c8-4d89-b3ce-c3a80ef8c343/)

Full (proposed) schedule of breakouts: [W3C Breakouts Day 2025](https://www.w3.org/2025/03/breakouts-day-2025/#schedule)

### User considerations for credentials on the Web

[Pull requests · w3c/credential-considerations · GitHub](https://github.com/w3c/credential-considerations/pulls)

Nick: There are some changes. Here is a PR: [Pull requests · w3c/credential-considerations · GitHub](https://github.com/w3c/credential-considerations/pulls) ID issues are relevant. Digital identity has an additional threat. In response to some feedback, we talked about having governmental-issued credentials on the web. The link has some references. This is a new area of risk. Maybe, we can take that to the breakout sessions or the federal identity group, which will likely take on this issue.

### Privacy reviews status

[Privacy horizontal review dashboard](https://www.w3.org/PM/horizontal/board.html?name=Privacy) and privacy reviews status

Nick: The next item is privacy reviews. Phillippe, can you take us through the dashboard.

Phillippe: There is a draft charter. Charter request, in the future I can remove the section. There are a number os issues we care about and that are important and that accumulated over time. There are a number of tracker issues that other groups flagged as relevant, and my hope is that we can contribute to this. It is better to do sooner than later because other groups may get too far in the process before we raise privacy issues. Then, the next point is that this is giving us a window into what is going on elsewhere. There is, for example, a workshop on fingerprinting at TPAC 2023 (or 2022) and that is relevant as well.

Nick: Has anybody following distributed tracing or wants to follow that charter.

Pete: I have looked at that and am happy to continue or organize.

Nick: Have they done horizontal review? If you want to look at it, great! Otherwise, all reviews seem to be assigned. If we get to new requests, Tara can flag those.

### GPC

#### status of PRs (most already reviewed, ready to merge)

#### if time permits, [Give UAs more help in establishing user intent · Issue #52 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/52)

Nick: Justin, can you give us a summary?

Justin: There are seven open PRs. We have covered those before. We do not need to repeat those again. It seems to me we are on the same page. There are two that we have talked about. There is also the one from Jeffrey for PR preview, but I am unsure where we had left of. We all liked the idea.

Nick: I approved that, and I think we can just go ahead. It just makes the PR review easier.

Justin: If people want to talk about an issue, we can talk about that. Otherwise, I go to Jeffrey's. This one is about user intent, already opened in 2023. The explainer tries to address this issues partly. Ultimately, it is up to the individual jurisdictions what exactly a GPC signal means. I think that is the best we can do. I am happy to do more about it. But I think providing the legal guidance is the best. This is an older issue, but I wanted to flag this now so that we can move forward with the spec.

Nick: Thanks for the summary. The question I had was that there was another comment on there how to describe the feature to users. This is not about the legal impact. These are two different points.

Justin: I am fine with that. Generally, telling the world. I am fine with making recommendations. But I am also not an expert on this.

Michael: This is closely related to what we have covered here. But to be clear, the issue is that the browser has to worry about two different constituencies. One is our users: It would be really good if we could tell the browser users what their checkmark would do. So, we were struggling with the different jurisdictional meanings. The other half of the manner is the UI. The spec is currently silent on how the browser should present the choice. It is not the user only, though. The second constituency is regulators. Regulators also care about the spec. The reason why I think this discussion is useful is because then regulators would have some way to know what meaning they should give to the choice. At the very least, if we can do anything to rein in how the control might be interpreted by different regulators, then it would help browsers that are otherwise in the bad position of needing to think about the present and the future of what the law says in every jurisdiction.

Nick: I think there are two points. Browsers want to explain to user what GPC means. I speculated that there are many checkboxes in browser UIs right now. Maybe, browser vendors could specify what they need for a checkbox to work. So, if there is more specific guidance what checkboxes on other issues require, that would be useful. The second point is that it may be useful for regulators. Is that right?

Michael: Yes, and the response from Justin and Sebastian may be that the spec already does that. So, there may be nothing more to do. But it would be good if we could rein in what the choice means.

Nick: There are two sections in the spec. "User Interface Language" and "Definitions".

Justin: 5.3 seems to be the right section. Michael's explanation was helpful. I had not thought about it both ways. I am definitely fine to find one suggestion. Mozilla has one suggestion for checkbox language. Then, there is a link to a page that explains more. It is easier to tell folks. I am fine with adding language to section 5.3. I am happy to take this on, but also I am happy to work with others on the PR.

Michael: I am happy to help.

Sebastian: I am also happy to help with this.

Nick: Justin will work on this and Michael and Sebastian will help. Hopefully, that will come up with short PR so that everyone can look at that. That is all we had lined up for GPC.

### Mitigating browser fingerprinting

* merging PRs and process for reviewing

Nick: We have a new editor. Tom, in addition to doing a lot of work, you are also now an official editor. You updated the language PR. Phillippe is going to confirm. You had another PR about ephemeral fingerprinting.

Tom: Yes, one is about tabs and ephemeral fingerprinting. I pause if anyone wants to talk about that.

[Add references for Ephemeral Fingerprinting by tomrittervg · Pull Request #74 · w3c/fingerprinting-guidance · GitHub](https://github.com/w3c/fingerprinting-guidance/pull/74)

Jeffrey: I briefly glanced at the comment, and it seems fixed, But I have not yet looked into it in detail.

Nick: So, maybe we just let Jeffrey finish the review.

Jeffrey: I'm happy for y'all to go ahead before I've re-reviewed the whole thing.

Tom: The other one is a PR on randomness. This is maybe more opinionanted than ephemeral.

[Expand the section on randomness and update it. by tomrittervg · Pull Request #76 · w3c/fingerprinting-guidance · GitHub](https://github.com/w3c/fingerprinting-guidance/pull/76)

Pete: I know I owe a review on this and will get to it soon.

Phillippe: I do not think that randomness can always be avoided. There are memory attacks. 

Tom: This would be similar to security through obscurity. You can do it, but it should not be the only point.

Nick: Fuzzing as done by Brave may be one way to go.

Tom: Certain types of canvas fingerprinting are detected. It definitely has benefits. It depends on how sophisticated the fingerprinting is.

Pete: For naive fingerprinting it is very useful. For a more sophisticated fingerprinting it is more limited. 

Tom: The third thing issue 70. People can take a look and let me know if this is good.

Reorganizing BPs - [Adjust the organization of BPs and split one into two. · Issue #70 · w3c/fingerprinting-guidance · GitHub](https://github.com/w3c/fingerprinting-guidance/issues/70)

Nick: I can definitely take a look. If anyone else wants, feel free to go ahead,

Phillippe: We have this idea of a fingerprint marker. Has this been used? There should be an easy way to use. If we are serious about, e.g., is it applicable to GPC, we should start suggesting that people should have it.

Pete: It is mostly a matter whether we want to do it. If someone wants to do it, that would be great. But it is not a priority at the moment.

Nick: I think we have an issue on that?

Phillippe: I do not know where the issue is right now. 

Nick: Looks like the issue was closed on bikeshed? 

Jeffrey (in chat): [Bikeshed Documentation](https://speced.github.io/bikeshed/#tracking-vectors) is how to mark things with Bikeshed.

Phillippe: I am not sure if it is actually being used?

Jeffrey: I think the WHATWG is actually using it. ... https://dontcallmedom.github.io/webdex/t.html#tracking%20vector%40%40infra%25%25dfn lists references ... and [Ambient Light Sensor](https://www.w3.org/TR/ambient-light/#security-and-privacy) is a use outside of WHATWG.

Nick: OK, if assign the issue to you, Phillippe?

Phillippe: Yes, that is OK. I am not sure if it actually works. 

Nick: Yes, we have not made that a priority in reviewing. Anything else on fingerprinting? We have a few other issues. I am going to look at Tom's issue in 70. 

### AOB

Nick: There is one other topic. We are seeing a lot of child safety proposals. Some age verification. Some are privacy-invasive identifying the age of users and getting people's government IDs. Nothing that would come to us, but it come in the future. If anyone of you have implementations on this, I would love to hear.

Ari Chivukula: [Explainer: Private Proof API | private-proof](https://explainers-by-googlers.github.io/private-proof/) might be extendable into the sort of use case you're imagining
