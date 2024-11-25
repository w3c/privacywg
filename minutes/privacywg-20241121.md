# Privacy Working Group meeting - 21 November 2024

## Attendees

- Nick Doty (CDT, PrivacyWG co-chair)
- Christine Runnegar (invited expert, Privacy WG co-chair)
- Sebastian Zimmeck (Wesleyan University)
- Justin Brookman (Consumer Reports) 
- Tara Whalen (W3C)
- Kelsey Gilbert (Mozilla, WebGPU) (briefly)
- Joey Stanford
- Philippe Le Hegaret (W3C)
- Jeffrey Yasskin (Google Chrome)
- Chris Needham (BBC)

Apologies: 

- Pete Snyder (Brave, PrivacyWG co-chair)

Chair: Nick

Scribe: Christine

## Agenda

### 1. Introductions, Code of Conduct

https://www.w3.org/policies/code-of-conduct/

Nick gave a reminder of the code of conduct, especially about being inclusive and appreciating/seeking diversity

Introductions from Kelsey, will attend next meeting when we can discuss WebGPU

### 2. Open Privacy Reviews

## Accessibility Conformance Testing (ACT) Rules Format 1.1 2024-07-24

w3cping/privacy-request#141

Nick: there is a brief merged privacy and security considerations, appears they do not think there are significant privacy issues
PLH: testing, not consumer facing
Nick: looking for a reviewer
Jeffrey: [TAG examined](https://github.com/w3ctag/design-reviews/issues/977), it is a spec for specs, how to write a specification for accessibility requirements, no privacy considerations. It describes itself as a "format" though, and the TAG suggested they should think about making it machine-readable, perhaps to load tests into tools. If they do that, there probably would be privacy and security considerations, to ensure the loaded tests don't do anything outside the page they're meant to be testing.

### 3. GPC

Nick: published a first public working draft
PLH: Aram needs to join the WG before we can enable auto-publication (due to system requirements)
Nick: a good reminder, please remember to join the new WG, if problems contact chairs or W3C team
PLH: closing the IG in the next few days
Nick: will not remove people from mailing list?
PLH: correct

## a. Move laws to explainer gpc#81

Justin: feedback from CG that there is a lot of legal discussion and this is not the right place, should be in an explainer that can be updated more easily, put in a pull request, everyone seemed to think made sense, wanted to wait for first public working draft, one suggestion to have even less legal discussion, seems to be consensus, suggestion is to merge it and then tweak it over time if necessary (minor changes)
PLH: +1, we already have a decision to public the documents separately, which repo Justin?
Justin: defer to WG
PLH: once merge, needs to go into proper HTML W3C/respec, we can discuss
Chris: comfortable with giving historical context, but still discusses at least 2 states have identified ... feels like discussing things that are moving target, minor tweaking, if you are comfortable, I might suggest some wording
Justin: that's fine, I hear what you are saying, fine to say 2 states and others have opt-out, but totally agree that precise discussion should be in the explainer
Chris: read again and propose minor change
Justin: can hold off merge
Chris: merge and then I can suggest
Justin: okay
Nick: need a reminder?
Chris: no
Nick: seems like consensus to merge PR and thanks to Justin and Chris
(consensus on the call)
Nick: noted if someone finds an issue we can resolve
PLH: what name for the explainer?
Jeffrey: something else, not explainer, haven't double-checked what the document is trying to do, something re: legal
Christine: legal context, legal landscape
Justin: has other things in there, background and legal, the point is it is not just about legal issues
Nick: leave to editors to come up with a name
Joey: Legal and Implementation considerations 
Justin: fine with Joey suggestion
PLH: considerations?
Jeffrey: +1 for editors to decide

ACTION: GPC Editors to figure out the title for the GPC Explainer

Title: "GPC: Legal and Implementation Considerations" with https://www.w3.org/TR/gpc-considerations ?

## b. Say that the do-not-sell-or-share preference applies unless the site has an overriding signal gpc#80

Jeffrey: in privacy principles, a long discussion about what overrides what, signals, GPC is a general signal, sites don't have a way to overide, seems specific knowledge should override, but risk of threat banner, but if site has a good reason to ask again they should be able to do so, suggested some text in this issue
Justin: totally on board with that, can iterate on in the explainer, add a little more colour to the text provided by Jeffrey, do we want to make a normative statement about annoying users, once PR in, can iterate on that, confident that we can find a path forward
Sebastian: GPC signal can be per site, that is also how some browser extensions are implemented, maybe this could be made clearer
Nick: does this need to be specified? in the spec, or is the spec just to tell sites what they have received and sites will figure out themselves what to do
Jeffrey: specify one way in the spec, browser could misrepresent users, sites don't have a way to tell browsers to check user's preference and we don't want to add API, warning don't annoy users seems reasonable, should be able to use more specific, pointed to https://www.w3.org/TR/gpc/#definitions, possibility that singal is wrong and sites should be able to get that knowledge
Justin: minor tweaks to clarify would be helpful, specific override general and more detail in explainer, happy to take on as an action item
Sebastian: also agree with that, explainer is a good document where to do that, also some laws and regulations do that, conflicting privacy principle
Joey: q for Jeffrey, would an alternative approach be feasible, where we pass that the user did set as opposed to a browser default?
Jeffrey: would also solve, but contrary to the design of the header which is one bit, also "don't annoy user" could be in the spec's Privacy Considerations, other text in explainer
Nick: 3.1 expression format has some text, might be a place to modify to say what we want to say here. in DNT we did have an API for sites to communicate back to browser, but didn't succeed for this purpose, don't think a good idea - sounds like Justin will come up with text for spec and explainer
Justin: yes

## c. Add a security considerations section gpc#84

Nick: reminder from W3C team to add a security considerations section
PLH: need before we move to CR, start with the security and privacy questionnaire for inspiration as to what needs to go in there
Nick: Sebastian?
Sebastian: can do this, need some time and pointers to good examples

## d. If we have time, could get started on 82, 83

Justin (re: issue 82): heard at TPAC, CG, GPC is opt-out based signal and others say we blessing status quo tracking, happy to draft language in shortish-term to solve, say no endorsing tracking, just a tool, don't think it will be super controversial
Nick: maybe in introduction

(re: issue 83) Michael said some uncertainty as to what it is turning off, we should clarify not intended to turn off first-party, happy to address that, perhaps also addressed by the PR to move text to the explainer

Aram: do we have a specific language W3C on cross-site tracking etc?
Jeffrey: not in privacy principles re advertising, but maybe something from PATCG
Aram: maybe we can reference something there for issue 83 as well
Nick: Justin to consider whether the PR resolves or whether we need new text
Jstin: it is important, we should address it

### 4. Other documents

## a. Security/Privacy Questionnaire

Nick: Jeffrey pointed out that for shared documents need clarity as to process for changes/publishing
Jeffrey: does the editor need to come back to the relevant groups before changes are made
PLH: my hope, not (given autopublishing generally proposal)
Nick: would there be some check point?
PLH: we can to do that, or rely on editors to let us know when to check, could do a check at least once a year at TPAC, for example
Nick: proposal: Pete is the current editor from WG, we as a group could commit to doing a review at least once a year
PLH: could be once a year at TPAC, could do for all documents of the group
Christine: that seems reasonable
PLH: if someone notices something earlier, can bring up
Nick: seems consensus, will also send on email
(consensus for yearly check, formally, and informally as needed as concerns are brought up)
PLH: keep in low key and rely on editors to do the right thing

## b. Autopublishing generally

PLH: should do by default, can always decide otherwise on a case by case basis if needed
Nick: for standards, rec track, there are decision points of maturity (e.g. move to CR), PLH please help me with text for email to the group

### 5. Privacy topics from IETF 121

## privacy.txt

Nick: came up in ALLDISPATCH, researchers and one corporate author proposed a privacy.txt pointers to human readable policies and actions you might be able to take, some machine readable information on cookies in use, might seem similar to some proposals in W3C, but it is possible that it might be useful right now given the state of the technology, could reach out to authors and suggest might be of interest with CG
Aram: [IEEE 7012 WG work](https://standards.ieee.org/ieee/7012/7192/) seems very similar, do we want to push there? conceptually the same thing, facilitate user consent through and agent, could be fairly similar?
Nick: that would also be in this category, maybe one thing to point them to, but i think this proposal is more specific
Aram: that work in IEEE might be getting fairly close to publishing
Nick: maybe we recommend they look at it or cite it
Aram: a list of cookies is already required by the EU, the goal would be to accomplish something beyond listing, IEEE work seems closest to something "actioned"
Nick: will communicate to authors and potential incubation discussion

Slides: https://datatracker.ietf.org/meeting/121/materials/slides-121-alldispatch-a-file-format-to-aid-in-consumer-privacy-enforcement-research-and-tools-01
Draft: https://www.ietf.org/archive/id/draft-colwell-privacy-txt-00.html

### AOB

## interest in Asia-Pacific-accessible call time?

Nick: would it be reasonable to rotate?

Christine: give time for more people to formally join the group, and then check.

Nick: yes


