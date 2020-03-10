GitHub
======

This page documents the [FOSSRIT GitHub organization](https://github.com/FOSSRIT).
It explains how the GitHub organization is managed.


## Owners

Owners retain full administrative access to the entire FOSSRIT GitHub organization.
This includes read, triage, write, maintain, and admin permissions on _all_ repositories.
Currently the following people are owners of FOSSRIT:

* [Joe](https://github.com/ritjoe)
* [Justin W. Flory](https://github.com/jwflory)
* [Mel Chua](https://github.com/mchua)
* [Mike Nolan](https://github.com/Nolski)
* [Stephen Jacobs](https://github.com/itprofjacobs)

This list can be viewed in the GitHub organization [here](https://github.com/orgs/FOSSRIT/people?utf8=%E2%9C%93&query=role%3Aowner).


## Repositories

There is not much central management for repositories in the FOSSRIT organization.
Members of FOSSRIT are allowed to create their own repositories in the organization.
The only suggestion worth making is to add repository topic tags to new repositories.
These are added near the top of a specific repo.
Some common tags used are below:

* `rit`
* `rochester`
* `rochester-institute-of-technology`
* `university`

These make our repositories more discoverable on GitHub and also builds a portfolio of open source projects from RIT across all of GitHub.


## People

When adding new people to the FOSSRIT GitHub organization, invite them to a specific team, not the general GitHub organization.
See [Teams](#teams) below for more details about team management.

The only other detail worth noting is that GitHub sets organization membership to private by default.
Setting membership to public means the FOSSRIT organization appears on your GitHub user profile.
Generally it is a good idea to remind new members about this and encourage them to set their membership to public.
This is done by going to the [People](https://github.com/orgs/FOSSRIT/people) tab, searching for your profile, and changing the _Private_ dropdown to _Public_:

![Screenshot: How to change FOSSRIT membership from private to public](/_static/infra/github-projects-people-privacy.png)


## Teams

Teams are the cornerstone of access control and permission management in FOSSRIT.
They are complex, but not without good reason.
This was designed to make access organized and transparent over time.
[GitHub Owners](#owners) can modify membership of any teams.

Currently, there are four top-level teams in FOSSRIT.
Unless there is a _really_ good reason, new teams should be created as sub-teams of these four top-level teams.
The four top-level teams are as follows:

* FOSS@MAGIC
* Friends of FOSS
* Projects
* Students and alums

Each top-level team is explained in detail below.

### [FOSS@MAGIC](https://github.com/orgs/FOSSRIT/teams/foss-magic)

**NOTE**: This top-level team is the most nuanced and grants access to several things.
Please read this documentation carefully before making changes to this top-level team or any sub-teams.

The FOSS@MAGIC team is for payroll faculty, professors, other MAGIC staff, FOSS academia instructors, and community volunteers.
Team and sub-team membership should be regularly maintained for auditing purposes.

#### Membership

The top-level team is _only_ for people who are currently employed on the RIT MAGIC Center's payroll.
FOSS@MAGIC volunteers are not included on this team; they are included on one of the [sub-teams](#foss-magic-sub-teams).

#### Repositories

The top-level team grants different levels of access to the following repositories:

* [FOSSRIT/fossrit.github.io](https://github.com/FOSSRIT/fossrit.github.io): Maintain
* [FOSSRIT/runbook](https://github.com/FOSSRIT/runbook): Maintain
* [FOSSRIT/tasks](https://github.com/FOSSRIT/tasks): Maintain

Note these permissions have a "trickle-down" effect on all sub-teams.
Each sub-team inherits these permissions from the FOSS@MAGIC top-level team.

#### Projects

The top-level team grants **write access** to the [**FOSS@MAGIC operations**](https://github.com/orgs/FOSSRIT/projects/1?fullscreen=true) project board.
Each sub-team also inherits this access.
For more details on project board management, [see below](#organization-projects).

#### FOSS@MAGIC sub-teams

Currently there are two sub-teams of FOSS@MAGIC:

* FOSS academia
* Tech Team

Each sub-team is explained in detail below.

##### [FOSS academia](https://github.com/orgs/FOSSRIT/teams/foss-academia)

This sub-team is for people involved with the [Free and Open Source Software and Free Culture Minor](https://www.rit.edu/study/free-and-open-source-software-and-free-culture-minor) and curriculum.
Currently, this mostly means teaching faculty.
In addition to inheriting the top-level team permissions, it also grants admin access to a single private repository for the FOSS academia curriculum.

##### [Tech Team](https://github.com/orgs/FOSSRIT/teams/tech-team)

This sub-team is for people involved with the [FOSS@RIT Tech Team](/community/tech-team).
It grants a range of access to software and infrastructure projects in FOSSRIT (in addition to what is inherited from the FOSS@MAGIC top-level team):

* [FOSSRIT/infrastructure](https://github.com/FOSSRIT/infrastructure): Triage
* [FOSSRIT/shalom-street-Toy](https://github.com/FOSSRIT/shalom-street-Toy): Maintain

There is also a sub-team of the Tech Team: [Ansible maintainers](https://github.com/orgs/FOSSRIT/teams/ansible-maintainers).
This sub-team grants **maintain** access to FOSSRIT/infrastructure.
Ansible maintainers are a specific subset of the Tech Team who want to help with Ansible and config management.
Membership in this group means you are automatically assigned to review new pull requests in the FOSSRIT/infrastructure repository.

### [Friends of FOSS](https://github.com/orgs/FOSSRIT/teams/friends-of-foss)

This team is a collection of people who are associated with the FOSS@RIT community, but do not fit in another top-level team.
This is like a "catch-all" team for anyone who wishes to show their affiliation with our community on their GitHub profile.
This top-level team does not grant access to any repositories.

There is only one sub-team: [Founding members](https://github.com/orgs/FOSSRIT/teams/founding-members).
This sub-team is a historical archive of people who were involved in the earliest days of the FOSS program at RIT between 2009-2012.

### [Projects](https://github.com/orgs/FOSSRIT/teams/projects)

This top-level team is for groups of collaborators on specific projects in the FOSS@RIT community.

#### Repositories

The top-level team does not grant access to any repositories.
Instead, commit/admin access should be granted to specific sub-teams for a specific project or collection of projects.

#### Sub-team membership

Each sub-team created underneath this team should be for a specific project or collection of GitHub repositories.
For example, the [FOSS Letters](https://github.com/orgs/FOSSRIT/teams/foss-letters) sub-team includes three people.
These three people have full admin rights to two repositories associated with the FOSS Letters project.

Additionally, some of FOSS Letters team members are designated as **maintainers**.
This gives them permission to invite others in the FOSSRIT GitHub organization to their project and give them commit/admin access.

### [Students and alums](https://github.com/orgs/FOSSRIT/teams/students-and-alums)

As it implies, this group includes students and alums of RIT who are associated with the FOSS@RIT community.

#### Repositories

This group grants read access to a single private repo with planning materials for the [Free and Open Source Software and Free Culture Minor](https://www.rit.edu/study/free-and-open-source-software-and-free-culture-minor).

#### Sub-team membership

Do not add people to this group.
Add them to one of the appropriate sub-teams.
There are three sub-teams, with an indefinite number of sub-teams beneath them:

* Alums
* Current students
* FOSS curriculum students

##### [Alums](https://github.com/orgs/FOSSRIT/teams/alums)

This group includes sub-teams for graduating classes of RIT, sorted by graduating year.
If an alum's graduating year is unknown, add them to this team.
Otherwise, add them to a team with a specific graduating year.

##### [Current students](https://github.com/orgs/FOSSRIT/teams/current-students)

Every current student should be added to a sub-team for a specific graduating year.
This helps us understand who is an active student in our community over time.

##### [FOSS curriculum students](https://github.com/orgs/FOSSRIT/teams/foss-curriculum-students)

This team includes students and alums who participated in any of the FOSS courses taught at RIT.
There are two sub-teams, one for each course taught:

* IGME-582
* IGME-585

Beneath this, there are sub-teams for each semester.
Students of a particular class and semester should be added to a team for a specific semester.


## Organization projects

This section applies to organization project boards, not project boards on specific repos.
While this may change, currently there is only one organization project board: [**FOSS@MAGIC operations**](https://github.com/orgs/FOSSRIT/projects/1?fullscreen=true).
This project board is used by FOSS@MAGIC staff for weekly task planning and time management:

![Screenshot of the FOSS@MAGIC operations project board in February 2020](/_static/infra/github-projects-board-overview.png)

Note the duration of a sprint is flexible.
In early 2020, sprints typically lasted for two week intervals.
But use best judgment for how long a "sprint" should be, based on current number of staff and volunteers working on issues.

### Agile structure

Six columns exist on the project board:

* Backlog
* Waiting on external
* Next sprint
* Current sprint
* In progress
* Done

#### Backlog

Backlog is used to track things FOSS@MAGIC staff or community volunteers need to do, but there is not enough time right now to do them.
Eventually, issues from the backlog are selected for inclusion in upcoming sprints.
The backlog can become long over time, so it is important to prioritize the most important issues when planning future sprints.

#### Waiting on external

Waiting on external means an issue is blocked on something outside of the control of FOSS@MAGIC staff or volunteers.
Typically, this is when an outside collaborator or external stakeholder is needed to move a discussion or planning forward.
Since it is unclear when an issue will become "unblocked", this column is used to track things we might need to follow up on, but cannot push forward on our own.

#### Next sprint

The next sprint column is used to triage specific issues to be worked on in the next sprint.
Using this column is helpful to think ahead and prioritize what issues to work on from the backlog.
It leaves room for retrospection on what the most important future work is.

#### Current sprint

The current sprint column is used for issues that will be worked on in the current sprint, but work has not yet started.
By the end of a sprint, everything in this column should either be moved to _In progress_ or _Done_.
A good health metric to judge your project management skills on is how often this column is actually cleared.
If you put a lot of issues into the current sprint, but most of them are unfinished or incomplete by the end of the sprint, this is a sign you are being too ambitious in your planning.

Try to keep this column as realistic as possible for what can be completed in one sprint.

#### In progress

Any issues or pull requests that are actively in progress or open belong here.
New pull requests generally appear here automatically, but issues need to be moved over.
If there are several people working on FOSS@MAGIC tasks, this column is helpful to indicate to your team that work has started on an issue.
This avoids stepping on people's toes later if someone decides to take on a new issue from the _Current sprint_ column!

#### Done

When an issue is closed or a pull request is merged, it is automatically moved to this column.
At the end of a sprint, all cards under this column should be archived and the column should be emptied.
Nothing stays on the project board forever!

#### Note on column automation

Each column is configured with automation rules that move the issues across columns.
New issues generally appear in _Backlog_.
Closed issues and merged pull requests will go to _Done_.
Generally, everything between those two columns is managed manually.
Do your best to keep this up-to-date to get the most out of the project board!

### Linked repositories

Generally, only these repositories add issues to this project board:

* brand
* foss-profiles
* fossrit.github.io
* infrastructure
* tasks

The issues in this set of repositories typically involve FOSS@MAGIC staff (including student employees).
Therefore, they are linked to the project board.


## Settings

This section documents the [Settings](https://github.com/organizations/FOSSRIT/settings/) page of the GitHub organization.
To reduce documentation overhead, the only documented parts from settings are things that are expected to change or important logistic information.
Generally, the GitHub organization settings are changed rarely and infrequently.

### Billing

No billing information is added to the FOSSRIT GitHub organization.
However, in 2018, we were eligible for GitHub for Education's lifetime coupon for unlimited private repositories.
Currently, we receive a "100% off forever" coupon from GitHub:

![GitHub Settings > Billing: 100% off forever coupon applied](/_static/infra/github-settings-billing.png)

### Verified domains

Currently the only verified domain for the FOSSRIT GitHub organization is `fossrit.community`.
DNS settings are managed in our Namecheap account (see [Namecheap](namecheap)).

### Third-party access

Keep third-party access limited as it applies to our private repositories.
Currently the only private data is development resources around the FOSS Minor, but this could always change.
Granting third-party access to applications grants access to our private repos, so try to keep access under control:

![GitHub Settings > Third-party access: existing access policy, taken February 2020](/_static/infra/github-settings-third-party-access.png)

### Repository labels

In 2020, [@jwflory](https://github.com/jwflory) defined a custom set of repository labels based on his experience managing FOSSRIT GitHub repositories and also other open source communities.
These labels are included on any new GitHub repository created under FOSSRIT.
Generally, every label here was created because a need was identified.
It is always possible to add new labels, but generally avoid removing labels without a clear reason or motivation.
If in doubt, open an issue on [FOSSRIT/tasks](https://github.com/FOSSRIT/tasks)!

![GitHub Settings > Repository labels: 14 existing default labels for new repos](/_static/infra/github-settings-repo-labels.png)

### Teams

Team discussions are intentionally disabled.
They are disabled because they are not easily visible to the wider FOSS community, and we have _many_ teams and sub-teams.
Instead, it is encouraged to use the [Discourse forum](discourse) for community discussions.

![GitHub Settings > Teams: Team discussions are disabled](/_static/infra/github-settings-teams.png)
