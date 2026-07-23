# Scrum & Product Management — Criteria and Positioning

### Conceptual questions on Scrum and Product Management

---

## Context

The following answers are written from the perspective of a professional with over 4 years of experience in IT, with a background as a QA Engineer and SDET, experience in test automation, and a period as Scrum Master. This technical-agile background directly influences the way processes, quality criteria, and team management are approached.

---

## Table of Contents

1. [Purpose of acceptance criteria](#1-what-is-the-purpose-of-acceptance-criteria)
2. [Other types of requests in a product backlog](#2-besides-client-requirements-what-other-types-of-requests-can-be-added-to-a-product-backlog)
3. [Criteria for ordering a product backlog](#3-what-criteria-would-you-use-to-order-a-product-backlog)
4. [Number of product backlogs per project](#4-how-many-product-backlogs-can-we-have-per-project)
5. [Mandatory PO participation in Scrum ceremonies](#5-in-which-scrum-ceremonies-should-the-product-owner-participate-mandatorily)
6. [Critical bug found by QA during an active sprint](#6-if-the-qa-team-finds-a-critical-bug-during-an-active-sprint-what-decisions-would-you-make)
7. [Urgent production incident mid-sprint](#7-how-would-you-handle-an-urgent-production-incident-reported-mid-sprint)
8. [Product behind schedule](#8-if-a-product-is-behind-in-its-development-what-steps-would-you-take-to-minimize-the-impact)
9. [Urgent client change request mid-sprint](#9-a-client-requests-an-urgent-change-mid-sprint-how-would-you-handle-it)

---

## 1. What is the purpose of acceptance criteria?

The main purpose is to eliminate ambiguity. When you write a user story without acceptance criteria, every person on the team can interpret "done" differently. The developer thinks they finished, QA thinks half of it is missing, and the client expected something else entirely.

Acceptance criteria establish upfront exactly what needs to happen for everyone to agree the story is complete. They are also the direct foundation for test cases. If a criterion is well written in Given/When/Then format, it almost becomes an automated test by itself.

---

## 2. Besides client requirements, what other types of requests can be added to a product backlog?

The backlog is not just new features. It can also contain:

- **Technical debt**: Refactors, migrations, dependency updates the team needs to address to avoid accumulating technical risk.
- **Bugs**: Especially non-critical ones that need to be resolved before the next release.
- **Spikes**: Research or proof-of-concept tasks when there is technical uncertainty before committing to a solution.
- **Performance or security improvements**: Not explicitly requested by the client but necessary to sustain the product.
- **Infrastructure or DevOps tasks**: Configurations, pipelines, environments.
- **Technical stories**: Work that has no direct value for the end user but enables functionality that does.

---

## 3. What criteria would you use to order a product backlog?

I would not choose a single criterion because the backlog is dynamic and what matters changes over time. But if I had to provide a framework, I would combine three axes:

- **Business or user value**: How much real impact does this have if we deliver it.
- **Risk and uncertainty**: What carries the most technical or business risk should come first. If something can go wrong, better to find out early.
- **Dependencies**: Some things need to come first because others depend on them.

MoSCoW is useful as a first pass for classification, and then within each category items are ordered by value and risk. The conversation with stakeholders is key. The PM does not order the backlog alone.

---

## 4. How many product backlogs can we have per project?

Just one. It is a fundamental principle of Scrum. There is a single source of truth for the team's work, and that is the Product Owner's responsibility. Having multiple backlogs creates desynchronization, duplicated work, and loss of visibility.

Within that single backlog you can have filtered views, groupings by epic, labels by component or team. But it is always the same backlog. If the project is very large and has multiple teams, scaling models like SAFe or LeSS address this with a shared Program Backlog that feeds each team's backlog, but conceptually it remains a single source of truth.

---

## 5. In which Scrum ceremonies should the Product Owner participate mandatorily?

Mandatorily in three:

- **Sprint Planning**: The PO explains what will be built and why, clarifies the stories, and accepts the team's commitment.
- **Sprint Review**: The PO validates that what was delivered meets expectations and receives stakeholder feedback.
- **Refinement / Backlog Grooming**: Although technically not an official Scrum ceremony, in practice this is where the PO does the most work — prioritizing, clarifying, and breaking down stories with the team.

The Daily and the Retrospective are optional for the PO. In the Daily they can observe but should not interrupt the team's flow. In the Retro their presence depends on the team — sometimes it adds value, sometimes it inhibits honest conversation.

---

## 6. If the QA team finds a critical bug during an active sprint, what decisions would you make?

From my experience, the first step would be to assess the real impact: whether it affects functionality already in production, whether it is something within the current sprint, or whether there is a workaround available.

If it is critical and blocks any of the stories in progress, the first action is to communicate it immediately to the team and not wait for the next day's daily. In practice this means raising it directly with the responsible developer so they can address it as soon as possible.

If the bug affects the sprint commitment, it needs to be discussed with the Scrum Master and PO to evaluate whether to adjust the sprint scope, prioritize the fix over other tasks, or escalate if the impact exceeds what the team can absorb. As PM or PO, I would never ignore a critical defect just to protect the sprint — that always accumulates debt and real risk.

---

## 7. How would you handle an urgent production incident reported mid-sprint?

The first step is to understand the impact: how many users are affected, what functionality is down, whether there is any data loss involved.

If it is truly urgent, Scrum allows for interrupting the sprint. It is not ideal but it is valid when the production impact outweighs the value of the work in progress. In that case I would coordinate with the Scrum Master to reassign team capacity to the incident.

If the impact is contained, I would try to handle it in parallel: one developer addresses the incident while the rest of the team keeps moving. The incident is documented as a backlog item for traceability, and in the retrospective we analyze how to prevent it from happening again.

I would also be interested in understanding whether the incident went through testing and how. That conversation always adds value to the process.

---

## 8. If a product is behind in its development, what steps would you take to minimize the impact?

First, understand why it is behind. Technical debt, scope creep, and incorrect estimates are not the same thing — each cause has a different response.

Then I would evaluate options in this order:

- **Reduce scope**: Are there features in the release that are Could Have or Should Have and can be moved to the next cycle without breaking the core value?
- **Review dependencies**: Is there something blocked externally that can be unblocked?
- **Communicate early to stakeholders**: The worst moment to deliver bad news is on delivery day. The earlier expectations are adjusted, the more options are on the table.
- **Do not add people to the team abruptly**: Brooks' Law applies — adding people late in a project delays it further.

What I would not do is pressure the team to work longer hours. That lowers quality, increases bugs, and compromises the next sprint as well.

---

## 9. A client requests an urgent change mid-sprint. How would you handle it?

The first step is to listen and understand how urgent it really is. "Urgent" for a client sometimes means "I want it soon" and not necessarily "by tomorrow."

If after evaluating it is genuinely urgent and high priority, I would discuss it with the PO and Scrum Master to assess whether it makes sense to incorporate it. In Scrum, sprints are designed to protect the team from constant interruptions — but there are valid exceptions.

If it is incorporated, something from the current sprint needs to come out to keep the commitment realistic. The team cannot absorb new work without releasing something else. That conversation with the client is also part of the PM's job: helping them understand that adding something means removing something else, and that decision is theirs to make with clear information.

If it is not that urgent, it goes to the backlog, gets prioritized in the next planning, and is handled properly. That is the most common and healthiest response.

---

*PM Challenge · July 2026 · Francisco Roldán — [roldanfrancisco.personal@gmail.com](mailto:roldanfrancisco.personal@gmail.com) · [LinkedIn](https://www.linkedin.com/in/roldanfrancisco) · [GitHub](https://github.com/roldn)*
