# Ownership Models playbook page - synthesis outline

Outline for rewriting `docs/InnerSource/Playbook/Ownership-Models.md` (finos/InnerSource#220, draft PR #379).
The earlier draft's four invented models are dropped.

The page's spine is **Russell's three-dimension framework** (round 3), stated as the author's view.
Everything hung on it is what the InnerSource community has already published, with the source named against each point.
Anything that is my suggestion rather than a sourced claim or Russell's framing is marked **[suggestion]**.

Every source listed was opened and read in full; quotes are verbatim.

## The framework (author's view)

An InnerSource ownership model is a position on three independent dimensions.
The published models each bundle positions on several of these into one scale, which is why they disagree with one another.

**1. Who maintains it?**

- Is maintaining it someone's day job (an assigned, funded team, even if all from one business unit), or do people do it on top of their day job?
- How many maintainers are there, and how are they spread across the company (one team, several teams, several departments)?

**2. What do the maintainers commit to do?**

| Level | Commitment |
|---|---|
| 0 | Best effort, no guarantees. |
| 1 | Guaranteed maintenance: bug fixes, security fixes, dependency upgrades, and running it (deployment, on-call). |
| 2 | Maintenance plus new features built by the maintainers. |

**3. What are the maintainers open to?**

Closed; issues and bug reports; small fixes; entire features; write access for people outside the maintaining group.

## Evidence for each dimension

### Dimension 1 - who maintains it

Day job:

- [Core Team](https://patterns.innersourcecommons.org/p/core-team): a team "whose job it is to maintain this project", "full-time or a part-time", formed so the organisation can "empower and hold them accountable in the same way as any other team". Known instances: Nike, WellSky, BBVA AI Factory.
- Flutter stages 1 and 2: a single "maintaining team". ([Flutter, Pyramid](https://innersource.flutter.com/how/pyramid/))
- Learning Path PL05, level 2: "becoming a Trusted Committer of the project is tied to working for the initial project team." ([Project Leader 05](https://innersourcecommons.org/learn/learning-path/project-leader/05/))
- Bosch funded Trusted Committers "for 100 % of their time". ([Trusted Committer](https://patterns.innersourcecommons.org/p/trusted-committer))

On top of the day job:

- [Group Support](https://patterns.innersourcecommons.org/p/group-support): "No one is assigned by their day job to work on it"; volunteers from anywhere in the company, "enough so that the burden on each can be reasonably small".
- Learning Path: "In grassroots communities, the founders often assume the role of the Trusted Committer"; "On small, grass roots efforts a single person often fills both" the Product Owner and Trusted Committer roles. ([Trusted Committer 07](https://innersourcecommons.org/learn/learning-path/trusted-committer/07/), [Introduction 03](https://innersourcecommons.org/learn/learning-path/introduction/03/))

How many, and spread how:

- FINOS Maturity Matrix, Project > Ownership: level 0 "It is not clear who is responsible"; level 2 "Have more than one department contributing"; level 3 "Have at least 3 maintainers and at least 1 from different department or business group" and "More than one department with decision making ability". ([Maturity Matrix, Project](https://osr.finos.org/docs/innersource/maturity-matrix/project))
- Flutter stage 3: "at least one person in every regularly contributing team must be an expert "maintainer"", groups "commonly ... between 4-8", acting "as a virtual team". ([Maintainers in Multiple Teams](https://innersource.flutter.com/how/multiple-teams/), [Maintainer](https://innersource.flutter.com/how/roles/maintainer/))
- The Trusted Committer pattern adds outside Trusted Committers to the maintaining team, with "a path to Maintainer if they so desire".
- PayPal: Trusted Committers were about 10% of the Checkout Platform team. ([InfoQ, 2015](https://www.infoq.com/news/2015/10/innersource-at-paypal))
- More than one Trusted Committer "makes it easier when someone leaves". (Learning Path TC 07)

### Dimension 2 - what the maintainers commit to

- **Level 0:** Group Support's support is "best effort" only, and the group "is not expected to implement any new functionality for others". The Maturity Matrix's level 0 is "maintenance done on a best effort basis with no SLAs". The governance-levels pattern's own rationale for its first level: "you can report the bug, but its on the owner to find the time to fix it".
- **Level 1:** Core Team's work list includes "Production bugs", "CI/CD", "Versioning" and "Monitoring". The ISC Maturity Model's Support and Maintenance row runs from SM-0 "A business contract guaranties the support" and SM-1 "a dedicated supporting team" to SM-3 support "given by a mature community". ([Maturity Model](https://patterns.innersourcecommons.org/p/maturity-model))
- **Level 1, for contributed code:** a Flutter stage 2 maintaining team "retain[s] full accountability" and "will take forward responsibility" for each accepted contribution ([Guest Contribution](https://innersource.flutter.com/how/guest-contributions/)); the Learning Path lists "Ongoing maintenance of submitted code (after the warranty window)" among the host's duties ([Introduction 08](https://innersourcecommons.org/learn/learning-path/introduction/08/)).
- **Level 2:** at Flutter stage 1, "all changes to the service implemented by this maintaining team". Core Team reaches partly into it ("Trailblazing new classes/categories of features") but "doesn't have its own business agenda".
- **Who does the unpopular part of level 1** (security updates, dependency upgrades): maintaining team, sponsorship, a virtual maintainers team, or a funded "strategic intervention". ([Flutter, Unpopular Work](https://innersource.flutter.com/blog/unpopular-work))
- **Running it is part of maintaining it.** Backstage's owner is "the point of contact if something goes wrong" ([descriptor format](https://backstage.io/docs/features/software-catalog/descriptor-format/)). [Service vs. Library](https://patterns.innersourcecommons.org/p/service-vs-library) is the published way to split the running part out per team when teams can't share an on-call rota.

### Dimension 3 - what the maintainers are open to

The community's openness ladder lives here.

| Openness | Governance Levels pattern | Flutter InnerSource Pyramid | Learning Path PL05 (paraphrased by me) |
|---|---|---|---|
| Closed | (none) | Stage 0 - Closed Source | (none) |
| Issues and bug reports | 1. Bug Reports and Issues Welcome | Stage 1 - Readable Source | Code visible, no time to mentor |
| Small fixes / entire features | 2. Contributions Welcome | Stage 2 - Guest Contribution | Patches welcome, time set aside to mentor |
| Write access for outsiders | 3. Shared Write Access, 4. Shared Ownership | Stage 3 - Maintainers in Multiple Teams | Shared write access; then shared "control over who gets write access next as well as project vision and mission" |

- Each step up "adds more influence/karma to the contributing team" but "requires more transparency and shared communication resources" ([Explicit Governance Levels](https://patterns.innersourcecommons.org/p/governance-levels)); "a higher stage does not mean "better" - it just means "more complex"" (Flutter).
- Small fixes versus entire features is the author's split; every ladder treats "Contributions Welcome" as one level. The nearest published idea is Flutter's [Major vs Minor](https://innersource.flutter.com/blog/major-vs-minor) change triage.

## Published models expressed in the three dimensions

The page can show the author's claim directly: each existing model is a bundle of positions.
"-" means the source doesn't say.

| Published model | 1. Who maintains | 2. Commitment | 3. Open to |
|---|---|---|---|
| Governance Levels 1 - Bug Reports and Issues Welcome | host team | 0 ("on the owner to find the time") | issues |
| Governance Levels 2 - Contributions Welcome | host team | - | features |
| Governance Levels 3 - Shared Write Access | host team plus outside committers | - | write access |
| Governance Levels 4 - Shared Ownership | equal peers across teams | - | write access, shared direction and membership |
| Flutter stage 0 - Closed Source | one team | 2 | closed |
| Flutter stage 1 - Readable Source | one maintaining team | 2 | issues (read access) |
| Flutter stage 2 - Guest Contribution | one maintaining team | 1 or 2 ("full accountability") | features |
| Flutter stage 3 - Maintainers in Multiple Teams | a maintainer in each contributing team, 10-20% of their time, plus a named owner | - | write access |
| Group Support | volunteers from anywhere, on top of the day job | 0, no features for others | features |
| Core Team | dedicated team, full- or part-time | 1, some features | features |
| ISC Maturity Model SM-0 / SM-1 / SM-3 | core team / dedicated support team / community | 1 / 1 / community | - |
| FINOS Maturity Matrix Ownership 0 / 2 / 3 | nobody / more than one department / at least 3 maintainers, at least 1 from another department | 0 / 1 for contributed code / - | - / features / shared decision-making |
| Best-Candidates Q5 - strong central governance | "a small maintainer group" | - | curated contributions |

## What the three dimensions deliberately leave out

Things the published models mix in that aren't a choice of ownership model.
**[suggestion]** Name them briefly on the page so readers who know the other models see where they went.

1. **Contributor commitments after merge** (30 Day Warranty, Matrix level 1, ISC SM-2): a contribution practice; goes in the pressures section.
2. **Outcomes** ("more than one department contributing", "The people finding the issues are the ones fixing the code"): things you measure, not choose.
3. **Lifecycle** ("putting projects up for adoptions", "maintenance / deprecation strategy"): goes in "moving between models".
4. **Consumer policy** (Best-Candidates Q5's "mandated adoption").
5. **Visibility** (who can see the code, from [Balancing Openness and Security](https://patterns.innersourcecommons.org/p/balancing-openness-and-security)): closely tied to the bottom of dimension 3; covered in the financial-services section.

## Remaining calls for you

1. **Flutter stage 3 maintainers** are part-time but have their time formally budgeted (10-20%). **[suggestion]** Treat "day job" as "time formally allocated", so they count as day-job maintainers spread across teams.
2. **Governance level 4's "equal say on the project direction" and "who else to add to this group"**. **[suggestion]** Make that the top rung of dimension 3 ("write access and shared direction").

## Proposed page outline

1. **Opening.** "Instead of "governance levels" we might also say "operating models", or "ownership models"" (governance-levels pattern). Teams all say "InnerSource" while meaning different things, which causes "confusion and frustration". Position the page as the deep dive behind Blueprint step 3.
2. **The three dimensions** (author's view).
3. **Dimension 1: who maintains it** - evidence above.
4. **Dimension 2: what maintainers commit to** - evidence above.
5. **Dimension 3: what maintainers are open to** - the ladder table.
6. **The published models in these terms** - the mapping table, plus what the dimensions leave out.
7. **What stays constant: someone is always accountable** (below).
8. **Roles** (below).
9. **Declaring your model:** pick a position on each dimension and publish it (below).
10. **Patterns for the pressures on ownership** (table below).
11. **Making ownership visible** (below).
12. **Financial-services context** (below).
13. **Moving between models** (below).

### What stays constant: someone is always accountable

- "If everyone owns it, nobody is accountable." ... "each InnerSource project has a dedicated team of Trusted Committers" who "set the mission and goals for the project". (Learning Path PL05)
- "Technical ownership and accountability is important at all stages of the inner source pyramid. ... At stage 3 the owner isn't obvious from the org chart, and it helps to recognise a named individual as a Capability Owner." ([Flutter, Capability Owner](https://innersource.flutter.com/how/roles/owner/)) Without one, the capability becomes "a shared resource that's incrementally ruined by all divisions acting rationally but purely in their own interests."
- Backstage: "there will always be one ultimate owner."
- FINOS: "Your team remains the core maintainers - Your group reviews, approves, and shape contributions". ([Driving InnerSource Culture](https://osr.finos.org/docs/InnerSource/driving_innersource_culture))

### Roles

- Learning Path roles: Host / Guest team, Product Owner ("determines what functionality the host team is willing to accept"), Contributor, Trusted Committer.
- Naming: the Learning Path avoids "Maintainer" because it "conflicts with other technical roles such as the "Maintainer" role defined by GitHub"; Flutter uses Maintainer and Owner. **[suggestion]** One sentence acknowledging both terms.
- Trusted Committer rotation, nomination and sunsetting (Learning Path TC 07; Trusted Committer pattern).

### Declaring your model

- Define the levels centrally, name them, label projects in the portal, and "Present the governance levels as a menu of adoption options when launching new InnerSource projects." (governance-levels)
- What the host team must make explicit: response times, channels, and "governance levels to expect from the project". (Learning Path PL05)
- Per-level starter kits: [Governance Level Guided Project Setup](https://patterns.innersourcecommons.org/p/governance-based-project-setup) (Initial).
- **[suggestion]** A short README / CONTRIBUTING snippet stating a project's position on all three dimensions.
- Cross-link Best-Candidates Q5 rather than restate.

### Patterns for the pressures on ownership

| Pressure | What the community published |
|---|---|
| Host won't take on maintenance of contributed code | [30 Day Warranty](https://patterns.innersourcecommons.org/p/30-day-warranty) (PayPal, GitHub, Microsoft, SAP); [Reluctance to Accept Contributions](https://patterns.innersourcecommons.org/p/reluctance-to-accept-contributions) (Initial); Maturity Matrix "Defined post-merge expectations from contributors (i.e., 90-day warranty)" |
| Teams can't share an on-call rota | [Service vs. Library](https://patterns.innersourcecommons.org/p/service-vs-library) (Flutter, Europace, WellSky); Learning Path PL05's options for "you build it, you run it" |
| Host flooded with contributions | [Extensions for Sustainable Growth](https://patterns.innersourcecommons.org/p/extensions-for-sustainable-growth) (IBM); [Core Team](https://patterns.innersourcecommons.org/p/core-team); Flutter [Major vs Minor](https://innersource.flutter.com/blog/major-vs-minor) |
| Nobody owns it any more | [Group Support](https://patterns.innersourcecommons.org/p/group-support); [Explicit Shared Ownership](https://patterns.innersourcecommons.org/p/explicit-shared-ownership) (Initial); Core Team as the long-lived home |
| Deciding across maintainers in different teams | [Transparent Cross-Team Decision Making using RFCs](https://patterns.innersourcecommons.org/p/transparent-cross-team-decision-making-using-rfcs) (BBC, Europace, Uber, SAP); Flutter [Lazy Consensus](https://innersource.flutter.com/blog/lazy-consensus), including "Don't Be Too Lazy": security, data protection and legal "typically require you to wait for an explicit approval" |
| Unpopular work | Flutter [Unpopular Work](https://innersource.flutter.com/blog/unpopular-work) |
| Emergency change outside normal approvals | Flutter Major vs Minor, "Emergency Changes" |

### Making ownership visible

- Base Documentation's "Who we are" section and "the criteria ... to turn contributors into Trusted Committers - if that path exists". ([Standard Base Documentation](https://patterns.innersourcecommons.org/p/base-documentation))
- CODEOWNERS: "to define individuals or teams that are responsible for code in a repository". ([GitHub Docs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners))
- Backstage `spec.owner`, which is for display and "not to be used by automated processes to for example assign authorization in runtime systems".
- [Centralized InnerSource Repository Governance](https://patterns.innersourcecommons.org/p/centralized-repository-governance): readiness profiles per operating model (Initial, no known instances).

### Financial-services context: what the sources already say

- Separate **who can see the code** from **who decides on it**: Balancing Openness and Security's sharing levels (PUBLIC / INTERNAL / RESTRICTED / CLOSED) and "Code from SHARED repositories will not be distributed directly to Production."
- Service vs. Library lists "different security or regulatory constraints governing their deployments" as a force; Flutter's instance is "driven by varying regulatory requirements".
- PayPal's regional teams "ensure that PayPal complies with the different regulations of the many different countries it works in".
- InnerSource Guidance Group's only known instance is "A large, highly regulated, financial organization".
- Brittany Istenes: "Support Compliance - Standardized review processes aligned with regulatory needs to build audit-friendly software".

### Moving between models

- Group Support expects to "dissolve again", so use the stable period to find a long-lived home such as a Core Team (day job, commitment level 1).
- A Flutter stage 2 capability "if contribution stops over time can become Delegated". ([Flutter, Choosing](https://innersource.flutter.com/how/choose/))
- [Transitioning Contractor Code](https://patterns.innersourcecommons.org/p/transitioning-contractor-code-to-innersource-model): a handover plan naming "a new maintainer team".
- Trusted Committer sunsetting; Maturity Matrix level 3 "putting projects up for adoptions" and "a clear maintenance / deprecation strategy".

## Gaps the published material does not cover

**[suggestion]** topics for your own view; none is sourced.

1. One person maintaining on the side.
2. Mapping each model to named accountability for audit, risk and incident ownership.
3. Segregation of duties / maker-checker rules versus Trusted Committer or shared merge rights.
4. Critical production services with best-effort (level 0) maintainers: Group Support rules itself out.
5. Ownership transfer when a team is reorganised.
6. Few financial-services known instances: BBVA (Core Team), PayPal, and the unnamed regulated organisation in the Guidance Group pattern.

## Scope boundary with other playbook pages

- **Blueprint (step 3):** this page is its deep dive.
- **Best-Candidates (Q5):** link, don't restate.
- **Organisational Enablement (#212, stub):** the org-level patterns ([Review Committee](https://patterns.innersourcecommons.org/p/review-committee), [Contracted Contributor](https://patterns.innersourcecommons.org/p/contracted-contributor), [Dedicated Community Leader](https://patterns.innersourcecommons.org/p/dedicated-community-leader), [InnerSource Guidance Group](https://patterns.innersourcecommons.org/p/innersource-guidance-group), [Include Product Owners](https://patterns.innersourcecommons.org/p/include-product-owners)) and the Learning Path's "Impact on leadership" belong there. **[suggestion]** One "see also" line here.
- **Practices (#208, stub):** review and contribution mechanics belong there.
- **Agentic Development:** already says agent changes follow "the same ownership and review model".

## Sources not opened

The BBC talk (Tom Sadler), the BBVA Mercury article, the RBC talk, and the book *Adopting InnerSource*.
