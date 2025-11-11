# Privacy Working Group, 6 November 2025


## Attendees 

    Nick Doty (CDT)

    Benjamin VanderSloot (Mozilla)

    Don Marti (invited expert)

    Sebastian Zimmeck (Wesleyan University, invited expert)

     Justin Brookman (invited expert)

     Shankar Garikapati (invited expert)

    Aram Zucker-Scharff (The Washington Post) 

    Ted Hardie (invited expert)

    Pete Snyder (Brave Software)

    Tara Whalen (W3C)

    Jeffrey Yasskin (Google Chrome)


Apologies: 
    Michael Kleber — regrets, en route to TPAC


Chair: Nick Doty, 
Scribe: Tara

# Agenda

1. Introductions, Code of Conduct

https://www.w3.org/policies/code-of-conduct/

Welcome to:
Ted Hardie (Invited Expert), joining us from IETF meeting in Montreal!
Shankar Garikapati (Invited Expert), working on privacy and security at Lyft

2. GPC
GPC editors see stability and want to talk about next steps, including flagging a few issues for discussion:

Justin:
Syntax hasn't changed too much. CA passed law in Oct: all web browsers in CA must have some kind of opt-out signalling by 2027. GPC is pretty advanced but this should be place: legitimacy/solidity is useful for regulatory space. 
Several other issues have been flagged; we can plan resolution of these

    Progress toward Candidate Recommendation gpc#111

Give UAs more help in establishing user intent gpc#52
Is the user's request actually "except as permitted by law"? gpc#92

    Consistency in use of sell/share/track/target terminology gpc#94
    
#52 and #94
- changes to address relationship between user and site
109: not designed to affect same-site relationship -- site can show ads based on activity on that particular site

Last PR got most of issues
ready to close out #94 on terminology
#52 needs clarity for communicating to users about what is actually promised


Nick: #109 isn't merged, suggestion to link to definitions
Justin: not sure where W3C defines "site" but can dig into this for consistency
Jeffrey will send recommended textual change

Nick: Justin or another editor, please review Jeffrey's suggestion and we can move to merge that PR and close those issues on the mailing list.

Justin:
"do not share my data" user expectation might not match legal text; Jeffrey has approved PR of text change. Can merge and close {issue #92 PR #110}

Two outstanding issues:
    * if we change header to structured field values
    * whether to extend for further rights
    
Justin: would not be inclined to modify syntax right now, could create another header as needed, but maintaining status quo for now seems a better path. (don't want to break given the usage and legal enforceabiilty of what's already deployed and in use.)

Smaller issues exist: we can discuss these to get resolved. Robin Berjon wanted to tie this to other documents (e.g., principles), we can look into this.

Sebastian: we're measuring adoption of GPC and seeing a large growth in uptake. Dramatic increase (10x increase in a few months), so we should likely keep it stable (as Justin recommended). Legal non-normative guidance would be a good place for more explanation; I am working on a paper for GPC adoption in EU context. Explainer would be helpful for this initiative.

Aram: two big issues, the header + more privacy signals: there hasn't been substantive change in these, I recommend we close these out at TPAC, not much reason to keep them open much longer.

Nick - Next week we have TPAC. Chairs are not there in person. 12 hr later than *this* call. Are GPC editors going to be there? How would you like input? We will work on progress as best we can at TPAC.
We had discussed re: if there are related but not identical laws, can we add non-normative guidance? We could add to non-normative document in this case.
    
3. privacy reviews

css-color-adjust-1 2025-09-17 > 2025-10-31 w3cping/privacy-request#176

Ted reviewed this. One significant change: to detect use of "forced color" mode used to involve a request and now doesn't (user may not know), but this is minor.
Nick: this is a pattern, where sometimes it's harder to tell whether data is being requested. But in this case it seems benign? Ted: yes, *what* is being requested is same (just not "how").
Next step: reply to say "no action required", Pete will send message.

Geolocation 2025-09-01 > 2025-10-02 w3cping/privacy-request#172

Nick: old spec but has new amendments. Asked for privacy review. 

Pete reviewed the changes.
Issue to file - advisory only - add method, serialized info so can be saved as JSON text. JSON *is* text representation
Anything to or from JSON should be text/string
Jeffrey: Pete is technically correct but that's consistent with spec: 

https://webidl.spec.whatwg.org/#idl-tojson-operation

Jeffrey: it's going to return an object, webidl says that's what they are *supposed* to do. 
Pete: I will look at that spec and see whether that changes my comment

    Web Sustainability Guidelines 2025-10-06 w3cping/privacy-request#180
    Publishing a note and want wider review. Note that "sustainability" is being broadly applied/interpreted.
    Jeffrey would like a co-reviewer, please volunteer - especially as Jeffrey has already done reviews of this wearing other hats (e.g., TAG) Note that they are meeting at TPAC.
    Shankar volunteering to look at document.

4. differential privacy
Nick: back on agenda for process. Background: we're seeing differential privacy being applied a lot, appears in specs, should we give guidance? We have a note - thanks to Pete + co-authors. This is not recommendation track: it's a "Note"/"Note Draft". 
Do we want to publish it now or wait for it to mature to later stage? We have a lot of latitude in terms of process, since this is not rec track.
Proposal: publish as Note Draft, which shows "we're working on it but it's okay to publish". 
Or: we can ask editors to make a more mature draft before publishing.
Pete: would be good to move doc to Github, easy to do as Note Draft
Nick: it'll move to Github with the expected document format

Current doc link:
https://docs.google.com/document/d/1pE3p6TVsERPln00PLXj6j9rTdoG3PmiNHhv3NtXDtEU/edit?tab=t.0#heading=h.8174k9yshcu7

Looks like there is general support for Note Draft: Nick to confirm on mailing list about Note Draft and autopublishing.

    
5. TPAC
    https://github.com/w3c/privacywg/issues/17
    
    AB wants to come to talk to us about process given our role in formal review process.
    We have some open issues we can discuss.
    Google Chrome asked about third-party cookies and blocking from iframes - people are interested in topic, but recommend this be brought to the Privacy CG (rather than WG at TPAC). 
    Nick: you can add to TPAC agenda (on Github), hopefully by tomorrow so we can finalize agenda 
    
    
6. AOB
Ben: FYI - Mozilla has web platform tests for GPC now. Uses testdriver extension; not exhaustive but does cover reasonable amount of functionality. 

Jeffrey: TPAC scheduling tool: https://github.com/matatk/tpac-scheduling-helper, with the TAG's use at https://github.com/w3ctag/tpac-meetings/issues.
Can be useful to assign people to different groups. (Might be late for this meeting but hopefully good for next year -- privacy folks are super busy.)

