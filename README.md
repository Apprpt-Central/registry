<p align="right">
    <a href="https://github.com/apprpt-central/registry/stargazers"><img src="https://img.shields.io/github/stars/apprpt-central/registry.svg?style=social&label=Star" style="margin-left:5em"></a>
    <a href="https://github.com/apprpt-central/registry/network/members"><img src="https://img.shields.io/github/forks/apprpt-central/registry.svg?style=social&label=Fork"></a>
    <a href="https://github.com/apprpt-central/registry/watchers"><img alt="GitHub watchers" src="https://img.shields.io/github/watchers/apprpt-central/registry?style=social"></a>
</p>

<p align="center">
    <a href="https://github.com/Apprpt-Central/registry/wiki"><img src="https://img.shields.io/badge/Docs-wiki-blue.svg?style=for-the-badge"></a>
    <a href="https://github.com/apprpt-central/registry/issues"><img src="https://img.shields.io/badge/Status%3F-WIP-orange.svg?style=for-the-badge"></a>
    <a href="https://github.com/apprpt-central/registry/issues"><img src="https://img.shields.io/github/issues/apprpt-central/registry.svg?style=for-the-badge"></a>
    <a href="https://github.com/apprpt-central/registry/pulls"><img src="https://img.shields.io/github/issues-pr/apprpt-central/registry.svg?style=for-the-badge"></a>
</p>

### 10 Feb 21: WIP - This is a work in progress.  Please see the Issues and visit the Wiki for information regarding the status of this registry.

Wiki is available here:  https://github.com/Apprpt-Central/registry/wiki.  Please be patient as this wiki is being built.  
Note:  [Getting Started](https://github.com/Apprpt-Central/registry/wiki/Getting-Started) contains basic information on the main registry objects.

Due to WIP status applications (PRs) for Network Prefixes will be accepted in the coming days.  Check back here for an announcement when 
the registry is ready for use.

In the meantime we invite you to explore the objects in the registry, wiki, and other items listed in this registry. 

You can still submit issues related to problems found with the registry objects under the data directory.  

Looking for help or wish to join the discussion?  Visit [![Gitter chat](https://badges.gitter.im/Apprpt-Central/registry.png)](https://gitter.im/Apprpt-Central/registry)

---

# Guide for creating a Pull Request

1.  **Create a local clone of the registry repository**

```
git clone https://github.com/Apprpt-Central/registry.git
```

*You will need to fork the repository to make your changes. .  New 

2. **Create a branch for your changes**

The name of the branch ***must*** follows a specific format:
`<username>-YYYYMMDD/<name>`
  - `<username>` is your GitHub username.
  - `YYYYMMDD` is the current date.
  - `<name>` is  the short name for your new network.

The branch must be created in the registry on the date described in the branch name, so create the branch and push it to the registry immediately.

```
# create a new branch and switch to it
   
git checkout -b foo-20210104/foonet
```

3. **Make your changes on your new branch**

See the <insert wiki link here> guide in the Wiki for more information.

 - 

```
$EDITOR foonet
git add .
git commit
```

4.  **Push your changes back to the registry**

You must squash multiple commits together and sign them using your <insert auth method type and link for info>.
It is also good practice to rebase your work on top of any other changes that may have happened to the master branch.

The registry contains a script that will automatically rebase and squash your commits:

```
./squash-my-commits
git push
```

or you can do it manually:

```
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

git push
```

5. **Create a pull request**

In Github, select your branch, check your changes again for a final time and then hit the `Pull Request` button.

If you are using SSH authentication, please post the full commit hash that you signed and teh SSH signature into the PR comments.

Your changes will now go through a check and review by the registry maintainers.

6.  **Making updates**

If you need to make changes to fix review issues simply make the updates to your branch and follow the process in (4) to rebase, squash and sign your changes again.  **You must do this for every update**.

Do not close and re-open a new pull request, any changes you make on your branch will be automatically updated in the PR. Creating a new PR loses all the history and makes tracking changes harder.

# GitHub usage

GitHub and the Apprpt-Central registry may contain personal information for users who have submitted data to the registry.  This information is stored on GitHub servers and viewable by anyone who accesses the registry.   In addition, anyone may make their copies of the registry, which they may then process or transfer in arbitrary ways.  You must assume that all data entered in the registry is public information.

Any personal information stored in the registry is optional and voluntarily provided by you.  Whilst the registry maintainers will make best efforts to update or delete personal data, you must accept that the technical restrictions of git may make this impossible and that your information will likely have been distributed beyond the control of the registry maintainers.

If this is not acceptable for you, you must not upload your personal data to the registry.

Anyone has the ability to make copies of the registry data for their own use.  If you do copy the registry you must ensure that any copies you make are deleted when no longer required and that you will make best efforts to update or delete personal data when requested.

