# Guide for creating a Pull Request

1.  **Create a local clone of the registry repository**

```sh
git clone https://github.com/Apprpt-Central/registry.git
```

*You do not need to fork the registry repository.  New users will be provisioned as collaborators, allowing everyone to create new branches in the main repository.*

2. **Create a branch for your changes**

The name of the branch ***must*** folow a specific format:
`<username>-YYYYMMDD/<name>`
  - `<username>` is your GitHub username.
  - `YYYYMMDD` is the current date.
  - `<name>` is a descriptive name for your change.

The branch must be created in the registry on the date described in the branch name, so create the branch and push it to the registry immedately.

````sh
# create a new branch and swtich to it

git checkout -b foo-20210104/foonet
```

3. ***Make your changes on your new branch***

See the <insert wiki link here> guide in the Wiki for more information.

 - 

````sh
$EDITOR foonet
git add .
git commit
```

4.  **Push your changes back to the registry***

You must squash multiple commits together and sign them using your <insert auth methord type and link for info>.
It is also good practice to rebase your work on top of any other changes that may have happeend to the master branch.

The registry contains a script that will automaticaly rebase and squash your commits:

```sh
./squash-my-commits
git push --force
```

or you can do it manually:

```sh
# make sure your local copy of master is up to date

git fetch origin master

# ensure you are using your new branch

git checkout foo-20210104/foonet

# rebase your branch on top of the master
#
# -i to interactively pick the commits
# -S to sign the result with your GPG key (not required for SSH authentication)
#
# In interactive mode, make sure the first commit says 'pick'
# change the rest from 'pick' to 'squash'
# save and close to create the commit

git rebase -i -S origin/master

# force push your changes back to the registry

git push --force
```

5. **Create a pull request**

In Github, select your branch, check your changes again for a final time and then hit the `Pull Request` button.

If you are using SSH authentication, please post the full commit has that you signed and teh SSH signature in to the PR comments.

Your changes will now go through a check and review by the registry maintainers.

6.  ***Making updates***

If you need to make changes to fix review issues simple make the updates to your branch and follow the process in (4) to rebase, squash and sign your changes again.  **You must do this for every update**.

Do not close and re-open a new pull request, any changes you make on your branch will be automatically updated in the PR. Creating a new PR loses all the history and makes tracking changes harder.

# GitHub usage

GitHub and the Apprpt-Central registry may contain personal information for users who have submitted data to the registry.  This information is stored on GitHub servers and viewable by anyone who access the registry.   In addition, anyone may make their copies of the registry, which they may then process or transfer in arbitrary ways.  You must assume that all data entered in the registry is public information.

Any personal information stored in the registry is optional anvountarily provided by you.  Whilst the registry maintainers will make best efforts to update or delete personal data, you must accept that the techincal restrictions of git may make this impossible and that your information will likley have been distributed beyond the control of the registry maintainers.

IF this is not acceptable for you, you mustnot upload youer personal data to the registry.

Anyone has the ability to make copies of the registry data for their own use.  If you do copy the registry you must ensure that any copies you make are deleted when no longer required and that you will make best efforts to update or delete personal data when requested.

