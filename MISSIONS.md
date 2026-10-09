# Missions

Your team is planning the office trip to the beach. The plan is in your team's repo (`trip-team-a` or `trip-team-b`): the itinerary, the lunch menu, the packing list and the games. Some of it is broken on purpose.

There's no coding. It's all about working on one shared plan together.

**Do everything in VS Code:** Source Control, the GitHub view (from the GitHub Pull Requests extension) and the Command Palette (`Ctrl+Shift+P`). Use the terminal (`` Ctrl+` ``) only where a step says so.

**Each mission has an issue assigned to you here.**
- Tick the boxes as you go.
- Stuck? Comment on the issue and add the `help` label.
- Done? Comment the proof link it asks for.

## Skill check

You do this twice: once at the start and once at the end. It isn't a test you pass or fail. It shows what you can do on your own, so the day can be judged on what changed.

**Rules:**
- work alone;
- don't look at the cheatsheet or MISSIONS;
- don't ask anyone;
- do as many as you can in the time given, and skip anything you don't know.

Work in your team's trip repository.

1. Clone it in VS Code.
2. Make a branch called `check/<your-name>-start` (at the end: `-end`).
3. Add one item to `packing-list.md` and commit it with a clear message.
4. Push the branch and open a pull request. Don't merge it.
5. Change a line in `itinerary.md`, then throw the change away.
6. Find out when the return time in the itinerary was changed, and to what. Write the answer in a comment on your pull request.
7. Merge `scenario/conflict-prices` into your branch and resolve the conflict so that plain tea and milk tea stay.
8. Undo your packing-list commit in a way that is safe for others, and push.

When the time is up, comment on your pull request with the numbers you finished, for example `done: 1 2 3 4`.

---

## Mission 1: on your own

Up to 30 XP.

**1.1 Set up VS Code (5 XP)**

1. Install the extension **GitHub Pull Requests** (by GitHub) from the Extensions view.
2. Click the **Accounts** icon (bottom left) > **Sign in with GitHub** > allow it in the browser.
3. In the terminal, tell Git who you are, once, using the same email as your GitHub account:

```
git config --global user.name "Your Name"
git config --global user.email "<the email on your GitHub account>"
git config --global core.editor "code --wait"
```

**1.2 Get the trip plan (5 XP)**

1. Open the Command Palette and choose **Git: Clone** > **Clone from GitHub** > your team's repository.
2. Choose a folder, then **Open**.
3. Look around:
   - **Explorer:** the files;
   - **Source Control > Graph:** the history and the `scenario/` branches (don't touch those yet);
   - right-click `itinerary.md` > **Open Timeline**: this file's history.

**1.3 Your first commit, on your own branch (10 XP)**

1. Click the branch name at the bottom left > **Create new branch** > `hello/<your-name>`.
2. In `team/`, create `<your-name>.md` with three lines: your name, your favourite trip food, and one thing you want to learn today.
3. In **Source Control**, hover over the file and press **+** to stage it. Type a message, `Add <your name> to the team`, then press **Commit**.
4. Press **Publish Branch**. Your branch is now on GitHub.

**1.4 Keep private things out (5 XP)**

1. Create `my-private-notes.txt` and write anything in it. Source Control wants it.
2. Right-click it in Source Control > **Add to .gitignore**. It disappears from the list.
3. Commit the `.gitignore` and **Sync Changes**.

**1.5 Undo before you commit (5 XP)**

1. Change two lines in `packing-list.md`.
2. In Source Control, click the file to see the **diff** (red is old, green is new).
3. Throw one change away: in the diff, use the arrow next to that change (**Revert Block**).
4. Throw the other away: right-click the file > **Discard Changes**.

**Bonus (+5 XP):** post your best commit message in the "Commit message court" discussion. The most 👍 wins.

---

## Mission 2: working as a team

Up to 50 XP.

**2.1 Take your issue (5 XP)**

1. In the **GitHub** view in VS Code, open **Issues**, and find "Add <your name> to the team page".
2. Press **Start Working on Issue**. VS Code creates a branch for it and assigns it to you.

**2.2 Make the change (10 XP)**

1. In `team/README.md`, add **one line** about yourself **directly under `# Team`**. Everyone writes on the same line. Yes, on purpose.
2. Stage, commit, then **Sync Changes** or **Publish Branch**.

**2.3 Open the pull request (10 XP)**

1. In the GitHub view, click **Create Pull Request**.
2. Title: what you did. Description: `Closes #<issue number>`.
3. Under **Reviewers**, add a teammate. Press **Create**.

**2.4 Review relay (15 XP)**

1. The PR you were given appears in the GitHub view under **Waiting for my review**. Open it, then **Checkout** to see it in your own VS Code.
2. Read the **whole** change.
3. Click a line and leave a useful comment.
4. Leave **one suggested change**: in the comment box, use **Make a suggestion**.
5. Then **Approve**, or **Request changes**.
6. The author accepts the suggestion and pushes it.

**2.5 Conflict party (10 XP)**

1. The first PR is merged by its author: in the PR view, choose **Squash and Merge**, then **Delete branch**.
2. Now everyone else's PR has a **conflict**. Fix yours:
   1. Switch to `main` (the bottom left) and **Sync**.
   2. Switch back to your branch.
   3. Command Palette > **Git: Merge Branch...** > `main`.
3. VS Code marks `team/README.md` with a **!**. Open it, then **Resolve in Merge Editor**.
4. Tick both changes (**Accept Combination**) so both lines stay, then **Complete Merge**.
5. Commit and Sync. Merge your PR once it's approved. Check that the issue closed itself.

**Bonus (+5 XP):** on a throwaway branch, merge `scenario/conflict-prices`.

1. In the merge editor, keep plain tea and milk tea **and** the Rs. 10 rises.
2. Push it and comment the branch link on your Mission 2 issue, then delete the branch on GitHub. Don't merge it.

---

## Mission 3: the undo escape room

10 XP per station.

Four stations, all in your Mission 3 issue. Team A starts at Station 1, Team B at Station 3, then go round in order when the move is announced.

- At each station, first make a fresh branch from `main`: `escape/<station>-<your-name>`.
- Tick the station's box and paste the proof (a link to the commit, or a screenshot) in a comment.

**Station 1: "The forgotten file"**

1. Change `itinerary.md` and `packing-list.md`.
2. Commit **only** `itinerary.md`, with the message `Updte plan`.
3. Fix both mistakes **without a new commit**:
   1. stage `packing-list.md`;
   2. Command Palette > **Git: Commit Staged (Amend)**;
   3. correct the message.

**Proof:** in the Graph, one commit holds both files under a well-spelt message.

**Station 2: "Take it back"**

1. Make two commits.
2. Command Palette > **Git: Undo Last Commit**, twice. The changes come back as uncommitted.
3. Commit them again.

**Then the scary one, in the VS Code terminal:**

```
git reset --hard HEAD~2     # both commits gone
git reflog                  # ...not gone
git reset --hard HEAD@{2}   # or the exact line from reflog
```

**Proof:** the Graph shows both commits back. In your comment, explain in one line what "hard" did that "Undo Last Commit" didn't.

**Station 3: "The mistake everyone already has"**

1. Commit a silly change to `lunch-menu.md`, and **Sync** it.
2. Undo it **without rewriting shared history**:
   1. open the Graph;
   2. right-click the commit > **Revert Commit**. If your version doesn't show it, run `git revert HEAD` in the terminal;
   3. Sync.

**Proof:** the Graph shows the mistake **and** the revert. In your comment, say why "Undo Last Commit" would be wrong here.

**Station 4: "The buried fix and the messy history"**

1. The branch `scenario/abandoned-boat-ride` has one good fix among dropped ideas. Bring **only** that one across:
   1. Command Palette > **Git: Cherry Pick...**;
   2. pick "Fix: the rest house check-in is at 14.00, not 12.00".
   3. If you're asked for a hash, copy it from the Graph (right-click > **Copy Commit ID**).
2. Then clean the games history:
   1. make a branch `clean-games` from `scenario/messy-history`;
   2. in the terminal, run `git rebase -i main`;
   3. VS Code opens the list: keep the first line as `pick`, change the others to `fixup`, save and close;
   4. Command Palette > **Git: Commit Staged (Amend)** > set the message to `Add the beach games`.

**Proof:** the Graph shows `clean-games` with **one** commit on top of `main`.

**Interrupt (anytime, +5 XP):** an "URGENT" announcement arrives in your GitHub notifications while you're mid-change.

1. Source Control `...` > **Stash** > **Stash**.
2. Switch to `main`, deal with the "urgent" thing, then switch back.
3. `...` > **Stash** > **Pop Latest Stash**.

---

## Mission 4: GitHub's power tools

Up to 45 XP.

**4.1 The robot checker, GitHub Actions (15 XP)**

1. On a new branch, create `.github/workflows/check.yml` and paste this in. You don't need to understand every word; the Office explains it.

```yaml
name: Check
on: [pull_request, push]
jobs:
  no-todo:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: No TODO left in the plan
        run: "! grep -rn TODO --include='*.md' ."
```

2. Commit and open a PR. In the PR view, watch the check run. It goes **red**. Why? Something in the trip plan still says TODO.

**4.2 Detective race: who lost the meeting point? (15 XP; first team +10)**

1. The first plan, tagged `v0.1.0`, said where to meet. Today's doesn't. Find the exact change that lost it.
2. First try VS Code: open `itinerary.md` > **Timeline**, and click through the versions.
3. Then the fast way, in the terminal. Git checks each version for you:

```
git bisect start
git bisect bad main
git bisect good v0.1.0
git bisect run grep -q "office main gate" itinerary.md
git bisect reset
```

4. Name the commit and what it changed.
5. Fix it on a branch: put back `**Meeting point: the office main gate.**`, then open a PR. The check turns **green**.

**4.3 Watch `main` get locked (5 XP)**

The Office turns on a **ruleset** live:

- pull request required;
- 1 approval;
- the `no-todo` check must pass.

Commit something on `main` in VS Code and try **Sync**. Read the refusal. That's the point.

**4.4 Templates and owners (10 XP)**

1. In one PR, add these two files:
   - `.github/pull_request_template.md`, with the headings *What*, *Why*, *Closes #*;
   - `.github/CODEOWNERS`, with the line `/lunch-menu.md @<a teammate>`.
2. Open a new PR that changes the lunch menu. Watch the owner get asked for a review automatically.

**Seen, not done (the Office shows them):**

- releases and tags;
- Dependabot;
- secret scanning and push protection;
- the project board's automation;
- GitHub Pages;
- Codespaces.

---

## Boss fight: publish the final trip plan v1.0.0

Team against team.

**Goal:** a GitHub **Release `v1.0.0`** of your team's trip plan.

Every change goes through a PR, a review by a teammate and a green check. Direct pushes don't count.

**Must have (10 XP each):**

1. The meeting point restored (if not already merged in 4.2).
2. The beach games from `scenario/messy-history` merged as **one clean commit**.
3. The check-in fix from `scenario/abandoned-boat-ride`, **and only that**: no boat ride.
4. The price rise from `scenario/conflict-prices` merged **without losing** plain tea and milk tea.
5. A `CHANGELOG.md` with a `1.0.0` section that lists what changed.
6. **The release:**
   1. on GitHub, go to **Releases** > **Draft a new release**;
   2. create the tag `v1.0.0` on `main`;
   3. press **Generate release notes**, then **Publish**.

**Traps you'll meet:**

- the games branch also carries the old TODO, so its check stays red until the meeting point is fixed on `main`;
- the price-rise branch conflicts with the tea split;
- the boat-ride branch carries two ideas you must **not** bring across.

**Scoring:**

| | XP |
|---|---|
| Each must-have done properly | 10 |
| First team to publish a correct release | +30 |
| Every member authored at least one merged PR and gave one real review | +20 |
| `main` never red after a merge | +10 |
| A direct push to `main`, or a merge that loses the tea split or adds the boat ride | -10 each |
