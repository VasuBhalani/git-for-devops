so what is diff in staging and commited 
if file in staging area means it is track by git and in both case we restore file

Yes — both staging and committed files are tracked by Git.
But there is a very important difference.

Core Difference
Staging Area	Committed
Temporary snapshot	Permanent snapshot
Ready for commit	Already saved in Git history
Can still change before commit	Fixed historical version
Stored in index/staging	Stored in repository database
Simple Understanding
Staging Area

When you do:

git add app.js

Git says:

"Okay, I prepared this version for next commit."

But it is NOT permanently saved yet.

Committed

When you do:

git commit -m "added app"

Git says:

"Now this snapshot becomes part of project history permanently."

Real Example
Step 1 — Create File
Hello
Step 2 — Stage File
git add app.js

Now snapshot stored in staging.

Step 3 — Edit Again

File becomes:

Hello
New Line

Now:

Area	Content
Working Directory	Hello + New Line
Staging Area	Hello

See?
Staging contains OLD snapshot until you run git add again.

Now Important Part
Can We Restore in Both Cases?
✅ YES — But Source Is Different
Case 1 — Restore From Staging Area

If file is staged but not committed:

git restore app.js

Git restores file from:

Staging Area
Case 2 — Restore From Commit

After commit:

git commit -m "save"

Now restore happens from:

Last Commit (HEAD)
Important Difference in Safety
Situation	Safe?
Only staged	Semi-safe
Committed	Fully safe

Why?

Because:

staging can still be overwritten
commit becomes permanent history
Interview-Level Explanation

Files in staging area are tracked and prepared for commit, but they are not yet permanently stored in Git history. Committed files are permanently stored snapshots inside the repository history and can always be recovered using commit references.

Best Visualization
Working Directory
      ↓ git add
Staging Area (temporary snapshot)
      ↓ git commit
Repository (permanent history)
One Important Thing

If staged file gets deleted:

✅ recoverable

If committed file gets deleted:

✅ also recoverable

BUT:

Committed version is much safer because Git history permanently stores it.

Memory Trick
Staging = Ready to save
Commit = Already saved forever