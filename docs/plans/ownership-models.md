# Ownership Models playbook page - synthesis outline

Outline for rewriting `docs/InnerSource/Playbook/Ownership-Models.md` (finos/InnerSource#220, draft PR #379).
The earlier draft's four invented models are dropped.

The page's spine is **Russell's framework** (round 2), stated below as the author's view.
Everything hung on it is what the InnerSource community has already published, with the source named against each point.
Anything that is my suggestion rather than a sourced claim or Russell's framing is marked **[suggestion]**.

Every source listed was opened and read in full for this outline; quotes are verbatim.

## The framework (author's view)

Two questions, asked in order.

**Question 1 - who maintains it?**

- **A. An assigned team.** Maintaining the project is their day job: a funded, formal (e.g. scrum) team, even if everyone on it is from one business unit. This is one of the strongest ownership models.
- **B. People doing it in addition to their day job.** No team is assigned; maintainers give time on the side.

**Question 2 depends on the answer.**

- **If A: how open is the team?** Issues and bug reports only, small fixes, or entire features (and, further up, write access for outsiders).
- **If B: how many people are responsible?** Nobody, one person, a few, or three or more. Side-of-desk maintainers are effectively always open to contributions, so openness is not the variable; headcount is.

## How the published material maps onto the framework

### Branch A - an assigned team

The community's openness ladder lives almost entirely here.

| Openness (author's wording) | Governance Levels pattern | Flutter InnerSource Pyramid | Learning Path PL05 (paraphrased by me) |
|---|---|---|---|
| Closed | (none) | Stage 0 - Closed Source | (none) |
| Issues and bug reports | 1. Bug Reports and Issues Welcome (aka Readable Source) | Stage 1 - Readable Source | Code visible, no time to mentor; only feature requests and bug reports |
| Small fixes / entire features | 2. Contributions Welcome (aka Guest Contributions) | Stage 2 - Guest Contribution | Patches welcome, time set aside to mentor; "Final decision making though rests with the team of Trusted Committers" |
| Outsiders invited to commit | 3. Shared Write Access | (folded into stage 3) | Open to sharing write access after building trust; "can remove the review bottle neck" |

Sources that describe the assigned team itself:

- Flutter stage 2: the maintaining team "retain full accountability" and, on accepting a contribution, "will take forward responsibility for it". ([Guest Contribution](https://innersource.flutter.com/how/guest-contributions/))
- Learning Path PL05, level 2: "becoming a Trusted Committer of the project is tied to working for the initial project team." ([Project Leader 05](https://innersourcecommons.org/learn/learning-path/project-leader/05/))
- [Core Team](https://patterns.innersourcecommons.org/p/core-team): a team "whose job it is to maintain this project", "full-time or a part-time", formed so the organisation can "empower and hold them accountable in the same way as any other team"; it "doesn't have its own business agenda". Known instances: Nike, WellSky, BBVA AI Factory.
- [Trusted Committer](https://patterns.innersourcecommons.org/p/trusted-committer): the README template lists "Maintainers: Your team" separately from outside "Trusted Committers", who get "a path to Maintainer if they so desire". This is the "outsiders invited to commit" row. Bosch funded Trusted Committers "for 100 % of their time".
- PayPal: Trusted Committers were about 10% of the Checkout Platform team. ([InfoQ, 2015](https://www.infoq.com/news/2015/10/innersource-at-paypal))
- FINOS's own voice: "Your team remains the core maintainers - Your group reviews, approves, and shape contributions". ([Driving InnerSource Culture](https://osr.finos.org/docs/InnerSource/driving_innersource_culture))
- Each step up "adds more influence/karma to the contributing team" but "requires more transparency and shared communication resources" ([Explicit Governance Levels](https://patterns.innersourcecommons.org/p/governance-levels)); "a higher stage does not mean "better" - it just means "more complex"" ([Flutter, Pyramid](https://innersource.flutter.com/how/pyramid/)).
- Unpopular work: the maintaining team does it, with "pre-agreed dedicated time or sprints". ([Flutter, Unpopular Work](https://innersource.flutter.com/blog/unpopular-work))

### Branch B - in addition to the day job

- [Group Support](https://patterns.innersourcecommons.org/p/group-support): "No one is assigned by their day job to work on it"; volunteer Trusted Committers; support is "best effort" only and "not well-suited for run-time critical, production projects"; it will "likely ... dissolve again", so use the stable period to find a long-lived home such as a Core Team (i.e. move to branch A).
  It backs the "always open" claim: the group gives contributors "the design and technical support necessary for them to build it", but "is not expected to implement any new functionality for others".
- [Explicit Shared Ownership](https://patterns.innersourcecommons.org/p/explicit-shared-ownership): how such a group forms, by a pull request to the README proposing "a proposed list of initial Trusted Committers". (Initial)
- The governance-levels pattern's 4th level, **Shared Ownership** ("Members of different teams collaborate on the project as equal peers"), lists Group Support as its related pattern, so it fits this branch rather than branch A.
- Learning Path: "In grassroots communities, the founders often assume the role of the Trusted Committer", and "On small, grass roots efforts a single person often fills both" the Product Owner and Trusted Committer roles; more than one Trusted Committer "makes it easier when someone leaves". ([Trusted Committer 07](https://innersourcecommons.org/learn/learning-path/trusted-committer/07/), [Introduction 03](https://innersourcecommons.org/learn/learning-path/introduction/03/))
- FINOS Maturity Matrix, Project > Ownership: level 0 "It is not clear who is responsible and maintenance done on a best effort basis with no SLAs"; level 3 "Have at least 3 maintainers and at least 1 from different department or business group" and "More than one department with decision making ability". ([Maturity Matrix, Project](https://osr.finos.org/docs/innersource/maturity-matrix/project))
- Flutter's "maturity" reason for stage 3: an old library whose authors have moved teams and "team ownership if assigned at all is nominal". ([Maintainers in Multiple Teams](https://innersource.flutter.com/how/multiple-teams/))

### Moving between branches

- B to A: Group Support's own resolution is to find a Core Team.
- A to "delegated": a Flutter stage 2 capability "if contribution stops over time can become Delegated". ([Flutter, Choosing](https://innersource.flutter.com/how/choose/))
- Into A from outside: [Transitioning Contractor Code](https://patterns.innersourcecommons.org/p/transitioning-contractor-code-to-innersource-model) requires a handover plan naming "a new maintainer team".
- Out of either: Trusted Committer sunsetting; Maturity Matrix level 3 "putting projects up for adoptions" and "a clear maintenance / deprecation strategy".

## Where the sources don't line up with the framework

For you to decide; each changes a sentence or two on the page.

1. **The Maturity Matrix levels aren't headcount in the text.**
   Level 0 is "nobody responsible" and level 3 is "at least 3 maintainers", which match your reading.
   But level 1 is "defined expectations of person contributing code in terms of code maintenance, often with an SLA" (a contributor warranty), and level 2 is "more than one department contributing" with the nominal owner responsible.
   **[suggestion]** Let the page define the branch B levels (nobody / one / a few / three or more) as the author's, and cite the Matrix for levels 0 and 3 only.
2. **Flutter's stage 3 is neither branch cleanly.**
   Its maintainers are part-time ("No-one is a full-time maintainer", "10-20% of their working time") but the time is formally budgeted in each contributing team, and a named Capability Owner sits over them.
   **[suggestion]** Place it in branch B as the "a few / three or more" end done well, with a note that the time is budgeted rather than volunteered.
3. **"Small fixes" versus "entire features" is your split, not the sources'.**
   Every ladder treats "Contributions Welcome" as one level.
   The nearest published idea is Flutter's [Major vs Minor](https://innersource.flutter.com/blog/major-vs-minor) change triage (minor changes need one maintainer's approval; major ones need a written proposal agreed across divisions).
4. **One person on the side has almost no material** beyond the Learning Path's grassroots lines above.
   It is the clearest place for your own view.

## Proposed page outline

1. **Opening.** The terms are interchangeable: "Instead of "governance levels" we might also say "operating models", or "ownership models"" (governance-levels pattern). Teams all say "InnerSource" while meaning different things, which causes "confusion and frustration" (same pattern). Position the page as the deep dive behind Blueprint step 3.
2. **The framework** - the two questions, as above, as the author's view.
3. **Branch A: an assigned team, and how open it is** - the ladder table and the branch A sources.
4. **Branch B: in addition to the day job, and how many people** - the branch B sources and levels.
5. **What stays constant: someone is always accountable** (section below).
6. **Roles** (section below).
7. **Declaring your model** (section below).
8. **Patterns for the pressures on ownership** (table below), noting which branch each mostly applies to.
9. **Making ownership visible** (section below).
10. **Financial-services context** (section below).
11. **Moving between models** - the "Moving between branches" list above.

### What stays constant: someone is always accountable

- "If everyone owns it, nobody is accountable." ... each project has "a dedicated team of Trusted Committers" who "set the mission and goals for the project" and "decide on change acceptance accordingly." (Learning Path PL05)
- "Technical ownership and accountability is important at all stages of the inner source pyramid. At stage 1 or 2 the owner is the leader of the maintaining team. At stage 3 the owner isn't obvious from the org chart, and it helps to recognise a named individual as a Capability Owner." ([Flutter, Capability Owner](https://innersource.flutter.com/how/roles/owner/)) Without one, the capability becomes "a shared resource that's incrementally ruined by all divisions acting rationally but purely in their own interests."
- The guest gets the feature "without taking on the long-term burden of maintenance". (Learning Path, Introduction 03)
- Backstage defines a component's owner as "the singular entity (commonly a team) that bears ultimate responsibility for the component" and adds "there will always be one ultimate owner." ([Backstage descriptor format](https://backstage.io/docs/features/software-catalog/descriptor-format/))

### Roles

- Learning Path roles: Host / Guest team, Product Owner ("determines what functionality the host team is willing to accept"), Contributor, Trusted Committer.
- Naming: the Learning Path avoids "Maintainer" because it "conflicts with other technical roles such as the "Maintainer" role defined by GitHub"; Flutter uses Maintainer and Owner. **[suggestion]** One sentence acknowledging both terms.
- Staffing numbers from practice: Flutter maintainers take "10-20% of their working time", groups "commonly ... between 4-8" ([Flutter, Maintainer](https://innersource.flutter.com/how/roles/maintainer/)); PayPal about 10% of the team; Trusted Committer rotation (Learning Path TC 07).

### Declaring your model

- Define the levels centrally, name them, label projects in the portal, and "Present the governance levels as a menu of adoption options when launching new InnerSource projects." (governance-levels)
- Per-level starter kits: [Governance Level Guided Project Setup](https://patterns.innersourcecommons.org/p/governance-based-project-setup) (Initial).
- What the host team must make explicit: response times, channels, and "governance levels to expect from the project". (Learning Path PL05)
- FINOS Best-Candidates Q5 already describes "InnerSource with strong central governance (a small maintainer group that curates contributions)". **[suggestion]** Cross-link rather than restate.

### Patterns for the pressures on ownership

| Pressure | What the community published | Mostly applies to |
|---|---|---|
| Host won't take on maintenance of contributed code | [30 Day Warranty](https://patterns.innersourcecommons.org/p/30-day-warranty) (PayPal, GitHub, Microsoft, SAP); [Reluctance to Accept Contributions](https://patterns.innersourcecommons.org/p/reluctance-to-accept-contributions) (Initial); Maturity Matrix "Defined post-merge expectations from contributors (i.e., 90-day warranty)" | A |
| Who carries the pager | [Service vs. Library](https://patterns.innersourcecommons.org/p/service-vs-library) (Flutter, Europace, WellSky); Learning Path PL05's options for "you build it, you run it" | A |
| Host flooded with contributions | [Extensions for Sustainable Growth](https://patterns.innersourcecommons.org/p/extensions-for-sustainable-growth) (IBM); [Core Team](https://patterns.innersourcecommons.org/p/core-team); Flutter [Major vs Minor](https://innersource.flutter.com/blog/major-vs-minor) | A |
| Nobody owns it any more | [Group Support](https://patterns.innersourcecommons.org/p/group-support); [Explicit Shared Ownership](https://patterns.innersourcecommons.org/p/explicit-shared-ownership); Core Team as the long-lived home | B |
| Deciding across maintainers in different teams | [Transparent Cross-Team Decision Making using RFCs](https://patterns.innersourcecommons.org/p/transparent-cross-team-decision-making-using-rfcs) (BBC, Europace, Uber, SAP); Flutter [Lazy Consensus](https://innersource.flutter.com/blog/lazy-consensus), including "Don't Be Too Lazy": security, data protection and legal "typically require you to wait for an explicit approval" | B |
| Unpopular work (security updates, refactoring) | Flutter [Unpopular Work](https://innersource.flutter.com/blog/unpopular-work): maintaining team, sponsorship, virtual maintainers team, strategic intervention | both |
| Emergency change outside normal approvals | Flutter Major vs Minor, "Emergency Changes" | both |

### Making ownership visible

- Base Documentation's "Who we are" section and "the criteria ... to turn contributors into Trusted Committers - if that path exists". ([Standard Base Documentation](https://patterns.innersourcecommons.org/p/base-documentation))
- CODEOWNERS: "to define individuals or teams that are responsible for code in a repository", with optional required code-owner approval. ([GitHub Docs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners))
- Backstage `spec.owner`, which is for display and "not to be used by automated processes to for example assign authorization in runtime systems".
- [Centralized InnerSource Repository Governance](https://patterns.innersourcecommons.org/p/centralized-repository-governance) audits each repository against a profile per operating model (Initial, no known instances).

### Financial-services context: what the sources already say

- Separate **who can see the code** from **who decides on it**: [Balancing Openness and Security](https://patterns.innersourcecommons.org/p/balancing-openness-and-security) gives sharing levels (PUBLIC / INTERNAL / RESTRICTED / CLOSED) and "Code from SHARED repositories will not be distributed directly to Production."
- Service vs. Library lists "different security or regulatory constraints governing their deployments" as a force; Flutter's known instance is "driven by varying regulatory requirements".
- PayPal's regional teams "ensure that PayPal complies with the different regulations of the many different countries it works in".
- InnerSource Guidance Group's only known instance is "A large, highly regulated, financial organization".
- Brittany Istenes: "Support Compliance - Standardized review processes aligned with regulatory needs to build audit-friendly software".

## Gaps the published material does not cover

**[suggestion]** topics for your own view; none is sourced.

1. One person maintaining on the side (see mismatch 4).
2. Mapping each model to named accountability for audit, risk and incident ownership.
3. Segregation of duties / maker-checker rules versus Trusted Committer or shared merge rights.
4. Ownership of critical production services in branch B: Group Support rules itself out.
5. Ownership transfer when a team is reorganised.
6. Few financial-services known instances: BBVA (Core Team), PayPal, and the unnamed regulated organisation in the Guidance Group pattern.

## Scope boundary with other playbook pages

- **Blueprint (step 3):** this page is its deep dive.
- **Best-Candidates (Q5):** link, don't restate.
- **Organisational Enablement (#212, stub):** the org-level patterns ([Review Committee](https://patterns.innersourcecommons.org/p/review-committee), [Contracted Contributor](https://patterns.innersourcecommons.org/p/contracted-contributor), [Dedicated Community Leader](https://patterns.innersourcecommons.org/p/dedicated-community-leader), [InnerSource Guidance Group](https://patterns.innersourcecommons.org/p/innersource-guidance-group), [Include Product Owners](https://patterns.innersourcecommons.org/p/include-product-owners)) and the Learning Path's "Impact on leadership" belong there. **[suggestion]** One "see also" line here.
- **Practices (#208, stub):** review and contribution mechanics belong there.
- **Agentic Development:** already says agent changes follow "the same ownership and review model".

## Sources I did not open

The BBC talk (Tom Sadler), the BBVA Mercury article, the RBC talk, and the book *Adopting InnerSource*.

## Questions for you

1. The four mismatches above: take the suggestion on each, or something else?
2. Pressures section: table with links out, or a short paragraph per pressure?
3. Which gaps, if any, will you write your own view on?
4. Read any of the unopened sources before drafting?
