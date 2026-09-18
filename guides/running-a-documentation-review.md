# Running a documentation review

How to review someone else's draft so that the document improves and the author still wants to send you the next one.

Reviewing is a skill separate from writing. A good writer who reviews badly slows a team down: authors learn to route around the reviewer, or to submit late so there is no time for feedback.

## Before you open the document

Ask three questions. Without the answers, you are reviewing against your own assumptions.

1. **Who is this for?** A guide for integration partners and a guide for internal support engineers look nothing alike, and the same sentence is wrong in one and right in the other.
2. **What stage is this?** An outline needs structural feedback. A final draft needs accuracy and polish. Copy-editing an outline wastes both people's time; restructuring a final draft the day before release is worse.
3. **What does the author want?** Ask directly. "I am unsure about the ordering" is a different review from "check the API details". Authors usually know where the weak part is.

If a draft arrives with none of this, send one message asking, rather than reviewing blind.

## The passes

Review in passes, coarse to fine. The reason is practical: a paragraph you polished may be cut in the structural pass, and time spent polishing it is gone.

### Pass 1 — Does it do its job?

Read it as the intended reader. Do not annotate; read it through.

- Does this document have **one** job, or has it become two documents?
- Could the reader accomplish the task with only what is here?
- Is anything missing that the reader has no way to know they need — a permission, a prerequisite, a version?
- Does it stop, or does it end? A document that ends tells the reader where to go next.

If the answer to the first question is "two documents", stop. Everything else is premature. Say so, propose the split, and send it back.

### Pass 2 — Is it accurate?

Verify rather than assume. This is the pass that justifies your existence as a reviewer.

- Run the commands. Follow the steps in a real environment.
- Check every parameter name, flag, role, and limit against the source of truth — the code, the API spec, the console, not another document.
- Check that examples produce the output claimed.
- Check version numbers and dates.

You will not always have an environment. When you cannot verify something, say so explicitly in the review: "I could not test step 4; someone with production access should confirm." An unverifiable claim silently approved is how wrong documentation ships.

### Pass 3 — Is it usable?

- Are decisions presented before the steps that depend on them?
- Is each step one action?
- Can a reader scan the headings and find their situation?
- Are warnings placed before the action they apply to?
- Is terminology consistent with the rest of the set, not just internally consistent?

### Pass 4 — Language

Passive voice where the actor matters, hedging, sentence length, heading parallelism, the style-guide rules. Last, and least, because it is the easiest to fix and the least important to the reader.

## How to write the feedback

**Sort by severity, not by position in the document.** A list of 40 comments in page order buries the three that matter. Lead with blockers.

**Say what is wrong, where, and why it matters.** "This is confusing" is not actionable. "Step 3 assumes the endpoint already exists, but nothing has created it — a reader following in order will fail here" is.

**Separate what must change from what you would do differently.** Authors cannot tell the difference unless you tell them, and they will either fight every comment or accept every comment. Both are bad. I label them:

| Label | Meaning |
| --- | --- |
| **Blocker** | Ship this and a reader fails, gets locked out, or loses data. |
| **Should fix** | The reader will succeed but stumble. |
| **Suggestion** | My preference. Take it or leave it, and I will not ask again. |

**Give the rewrite when the fix is wording.** Explaining what is wrong with a sentence takes longer than writing a better one, for you and for them.

**Do not rewrite the document.** A returned draft in your voice teaches the author nothing, and they can no longer see what changed. If a document needs that much work, say so and pair on it instead.

**Say what works, once, specifically.** Not as a sandwich — authors see through that — but because specific praise tells them what to repeat. "The prerequisites section is the clearest I have seen in this set" is useful. "Nice work!" is not.

## Calibration

Two failure modes, equally common.

**The reviewer who approves everything** is pleasant and useless, and the documentation degrades until someone else has to fix it publicly.

**The reviewer who rewrites everything** is thorough and exhausting. Authors stop trying, because the draft will be replaced anyway. If you find yourself marking every stylistic preference as a required change, you are in this mode.

A useful check: after your review, could the author make every required change themselves without asking you what you meant? If not, the review was about you.

## Closing the loop

- Respond to the author's replies. A review that is issued and abandoned leaves the author guessing.
- Re-check only what changed. Do not re-review the whole document unless it was restructured.
- Approve clearly. "Approved, with the two suggestions optional" beats silence.
- Note anything that came up twice across reviews. If three authors made the same mistake, the style guide is missing a rule, and that is a fix worth more than any single review.

## Related

- [Planning a documentation project](planning-a-documentation-project.md)
- [Auditing an existing documentation set](auditing-an-existing-doc-set.md)
