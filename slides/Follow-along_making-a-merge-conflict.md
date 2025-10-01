# Creating and resolving a merge conflict

1. start file on main branch with "red" in first line
   - `code colors.txt`
   - write "red \n" on first line
   - save
   - `git status` and/or `git diff`
   - `git add colors.txt`
   - `git commit -m "add red to first line on main branch"`
   - see the commit with `git log`

2. edit file on new-branch by writing "blue" on second line
   - `git checkout -b new-branch`
   - `code colors.txt`
   - write "blue \n" on the second line
   - save
   - `git status` and/or `git diff`
   - `git add colors.txt`
   - `git commit -m "add blue to second line on new-branch branch"`
   - see the commit with `git log`

3. edit file on main branch by writing "green" on second line
   - `git checkout main`
   - `code colors.txt`
   - write "green \n" on the second line
   - save
   - `git status` and/or `git diff`
   - `git add colors.txt`
   - `git commit -m "add green to second line on main branch"`
   - see the commit with `git log`

4. merge new-branch into the main branch
   - `git branch -v` to see which branch you're on; you should be on main still
   - `git merge new-branch`
   - resolve merge conflict manually with one of these options
     - keep green OR blue
     - keep green AND blue, deciding which color should be on the second and third lines
   - save
   - `git status` and/or `git diff`
   - `git commit -m "merging - kept only green on second line"`
   - see the commit with `git log`

5. display the commits with a visualization of the branches
   - add the custom command `fancylog` by inputting `git config --global alias.fancylog 'log --pretty=format:"%h - %an, %ar : %s" --graph'`
   - `git fancylog`