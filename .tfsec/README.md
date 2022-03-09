<!--
The name of the project. Can also be a logo or ASCII Art Header (this [site](http://patorjk.com/software/taag/#p=display&f=Slant&t=Pro%20WebApp) can generate nice ASCII art)	
-->	
# Terraform Linting Rules

<!---
Some prose that describes the project, in as much detail as necessary to ensure the reader walks away with a basic understanding of the purpose of this repository. Diagrams included here can be useful to help the reader understand how the system is architectured. Links to other relevant documentation might also be useful.
-->
Shared and agreed upon custom rules for our Terraform linting / security scanning tools.

<!-- 
A description of how the code included in the project runs in various environments, including the URLs if that's appropriate
-->
## Where Does This Run

This is meant to be pulled as a subtree into a repository where Terraform code exists

<!--
Step-by-step instructions on how to install the code and any necessary dependencies
-->	
## How to Use

### Add to Repos with Terraform via git subtree

`git subtree add --prefix .tfsec https://github.com/invitation-homes/terraform-linting-rules main --squash`
or for SSH
`git subtree add --prefix .tfsec git@github.com:invitation-homes/terraform-linting-rules main --squash`

This will rewrite the subtree squash commit so that you don't anger the great Jira github action
`git filter-branch -f --msg-filter 'sed "s/Squashed/<JIRA TAG> Squashed/g"' HEAD...HEAD~1` 


### Update rules

`git subtree pull --prefix .tfsec https://github.com/invitation-homes/terraform-linting-rules main --squash`
or for SSH
`git subtree pull --prefix .tfsec git@github.com:invitation-homes/terraform-linting-rules main --squash`

<!-- 
Instructions on how to run locally -- necessary configuration files, secret configuration, etc. As a developer, this section combined with the previous section should give me all of the necessary information to check out and run the project locally	
-->	
### Local Development

These rules are meant to be in a .tfsec folder. That is where tfsec looks for rules.

<!-- 
How is the code built and deployed? Where does the project run? What linting and security checks are in place? Where can you view test results & static code analysis?
-->	
## CI/CD & Deployment
Github Actions:

* [reviewdog/action-yamllint](https://github.com/reviewdog/action-yamllint)
