# How to Conduct a Privacy Review
(or, "what to expect when you're inspecting a spec")


## Questions and Concerns
This document is managed by the Privacy Working Group
chairs and <abbr name="World Wide Web Consortium">W3C</abbr> staff. Please feel
free to reach out with any questions or concerns you have.
<a href="https://www.w3.org/groups/wg/privacy/participants">List of current chairs and team contacts</a>


## Goals
This document is intended to provide a guide for how the privacy review process
works, and procedurally how to find, conduct, and complete a privacy privacy review.
This document does not describe the *substance* of a review, or the kinds of
issues to look for in a spec you're reviewing.  If you have questions
about about the substance of a review you're conducting, please reach out to the privacy wg chairs.


## Stages of a Privacy Review
The following subsections describe the different steps in conducting a review,
including how to [find a spec to review](#finding-new-proposals),
[where to find the proposed spec text to review](#reviewing-a-spec),
[how to share your findings on a privacy call](#presenting-a-review),
and [how to present your findings with the proposed spec's authors](#finishing-a-review).


### <a id="finding-new-proposals" />1. Identifying Proposals To Review
The privacy review process begins by a group formally requesting a privacy
review from privacy. Groups request a review by creating an issue
in WG's [privacy-request repo on GitHub](https://github.com/w3cping/privacy-request/).
New requests will appear as [open issues](https://github.com/w3cping/privacy-request/issues).

When the Privacy WG receives a new request, the Privacy WG chairs will usually send a message
out to all Privacy WG members in the rivacy WG Slack workspace #privacyreviews to invite volunteers to perform the review.
Sometimes, Privacy WG chairs may approach area experts directly or take on the review themselves. If you see a new review request for a spec
you would like to review, please feel free to contact a Privacy WG chair and let them
know. Most likely this will make their day and they'll happily assign the
review to you. 

Usually a proposal is reviewed by just one Privacy WG member, though occasionally
two or more Privacy WG members may collaborate on a review. This is more common
when a proposed spec is very long, highly technical, or one of the reviewers
is new to the process.

Privacy WG keeps track of which reviewer(s) are reviewing which spec by using the
"assigned to" field on each privacy-request issue.
[Review #56](https://github.com/w3cping/privacy-request/issues/56), for example,
was reviewed by three reviewers.

Privacy WG communication for privacy reviews is mostly done over Slack. If you would like to participate
in reviews, but are not yet on the Privacy WG Slack workspace, please contact a Privacy WG chair.


### <a id="reviewing-a-spec" />2. Conducting the Review
Once you've been assigned a privacy review, you can find the proposed
spec to review in the text of the privacy-review issue. For example,
[privacy-request #56](https://github.com/w3cping/privacy-request/issues/56)
is a request from the [W3C Web Payments Working Group](https://www.w3.org/Payments/WG/),
requesting a review of the [Secure Payment Confirmation](https://w3c.github.io/secure-payment-confirmation/)
proposal, the URL of which is https://w3c.github.io/secure-payment-confirmation/.

Your review should focus on the text of the proposed spec. However, you might
find additional, complementary resources helpful to understand the goals
and methods used in the proposal. Often the working group requesting the review
will include links to additional resources in the privacy-request issue.
For example, in [privacy-request #56](https://github.com/w3cping/privacy-request/issues/56),
the working group included a link to an "explainer" (or a high level, less
technical document summarizing the aims and means of the more technical document).
The URL of that explainer is https://github.com/w3c/secure-payment-confirmation/blob/main/explainer.md.

When reviewing the proposal, you should take care to read the entire proposal.
A comprehensive list of technical issues to consider is beyond the scope
of this document, but the W3C's [Security and Privacy Self-Review Questionnaire](https://w3ctag.github.io/security-questionnaire/)
(co-maintained by the W3C <abbr name="Technical Architecture Group">TAG</abbr> and Privacy WG)
may be helpful in identifying questions and issues to consider during your review. Another useful resource is the Group Note on [Mitigating Browser Fingerprinting in Web specifications](https://www.w3.org/TR/fingerprinting-guidance/).

Note the issues you identify during your review for later discussion. Issues
could either be specific issues you've identified, or general concerns
you're not sure about and would like to discuss with other members in the Privacy WG.

When you find other-than-privacy issues, feel free to open issues in the proposal's GitHub repo.  Privacy WG reviews typically happen as part of "wide review", in which all concerns about a spec are fair game. Those issues don't need to be discussed on the Privacy WG call nor tracked in our tooling.


### <a id="presenting-a-review" />3. Presenting Your Review to the Privacy WG
The next step is to present your findings to the rest of the Privacy WG, usually by
joining one of WG's bi-weekly calls. Information about Group calls and
how to join those calls are on the [Privacy WG home page](https://www.w3.org/groups/wg/privacy/).
A Privacy WG chair will work with you to add your review to a meeting agenda.

Presenting a review on a call is an informal process. Most of the
time members of the working group proposing the spec *are not* on the call. But, sometimes where it would be helpful for the reviewer and the relevant working group, editors and other members of the working group will be invited to provide an overview of the spec and to discuss its privacy considerations.

The review discussion process starts with the reviewer(s) summarizing 
the proposed spec to the rest of WG. These summaries are generally high
level, and not intended to describe specific method calls
or implementation algorithms in detail. The goal is to provide the rest of WG with
an understanding of the goals of the proposal, and enough background to
understand the privacy issues you've identified (and to suggest additional
possible areas of concern). It is helpful to describe the spec functions and features.

Next, reviewers describe each privacy issue they identified during their
review. These might be issues the reviewer is confident about, or concerns
the reviewer was unsure about, and wanted to bring to WG's attention for
further discussion and consideration. WG as a group will discuss each issue
as needed.

After discussion, the reviewer will retain, discard, or alter the privacy
issues they've identified as the reviewer sees fit. **Note that issues
from privacy reviews are filed as individuals, not collectively by WG
as a group.** This means that individual WG members may disagree on the results
of a privacy review, or might even file contradictory privacy issues if
WG members disagree. Disagreement is rare. In the case that a WG privacy review results in 
contradictory (or mutually exclusive) issues being filed, its the responsibility
of the working group making the proposal (and, ultimately the director)
to figure out how to proceed. However, the chairs will work with the working group and reviewer
as needed with the aim of resolving any outstanding issues.

If a reviewer is unable to resolve an issue with the working group
and the issue may lead to a formal objection, the reviewer
is encouraged to bring the issue to the WG chairs, who can schedule discussion with WG on a call.
WG can then explore other ways to try and resolve the concern without the Formal Objection. WG can also  document the concern and positions of WG reviewers and the Working Group, to facilitate subsequent resolutions of any Formal Objection.

### <a id="finishing-a-review" />4. Documenting Your Review
The final step in the review process is to present your findings to the
working group that requested the review in the first place. This
is done in several steps.

1.  Create GitHub issues for each privacy issue you identified in the
    proposal's repo.  (WG's
    privacy-request repo keeps track of privacy review requests we receive, but
    the substance of those reviews (i.e., the issues that need to be addressed
    in the proposed spec) must be filed in the repo for the proposed spec.
    For example, [privacy request #56]([Review #56](https://github.com/w3cping/privacy-request/issues/56)
    is an issue in WG's privacy-request repo, but issues resulting for the review
    should be filed in the [Secure Payment Confirmation repo](https://github.com/w3c/secure-payment-confirmation/issues).)

    Create one issue in the working group's repo for each issue you
    identified. We suggest starting each filed issue by noting i) that the issue
    was the result of a privacy review, and ii) with a link back to
    the privacy-requests issue requesting the privacy review. See, for example,
    the first line of [this issue](https://github.com/w3c/imsc-hrm/issues/28).
    
    Each privacy issue you create should include the following:
    
    -   A brief and succinct description of the privacy issue you identified
    -   If applicable, what resolution you think would be appropriate to solve / address
        the issue. It **is not** your responsibility to suggest a solution to the
        problem you identified (i.e., you don't need to provide a solution to the privacy
        vulnerability), though it can be helpful to say what criteria you would judge
        a solution by or to provide a solution if you have one. For example, if you identify new browser fingerprinting
        surface exposed by proposed spec, its helpful to say "this issue would be
        resolved by preventing fingerprinting scripts from accessing this information",
        but its not your responsibility to say "the spec should prevent fingerprinting
        scripts from accessing this information through methods X, Y, and Z."
    -   Add either a `privacy-tracker` or `privacy-needs-resolution` label to the
        issue (but not both). The `privacy-tracker` label denotes that you want
        to bring the issue to the group's attention, but don't think the issue is
        critical. The `privacy-needs-resolution` label denotes that you think the
        identified issue is critical, and that the proposal should not continue
        through the standardization process until the issue is addressed.  If you can't add the labels yourself,
        ask the chairs to add them.
    
2.  Once you've created an issue in the proposed spec's repo for each
    privacy concern you've identified, add a comment on the original
    privacy-requests issue summarizing your review. This summary can be just
    a list of issues you've identified; it does not need to include additional
    text. [This comment on the review of the IMSC-HRM proposal](https://github.com/w3cping/privacy-request/issues/65#issuecomment-1006978947)
    gives an example of such a review-summary comment.

3.  Finally, after you discuss the privacy review in a Group call, the chairs will close the privacy-requests issue. In some cases, the closing comment will note that there are still unresolved issues that will be tracked via the privacy-tracker.


### <a id="following-up" />5. Following Up on a Review
At this point you've successfully completed a privacy review.
Congratulations! The working group will respond to the issues you filed,
and hopefully thank you for your review. You are encouraged (though not
required) to continue discussing the privacy issues you filed with the working
group, as they try to understand, and then correct, the privacy issues you
identified.

Sometimes working groups will not agree with your issues, and thats okay.
However though, working groups should never close an issue you filed
until you agree that the issue has been satisfactorily resolved. If a working
group does close an issue in a way or for a reason you don't agree with,
please notify or involve a chair or team leader, who will gladly
get involved to try and address the situation.

Finally, if for whatever reason you are not able or interested in continuing
the discussion around an issue you filed, please also notify a chair
or team leader. We understand that obligations and availability change over time,
and we'll be glad to work with you to transfer ownership of an issue to someone
else.


## Links And Resources
- [Privacy WG Home Page](https://www.w3.org/groups/wg/privacy/)
- [Privacy WG "Privacy Requests" Repo](https://github.com/w3cping/privacy-request/)
- [Review label cheat sheet](https://w3c.github.io/horizontal-issue-tracker/HOWTO) - how to use the issue tracker
- [Self-Review Questionnaire: Security and Privacy](https://w3ctag.github.io/security-questionnaire/)
- [Mitigating Browser Fingerprinting in Web specifications](https://www.w3.org/TR/fingerprinting-guidance/)
- [Privacy Anti-Patterns in Standards](https://www.w3.org/blog/2019/06/privacy-anti-patterns-in-standards/)
- [Privacy WG Signup Form](https://www.w3.org/groups/wg/privacy/join)
- [Open Privacy Tracking Issues](https://w3c.github.io/horizontal-issue-tracker/?repo=w3cping/tracking-issues)
