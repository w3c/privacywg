# Privacy Working Group, 16 April 2026

## Attendees 

1. Nick Doty (CDT)
2. Pete Snyder (Brave Software)
3. Sebastian Zimmeck (Wesleyan University)
4. Ted Hardie (Invited Expert)
5. Ben VanderSloot (Mozilla)
6.  Bhavani Shankar Garikapati (Invited Expert)
7. Christine Runnegar (co-chair, invited expert)
8. Aram Zucker-Scharff (The Washington Post)
9. Jeffrey (Google; TAG)

Apologies: Tara Whalen

Chair: Nick Doty

Scribe: Sebastian

# Agenda

## Introductions, Code of Conduct

https://www.w3.org/policies/code-of-conduct/
"Encourage all voices. Help new          perspectives be heard and listen actively.
Be aware of how much time is taken up by dominant members of the          group. If you find yourself dominating a discussion, it is especially important to step back and          encourage other voices to join in."

Nick: One of the items that is particularly relevant is to encourage all voices. It is important that everyone has a chance to participate. If you are not sure, please speak up. We are grateful for any particpation.

## group charters for review

(https://github.com/w3cping/privacy-request/issues?q=is%3Aissue%20state%3Aopen%20label%3Acharter)

Nick: Whenver there is a new charter or revision, there is a horizontal review necessary. Usually, it is straightforward and approval is quick.

Christine: The purpose is to identify problems early on. At the charter stage, that is a good point in time.

### Accessibility Group

- Reveiwer: Nick
- Issue: https://github.com/w3cping/privacy-request/issues/201

Nick: Accessibility guidelines also requires/does horizontal review. They do not refer to ethics. Maybe, they do not have that, but that is something we encourage groups to have in their charter. Also, security and privacy implications are good to mention as well as inter-operatibility.

### WebAuthn

- Reviewer: Nick
- Issue: https://github.com/w3cping/privacy-request/issues/202

Nick: Substantively speaking, WebAuthn group is adding new functionality, e.g., for passkeys and credentials more broadly. Also, they are adding additional trust signals for hardware on device for authentication. They want to communicated additional signals. That was a controversial item in the past WebAuthn specs. There are obviously a lot of privacy and security implications. It could also involve that you can only use certain software and not others. That is a head up for work that is coming up, but also giving them advice to anticipate or document the issue and how to address it in an effective way.

### Math

Shankar: Will provide findings in a doc for Math working group Privacy Review Request in a week

### Web of Things

- Reviewer: Nick
- Issue: https://github.com/w3cping/privacy-request/issues/204

Nick: Web of Things. They published a document on privacy and security guidelines a while back. Maybe, we can suggest that they can update it. Their work is not yet completely figured out. So, there is an opportunity to make an update.

### WebPerf

- Reviewer: Pete Snyder
- Issue: https://github.com/w3cping/privacy-request/issues/195

Pete: Web Perf. In addition, to deletion and additions, it is about how a group has responded to privacy and security issues in the past. How where those addressed? That is what I have been looking into. The main issue that has come up is user consent and being informed. There are a number of related performance APIs, particularing timing APIs. In parallel, there are other Reporting APIs where the page can ask the client and receive back a lot of different information. E.g., the browser is using a deprecated API. Some of them have straightforward privacy concerns, but others seem to not have clear scope or even put users at risk. In 2023, there were already a number of discussions and issues, but there has been little progress. This is also a task for Tara and the W3C to take on. I will do a more thorough review of the charter. But I do not think this is resolved. It is worthwhile to keep the issues open.

### Other Charters

Nick: Any other comments? Web assembly?

Ted: I am interested. Part of what is happening here is that they are narrowing their scope. Has that surfaced anything that we care about. Feel free to put my name on for looking into that.

Pete: I will sign you up.

Nick: I have some comments to file. I am looking at the perf stuff and web assembly.

Pete: Close out Math and Accessibility? Nick: Leave open for the time being.

## privacy reviews

(https://github.com/w3cping/privacy-request/issues?q=is%3Aissue%20state%3Aopen%20-label%3Acharter)

Nick: On the privacy reviews, CSS specs assigned to Roy. Shankar will have an update on MathML to the Working Group soon.  Then, we have three new specs in the RDF space. Semantic Web and data models. They are likely small and just describe what has changed. We are looking for reviewers for those. They will be similar. 

Then, Web Transport.

Pete: Looked at an earlier version a few years back. There are some issues. Cross-site and also statistics APIs. Could be user-interest vs site-interest issues. There could also be some concerns on what a network partition key is. That is intentionally under-defined. Top-level with sub-keys (?) and some people are not completely sure about that definition. Another set of eyes may be valuable.

Ted: Did you look at fingerprinting etc.?

Pete: Yes. Useful to look also in this context on the under-defined definition.

Ted: A number of works going on in IETF regarding connection pooling and media (and other) running over QUIC. It is difficult to surface. Part of the issue is that it is too high-level. Need to go into the 10,000 foot level vs 30,000 foot level. Not quite sure how to do that.

Pete: Sounds like privacy concerns are open and addressed. Other approach is that it is not yet recommendation stage. So, can still be addressed. 

Christine: Elaborate more on what Pete was saying?

Ted: The issue is how it is going to be and going through the liaison process. Fingerprinting may be good to think about for Qlog especially, Because the dictionary allows you compresssion. Gathers data that is more compressable. And there are security concerns. Set up conversation with Will Law (?). Is the mechanism that I sent Pete and Will a note?

Pete: Filing the issues and concerns is good. There is no fixed deadline. At one point we need to have one, but we are not there yet.

Ted: I will be traveling, but I will send a note to Will and cc you, Pete.

Nick: Network partition key, I thought better definition, but did not realize issues on the IETF side. It is good that we are noticing those. 

### Web Transport (initial review)

- Initial reviewer: Pete Snyder
- Request Issue: https://github.com/w3cping/privacy-request/issues/205

## GPC updates 
    * (including w3c/gpc#113, w3c/gpc#114)
    
### Does the GPC Support Resource apply to origins or sites? (#113)


Nick: Get some updates on GPC. Wide review?

Pete: (filed by Jeffrey) on scope of .well-known resource. Origin seems like the right solution here. Pete will write text. (+1s)

### Define the header value parser (#114)

Pete: how implementations should handle malformed, multiple instances of the header with conflicting values, etc. Anne provided some answers, and Pete will follow the recommendation, write up the same solution that what Fetch is doing.

With those issues, I think we have all the technical issues addressed, can continue with seeking wide review.

## AOB

* age restriction/child safety update

Nick: I have one item. We have a follow-up session on the age restriction/child safety work. If you are interested in that, please feel free to get in touch. Ben is working on some proposals. Maybe, also good to start a Community Group. Not a specific track but to brainstorm and talk about requirements. I think Tara had a draft for a Community Group. I will share it with the group.

Christine: Shankar and Aram have indicated interest. I am also in favor. More online safety than just age verification. Jeffrey, maybe able to review.

Ted: I have people talking to me about this. I have concerns about this approach. E.g., Portugal and Spain approaches are not very good. In almost every case will create identifier that can be linked. But more than that, why are we stopping at children? Somebody just does not want to do the hard work at the regulatory level. If you think the algorithm is problematic, why does that stop at 16 years of age (e.g., as to the image of women on Instagram, it also affects older women). The obvious thing is that this has nothing to do with age verification but with regulating algorithms. So, a Community Group should not be just age verification but the broder picture instead.

Nick: I tend to agree. Online safety should be for everyone. You can provide technology with less data collection that would help everyone.

Aram: 100% with everything you said Ted. Coming at this from the angle of a media company. Yes, we need an online safety group, but maybe we also need a narrowly defined age verification Group. I would rather want this technology not exist, but there are state laws in the US that we are required to comply with. I feel the other side. What if it becomes too broad, and the very broad tool is the only tool. From a standards perspective, the narrow path is worthwhile to satisfy the unavoidable question. We are in danger of putting out something that becomes too powerful for a narrow use case.

Shankar: My experiene is similar to Aram's. I work for Lyft. Useful starting point and expand to other use cases.

Ted: I understand your and Aram's perspective. Not a slippery slope but cliff. Based on characteristics of people. This will not be the only thing we are being asked for. The most critical is regulators dealing with applications and service. E.g., digital wallet in Portugal or Spain, just expose some characteristic, based on that functionality can be turned off. Could be age, could be citizenship, ... We need to think narrowly to avoid what will naturally follow for authoritarian government and authoritarian tendencies.

Christine: Take a look at web authentication work. Maybe, the passkey model could be extended. They are related to user account and devices already. Maybe, with your thinking, you can take a look. I also appreciate what Ted said about the Community Group. It is part of the core W3C ethical principles to bring them to life (a safer Web). What do you, Aram and Shankar, have in mind for targeted approach?

Ben: Let us not overimagine the power of this Community Group. In practical reality the laws will come into effect. People will implement those. This CG is one place. It has no power to stop any of that.

Aram: This also goes into my concern. The technical work is already going on in other parts of the W3C (Verifiable Credentials, Digital Credentials, e.g.). My concern is, from the media perspective, things will come down differently than what the group is envisioning. The W3C is international. Feedback can be leveled from international contributors. Otherwise, we will end up with ceding the regulations to the government that gets there first. You could enact age control in Apple platforms. A lack of movement means that we will cede how this work, maybe, to Apple, which would be the best case. But it may be worse. Broad definition chances us to create the wrong feedback. By the end of this year, maybe restric all access to Apple users who is under a certain age. From a business perspective, that is not good.

Jeffrey: From TAG perspective, there seems appetite to address this. We discussed the IETF/W3C workshop at https://github.com/w3ctag/meetings/blob/gh-pages/2026/03-London/03-04-minutes.md#age-workshop-report. Keep us posted. 

Nick: Community Group is good place to discuss and generate text, and even though the W3C as a whole is unlikely to take strong opionated positions, we might be able to help other groups, like the TAG, that can make those strong opionated text.
Shankar: We want to know less about the user, but we are pushed into the other direction. The more we collect these, the more regulatory requests we may get about them.

Nick: Continue the discussion. I will take a first pass and take it up. I will propose some text.