# changie_bot_autogenerate
- [ ] A detailed description of what the action does
# **what?**
# Add a changelog yaml file per changie expectation when a bot creates a PR.  The new yaml file 
# will be created if none already exists on the PR when the PR has a specifed label.  Once created,
# it will be committed by a specified bot and commit will be pushed to the PR.
#
# **why?**
# Automate changelog generation for more visability with automated bot changes.

# **when?**
# Once a PR is created and it has been correctly labeled.  
#
# An exampe use is for PRs created by dependabot.  You can also manually trigger this by adding the
# specified label at any time.
- [ ] Required input and output arguments
  bot_PAT:
    description: Personal Access Token of the bot that will commit the file
    required: true
  commit_author: # author expected in the format "Lorem J. Ipsum <lorem@example.com>"
    description: Author of the commit for the changelog file
    required: true
  changie_kind:
    description: Type of changelog file  # TODO: how does changie define this?
    required: true
  label:
    description: GitHub label to trigger off of
    required: true
- [ ] Optional input and output arguments
  commit_message:
    description: Message to put on commit of new changelog file
    required: false
    default: "Add automated changelog yaml from template"
  custom_changelog_string: # is this the right way?  could it be templated? start here and iterate.
    description: The multi-line string containg the expected contents of the custom fields for a changelog entry.
    required: false
    default: ''  # needed?
  filename: 
    description: The name of the file to use as the issue template
    default: .github/CHANGELOG_TEMPLATE.md
    required: false
- [ ] Secrets the action uses
    PAT
    action token
- [ ] Environment variables the action uses
    none
- [ ] An example of how to use your action in a workflow