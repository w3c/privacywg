# Privacy Working Group, 5 February 2026

## Attendees

1. Peter Snyder (Brave)
  
2. Christine Runnegar (co-chair)
  
3. Tara Whalen (W3C)
  
4. Don Marti (invited expert)
  
5. Benjamin VanderSloot (Mozilla)
  
6. Ted Hardie (invited expert)
  
7. Sebastian Zimmeck (Wesleyan University, Invited Expert)
  
8. Justin Brookman (Consumer Reports, Invited Expert)
  
9. Jeffrey Yasskin (Google Chrome)
  
10. Joey Stanford (invited expert)
  
11. Michael Kleber (Google Chrome)
  
12. Robin Berjon (Supramundane Agency)
  
13. Aram Zucker-Scharff (Washington Post)
  

Chair: Pete Snyder

Scribe: Jeffrey Yasskin

# Agenda

## 1. Introductions, Code of Conduct

https://www.w3.org/policies/code-of-conduct/

Pete: Brief agenda: GPC and privacy pre-reviews.

## 2. GPC

Justin: 4-ish things to discuss.

### How does GPC apply in Europe?

[Change phrasing of legal interpretation for EU/GDPR · Issue #93 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/93)

Justin: Harsh wants the text to be a little more prescriptive about how GPC applies under GDPR. Currently spec says it might apply under 7 and 21. The explainer is more detailed about how it applies under Article 21. European regulators haven't weighed in much. There's an omnibus package in which they're revisiting GDPR, and they've talked specifically about signaling as a way to resolve issues in Europe. There's a disconnect between the explainer and the spec, because the spec mentions an article the explainer doesn't talk about. But it's also "maybe, I dunno". Michael from Google weighed in on the issue, wanting not to be more prescriptive, partly because GDPR is being rebooted anyway. I don't feel strongly. Sebastian and Robin have written a lot about how GPC should apply in Europe.

Robin: On how prescriptive the spec should be, I'm fine with it not being prescriptive as long as it's clear. That's where the other PRs come from. I don't think it's the spec's job to say how to apply the GDPR. Work we've done shows the spec is unclear in some cases, partly because the terms aren't defined and aren't linked to the definitions in the [Privacy Principles](https://www.w3.org/TR/privacy-principles/). If we provide that clarity, we don't need to be prescriptive. If we aren't clear, we need to be prescriptive. 

Sebastian: On one specific point, that the spec currently mentions Article 7 and 21 of the GDPR, and the spec doesn't. Maybe it should be the other way around. They should match. My preference is to mention both in both. But no strong opinion.

Justin: I'm fine adding a quick line to the explainer to mention that Article 7 might be implicated. Wouldn't say "is" or "should be", but "could be". Could say in the explainer that there's a process in place to re-do GDPR. Implementation guidance and legal guide is designed to change over time. Can say it's "currently" being debated, including signaling.

Christine: Wholeheartedly agree with Robin that we need to be clear. Sebastian mentioned where it appears. I think the right place is for the detail of Article Whatever to be in the explainer, not the spec. 

Justin: One line in the spec says "maybe Article 7 and 21". Explainer has a paragraph, but specifically on 21. Maybe we add a line to the explainer saying it might be relevant to revocation of consent, and that it's up to European policymakers.

Christine: Happy we're not trying to say what European law is.

Michael-on-zoom: :thumbs-up:

Justin: I'll plan to move forward. And tell us if you don't like what we write.

Spec: [Global Privacy Control (GPC)](https://w3c.github.io/gpc/) 

Explainer: [Global Privacy Control (GPC) Legal and Implementation Considerations Guide | gpc](https://w3c.github.io/gpc/explainer)

### Clarifications and anchoring

https://github.com/w3c/gpc/pull/108 - Clarifications and anchoring

Justin: Meant to be narrow. Jeffrey objected to some of the substantive changes. If we limit it to just linking, Jeffrey noted he'd be fine with that.

Robin: This is really just about defining terms. Several of us spent a bunch of time defining terms in another document, so documents in the privacy space could link to them. PR was a mix of links and what I thought were small editorial corrections. Jeffrey wasn't comfortable with the corrections, so I removed them. One issue remains. PR predates #127, so it has a similar change. If we agree that people are happy, want to take it provisionally depending on the decision of the other PR. If we disagree on #127, I'll change this to match the other.

Jeffrey: reasonable, remove overlap and deal in #127

Robin: Since we're discussing today, I'll just do today's decisions in both.

Jeffrey: Sounds good.

### "Same contexts"" vs "same sites"

[Make spec consistent about same contexts rather than same sites by darobin · Pull Request #127 · w3c/gpc · GitHub](https://github.com/w3c/gpc/pull/127) - Make spec consistent about same contexts rather than same sites

Justin: Narrow, but might cause more disagreement. Design is that GPC says I don't want my behavior tracked across different contexts. At the same time, we discussed clarifying that same-site is out of scope. I'd thought of same-site as more narrow, because most of the time when you go to a site, you understand who you're dealing with. GPC isn't designed to address that: not designed to tell ESPN to forget me based on what I do on ESPN.com. In this PR, there can be cases where a site is more expansive than context. Say ESPN did every thing on Disney.com, all in the same domain, but you interact with it thinking of it as Disney, ABC, ESPN, etc. That might seem to cross contexts. We agreed that we didn't want to say tracking across a business. I thought it was a useful clarification that tracking across same-site isn't included, but there might be cases where same-site tracking might feel like it crosses contexts.

Robin: I thought the right solution was that, the way the Privacy Principles are architected around context instead of site, because you can have massive sites that gobble in new services, and you claim that you're inside the same site (TLD+1), but you're actually tracking across contexts. Originally, when we started GPC, on the legislative and technical side, there was a demand by the publisher community that we be context-based instead of site-based, because otherwise it's an incentive for continuous integration. Gives an unfair market advantage. Context is more restrictive than site. There was some debate about whether that reflected the group consensus. Previous minutes seemed to indicate that context was the consensus. Thought PR reflected that, but I wasn't there. Context is more restrictive, and we shouldn't be incentivizing market concentration when we don't need to.

Michael: At the TPAC meeting, we spent a while talking about this. Think the conclusion there is different than Robin's statement here. At TPAC, we discussed the prospect of context as a notion that's broader than site, and might span across multiple sites. When we came to the possibility of GPC restricting use within the same site, consensus was that we didn't intend to do that. Didn't want GPC to establish a new information flow boundary, that was trying to be narrower than all other information flow boundaries that existin in the browser. Cookies are shared at the site level. Prospect of establishing something that breaks sites into smaller chunks that are narrower than cookie sharing, was a daunting and undesirable prospect. Second, we talked about question of what laws actually do. I'm not enormously knowledgeable, but my understanding of the various U.S. state privacy laws that are triggered by the GPC header, is that they don't operate at the level of sharing more granular than the site level. For both reasons, I thought it was undesirable to leave the spec ambiguous. Making the spec as clear as possible is highly desirable. I'd prefer clarity that the spec doesn't intend to cut up information sharing more finely grained than the level of the site.

Ben: Wording of context in the Privacy Principles: I interpret it as being both narrower and broader than same-site. Maybe that's part of the issue.  That might be the definition we want, depending on the user's request. Don't mean to say "let's not do context", but it's both larger and smaller.

Christine: Michael's talking of a broader definition ... example of one context but multiple sites?

Justin: Think there was agreement that not all intra-company tracking was within the same context. You're right that most laws talk about "party" and "commonly branded", which are relevant to context. In most cases, same-site tracking is outside the scope of GPC, so wanted a narrow clarification, that same-site tracking is likely or almost always excluded from the GPC. But maybe multiple services will operate on the same domain that would be multiple contexts.

Sebastian: In my mind, it's about defining what the user expects.  They think "this is the same site or context that I want to interact with." That's critical. Difficult to get the exact term. Whatever term we use, e.g. "context," it should be the context as defined in the Privacy Principles. We shouldn't use the same term with a different definition. If we think of the future, with users no longer interacting with websites directly. Maybe they ask their AI agent to book them a flight. There, the context becomes much more important. So, whatever we define as "context," defining the boundaries with this term is more future-proof.

Don: State privacy laws don't usually say "site" or "context". They address businesses or something like that. The text of state privacy laws and regulations isn't that helpful in determining between site and context. They address business entities that a customer feels like they're interacting with. State privacy law text doesn't give us a black-and-white answer.

Jeffrey: definition in privacy principles, it cuts more finely than sites, but also more broadly, if this spec uses context it should use same meaning as privacy principles, but we don't have to use the word context, if said you have to figure out context in user's head, would affect long term policy/law - we need to figure out what we want to say, what we want to tell sites, etc. to do

Ted: Want to think about who's going to read this. Jeffrey pointed out that one thing that might happen is that regulators will read this. We should think of them as a potential audience. That makes me think we should keep "context" instead of going to site. Publishers were making the point about aggregation putting multiple contexts on the same site. Matrix.itasoftware.com was bought by Google, and is available on the original site, in a more complicated way than on flights.google.com or google.com/flights. Have to look at it from the point of view of the user or the regulator. If the user sees a different presentation form for interaction, it's valuable to use this signal differently. If I'm on a Google.com search, I have a different context than for the flight search. From a user perspective, good to go ahead saying those are different contexts. Regulatory aspect might not catch up, but valuable for us to send that signal.

Robin: Largely agree with Ted. One thing that makes the conversation uncomfortable is that what we're doing with GPC is different from usual W3C specs. Some parts need to latch onto the technical part, like the header. Other parts need to latch onto legal frameworks anywhere in the world, which is fundamentally challenging. Argument in favor of context is that it needs to hang onto the legal side. If we wanted it to live on the technical site, we'd say something about cookies. "Context" is the right concept on the legal side, in a transnational way. Hangs on people's understanding, which is really key in legal contexts. "Reasonable expectation". Engineers hate that: "we can't figure out what's in people's heads". That's the lawyers' job. Our job in the spec is to hang onto that. Context matches "reasonable expectation of data subjects".

Michael: What normal humans expect is 100% the most important question. Don't want to throw away the legal issues. GPC has value over Do Not Track because it's triggering a legal protection. Want to lean into having GPC as we represent it to users, stick close to the effect it actually had. Agreed with Ted until it being ok to represent GPC as trying to do something even if the legal protections never catch up. Don't want to try to claim that GPC does something if, from a legal point of view, it never actually does the thing we claim it does. I keep saying that from the point of view of a browser vendor, we need to tell the user what this checkbox does. They'll check a checkbox saying "I want something", and the browser needs to tell the user what they're opting into. That's the way the user knows what preference they're expressing. If the header expresses a user choice, it only does so if the browser informs the user correctly. I'm extremely reluctant to try to tell the user that GPC does something, if that thing we're saying it does, doesn't match any of the laws. We need to have some language, whether it's int he spec or up to the browser, where we tell the user what they're choosing. The language that was widely used at the beginning of  GPC was "do not sell or share my data". That's a little unclear, but with contexts, I'm not sure what selling or sharing means within a single entity. Within a single entity, no selling or sharing took place. We've expanded GPC to mean "do not sell or share or personalize advertisements", and the detail here is hidden in "personalize". How can a site choose what ads to show users? Is information from the same site fair game? If we go outside what we can express to users, we're in extremely shaky territory, the header has lost the connection it needs to have to what the user thought when they checked the checkbox.

Ben: There's a subtlety about the Firefox string, which says "Tell sites not to sell or share your data". Browser's communicating a preference, rather than guaranteeing behavior. The "Tell sites" makes me much more comfortable.

Ben: I think the idea of context might be the right one here. Might be something else if the concern is truly that having context split sites in half because cookies are shared, and you're also getting this header. Maybe "context but no narrower than site" is better. But root in "context" based on Robin's argument.

Aram: 1) Generally, in our previous conversation, we'd agreed to use "context" throughout the document, but didn't in that PR because it was in parallel with that decision. New text, so that doesn't determine this conversation. 2) This question of what context means w.r.t. site owners, and uncertainty. That's in the norm of how site owners deal with concerns on the web. Within our capabilities. Publishers have changed things where context needed to be changed because of some external privacy and non-business reason. FB pages needed to map to a single site, so publishers created a lot of sub-domains. When SEO pointed the other way, publishers spun them back in. Question of what users think a law or signal means isn't something we can address here. Risk is taken on by sites and lawyers. e.g., in media space, California CIPA (California Invasion of Privacy Act, wiretapping) might apply to publishers. And VPPA and video and how that applies to publishers. Some publishers have added a checkbox, but not all because it's still being decided in court. Users come in with different assumptions, and decide whether to sue us or not, and our lawyers figure it out. Better to use "context", and that creates a better discussion with our lawyers. We can have a discussion about "context' in ways that aren't as clear as "site". Valuable to come into these conversations with the sense that GPC is a request to the site, and the site decides how to comply based on its understanding of applicable laws. Number of court cases that change the understanding, and then sites make a decision about what to risk. To Robin's point, this isn't a checkbox that turns off cross-context sharing. It sends a signal, and then sites make a decision. "Context" is valuable here.

Ted: Similar to Ben, what we're trying to do here is to send a signal to a publisher who understands their own sense of "context", and they have lawyers who understand that they might get sued. Michael's problem is real that he needs to put up a string, but the site's decision will depend on their notion of their laws and contexts. Not fun to design the string, but it's still the right thing to say. Understanding will change over time. Context remains the right choice.

### Progress toward CR.

[Progress toward Candidate Recommendation · Issue #111 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/111) - Progress toward CR.

Justin: What do we need to do here?

Tara: https://www.w3.org/guide/transitions/?profile=CR&cr=new This is the high-level process, to see what we need to do. Most significant part is about document review.

https://www.w3.org/guide/documentreview/

Tara: That's wide review, which includes horizontal review. Before this goes forward, you need to give the wider community a chance to comment. I'll spin up an issue based on a template, with several checklists (e.g., questionnaires). Look at accessibility, internationalization, etc. Have to demonstrate before CR that this has been done. There are guides in Document Review about steps, good practices, and pitfalls. Consider dependencies, groups you're working with. Don't have to do this alone. Can include general public or particular parties. (They don't have to be listed in the charter to be consulted.) Will track in the github issue. Documents what we've done in the WG, for the Team to review the transition request. There's an assumption that the feedback will be incorporated. Give yourselves lead time.

## Privacy Request Updates

- DID Resolution v0.3: https://www.w3.org/TR/did-resolution/
  
- CSS Anchor Positioning: https://www.w3.org/TR/css-anchor-position-1/
  
- Web Editing WG charter: [[draft] Web Editing Working Group Charter](https://w3c.github.io/charter-drafts/2025/webediting-wg.html)
  

Pete: We've received these. Chairs do an initial triage review to try to identify what's substantive or interesting enough to warrant asking a domain expert to do a full review. Didn't think any of these 3 have privacy concerns or uncertain privacy-relevant behavior. Plan to close in a couple days.

Ted: I had a concern about Web Editing. Charter doesn't say whether it's addressing situations where multiple people are editing at the same time. Some specs clearly don't, but some might. Clarity would be good.

Pete: Do you want to work together on a more detailed review?

Ted: will ask question of charter editors

Jeffrey: Looking at DID from TAG perspective, don't define well what methods have to do, so process of resolving a DID is not well-defined, includes leaking information that the person is trying to resolve with DID, look at this with the review

Pete: Will look for reviewers.

Jeffrey: happy to help, but already reviewing as TAG, want to make sure another person from Privacy WG involved in review

## AOB

- Considerations for Reviewing Differential Privacy Systems doc: [Considerations for Reviewing Differential Privacy Systems (for Non-Differential Privacy Experts)](https://w3c.github.io/differential-privacy-guidance/)

Pete: TAG and Jeffrey asked if we had considerations for reviewing Differential Privacy. Want to get group memebers to revise and improve this. Want to move discussion from Slack to issues.

- wrap up of discussion on [Make spec consistent about same contexts rather than same sites by darobin · Pull Request #127 · w3c/gpc · GitHub](https://github.com/w3c/gpc/pull/127) 

Christine: To wrap up discussion of GPC#127. Aram said we'd already made a decision to use "context" and we're discussing it again. Want to note that we hear the concerns Michael raised. Ben suggested being clear that this is a signal from the browser, and that we have consensus to use "context", so we don't have to have the discussion again.

#
