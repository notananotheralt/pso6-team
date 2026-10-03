# pso6-team

Repository: https://github.com/notananotheralt/pso6-team

Partner A (owner): Derek Yang / `notananotheralt`.
Partner B (contributor): fill in your name and GitHub username.

Partner A has created the public repository, added the initial three-line `team.txt`, and published a separate motto change on `main`. Partner B can now complete the fork, pull request, and conflict-resolution work. Partner A will still review and merge the PR afterward.

## Partner B: start here

1. Fork this repository into your own GitHub account.
2. Replace `B-USERNAME` in the commands below with your GitHub username. Clone **your fork** and add the original repository as `upstream`:

```bash
git clone git@github.com:B-USERNAME/pso6-team.git
cd pso6-team
git remote add upstream https://github.com/notananotheralt/pso6-team.git
git remote -v
```

3. **Use this branch command instead of the handout's `git checkout -b motto`:**

```bash
git checkout -b motto 9fcefdc0efd1fb83428546f6cf8c97bb4690f570
```

This starts your branch at the original `Team motto: TBD` commit. Partner A completed the motto edit before your fork, so this extra starting point preserves the two independent changes and the required merge conflict. Starting from the latest `main` would normally produce no conflict. The README in that older commit is minimal; keep these instructions open on GitHub's `main` branch.

4. Edit `team.txt`: replace `B-USERNAME` with your username on line 1, leave the programming language as `TBD`, and replace the motto on line 3 with your own independently chosen motto. Keep exactly three lines. Your motto must differ from Partner A's.
5. Commit and push:

```bash
git add team.txt
git commit -m "Set contributor team motto and identify Partner B"
git push -u origin motto
```

6. Open a pull request with:

   - Base repository: `notananotheralt/pso6-team`; base branch: `main`.
   - Head repository: `B-USERNAME/pso6-team`; compare branch: `motto`.
   - Title: `Set team motto`.
   - Description: one sentence explaining your change.

GitHub should report a merge conflict. Open the PR **before** merging `upstream/main` into `motto`, so the conflict can be seen and reviewed.

7. Send Partner A the PR link. Agree together on a final motto, and have Partner A comment on the PR with the agreed wording.
8. After that review, resolve the conflict on the command line with Partner A present, as the handout requests:

```bash
git checkout motto
git fetch upstream
git merge upstream/main
```

The conflict in `team.txt` is expected. Run `git status`, open the file, remove all conflict markers, and keep three lines containing both actual usernames, the programming language `TBD`, and the agreed motto. Then:

```bash
git add team.txt
git commit -m "Merge upstream/main and resolve motto conflict"
git push origin motto
```

This updates the same PR; do not open a second one.

## Finish together

Partner A reviews the final diff, leaves a short review comment, and uses **Create a merge commit** to merge the PR, preserving the joining history required by the handout. Partner A then runs:

```bash
git pull origin main
cat team.txt
git log --oneline --graph
```

After the PR is merged, Partner B syncs the fork:

```bash
git checkout main
git pull upstream main
git push origin main
```

Submit Partner A's public repository: https://github.com/notananotheralt/pso6-team
