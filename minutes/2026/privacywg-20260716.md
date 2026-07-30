# Privacy Working Group, 16 July 2026


## Attendees 

    Nick Doty (CDT)

    Pete Snyder (Brave)

    Chris Needham (BBC)

    Aram Zucker-Scharff (The Washington Post)

     Bhavani Shankar Garikapati (Invited Expert)

    Don Marti (Invited Expert)

    Sebastian Zimmeck (Invited Expert; Wesleyan University)

    Lola Odelola (Invited Expert)

    Max Gendler (News Corp)

    Benjamin VanderSloot (Mozilla)

    Ari Chivukula (Google Chrome)

    Benjamin Case (Meta)


Apologies: 

Chair: Nick Doty
Scribe: Shankar

# Agenda

## Introductions, Code of Conduct


## privacy reviews

some privacy reviews are new or significant enough topics that they would likely benefit from more discussion on a call:

    Attribution Level 1 2026-06-29 > 2026-07-29 w3cping/privacy-request#215

    [Benjamin] Provided overview

    private solution for cross site ad measurement.

    Threat model: on device privacy budgeting - uses differential privacy

    impressions are logged and stored on device database.

    Using 2 party MPC, encrypted reports can be submitted by website to aggregate them.

    [Don] Can we have two privacy reviews ? Can be most productive for mathematical proofs (DP math), and the second for the web, how it integrates with the ecosystem.

     [Pete] Number of concerns I have

    Not in aligned with priority of constituencies. This need not be good for users. Very beneficial for sites

    Not per site DP budget in place. Potential fraud issues of competitors and potential abuse to drain budget from one another.

     Potential fraud: Adversarial parties can collude and exhaust potential budget. What to do when budget is exhausted is not stated. 

    How to confirm guarantees/requirements documented in the spec but not described how to implement.

    [Benjamin] Broad constituencies and user value. Some of these are privacy concerns (leakage in API), others are utility concerns (eg: budget, fraud are utility concerns). Methods exist to restrict access to global budget (eg: rate limits). There is ongoing work to define threat model for potential Fraud. Sites should not learn about budget exhaustion, will look into it. All reports are encrypted and so users opting out of the API won't be visible nor will the budget exhaustion. 

    [Pete] Can colluding parties not break the Indistinguishability assumption whether budget is exhausted or not ?

    [Benjamin] Data is on the device, any data that leaves device is encrypted report. The report 1-party gets is nothing. They cannot learn anything from it. Data can be accessed only using aggreation queries. 

    [Aram] colluding parties need not use attribution API's if they share their impressions out of band.

    [Nick] What happens when something gets broken (the attribution services leaks or the encryption is broken) ? We need to clearly define accountability section. What could go wrong ? And how to address those issues when things go wrong. Can we also protect privacy of groups, not only individuals. Eg: All member of privacy working group are using a particular sensitive websites, even if the system doesn't reveal a specific user's browsing history.

    [Ben]

    Response to What happens when security is broken ?

    On device design - as underlying principle, so even if data leaks, there is lot less information that is lost. eg: nothing about impressions leaves the device. Data minimization principle, on what actually leaves the device makes it safe. WHat can be learned from the data that is in encrypted report is minimal (histogram bins.)

    [Sebastian] Relation of GPC and MPC has not materialized yet. For example, from a GPC perspective, users have right to opt out in California or Connecticut. it is important to not undermine this right with the Attribution API. On the other hand, GPC and Attribution API could also nicely complement each other.

    [Aram] GPC Is signal to site owner. When there is opt-out, the domain owner is responsble to manage the privacy preference by turning on or off the code that activates the impression. 

    [Lola] Bring attention to Ted's Review that was emailed to group. 

    https://lists.w3.org/Archives/Public/public-privacy/2026JulSep/0004.html 

    My comments are in private position, does not reflect opinions of my employer or the TAG, although the TAG is also discussing it.

    Second question: On the allowlist, if it is empty, does it mean the permissions are open ? Is there a mechanism for users to opt-out from attributions.

    [Aram] We anticipate that browsers will handle applying the UI like they do to other features and we have gone to the web extensions group for advice on how to make the control easily accessible to the user through installed expressions as well. 

    [Benjamin] Biggest tool we have API provides both sites ability to impose limits for fraud prevention (impression site can specify which advertisers could query agasint it)

    [Pete] Users should be asked (as a permission) whether these API can be used or not. This is much more user aligned.

    [Lola] Does it change the role of the browser ? Does it become data processor ?

    [Aram] Generally, we don't believe it is data processor as defined by regulators. Browsers make use of other data like fingerprinting that is very similar to this. We provide two specific outcomes. For adverstiers, you are using lot of data, that is invasive, not providing much benefit. This API would be more useful, while not violating user's privacy. For users, there is lot of things, browsers are doing right now, which in theory you can disable, but in practice, the websites may not work, or have a good user-experience, if you disable them. We know web is fundamentally supported by Ads.

    [Benjamin] Attritution API is many ways incremental to what browsers vendors are already doing (Eg: privacy sandbox). This standardize the path for all browsers.

    [Lola] If we talk about standarization, we should be careful. We should not do it because industry is doing it, but because we need it. We need to consider aspects like opt-out. Use of choice and users first is the approach we need to consider.  

    [Nick] We could have a separate call just to talk about this. Our goal should be getting some useful feedback as a group (consolidate) that we can provide. And, as had already started, might use the mailing list for discussion, since there are big topics that might not narrowly fit into github issues, that we want to eventually consolidate and file.


Roxana Geambasu (academic from Columbia University's Computer Science Department) willing to talk about differential privacy and the details with any reviewers who are interested.

    WebMCP 2026-06-25 > 2026-08-01 w3cping/privacy-request#213

    [Ben VanderSloot] Not editor, helping writing security & privacy implications. Spec helps write description of the functions, so that it can used by LLMs. Very big punt in S&P considerations. It says nothing about agentic browser.  

    [Pete] Typos in the spec. Main concern is that any function that takes anything and do anything is the lose standarization. Can we more narrowly tailor to more standarize the behavior ?

    [Nick] Shocked reading about seriousness of the threat. It is very broad. My concern with the approach, if we provide these tools that aren't generally visible, users and agents can be mislead. It makes much easier for malicious websites to mislead the users and agents to take actions.

    [ Ben VanderSloot] We have a pending PR, that we can restrict this to a form. Feeback is consistently, agentic browser will be tricked consistently, the gap of harm is less by introducing this feature.

    [Pete] always possible, but documenting visible buttons is more likely to give expectations of constrained behavior, rather than entirely open-ended.

    [Max Gendler] knowing next step of injection would be useful here - we saw a presentation on webskills this week at webai IG, so while not formally part of the webmcp work would be good to keep in mind [webskills presented to webai IG this week: https://docs.google.com/presentation/d/1del1JQrDneDNVdwMYkcyBqHaCRS-EarIVPT1TN4sFJc/edit?slide=id.g3f5231adf52_2_407#slide=id.g3f5231adf52_2_407]


    WebTransport update



## GPC

    status check on wide review steps: Seek wide review gpc#138

editors to work on wide review and seek help from chairs or other volunteers as necessary.

## AOB

may need to discuss at a future meeting

    doing a privacy review and presenting it to the Privacy WG in some form where we can give feedback

    Web Application Manifest looking for co-reviewer with @npdoty

