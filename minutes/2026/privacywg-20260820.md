# Privacy Working Group, 20 August 2026

## Attendees 

    Nick Doty (CDT)

    Pete Snyder (Brave)

    Christine Runnegar (ISOC)

     Benjamin Case (Meta)

    Beckett LeClair (invited expert, 5Rights)

    Ted Hardie (Invited Expert)

    Tara Whalen (W3C)

    Sebastian Zimmeck (Invited Expert, Wesleyan University)

    Justin Brookman (Invited Expert, Consumer Reports)

     Bhavani Shankar Garikapati (Invited Expert, Lyft)

    Don Marti (Invited Expert)

    Ehsan Toreini (Samsung)


Apologies: 

Chair: Nick Doty
Scribes: Shankar and Pete

# Agenda

## 1. Introductions, Code of Conduct

Hellos and intros from Beckett and Ehsan

## 2. privacy reviews

### 2.1 doing a privacy review and presenting it to the Privacy WG in some form where we can give feedback

https://github.com/w3c/privacywg/blob/main/howto-conduct-a-privacy-review.md

Pete: keeping a guide on doing privacy reviews, and chairs trying to improve as we get an increasing number of requests. chairs often triaging -- if there's a spec that doesn't have notable privacy-relevant issues, we can just close it out and mention it to the rest of the Privacy Working Group.

Reviews are done as individuals, we don't always agree on a consensus group position on a review, but we have different expertise and opinions and requirements. 

Some issues come up perennially: behavior might be privacy-concerning, but it's dependent upon some other technology in the web platform, and that spec doesn't conform to our privacy expectations and the Privacy Principles. Sometimes we file an issue with the underlying spec, or add a note to the higher level spec until it's fixed., but trying to bring more expertise to bear, and resolving questions as a group when we can.

It's especially helpful to have more reviewers. if you haven't done a review before, then it's great to work with someone else who has done reviews before. You can also focus on subjects where you can add your specific expertise but not feel pressure to find and catch every issue.

For reference, you can find new charters through:
    * the public list - https://lists.w3.org/Archives/Public/public-new-work/ 
    * on GitHub, you can see drafts: https://github.com/w3c/charter-drafts
    
Christine: One of the questions we get is how to fix it (privacy issues). Keep in mind: we may not have expertise to fix the vulnerability. Don't be concerned if the group asks what to do next. Provide an overview of the issue, the concern that needs to be addressed.

### 2.2. follow-ups or further discussion (Attribution, WebMCP, Web Transport, any others?)

Don: on displacement/substitution effects, previous efforts on Google Privacy Sandbox and Safari, (Google’s “Privacy Sandbox” included an Attribution Reporting API, Apple Safari has “privacy-preserving ad attribution” that came out in 2021 -- any info on adoption of those features as replacements for other tracking?)

Pete: concerns over users sending messages even when they have indicated that they do not want to report to these systems

Ben: When Users opt out, it is indistinguishable to websites.  Do we want two modes: opted-out in undetectable way (sending no useful data/can't distinguish user) or obviously opted out (but that status can be detected)?

Ted: If its not possible for sites to know if the user is participating / contributing, or has the feature enabled, how would that impact the possiblity of the site disabling other, more odius practices? If the site can't be confident the user is participating, then it raises the possibility that this will be additive information, and not substitute for other practices.

Its also possible that this feature would improve privacy in jusridictions where there are regulatory requirements that encourage or force sites to use this capability, but could reduce privacy in other regions.  That might be net positive for the Web, but its not clear.

Nick: I understand that the goal is for implementors to reduce risks to users for enabling, but what exactly the risk is to the user might not be certain; how can we quantify that risk? Spec does not specify an epsilon. Could the spec specify a range? Or if the range isn't specified, do we know what the amount or risk of exposure is given a particular implementation's epsilon?

Benjamin: re opt-ing out is the same as setting a budget to zero, we could specify the implementation this way.

There isn't an individual level that an advertiser could know the budget remaining for particular participants, but spec specifies epocs, and at the start of each epoc the budget resets. Sites could find that if the site is useing the buget too aggressively, they start getting null reports, and could adjust how they use their budget accordingly. Week seems reasonable to allow sites to tune behavior to optimize the sites utility.

re displacement, a shift from current privacy harming behaviors to this behavior would take time and not occur all at once. Also, this is the first step in the advertising space, but doesn't replace all status quo advertiser uses / needs, and we're exploring things that could increase advertiser utility

re episilon, i think standards bodies are unlikely to set ranges, implementors would need to decide (thats how the WG has handled things so far). Waiting to hear back from implementors
   
Ted: Can you say more about why the spec can't give a range of episilon recomendations? Even if they're not binding on implentors, and they're "only" intended as guidance.

Benjamin: Difficult for standards bodies to make these decisions bc of economic impact.  WG didn't think this was in scope. WG has had presentations on episilon values in real-world systems. I can try and give pointers on those discussions.

Pete: Other reason to have guidance (epsilon values), it is difficult to think through when different participants have different values, to determine the privacy impact. 

Benjamin: It is your's epsilon value, that will impact your privacy, it is not impacted by other participants epsilon values. MPC helpers respect most conservative choice in a batch, and apply noise accordingly. 
 
 WebMCP
 
Nick: we haven't closed the review out and filled all issues. I will file more issues and move discussion to slack. The primary reviewer (Ben Vandersloot) on leave and can't organize our feedback at the moment.
 
### 2.3. other review requests (Web Application Manifest looking for co-reviewer with @npdoty)

Nick reviewed a long time ago, haven't re-reviewed yet, but would be happy to work with someone to review.

### 2.4. CSS Image Animation
Reviewer: Pete
Proposal: https://www.w3.org/TR/2026/WD-css-image-animation-1-20260409/

allow site to control whether image is animated

Pete: the review I left on non-normative concerns
https://github.com/w3cping/privacy-request/issues/218#issuecomment-5288707192

- no privacy concerns in general, more criticisms about the spec itself (e.g., lack of clarity in the writing)

### 2.5.Immersive Web
Charter: https://w3c.github.io/charter-drafts/2026/iwwg-charter.html
Reviewer: Pete

- charter; topic is domain like VR goggles and similar tech
- group mentioned wanting to work on very specific APIs that learn about device capabilities. This is generally not a good approach from a privacy perspective: it's better to not collect information about devices, and there's guidance about this

Pete: the review i left on the charter, with several notes on where the charter text conflicts with privacy principals and the TAG's design principals
https://github.com/w3cping/privacy-request/issues/220#issuecomment-5259810792

Nick: will do Verifiable Credentials review

## 3. GPC: status check on wide review steps: https://github.com/w3c/gpc/issues/138

Ted, Lola, Beckett may be able to help with accessibility
Beckett to help with security
Justin and Nick to look at internationalization
TAG review request already filed.

## 4. AOB

### Web Transport
Pete: Concern about Partitioning definition, which is largely unspecified. It is not unique issue to this spec. Ideal outcome is to discuss this in the spec.  



### TPAC

Privacy Working Group? other meetings / breakouts / workshops?

Tara: Other groups will be meeting, including the PATWG folks working on attribution. There are some small workshops (longer break out sessions) being held too on Wednesday, on topics like age verification, AI and society (? might have heard that wrong). There will be disucssion about tech + policy issues and overlap. Also equity discussions

Christine: WG will sometimes reach out and request PrivacyWG memebers to join their meetings, to talk through privacy issues in each WG's work. We have not gotten those requests yet this year, but they might come in

Nick: Are there things folks in this group would like to discuss (even if ad hoc, not in the formal agenda)? Please file an issue if so

Christine: 
    1. is there any value in a short breakout meeting for GPC to socialize, at this point in the process?
    2. we could have a breakout brainstorming meeting?

Sebastian: I think meeting to discuss GPC is a good idea, but I will not be there. 

Justin: I'll ask the other GPC folks

