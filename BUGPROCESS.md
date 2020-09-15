# Terraform Core GitHub Bug Triage & Labeling
The Terraform Core team has adopted a more structured bug triage process than we previously used. Our goal is to respond to reports of issues quickly.

## Goal
We see working on Terraform as a collaborative process with the community of users. When people find bugs, or run into trouble using Terraform, we want to help.

When a bug report is filed, our goal is to either:
1. Get it to a state where it is ready for engineering to fix it in an upcoming Terraform release, or 
2. Close it explain why, if we can't help

The intent of this process is to resolve issues quickly, either by getting them to a state where engineers can fix them, or by closing them when reproduction and resolution is not possible based on available information. 


## Process

### 1. [Newly created issues](https://github.com/hashicorp/terraform/issues?q=is%3Aopen+label%3Anew+label%3Abug+-label%3Abackend%2Foss+-label%3Abackend%2Fazure+-label%3Abackend%2Fs3+-label%3Abackend%2Fgcs+-label%3Abackend%2Fconsul+-label%3Abackend%2Fartifactory+-label%3Aterraform-cloud+-label%3Abackend%2Fremote+-label%3Abackend%2Fswift+-label%3Abackend%2Fpg+-label%3Abackend%2Ftencent++-label%3Abackend%2Fmanta++-label%3Abackend%2Fatlas++-label%3Abackend%2Fetcdv3++-label%3Abackend%2Fetcdv2+-label%3Aconfirmed+-label%3A%22pending+project%22+-label%3A%22waiting+for+reproduction%22+-label%3A%22waiting-response%22+-label%3Aexplained) require initial filtering. 

**Goal**: Most issues triaged within a few days, and no issues should stay in this state for more than 7 days

These are raw reports that need categorization and support clarifying them. They need the following done:

* label backends, provisioners, providers so we can appropriately route work on codebases we don't support to the correct teams
* point requests for help to the community forum and close the issue
* close reports against 0.11
* prompt users who have submitted obviously incomplete reproduction cases for additional information
* If an issue requires discussion with the user to get it out of this initial state, leave "new" on there and label it "waiting-response" until this phase of triage is done.

Once this initial filtering has been done, remove the new label. If an issue subjectively looks very high-impact and likely to impact many users, add it to the [0.13.x milestone](https://github.com/hashicorp/terraform/milestone/17) to mark it as being urgent. 

### 2. Prompt reproduction cases for unreproduced issues

Many bug reports, as originally reported, describe valid issues, but are not detailed enough for engineers to fix. At this stage, we work with people who report bugs to generate clear reproduction cases. 

A core team member initially determines whether the issue is immediately reproducible. If they cannot readily reproduce it, they label it "waiting for reproduction" and correspond with the reporter to describe what is needed. When the issue is reproduced by a core team member, they label it "confirmed". 

"confirmed" issues should have a clear reproduction case, not just be one-off reproduced by someone on the team. Anyone who picks it up should be able to reproduce it readily without having to invent any details.

### Goals for unreproduced issues
In May 2020, we decided to draw a line and prioritize issues newer than that date, and gradually work down the remaining backlog over time.

1. for [unreproduced issues reported since May 2020](https://github.com/hashicorp/terraform/issues?q=is%3Aopen+label%3Abug+created%3A%3E2020-05-01+-label%3Aprovisioner%2Fsalt-masterless+-label%3Adocumentation+-label%3Aprovider%2Fazuredevops+-label%3Abackend%2Foss+-label%3Abackend%2Fazure+-label%3Abackend%2Fs3+-label%3Abackend%2Fgcs+-label%3Abackend%2Fconsul+-label%3Abackend%2Fartifactory+-label%3Aterraform-cloud+-label%3Abackend%2Fremote+-label%3Abackend%2Fswift+-label%3Abackend%2Fpg+-label%3Abackend%2Ftencent+-label%3Abackend%2Fmanta+-label%3Abackend%2Fatlas+-label%3Abackend%2Fetcdv3+-label%3Abackend%2Fetcdv2+-label%3Aconfirmed+-label%3A%22pending+project%22+-label%3Anew+-label%3A%22waiting+for+reproduction%22+-label%3Awaiting-response+-label%3Aexplained+sort%3Acreated-asc), we want to keep this number at zero, and have a goal of no issues of older than one month. The issues may not get fixed within a month, but they should either get to a reproducible state or be closed to clear out this queue.

2. For [unreproduced issues reported before May 2020](https://github.com/hashicorp/terraform/issues?q=is%3Aopen+label%3Abug+created%3A%3C2020-05-01+-label%3Aprovisioner%2Fsalt-masterless+-label%3Adocumentation+-label%3Aprovider%2Fazuredevops+-label%3Abackend%2Foss+-label%3Abackend%2Fazure+-label%3Abackend%2Fs3+-label%3Abackend%2Fgcs+-label%3Abackend%2Fconsul+-label%3Abackend%2Fartifactory+-label%3Aterraform-cloud+-label%3Abackend%2Fremote+-label%3Abackend%2Fswift+-label%3Abackend%2Fpg+-label%3Abackend%2Ftencent+-label%3Abackend%2Fmanta+-label%3Abackend%2Fatlas+-label%3Abackend%2Fetcdv3+-label%3Abackend%2Fetcdv2+-label%3Aconfirmed+-label%3A%22pending+project%22+-label%3Anew+-label%3A%22waiting+for+reproduction%22+-label%3Awaiting-response+-label%3Aexplained+sort%3Areactions-%2B1-desc), we want to reduce this number over time. We will roughly prioritize these by upvotes. However, many of the highest-voted issues are also some of the hardest to fix. We strictly prioritize staying on top of new issues.


### 3. Explain or fix [confirmed issues](https://github.com/hashicorp/terraform/issues?q=is%3Aopen+label%3Abug+-label%3Aexplained+-label%3Abackend%2Foss+-label%3Abackend%2Fazure+-label%3Abackend%2Fs3+-label%3Abackend%2Fgcs+-label%3Abackend%2Fconsul+-label%3Abackend%2Fartifactory+-label%3Aterraform-cloud+-label%3Abackend%2Fremote+-label%3Abackend%2Fswift+-label%3Abackend%2Fpg+-label%3Abackend%2Ftencent++-label%3Abackend%2Fmanta++-label%3Abackend%2Fatlas++-label%3Abackend%2Fetcdv3++-label%3Abackend%2Fetcdv2+label%3Aconfirmed+-label%3A%22pending+project%22+)
The next step for confirmed issues is to either:

* explain why the behavior is expected, label the issue as "working as designed", and close it, or
* locate the cause of the defect in the codebase. When the defect is located, and that description is posted on the issue, the issue is labeled "explained". In many cases, this step will get skipped if the fix is obvious, and engineers will jump forward and make a PR. 

#### Goals
Bugs with a high impact with widespread impact should be fixed in the next Z release.

1. All [confirmed crashes](https://github.com/hashicorp/terraform/issues?q=is%3Aopen+label%3Acrash+label%3Abug+-label%3Aexplained+-label%3Abackend%2Foss+-label%3Abackend%2Fazure+-label%3Abackend%2Fs3+-label%3Abackend%2Fgcs+-label%3Abackend%2Fconsul+-label%3Abackend%2Fartifactory+-label%3Aterraform-cloud+-label%3Abackend%2Fremote+-label%3Abackend%2Fswift+-label%3Abackend%2Fpg+-label%3Abackend%2Ftencent++-label%3Abackend%2Fmanta++-label%3Abackend%2Fatlas++-label%3Abackend%2Fetcdv3++-label%3Abackend%2Fetcdv2+label%3Aconfirmed+-label%3A%22pending+project%22+) should be fixed in each Z release, even if they are unlikely to have a widespread impact
2. [confirmed non-crash bugs](https://github.com/hashicorp/terraform/issues?q=is%3Aopen+-label%3Adocumentation+-label%3Acrash+label%3Abug+-label%3Aexplained+-label%3Abackend%2Foss+-label%3Abackend%2Fazure+-label%3Abackend%2Fs3+-label%3Abackend%2Fgcs+-label%3Abackend%2Fconsul+-label%3Abackend%2Fartifactory+-label%3Aterraform-cloud+-label%3Abackend%2Fremote+-label%3Abackend%2Fswift+-label%3Abackend%2Fpg+-label%3Abackend%2Ftencent+-label%3Abackend%2Fmanta+-label%3Abackend%2Fatlas+-label%3Abackend%2Fetcdv3+-label%3Abackend%2Fetcdv2+label%3Aconfirmed+-label%3A%22pending+project%22+sort%3Areactions-%2B1-desc) should be resolved roughly in order of upvotes. Most of these issues should be fixed within 4 weeks, and issues that are blocked on needing a larger research or refactor project should have a brief explanation posted and be labeled "pending project"

### 4. The last step for [explained issues](https://github.com/hashicorp/terraform/issues?q=is%3Aopen+label%3Abug+label%3Aexplained+no%3Amilestone+-label%3Abackend%2Foss+-label%3Abackend%2Fazure+-label%3Abackend%2Fs3+-label%3Abackend%2Fgcs+-label%3Abackend%2Fconsul+-label%3Abackend%2Fartifactory+-label%3Aterraform-cloud+-label%3Abackend%2Fremote+-label%3Abackend%2Fswift+-label%3Abackend%2Fpg+-label%3Abackend%2Ftencent++-label%3Abackend%2Fmanta++-label%3Abackend%2Fatlas++-label%3Abackend%2Fetcdv3++-label%3Abackend%2Fetcdv2+label%3Aconfirmed+-label%3A%22pending+project%22+) is to make a PR to fix them. 

The issue can be closed and labeled "fixed" after the PR is merged, even if it's not included in a release yet. Since issues can be closed automatically when linked from a PR, labeling them as fixed is not mandatory. This is a convenience to exclude them from these triage filter search results.

Explained issues that are expected to be fixed in a future release should have a milestone

#### Goals
* All explained issues should be fixed or assigned to a future milestone by the time the release candidate of the next major release ships

## GitHub Issue Labels
label                    | description
------------------------ | -----------
new                      | new issue not yet triaged
explained                | a Terraform Core team member has described the root cause of this issue in code
waiting for reproduction | unable to reproduce issue without further information 
not reproducible         | closed because a reproduction case could not be generated
duplicate                | issue closed because another issue already tracks this problem
confirmed                | a Terraform Core team member has reproduced this issue
working as designed      | confirmed as reported and closed because the behavior is intended
fixed                    | issue is fixed by PR that has been merged
pending project          | issue is confirmed but will require a significant project to fix

## What is a good reproduction case?

A reproduction case must be something a Terraform Core engineer can git-clone or copy-paste and run immediately, without inventing any details or context. 

### How to write a good reproduction case

* A short example can be directly copy-pasteable; longer examples should be in separate git repositories, especially if multiple files are needed
* Include all needed context. For example, if you figured out that an expression can cause a crash, put the expression in a variable definition or a resource
* Set defaults on (or omit) any needed variables. The person reproducing it should not need to invent variable settings
* If multiple steps are required, such as running terraform twice, consider scripting it in a simple shell script. For example, see [this case](https://github.com/danieldreier/terraform-issue-reproductions/tree/master/25719). Providing a script can be easier than explaining what changes to make to the config between runs.
* Omit any unneeded complexity: remove variables, conditional statements, functions, modules, providers, and resources that are not needed to trigger the bug
* When possible, use the [null resource](https://www.terraform.io/docs/providers/null/resource.html) provider rather than a real provider in order to minimize external dependencies. We know this isn't always feasible. The Terraform Core team doesn't have deep domain knowledge in every provider, or access to every cloud platform for reproduction cases.

## Lack of response and unreproducible issues
When bugs that have been [labeled waiting response](https://github.com/hashicorp/terraform/issues?q=is%3Aopen+label%3Abug+-label%3Abackend%2Foss+-label%3Abackend%2Fazure+-label%3Abackend%2Fs3+-label%3Abackend%2Fgcs+-label%3Abackend%2Fconsul+-label%3Abackend%2Fartifactory+-label%3Aterraform-cloud+-label%3Abackend%2Fremote+-label%3Abackend%2Fswift+-label%3Abackend%2Fpg+-label%3Abackend%2Ftencent+-label%3Abackend%2Fmanta+-label%3Abackend%2Fatlas+-label%3Abackend%2Fetcdv3+-label%3Abackend%2Fetcdv2+-label%3Aconfirmed+-label%3A%22pending+project%22+-label%3A%22waiting+for+reproduction%22+label%3Awaiting-response+-label%3Aexplained+sort%3Aupdated-asc) or [labeled "waiting for reproduction"](https://github.com/hashicorp/terraform/issues?q=is%3Aopen+label%3Abug+-label%3Abackend%2Foss+-label%3Abackend%2Fazure+-label%3Abackend%2Fs3+-label%3Abackend%2Fgcs+-label%3Abackend%2Fconsul+-label%3Abackend%2Fartifactory+-label%3Aterraform-cloud+-label%3Abackend%2Fremote+-label%3Abackend%2Fswift+-label%3Abackend%2Fpg+-label%3Abackend%2Ftencent+-label%3Abackend%2Fmanta+-label%3Abackend%2Fatlas+-label%3Abackend%2Fetcdv3+-label%3Abackend%2Fetcdv2+-label%3Aconfirmed+-label%3A%22pending+project%22+label%3A%22waiting+for+reproduction%22+-label%3Aexplained+sort%3Aupdated-asc+) for more than 30 days, we'll use our best judgement to determine whether it's more helpful to close it or prompt the reporter again. If they again go without a response for 30 days, they can be closed with a polite message explaining why and inviting the person to submit the needed information or reproduction case in the future.

The intent of this process is to get fix the maximum number of bugs in Terraform as quickly as possible, and having un-actionable bug reports makes it harder for Terraform Core team members and community contributors to find bugs they can actually work on.

## Helpful GitHub Filters

[Confirmed needs for documentation fixes](https://github.com/hashicorp/terraform/issues?q=is%3Aopen+label%3Abug+label%3Adocumentation++label%3Aconfirmed+-label%3Abackend%2Foss+-label%3Abackend%2Fazure+-label%3Abackend%2Fs3+-label%3Abackend%2Fgcs+-label%3Abackend%2Fconsul+-label%3Abackend%2Fartifactory+-label%3Aterraform-cloud+-label%3Abackend%2Fremote+-label%3Abackend%2Fswift+-label%3Abackend%2Fpg+-label%3Abackend%2Ftencent++-label%3Abackend%2Fmanta++-label%3Abackend%2Fatlas++-label%3Abackend%2Fetcdv3++-label%3Abackend%2Fetcdv2+)

[Confirmed bugs that will require significant projects to fix](https://github.com/hashicorp/terraform/issues?q=is%3Aopen+label%3Abug+label%3Aconfirmed+label%3A%22pending+project%22++-label%3Abackend%2Foss+-label%3Abackend%2Fazure+-label%3Abackend%2Fs3+-label%3Abackend%2Fgcs+-label%3Abackend%2Fconsul+-label%3Abackend%2Fartifactory+-label%3Aterraform-cloud+-label%3Abackend%2Fremote+-label%3Abackend%2Fswift+-label%3Abackend%2Fpg+-label%3Abackend%2Ftencent++-label%3Abackend%2Fmanta++-label%3Abackend%2Fatlas++-label%3Abackend%2Fetcdv3++-label%3Abackend%2Fetcdv2)

### By Milestone
[0.13.x Milestone](https://github.com/hashicorp/terraform/milestone/17). Issues in this milestone should be considered high-priority but do not block a Z release. All issues in this milestone should be resolved in a 13.x release before the 0.14.0 RC1 ships.
[0.14.0 Milestone](https://github.com/hashicorp/terraform/milestone/18). All issues in this milestone must be fixed before 0.14.0 RC1 ships, and should ideally be fixed before 0.14.0 beta 1 ships.
[0.15.0 Milestone](https://github.com/hashicorp/terraform/milestone/19). All issues in this milestone must be fixed before 0.15.0 RC1 ships, and should ideally be fixed before 0.15.0 beta 1 ships.