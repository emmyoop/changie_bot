# changie_bot_autogenerate
###  Description
**what?**
Add a changelog yaml file per changie expectation when a bot creates a PR.  The new yaml file  will be created if none already exists on the PR when the PR has a specifed label.  Once created, it will be committed by a specified bot and commit will be pushed to the PR.

**why?**
Automate changelog generation for more visability with automated bot changes.

**when?**
Once a PR is created and it has been correctly labeled.  

An exampe use is for PRs created by dependabot.  You can also manually trigger this by adding the specified label at any time.


#### Required input and output arguments

- bot_PAT: Personal Access Token of the bot that will commit the file
- commit_author: Author of the commit for the changelog file. Author expected in the format "Lorem J. Ipsum <lorem@example.com>"
- changie_kind: Type of changelog file  # TODO: how does changie define this?
- label: GitHub label to trigger off of


#### Optional input and output arguments
- commit_message:
    - description: Message to put on commit of new changelog file
    - default: "Add automated changelog yaml from template"
- custom_changelog_string: # is this the right way?  could it be templated? start here and iterate.
    - description: The multi-line string containg the expected contents of the custom fields for a changelog entry.
    - default: ''  # needed?
- filename: 
    - description: The name of the file to use as the issue template
    - default: .github/CHANGELOG_TEMPLATE.md


###  Secrets the action uses
- PAT (preferably of a bot) for the commit
- action token to checkout branch

### Example

TBD