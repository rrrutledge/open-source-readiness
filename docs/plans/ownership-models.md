# Ownership Models playbook page - synthesis outline

Outline for rewriting `docs/InnerSource/Playbook/Ownership-Models.md` (finos/InnerSource#220, draft PR #379).
The earlier draft's four invented models are dropped.
Everything below is what the InnerSource community has already published, with the source named against each point.
Anything that is my suggestion rather than a sourced claim is marked **[suggestion]**, and those are kept to structure and open questions.

Every source listed was opened and read in full for this outline; quotes are verbatim.

## The one-paragraph finding

The community has a well-developed answer, and it is not a set of competing "models".
It is a **ladder of how much influence a host team shares with contributors**, published in near-identical form in three places: the ISC pattern *Explicit Governance Levels*, the ISC Learning Path (Project Leader, chapter 5), and Flutter Entertainment's *InnerSource Pyramid*.
Alongside the ladder runs one constant that every source agrees on: at every level there is still an accountable owner, and the higher levels need that owner named more explicitly, not less.
The rest of the material is a set of patterns for the specific pressures ownership comes under (fear of maintaining someone else's code, on-call, orphaned projects, too many contributions, decisions across teams, unpopular work).

## Proposed page outline

### 1. Opening: what "ownership model" means here

- The governance-levels pattern says the terms are interchangeable: "Instead of "governance levels" we might also say "operating models", or "ownership models"." Its aliases include "Project Ownership Models".
  ([Explicit Governance Levels](https://patterns.innersourcecommons.org/p/governance-levels))
- The problem it names: teams all call their way of working "InnerSource" while welcoming contributions to very different degrees, which causes "confusion and frustration when teams collaborate".
  (same pattern, Problem)
- The Learning Path makes the same point: "Just because two projects you depend on use pull requests on a daily basis does not mean that their openness to team-external contributions is the same."
  ([Learning Path, Project Leader 05](https://innersourcecommons.org/learn/learning-path/project-leader/05/))
- **[suggestion]** Position the page as the deep dive behind Blueprint step 3, which already links to the governance-levels pattern for "different ownership models".

### 2. The ladder

A side-by-side table; the three sources line up almost exactly.

| Governance Levels pattern | Flutter InnerSource Pyramid | Learning Path PL05 (paraphrased by me) |
|---|---|---|
| (none) | Stage 0 - Closed Source | (none) |
| 1. Bug Reports and Issues Welcome (aka Readable Source, Shared Source) | Stage 1 - Readable Source | Code visible, team has no time to mentor; only feature requests and bug reports |
| 2. Contributions Welcome (aka Guest Contributions) | Stage 2 - Guest Contribution | Patches welcome, TCs set time aside to mentor; "Final decision making though rests with the team of Trusted Committers" |
| 3. Shared Write Access | (folded into stage 3) | TCs open to sharing write access, after building trust; "can remove the review bottle neck" |
| 4. Shared Ownership (aka Distributed Ownership, Maintainers in Multiple Teams) | Stage 3 - Maintainers in Multiple Teams | TCs also share "control over who gets write access next as well as project vision and mission" |

Sourced points to carry with the table:

- Each level "adds more influence/karma to the contributing team. However each step also requires more transparency and shared communication resources between both teams." (governance-levels)
- "a higher stage does not mean "better" - it just means "more complex"", and higher stages are "only justified if the circumstances require it". ([Flutter, Pyramid](https://innersource.flutter.com/how/pyramid/))
- "Increased sharing increases the need for communication and co-ordination. Increased shared accountabilities can slow down decision making." (Learning Path PL05)
- The open source analogy in the pattern's Rationale: shared source, single-vendor OSS, Apache committer, vendor-neutral foundation.
- Flutter's three stated reasons a capability needs stage 3: **velocity**, **control**, **maturity** (an old library whose "team ownership if assigned at all is nominal"). ([Flutter, Maintainers in Multiple Teams](https://innersource.flutter.com/how/multiple-teams/))
- Flutter's stage 2 definition is the clearest statement of host ownership in the corpus: the maintaining team "retain full accountability" and, on accepting a contribution, "will take forward responsibility for it". ([Flutter, Guest Contribution](https://innersource.flutter.com/how/guest-contributions/))

Inconsistency to flag: the Learning Path says the pattern "defines at least three governance levels" then lists four, and *Governance Level Guided Project Setup* talks of "three governance levels" and omits Shared Write Access.
**[suggestion]** Use the four from the Structured pattern and note Flutter merges levels 3 and 4.

### 3. The constant: someone is always accountable

- "If everyone owns it, nobody is accountable." ... "each InnerSource project has a dedicated team of Trusted Committers" who "set the mission and goals for the project" and "decide on change acceptance accordingly." (Learning Path PL05)
- "Technical ownership and accountability is important at all stages of the inner source pyramid. At stage 1 or 2 the owner is the leader of the maintaining team. At stage 3 the owner isn't obvious from the org chart, and it helps to recognise a named individual as a Capability Owner." ([Flutter, Capability Owner](https://innersource.flutter.com/how/roles/owner/))
- Flutter: "almost all successful capabilities in stage 3 have clear ownership with a named individual as a capability owner", with three objectives (maintainer collaboration, strategic path, long-term sustainability) and what goes wrong without each, e.g. "a shared resource that's incrementally ruined by all divisions acting rationally but purely in their own interests."
- The guest gets the feature "without taking on the long-term burden of maintenance". ([Learning Path, Introduction 03](https://innersourcecommons.org/learn/learning-path/introduction/03/))
- FINOS's own culture page, for the financial-services voice: "Your team remains the core maintainers - Your group reviews, approves, and shape contributions", and "Designate Maintainers - Appoint responsible owners who will review, merge, and guide contributions". ([Driving InnerSource Culture, Brittany Istenes](https://osr.finos.org/docs/InnerSource/driving_innersource_culture))
- Tooling definition, to show the industry convention is one owner: Backstage defines a component's owner as "the singular entity (commonly a team) that bears ultimate responsibility for the component" and adds "There may be others that also develop or otherwise touch the component, but there will always be one ultimate owner." ([Backstage descriptor format](https://backstage.io/docs/features/software-catalog/descriptor-format/))

### 4. Roles that carry ownership

- Learning Path roles: Host team / Guest team, Product Owner ("determines what functionality the host team is willing to accept"), Contributor, Trusted Committer; one person often holds both PO and TC on small efforts. ([Introduction 03](https://innersourcecommons.org/learn/learning-path/introduction/03/), [Trusted Committer 01](https://innersourcecommons.org/learn/learning-path/trusted-committer/01/))
- Naming: the Learning Path avoids "Maintainer" because it "conflicts with other technical roles such as the "Maintainer" role defined by GitHub". Flutter uses Maintainer and Owner. **[suggestion]** One sentence acknowledging both terms, since FINOS readers will meet both.
- How the role is earned and staffed:
  - Grassroots founders start as TCs; larger communities nominate or vote them in; some companies rotate the TC duty; more than one TC "makes it easier when someone leaves". ([Trusted Committer 07](https://innersourcecommons.org/learn/learning-path/trusted-committer/07/))
  - Flutter: maintainers take "10-20% of their working time", groups "commonly ... between 4-8", "a maintainer in each regularly contributing team is desirable". ([Flutter, Maintainer](https://innersource.flutter.com/how/roles/maintainer/))
  - PayPal: TCs were about 10% of the Checkout Platform team; they reviewed in-team code too, to make the change politically acceptable. ([InfoQ, 2015](https://www.infoq.com/news/2015/10/innersource-at-paypal))
  - The TC pattern: document the role's scope per project, list TCs in the README, and plan for sunsetting a TC. ([Trusted Committer](https://patterns.innersourcecommons.org/p/trusted-committer))

### 5. Choosing and declaring a level

- Define the levels centrally, name them, use the names in docs and contributing guides, label projects in the portal, and "Present the governance levels as a menu of adoption options when launching new InnerSource projects." (governance-levels, Promote section)
- Per-level starter kits: which patterns and maturity-model levels apply to each. ([Governance Level Guided Project Setup](https://patterns.innersourcecommons.org/p/governance-based-project-setup), Initial)
- What the host team must make explicit to contributors: response times, communication channels, and "governance levels to expect from the project". (Learning Path PL05)
- Flutter's "Choose" page puts InnerSource beside two non-InnerSource options (Independent, Delegated), and notes a stage 2 capability "if contribution stops over time can become Delegated". ([Flutter, Choosing](https://innersource.flutter.com/how/choose/))
- FINOS Best-Candidates Q5 already describes "InnerSource with strong central governance (a small maintainer group that curates contributions)". **[suggestion]** Cross-link rather than restate.

### 6. Patterns for the pressures on ownership

Grouped by the problem a reader has; one or two lines each, linking out.

| Pressure | What the community published |
|---|---|
| Host won't take on maintenance of contributed code | [30 Day Warranty](https://patterns.innersourcecommons.org/p/30-day-warranty) (PayPal, GitHub, Microsoft, SAP); [Reluctance to Accept Contributions](https://patterns.innersourcecommons.org/p/reluctance-to-accept-contributions) (Initial); FINOS Maturity Matrix Contributing Process level 2 "Defined post-merge expectations from contributors (i.e., 90-day warranty)" |
| Who carries the pager | [Service vs. Library](https://patterns.innersourcecommons.org/p/service-vs-library): share the code, keep deployment and escalation per team (Flutter, Europace, WellSky); Learning Path PL05's three options for "you build it, you run it" (modularise, contract tests, warranties/internal SLAs) |
| Host flooded with contributions | [Extensions for Sustainable Growth](https://patterns.innersourcecommons.org/p/extensions-for-sustainable-growth) (IBM); [Core Team](https://patterns.innersourcecommons.org/p/core-team); Flutter's [Major vs Minor](https://innersource.flutter.com/blog/major-vs-minor) change triage |
| Nobody owns it any more | [Group Support](https://patterns.innersourcecommons.org/p/group-support) ("best effort" only, "not well-suited for run-time critical, production projects"); [Explicit Shared Ownership](https://patterns.innersourcecommons.org/p/explicit-shared-ownership) (propose TCs by pull request to the README; Initial); Core Team as the long-lived home |
| Deciding across owning teams | [Transparent Cross-Team Decision Making using RFCs](https://patterns.innersourcecommons.org/p/transparent-cross-team-decision-making-using-rfcs) (BBC, Europace, Uber, SAP); Flutter's [Lazy Consensus](https://innersource.flutter.com/blog/lazy-consensus), including "Don't Be Too Lazy": security, data protection and legal "typically require you to wait for an explicit approval" |
| Unpopular work (security updates, refactoring) | Flutter's [Unpopular Work](https://innersource.flutter.com/blog/unpopular-work): maintaining team, sponsorship, virtual maintainers team, strategic intervention; Core Team |
| Ownership changing hands | TC sunsetting; [Transitioning Contractor Code](https://patterns.innersourcecommons.org/p/transitioning-contractor-code-to-innersource-model) (handover plan naming the new maintainer team); Group Support as a bridge to a Core Team; FINOS Maturity Matrix Ownership level 3 "putting projects up for adoptions" and "a clear maintenance / deprecation strategy" |
| Emergency change outside normal approvals | Flutter Major vs Minor, "Emergency Changes": pre-agreed on-call process, retrospective review |

### 7. Making ownership visible

- Base Documentation's "Who we are" section and "the criteria ... to turn contributors into Trusted Committers - if that path exists". ([Standard Base Documentation](https://patterns.innersourcecommons.org/p/base-documentation))
- Governance level as a portal label (governance-levels).
- CODEOWNERS: GitHub's mechanism "to define individuals or teams that are responsible for code in a repository", with optional required code-owner approval via branch protection. ([GitHub Docs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners))
- Backstage `spec.owner`, with its own caveat that it is for display and "not to be used by automated processes to for example assign authorization in runtime systems".
- [Centralized InnerSource Repository Governance](https://patterns.innersourcecommons.org/p/centralized-repository-governance) audits readiness against a profile per operating model (`contributions-welcome`, `shared-ownership`), including CODEOWNERS; Initial, no known instances yet.

### 8. How the FINOS Maturity Matrix measures ownership

Quote the Project > Ownership row (levels 0-3) and show how it maps onto the ladder, e.g. level 3 "Have at least 3 maintainers and at least 1 from different department or business group" and "More than one department with decision making ability" correspond to Shared Write Access / Shared Ownership.
**[suggestion]** The mapping itself is mine, so present it as a reading aid, not as a claim of the Matrix.

### 9. Financial-services context: what the sources already say

- Separate **who can see the code** from **who decides on it**: [Balancing Openness and Security](https://patterns.innersourcecommons.org/p/balancing-openness-and-security) gives sharing levels (PUBLIC / INTERNAL / RESTRICTED / CLOSED) and "Code from SHARED repositories will not be distributed directly to Production." Flutter's Readable Source page splits sensitive parts out or narrows the sharing boundary, with pricing models as its example.
- Service vs. Library lists "Teams may have different security or regulatory constraints governing their deployments" as a force; Flutter's known instance is "driven by varying regulatory requirements, service and incident management practices".
- PayPal's case began with regional teams that "ensure that PayPal complies with the different regulations of the many different countries it works in".
- InnerSource Guidance Group's only known instance is "A large, highly regulated, financial organization".
- Brittany Istenes: "Support Compliance - Standardized review processes aligned with regulatory needs to build audit-friendly software".

## Gaps the published material does not cover

These are **[suggestion]** topics where you might add your own view; none of them is sourced, and I would not write them without your direction.

1. Mapping each governance level to named accountability for audit, risk and incident ownership.
2. Combining governance levels (who decides) with sharing levels (who can see) as two independent axes.
3. Segregation of duties / maker-checker rules versus Trusted Committer or shared merge rights.
4. Ownership of critical production services: Group Support rules itself out, and Service vs. Library is the only pattern that addresses it.
5. Ownership transfer when a team is reorganised (the material covers orphaning and contractor handover, not reorgs).
6. Few financial-services known instances: BBVA (Core Team), PayPal, and the unnamed regulated organisation in the Guidance Group pattern.

## Scope boundary with other playbook pages

- **Blueprint (step 3):** this page is its deep dive; Blueprint keeps its summary and links here.
- **Best-Candidates (Q5):** link, don't restate.
- **Organisational Enablement (#212, stub):** the org-level patterns ([Review Committee](https://patterns.innersourcecommons.org/p/review-committee), [Contracted Contributor](https://patterns.innersourcecommons.org/p/contracted-contributor), [Dedicated Community Leader](https://patterns.innersourcecommons.org/p/dedicated-community-leader), [InnerSource Guidance Group](https://patterns.innersourcecommons.org/p/innersource-guidance-group), [Include Product Owners](https://patterns.innersourcecommons.org/p/include-product-owners)) and the Learning Path's "Impact on leadership" (performance reviews across team lines) look like they belong there.
  **[suggestion]** One "see also" line here, and flag the boundary to Michaela.
- **Practices (#208, stub):** code review and contribution flow mechanics belong there; this page only covers who decides.
- **Agentic Development:** already says agent changes follow "the same ownership and review model"; no change needed.

## Sources I did not open

The BBC talk (Tom Sadler, *Ownership in a DevOps and InnerSource environment*), the BBVA Mercury article, the RBC talk, and the book *Adopting InnerSource* were not opened, so nothing above draws on them.

## Questions for you

1. Is the ladder (governance levels + Flutter pyramid) the right spine for the page, with the "always an accountable owner" constant as section 3?
2. Section 6 is the bulk of the page. Table of pressures with links out, or a short paragraph per pressure?
3. Which of the six gaps, if any, do you want to write your own view on, and should those be marked as the author's view on the page?
4. Do you want any of the unopened sources (BBC talk is a Known Instance for governance levels) read before drafting?
5. Org-level patterns: one "see also" line pointing at Organisational Enablement, or a short section here?
