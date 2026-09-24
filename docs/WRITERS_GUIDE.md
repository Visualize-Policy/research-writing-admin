> **This is a copy, not the source of truth.** The original lives at
> `docs/WRITERS_GUIDE.md` in `wtdickens/health-dashboard` (the code repo — this copy exists so
> the guide's own audience, research/writing volunteers, can read it without needing code-repo
> access). Copied here on 2026-09-24, at commit `5f4efdd`. If the two ever disagree, the
> health-dashboard original is authoritative.
>
> Unlike some of the other copied docs in this folder, this one's real audience is entirely this
> repo — worth considering making *this* copy the source of truth instead, the next time it needs a
> real edit, rather than maintaining the asymmetry.

---

# Guide for Researcher-Writers: Working on GitHub in Your Browser

This is a **tutorial, not just a reference** — follow along and actually do each step as you read
it, using the practice issue and file set up for exactly this purpose. By the end you'll have
opened a real pull request and gone through the real mechanics once, so the next time you do this
for actual project work, it's already familiar.

You don't need to install anything, use a command line, or be granted any special access.

**How the process works.** Writing tasks are posted as *issues*. Issues come from project
leadership, from the coders building the project, and from team representatives who need to divide
up a team's work (see step 5). Each issue has its own file in the `writing/` folder. When you start
editing, GitHub automatically gives you your own personal copy of the project (a *fork*) and saves
your work there. Your draft is submitted as a *pull request*: a request to have your work reviewed
and merged into the official version of the project, called `main`. Nothing you do can change
`main` directly. Everything goes through review, so you can't break anything.

**The one rule to remember:** after your first save, your **pull request is your home base**.
Always return to your work through it (see step 7).

**Your practice materials for this tutorial:**
- Issue **[#13](https://github.com/Visualize-Policy/research-writing-admin/issues/13)** — a real
  issue, marked as practice-only.
- File **[`writing/000-tutorial.md`](https://github.com/Visualize-Policy/research-writing-admin/blob/main/writing/000-tutorial.md)**
  — a real file, already sitting in the repo, waiting for you to edit it.

Nothing you do to either can break anything real. A project lead will close out practice pull
requests after each session without merging them — if yours doesn't get merged, that's expected,
not a mistake on your part.

---

## 1. Before you start

Create a free GitHub account at github.com if you don't have one. That's all you need. Do this now
if you haven't already.

## 2. Finding the repository

Do this now:

1. Log in at github.com.
2. Click the search box at the top of the page (or press the `/` key).
3. Type `research-writing-admin`. The repository
   **Visualize-Policy/research-writing-admin** should appear in the dropdown. Click it.
4. **Save yourself the search next time.** Do both of these:
   - Bookmark the page in your browser. The address is
     `https://github.com/Visualize-Policy/research-writing-admin`
   - Click the **☆ Star** button near the top right. Starred repositories are listed on your
     GitHub profile and are easy to find again.

## 3. A quick tour of the repository page

Across the top of the repository are tabs. You'll use three of them today:

- **Code** shows the project's files and folders.
- **Issues** is the list of writing tasks.
- **Pull requests** is where submitted work is reviewed. Your own work will live here once you've
  started.

## 4. Picking up an issue

This is how you'd normally choose a task — for today's practice, skip the choosing and go straight
to issue #13, but read this so you know the real process:

1. Click the **Issues** tab and open an issue to read it.
2. If you're taking it on, leave a comment ("I'll take this" or "Maria and I are working on
   this"). Leadership will assign it to you.
3. Note the issue's **number** (e.g. `#42`) and which file in `writing/` it refers to (e.g.
   `writing/042-medicaid-work-reqs.md`).
4. **If you're working with teammates, agree on one person to be the "lead writer"** who will
   start the draft. See step 8 for how the others contribute.

**For today:** open **[issue #13](https://github.com/Visualize-Policy/research-writing-admin/issues/13)**
now and read it. Its file is `writing/000-tutorial.md`.

## 5. Creating a new issue (team representatives) — skip this today

If you represent a team and your issue needs to be divided up, or it turns out to require a large
task of its own, you can post new issues:

1. Click the **Issues** tab, then **New issue**.
2. Give it a clear, specific title ("Estimate enrollment effects for section 3").
3. In the description, explain what needs to be done, and write **`Part of #42`** (using your
   team's original issue number). This creates a link between the two, visible on both issues.
4. Click **Create** (or **Submit new issue**).

Leadership will then set up the new issue's file in `writing/` and may link it formally as a
*sub-issue* of the original. Anyone can create an issue. Only leadership can assign people or add
labels.

**You won't need this today** — it only comes up once you're leading a team's slice of work. Skip
ahead to step 6.

## 6. Opening your stub for the first time

Every issue already has a starter file waiting in `writing/` — you're not creating a new document,
you're opening and editing the one that's already there. Do this now, for real:

1. On the **Code** tab, open the `writing/` folder and click **`000-tutorial.md`** (issue #13's
   file).
2. Click the **pencil icon** (✏️, "Edit this file") at the top right of the file.
3. GitHub will explain that you don't have write access, and that your changes will be saved to
   your own copy (a fork). If it shows a **Fork this repository** button, click it. This is
   expected and only happens once.
4. Write your line — your name and one sentence about what you're most interested in working on,
   as the file itself asks. Use the **Preview** tab above the text box to see how it will look.
5. When you're ready to save, click the green **Commit changes…** (or **Propose changes**)
   button. Type a short description of what you did (e.g. "Add my intro line") and click
   **Propose changes**.
6. GitHub shows a "Comparing changes" page. Click **Create pull request**.
7. Give it a clear title (e.g. "Tutorial practice — [your name]"). In the description, write
   **`Part of #13`** — not `Closes #13`, since this is shared practice material other people are
   also editing, and nobody's pull request should close the tutorial issue.
8. **Make sure "Allow edits by maintainers" is checked.** This lets project leads help fix
   problems directly.
9. Your draft isn't finished yet, so click the arrow next to the green button and choose
   **Create draft pull request**. (A draft tells reviewers "work in progress, not ready for final
   review.")

You now have a real pull request. **Bookmark it.** It's your home base from here on — for today's
practice, and for real work later.

## 7. Continuing your work (every time after the first)

**Don't click the pencil on the file in the main project again.** That would start a fresh copy
from the official version, without your draft in it, and create a second, separate pull request.

Instead, practice this now — add a second line to what you just wrote (a follow-up thought, a
typo fix, anything):

1. Open your pull request (your bookmark, or the **Pull requests** tab, where it's listed with
   your name).
2. Click the **Files changed** tab. You'll see a header bar for each changed file, showing its
   name. **`000-tutorial.md`'s header bar is what you want** — at the **far right end of that same
   bar, on the same line as the filename**, there's a **⋯** (three dots) button. It's easy to miss
   because it has no label, just the three dots. Click it, then click **Edit file** from the menu
   that appears.
3. Write, then click **Commit changes…**, add a short description, and commit. Your pull request
   updates automatically — no need to open a new one.

**Commit often:** at least every 20–30 minutes, and always before closing the tab. GitHub doesn't
autosave, and each commit is a saved version you can go back to.

*Backup route:* your copy lives at `github.com/YOUR-USERNAME/research-writing-admin`. Your work is
on a branch with a name like `patch-1`. Use the branch button at the top left of the file list to
select it.

## 8. Working with teammates

Only the lead writer can save directly to the draft. Teammates contribute through the pull
request. **If someone is sitting near you today, pair up and practice this on each other's
tutorial pull request** — it only really makes sense with two people:

- **To suggest specific wording:** go to the pull request's **Files changed** tab and hover over a
  line. Click the blue **+** that appears, then click the three dot menu icon to the right of preview and select the **Add a suggestion** button (the icon of a page with ±) in the comment box. Edit the text shown, and click **Comment** (or start
  a review). The lead writer can then accept it with one click (**Commit suggestion**).
- **For general comments or larger contributions:** post them in the **Conversation** tab, and the
  lead writer incorporates them.
- **For big pieces of work:** split it up. Ask leadership for a separate file per section, so each
  teammate can have their own pull request.

If you're working solo today, read this section rather than practice it — it'll make sense once
you're back here with a teammate.

## 9. Writing in Markdown

Files ending in `.md` use *Markdown*, a simple way to format plain text:

| You type | You get |
|---|---|
| `# Title` / `## Section` | Headings |
| `**bold**` / `*italic*` | **bold** / *italic* |
| `- item` | A bulleted list |
| `[link text](https://example.com)` | A link |
| A blank line | A new paragraph |

**Tip:** Start each sentence on its own line. It displays the same (lines join into one paragraph
until a blank line), but it makes reviews much easier, because GitHub shows which *lines* changed.
With one sentence per line, a reviewer sees exactly which sentence you revised, instead of a whole
highlighted paragraph. It also makes teammates' line-by-line suggestions (step 8) far more
precise. Try formatting your practice lines this way now if you haven't already.

## 10. Submitting for review

For real work, do this when the draft is actually finished. For today's practice, go ahead and do
it now so you've seen the mechanics: open your pull request and click **Ready for review** near
the bottom of the Conversation tab, just above the 'Add a comment' field. Leave a comment tagging whoever should review it (type `@` and
their username) — for practice, tag whoever's leading today's session.

## 11. The review

Reviewers will read your work and leave comments. You'll get email notifications.

- The **Conversation** tab holds the general discussion.
- The **Files changed** tab shows exactly what you added (green) and removed (red). Click the
  small document icon (**Display the rich diff**) located between '<>' and 'Viewed' on the working window title bar to see it formatted
  instead of as raw text.
- **Replying:** type a reply under any comment.
- **Suggested changes:** accept a reviewer's proposed wording by clicking **Commit suggestion**.
- **Making revisions:** edit and commit exactly as in step 7. Don't open a new pull request.

When everything is resolved, a project lead approves and merges your pull request. Your work is
now part of the official version. **For today's practice, your pull request won't be merged** — a
lead will close it out instead, since #13 is shared practice material, not something that should
land on `main`. That's expected, not a failure.

## 12. Open and closed: where finished work goes

The **Issues** and **Pull requests** tabs show only *open* items by default. Just above each list
are two filters, **Open** and **Closed**, with a count next to each. Click **Closed** to see
everything that's finished or set aside. Nothing is ever deleted: closed items keep their full
history and discussion, and can be reopened.

**How a pull request gets closed:**

- **Merged** (purple icon): a lead approved it and added the work to `main`. This is the normal
  ending for real work.
- **Closed without merging** (red icon): the author or a lead closed it — for real work, this
  might mean it duplicated another pull request or the task was dropped; for today's tutorial,
  it's simply how practice pull requests get cleaned up. The draft is still there and can be
  reopened if needed.

**How an issue gets closed:**

- **Automatically,** when a pull request whose description says `Closes #42` is merged.
- **By hand,** when the person who opened it or a lead clicks **Close issue**. GitHub records
  whether it was closed as *completed* or as *not planned*.

An issue linked with `Part of #42` (like your practice pull request against #13) stays open until
someone closes it by hand or a final pull request says `Closes #42` — issue #13 itself will stay
open indefinitely, since it's reused for every future tutorial session.

## 13. Troubleshooting

**I clicked the pencil on the main project again and now have two pull requests.** Don't panic,
and don't delete anything. Post a comment on either one tagging a project lead, and they'll help
you combine them.

**The pull request says "This branch is out of date with the base branch."** Click
**Update branch**. This pulls in other people's recent changes.

**The pull request says there are conflicts.** Someone else changed the same lines — likely, for
today's tutorial, because someone else is also editing `000-tutorial.md` at the same time as you.
Tag a project lead in a comment and they'll help resolve it.

**I can't find my pull request.** Go to the **Pull requests** tab and type
`author:YOUR-USERNAME` in the search box. Also check the **Closed** list.

**The file for my issue doesn't exist yet.** Ask in the issue's comments. If you're told to create
it, open the `writing/` folder, click **Add file → Create new file**, and name it with the issue
number and a short title, like `042-medicaid-work-reqs.md`. Then continue from step 6, item 4.

## 14. Advanced topics: github.dev, for images and other files

Everything above uses GitHub's simple in-browser editor — good for plain text, but it can't add an
image, a PDF, or any other non-text file. For that, use **github.dev**, a fuller code-editor
experience that still runs entirely in your browser, no install required. It works on the exact
same fork and branch you already have from step 6 — it's a better editor, not a separate access
path, so you still need a pull request open (or about to be opened) the way the rest of this guide
describes.

**Opening it:** while you're looking at your fork or your pull request's branch on github.com,
press the **`.`** (period) key on your keyboard. The page reloads as github.dev — same repository,
richer editor, with a file explorer on the left and an editing pane on the right. (If the keyboard
shortcut doesn't do anything, you can also just change `github.com` to `github.dev` directly in the
address bar and reload.)

**Adding an image or file:**

1. In the file explorer on the left, find or create the folder you want the file in.
2. Either **drag the file from your computer** and drop it onto that folder in the explorer, or
   **right-click the folder → Upload…** and pick the file from your computer.
3. It appears in the file explorer and shows up as a pending change, the same way a text edit
   would.

**Saving your change:** github.dev doesn't have a "Commit changes" button sitting next to the
file the way the simple editor does. Instead, use the **Source Control** icon in the far-left
sidebar (it looks like a branching line, and usually shows a number badge for how many files
changed). Click it, type a short commit message in the box at the top, and click the checkmark (✓)
or **Commit**. This updates your pull request automatically, exactly like committing from the
simple editor in step 7.

**Referencing an uploaded image from your `.md` file:** use standard Markdown image syntax,
`![description of the image](path/to/the/file.png)` — the path is relative to wherever your `.md`
file lives, the same way a link works.

Everything else — Preview, branches, conflicts, the pull request itself — works the same as
described earlier in this guide. github.dev is just a more capable window onto the same fork and
the same pull request.

## Quick reference

| Word | Meaning |
|---|---|
| **Repository (repo)** | The project: all its files and their full history |
| **Issue** | A task posted for someone to address |
| **Fork** | Your personal copy of the project, created automatically |
| **main** | The official, approved version |
| **Commit** | Saving a version of your changes, with a short note |
| **Pull request (PR)** | Your submitted draft, where review happens |
| **Merge** | Adding approved work into the official version |

**The workflow in one line:** Pick an issue → click the pencil on its file → save and open a draft
pull request → keep working *through the pull request* → mark ready for review → revise → merged.

**What you just did, in one line:** Issue #13 → `writing/000-tutorial.md` → pencil icon → wrote a
line → draft pull request → added a second line via the **⋯** menu → marked ready for review. Next
time, it's the same steps on a real issue.
