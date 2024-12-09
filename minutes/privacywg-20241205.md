# Privacy Working Group meeting - 05 December 2024

## Attendees

- Nick Doty (CDT, PrivacyWG co-chair)
- Pete Snyder (Brave, PrivacyWG co-chair)
- Tara Whalen (W3C)
- Benjamin VanderSloot (Mozilla)
- Andrew Pascoe (NextRoll)
- Ari Chivukula (Google Chrome)
- Joey Stanford (Platform.sh)
- Michael Kleber (Google)
- Don Marti (Raptive)
- Justin Brookman (Consumer Reports)
- Kelsey Gilbert (Mozilla, WebGPU)

Apologies: 

- Christine Runnegar (invited expert, Privacy WG co-chair)

Chair: Nick

Scribe: Michael Kleber, Tara as backup

## Agenda

### 1. Introductions, Code of Conduct

https://www.w3.org/policies/code-of-conduct/

- lot of passionate people with differing opinions, let's work together with dignity and respect
* Ben VanderSloot - first time at Privacy WG meeting but long-time privacy person

* Kelsey Gilbert (Mozilla): co-chair WebGPU, joining to discuss agenda item

CryptPad becoming more inaccessible to more people! W3C Team to look into alternatives.

### 2. Open privacy reviews: status check

#### Input Events

https://github.com/w3cping/privacy-request/issues/147
Jeffrey Yasskin is doing TAG review; Pete completed a review for Privacy WG.

- Old way was to register for change events, level1 version of spec let you register for an input event (even before the change is committed), level2 adds a beforeinput version (i.e. can modify event on the way in, before the change reaches the page).  
- Also level2 adds more information about the sources of events.

Substantive observations:

- Normative section of document referring to nonnormative definitions (e.g. "kill buffer") which may lead to ambiguity

- Didn't understand how the history interaction part of the spec interacts with the page modifications stuff

- Some browsers don't fire events in some situations that are security/privacy sensitive (like using a password manager); want to check with people who made those implementation choices to see if they should be reconciled / noted / etc. in the spec.

#### Verifiable Credentials

https://github.com/w3cping/privacy-request/issues/146

- Nick has started taking a look, not yet done.  Deltas from previous publication seems small and won't need a lot of work from us.
- Pete says Kyle felt that way too.

### WebGPU

[WebGPU transition request](https://github.com/w3c/transitions/issues/676)

[fingerprinting surface issue](https://github.com/gpuweb/gpuweb/issues/3101)

- Kelsey Gilbert: All WebGPU WG participants are satisfied that they have mitigated the issues raised in that review.  Specifics available in the closing statement of the issue.
- Nick: Different mitigations were discussed in PING — different permissions for different browsers, removing fields that aren't used...
  https://www.w3.org/Privacy/IG/summaries/PING-minutes-20230706#1-webgpu          
- Kelsey: Structured the spec so that UAs can use a permissions approach if they want to, even though the UAs implementing so far have not chosen to do so.
- Kelsey: Many limits in the spec, but in practice not very much entropy being given out. If you want hardware-accelerated rendering, then observing the behavior of the rendering inherently gives away enough of the underlying hardware implementation to know what the card is. You can run in software mode and that is consistent across devices, if you are willing to tolerate the performance deficit.
- Pete: Seems like this all puts the privacy-helpful behavior outside of the spec, seems like an anti-pattern
- Kelsey: Feel free to join the WG, but we have exhausted our ability to figure out changes in those directions.  We feel we've tried very hard to move in your direction and we feel satisfied.  What are the next steps, if you're not satisfied?
- Nick: Thanks for coming back and doing the work.  Anyone else have comments?
- Ben: How much gap is there between the "necessarily revealed by allowing hardware acceleration" information and what the API reveals?
- Kelsey: The expert opinion of our WG is that we are already at the point where there is no gap.
- Nick: Summary is that there is information that is revealed by the accessibility of hardware acceleration, so a browser or a user concerned about not revealing that needs to not provide the functionality at all.
- Pete: That's partly my understanding.  (1) When is this functionality available to sites?  (2) Is there a way to reveal only a little bit?  (3) How much is made easy vs difficult for the site to get?  For next steps, I'm happy to keep discussing and attend another meeting, if the opportunity is still open.
- Kelsey: We don't think there is more to discuss along those lines; I don't think our group can satisfy you here.
- Pete: Perhaps there is nothing that is acceptable to you and privacy-preserving to me, in which case next step is that you move forward and a formal objection is filed.
- Kelsey: That seems like the direction this is going, and also seems unfortunate.  If you feel there are avenues to pursue, then please present alternatives!  We think we have explored all the options.
- Nick: I will put something on our mailing list, Pete will join a meeting (in January, possibly January 8)
- Philippe: If the Privacy WG wants to object to the formation of the WebGPU WG, then they should speak up.  Team has received a Transition Request for WebGPU and needs to act on it.

### GPC

* reviewing PRs based on last meeting's discussion

* https://github.com/w3c/gpc/pull/87 addressing w3c/gpc#82
  
          - About not blessing any particular regulatory approach
          - Nick: Thank you, seems good, though the folks who brought this up at TPAC aren't here

* https://github.com/w3c/gpc/pull/88 addressing w3c/gpc#80
  
          - Adding discussion in the explainer about agreements to share information on specific sites, which various regulations have opinions on.  Jeffrey has asked for a sentence in the spec as well; Justin will add it.
          - Nick: Seems good to point out this capability that is outside of the spec somewhere.
          - Ben: Looking forward to the Jeffrey-requested addition, I'll add it to this PR very soon
          - Michael: Justin: can you add your name to Github so we know who is making the pull requests?

* What do we need to do to have a separate Explainer document that we publish?
  
  - Philippe: Need automatic transformation from markdown to something digested.  Main spec using respec so probably switch this to use respec as well.  Keeping the same editors, unless/until you tell us not to.  In the team's hands.
  - Nick: Anything else?  We need to come up with a name?
  - Philippe: Up to the editors.  It will be "GPC Explainer" until you find a better name.
  - Justin: I'll talk to the other editors and find a better name soon.

### AOB

* privacy considerations for Digital Credentials Community Group Report]()
  
  * Nick: Community group trying to provide access to various kinds of credentials
    
    * could be government-issued, could just be a token from a website.  Nick pointed out to that group that the document they are preparing should have a privacy considerations section early on, fill out at least a skeleton of privacy implications and questions even if we don't have answers yet.
  
  * https://github.com/WICG/digital-credentials/pull/189 to add headings to their doc
    
    * user considerations, threat models, just headers for now but would be great to have additional text about the questions to consider.

* Request-OTR: should we suggest adoption into this Working Group?
  
  * Nick: Proposal to IETF and WebAppSec, want to get update on status of doc and whether this WG is ready to work on it.
  
  * Pete: No change sto spec or proposal, we are still interested if other people are.  Would give sites a way to indicate that the UA should try to isolate the impacts of visiting this site from other users of the device.  For sites with high-privacy-needed content, like health care or domestic abuse sites where you may not want other people with access to your device to know that you've accessed them.  Would love to work on it if other people in this group are interested.
  
  * Nick: Others from the browser side have looked into this?
  
  * Michael: unsure if Chrome folks have looked into this issue, will ask around to verify
  
  * Ben: I think Mozilla folks looked at this and had a couple of minor concerns but feel the use cases are compelling and we want to discuss.  This seems like a reasonable venue.
  
  * Pete: We have an implementation in Brave (aside from on iOS), so if people want to work on this space, whether or not in this particular proposal, we're interested in working on any approach.
  
  * Nick: Next step: Could we phrase charter language that people are interested in working on, without committing us to any partiuclar detailed answer.  We should let our browser folks look into it, then in the new year look at charter text to give us room to work on the topic.
    
    * (general thumbs up reactions in video and emoji)
- References:
  
  - (expired) I-D: https://datatracker.ietf.org/doc/html/draft-sahib-httpbis-off-the-record
  
  - presentation where it was discussed: https://datatracker.ietf.org/meeting/117/materials/slides-117-httpbis-sessb-request-otr-00
  
  - Brave blog post on their implementation: https://brave.com/privacy-updates/26-request-off-the-record/
