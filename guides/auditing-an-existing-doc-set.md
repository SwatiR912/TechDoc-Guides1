# Auditing an existing documentation set

How to assess documentation you have inherited, and produce a report someone will act on.

Two things make an audit useless: auditing against your own taste instead of the reader's need, and producing a finding list so long that it reads as "everything is wrong", which is the same as saying nothing.

## Before you start: agree the question

An audit answers a specific question. Ask the person requesting it which one:

- *Is this accurate?* — the fastest to answer and the most alarming when the answer is no.
- *Can users find what they need?* — structure and search.
- *What is missing?* — coverage against real tasks.
- *Can this be maintained?* — source format, ownership, duplication.
- *Is it consistent?* — terminology, voice, structure.

You can cover several, but you cannot cover all five well in one pass, and a report that tries reads as a complaint. Agree the order.

Also agree what happens with the result. An audit with no owner for the fixes is a document that makes everyone feel bad and changes nothing.

## Step 1: Inventory

Before judging anything, count what exists.

For each document: title, URL or path, type, owner if known, last meaningful update, and length. "Last meaningful update" is not the last commit — a typo fix does not refresh a page.

The inventory alone usually surfaces the first real finding: how much there is, and how much of it nobody has touched in two years.

## Step 2: Check accuracy first

Accuracy outranks everything. A beautifully structured set of wrong instructions is worse than a messy set of right ones, because readers trust it.

Sample rather than reading everything. Take the ten most-visited pages, or if analytics do not exist, the ten a new user would hit first. For each:

- Follow the procedure in a real environment
- Check parameter names, limits, and role names against the product
- Check screenshots against the current interface
- Note anything referring to a feature that no longer exists

Record each failure with the page, the step, and what actually happened. One verified failure carries more weight with a product owner than fifty style observations.

## Step 3: Check coverage against real tasks

Coverage is measured against what users do, not against the product's feature list.

Sources, in order of usefulness:

1. **Support tickets** — the questions people paid attention to ask. Categorise three months of them and check whether the documentation answers each category.
2. **Search logs for the docs site** — especially queries with no result or no click. This is a list of things people expected and did not find.
3. **Community and forum posts** — where users answer each other with information that should have been documented.
4. **The feature list** — last, because a documented feature nobody uses is not a win.

The output is a gap list where every entry can name its evidence.

## Step 4: Check structure

- Can a reader predict where something lives before they look for it?
- Are documents grouped by user task or by internal team structure? The second is the most common structural defect, and it is invisible to the people who built it.
- Is there a path for a new user, or only a pile of pages?
- Do page titles say what the reader accomplishes?
- Is the same information in three places, each slightly different?

Duplication deserves special attention. It is the thing that guarantees future inaccuracy, because one copy will be updated and the others will not.

## Step 5: Check consistency

Terminology first, because it is the one readers notice without being able to name. Then voice, then structure — do all how-to guides have prerequisites, or only some?

Count and locate rather than characterise. "Three terms are used for the same object across 40 pages" is a finding. "Terminology is inconsistent" is an opinion.

## Step 6: Check maintainability

The question is whether this set can survive the next two years.

- Is the source in version control, and can a contributor find it?
- Does publishing require a specific person or a manual step?
- Is there an owner per section, or is everything owned by "the docs team", which usually means nobody?
- How long does a typo fix take, end to end? If that is measured in days, nobody will fix typos.

## Writing the report

Structure it so that someone who reads only the first page can act.

**Open with the three findings that matter.** Not a methodology section. The three things that, if fixed, would change the most.

**Rank every finding by reader impact:**

| Severity | Definition |
| --- | --- |
| Critical | Users are being told something false, or are locked out of a task. |
| High | Users cannot find or cannot complete something important. |
| Medium | Users succeed but are slowed or confused. |
| Low | Polish, consistency, and preference. |

**Give every finding evidence and a location.** Page, section, and what is wrong. A finding a reader cannot verify will be argued with rather than fixed.

**Propose a sequence, not a list.** Group the fixes into what can be done this week, this quarter, and what needs a decision or a budget. Include the effort estimate; the difference between "fix 12 pages" and "restructure the information architecture" is the whole conversation.

**Say what is good.** Not for balance, but because something is working and the fixes should not destroy it.

**Keep the full finding list in an appendix.** The report is the argument; the list is the backing.

## Two things to avoid

**Do not audit against a style guide the set was never written to.** Every deviation becomes a finding, the report becomes 300 items long, and the genuinely broken pages are lost in it. If the set has no style guide, that is itself one finding, not three hundred.

**Do not present the audit as a verdict on the previous writer.** Most documentation problems are the result of deadline pressure and missing ownership, not carelessness. A report that reads as a criticism of a person makes the fixes political, and political fixes do not happen.

## Related

- [Planning a documentation project](planning-a-documentation-project.md) — what to do with the gap list.
- [Running a documentation review](running-a-documentation-review.md) — the per-document version of this.
