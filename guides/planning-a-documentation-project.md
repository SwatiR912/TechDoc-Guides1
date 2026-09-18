# Planning a documentation project

How to decide what documentation a release needs, in a way that survives contact with a shipping date.

The failure this guide prevents is the documentation plan that lists every document a product could theoretically have, gets approved because nobody objects to thoroughness, and then delivers 40% of itself on release day, chosen by whatever was most urgent that week.

## Step 1: Find out what is actually shipping

Not from the roadmap. From the tickets, the pull requests, and one conversation with the engineer who is building it.

Write down, for each change:

- What a user can do that they could not do before
- What changes for users who are already doing it the old way
- What breaks
- What is being removed, and what replaces it

That list is the documentation scope. Everything else in the release is internal and needs no words.

Do this early enough that the answers can still change, and expect them to change anyway.

## Step 2: Identify the readers, and be specific

"Users" is not an audience. A useful audience statement names a person and what they already know:

- *A backend engineer integrating our API for the first time, who knows REST but not our domain model*
- *An administrator who has used the console for a year and now has to configure SSO once*
- *A support agent who needs to recognise this failure mode in under 30 seconds*

Each of these needs a different document, and the third might need no document at all — it might need a better error message. Documentation is not always the answer, and noticing that is part of the job.

## Step 3: Decide what to write, and what not to

For each audience and task, choose the document type deliberately:

| Reader's situation | Document type | Test of success |
| --- | --- | --- |
| Never used this before | Quickstart | They get one thing working, fast |
| Has a specific task | How-to guide | They complete it without opening anything else |
| Needs to look something up | Reference | They find the field in under a minute |
| Something already went wrong | Troubleshooting | They recognise their symptom |
| Wants to understand why | Concept | They can predict behaviour they have not seen |

Then cut. A plan is only a plan once something is on the not-now list. Write that list down and keep it visible — it is what you point at when someone asks why X is missing, and it becomes the backlog for the next cycle.

**What to cut first:** conceptual documents nobody asked for, second quickstarts for audiences who can use the first one, and reference material the product's own interface already states clearly.

## Step 4: Size the work honestly

Estimate per document, in a unit you can defend:

| Document | Rough effort | What drives it |
| --- | --- | --- |
| Quickstart | 1–2 days | Testing the happy path end to end, repeatedly |
| How-to guide | 0.5–1 day | Whether you can run the task yourself |
| API reference, per endpoint | 2–4 hours | Quality of the spec you are given |
| Troubleshooting entry | 1–2 hours | Access to real support tickets |
| Release notes | 0.5 day | How well the commits were written |

Add review and revision time, which is typically a third of drafting time and is the first thing people forget. Add environment access time if you do not have it yet; waiting for a test account has delayed more documentation than writer's block ever has.

If the total exceeds the time available — and it usually does — go back to step 3 rather than to the estimates. Deciding to write less is a plan. Deciding to write the same amount faster is a wish.

## Step 5: Sequence by dependency and risk

Order the work so that the riskiest unknowns surface first:

1. **Documents that need information you do not have.** Start these first, because the blocker is other people's time.
2. **Documents that require testing an unfinished feature.** Draft the structure, fill in when the feature stabilises.
3. **Documents you can write from the spec alone.** These are safe to do last; nothing about them will surprise you.

Never sequence alphabetically or by document type. Sequence by what could go wrong.

## Step 6: Agree the deliverables and what "done" means

Before starting, agree with the product owner:

- Which documents ship with the release and which follow it
- Who reviews for technical accuracy, and by when
- What happens if the feature changes after the documentation is written — specifically, who tells you

That last one is the one that gets skipped and the one that causes the damage. Ask for it by name.

## Step 7: Track by document, not by percentage

"Documentation is 60% done" means nothing. Track states:

`Not started` → `Drafted` → `Technical review` → `Revised` → `Editorial review` → `Ready`

Anyone can read that at a glance and see that four documents sit in technical review with no reviewer assigned, which is a problem you can act on.

## After the release

Spend an hour, within two weeks, on three questions:

1. **What did users ask that the documentation should have answered?** Support tickets and forum posts are the honest test, and they are the only feedback you get for free.
2. **What did you write that nobody read?** If analytics exist, look. A page with no traffic is either badly placed or unnecessary, and both are worth knowing.
3. **What did you underestimate?** Adjust the numbers in step 4 with real data rather than repeating the same estimate next cycle.

## Related

- [Running a documentation review](running-a-documentation-review.md)
- [Maintaining an existing documentation set](maintaining-an-existing-doc-set.md)
