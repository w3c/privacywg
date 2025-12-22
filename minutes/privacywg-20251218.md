# Privacy Working Group, 18 December 2025

## Attendees

1. Peter Snyder (Brave)

2. Nick Doty (CDT)

3. Tara Whalen (W3C)

4. Ben VanderSloot (Mozilla)

5.  Bhavani Shankar Garikapati (Lyft)

6. Don Marti (unaffiliated)

7. Ted Hardie (unaffiliated)

8. Joey Stanford (Invited Expert)

9. Jeffrey Yasskin (Google Chrome)

10. Sebastian Zimmeck (Wesleyan University; Invited Expert)

11. Justin Brookman (Consumer Reports, invited expert)

12. Michael Kleber (Google Chrome)



Chair: Nick Doty, Pete Snyder

Scribe: Sebastian

## Agenda

### 1. Introductions, Code of Conduct

https://www.w3.org/policies/code-of-conduct/

- Nick: Welcome, this meeting is under the W3C conduct. Let us hold up our cultural differences, especially, since it is the end of the year.

### 2. Privacy reviews

#### Web Sustainability Guidelines review @gbshankar @jyasskin

- Nick: We are doing pretty well on the backlog. But web sustainability guidelines are open. Two of our colleagues, Shankhar and Jeffrey, looked at that. Shankhar, can you provide an overview?

- Shankhar: No major issues. A few things and a final recommendation. Use a PWA over a native mobile application if it meets sustainability, interoperability, and compatibility criteria. Maybe I will also ask for feedback. Difficult to write good security-grade code. Users can be decieved because some controls are not visible to user. Should we say anything about it? 

- Nick: tend to see strength for privacy and security in the web model, certainly wouldn't want to recommend against that anyway.

- Joey: +1

- Shankhar: Other than that it is straightforward.

- Ted: We want to regularly test to maintain stability. Remove privacy portion entirely?

- Jeffrey: That is a critique I had that many things are not connected to sustainability and may not belong here. But it is worth addressing.

- Nick: +1

- Ted: I think it is a privacy-relevant issue. Either they have to put up one of those warnings or this type of warning is not an appropriate response.

- Jeffrey: Text is pretty short, and they do not have anything PWA-specific. 

- Ted: Will look at the repo again.

- Jeffrey: They worry more about sustainability. Is it good advice? Generally, PWAs seem to be more sustainable, e.g., smaller, but I do not have data.

- Nick: General sustainability vs environmental sustainability.

- Jeffrey: Both should be covered.

- Shankhar: Made a comment on fingerprinting. Identification of users is an issue.

- Nick: That seems relevant. Privacy may limit sustainability.

- Shankhar: I made a few comments on security too. I have a recommendation on crypto. Using random identifiers instead of fixed ones. Choices should be honored.

- Nick: On the caching, the previous one. Should be tied to user choices. But generally, we should not say that caching is generally bad. This is a case-by-case basis. When the user logs out, you have to delete the cache even if it counters sustainability. Just add that it is not always risky. 

- Shankhar:  Avoid use of unnecessary VMs.  

- Shankhar: Avoid incremental backups; avoid PI data in the logs. Clean logs with PI data.

- Shankhar: The last one is not related to privacy. Add fairness requirements and metrics on explainability.

- Nick: The Privacy Principles and other documents may have related comments. Jeffrey, do you have other points to add?

- Jeffrey: I made a list of points that related to privacy. I mostly see no problems. So, we do not need to talk about them. In some instances the organization is not great. That can be improved, e.g., they are talking about server-side processing, that should probably come with a warning. If you move it to the server that may be more sustainable but is now also available to the server. So, that is a privacy issue that should come with a warning.

- Nick: Thank you both. We should have a discussion of the breadth of the work. If you open issues or if you make a PR, drop it into the Privacy WG Slack so that others can have a look.

#### Open reviews including charters?

- Nick: Here are links to charters requesting privacy review. We have not identified anything specific to discuss in this call:
  - [i18n WG rechartering 2025 · Issue #189](https://github.com/w3cping/privacy-request/issues/189)
  - [Verifiable Credentials WG · Issue #188](https://github.com/w3cping/privacy-request/issues/188)

### 3. GPC

-  [Weak requirements language · Issue #35 · w3c/gpc · GitHub](https://github.com/w3c/gpc/issues/35)

- non-normative explainer/guide
  
  - Nick: We have one point to discuss here. I opened an issue on a legal point. But we have issue 35 to talk about. Justin?
  
  - Justin: We have added a ton of text since the issue was opened three years ago. We have included new language since then. It is more interesting about the specific flavor that Nick raised is more relevant. I am happy to further discuss, but there is already said a lot in the spec.
  
  - Nick: The concrete sentence is "should" vs "must", fine with me to just keep "should."
  
  - Jeffrey: The earlier "may" should probably be "can." Not giving normative advice, just explaining what could happen.
  
  - Justin: That seems reasonable, very short PR.
  
  - Sebastian: concrete sentence in current text, just changing the word "may" to "should"?
  
  - Jeffrey: Yes.
  
  - Nick: OK, then let us change that and close the PR. I opened the other issue, and we can talk about that.

### 4. AOB

#### Fingerprinting

- Nick: On fingerprinting, there seems to be some fuzzing work.

- Pete: There is no PR for review. But it is on my to-do list. The place where it would be helpful to clarify is: If you are doing randomization for fingerprinting protection, give guidance.

#### Request-OTR

- Pete: Brave still interested. In all Chromium versions but not turned on by default. If Brave-specific, need not be discussed in Privacy WG.

- Nick: Chrome or Mozilla folks?

- Ben: Interest yes, but nothing more to say.

- Pete: Keep it as a work item or what is the best way?

- Ben: Not hold it as work item from our perspective but there is also Chrome.

- Pete: We can talk outside of Slack and see what makes sense.

- a draft of interest: [off-the-record-ietf-spec/draft-sahib-httpbis-off-the-record.md at main · brave-experiments/off-the-record-ietf-spec · GitHub](https://github.com/brave-experiments/off-the-record-ietf-spec/blob/main/draft-sahib-httpbis-off-the-record.md) 

#### Any other upcoming technical work for Privacy WG?

- Pete: Is anyone aware of other work? Open call for privacy-relevant work to track, for example, that might need to find a home in WG. Bring work items for the future. Is there anything?

- Ben: In Anti-fraud community group: PACT proposal. Could be relevant. Though, may be an expansion. I will provide more info. It is early incubation. (https://github.com/antifraudcg/proposals/issues/22)

- Pete: Perfect example then. Call to keep this in mind when you go back to your companies. 

#### Additional item: auto-publishing

- Tara: Any concerns on autopublishing of the "Reviewing Differential Privacy" guidance Draft Note ?
- Group response: no concerns, approve auto-publishing


