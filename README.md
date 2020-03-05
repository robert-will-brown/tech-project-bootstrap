
# Rob's Guide to Bootstrapping Technology Projects

## Contents
1. Rules
    - Automate everything
    - 2am test
    - Everyone to know the next milestone
    - Low mental excercise
    - Face-to-face beets all other communications methods
    - Low friction gets stuff done

1. Establish Communications
    - Setup the standup
    - Define collaboration hub
    - Backlog
    - Information radiator

1. Architecture
    - Define project name
    - Agree technology stack
    - Give _everything_ clear, concise names
    - Create & share diagram(s)
    - Agree environments
    - Agree naming standards
    - Agree standard logging levels

1. Environments
    - Agree Environments (Names, purpose, ephemeral nature etc)
    - Add to diagrams

1. Deployments
    - Agree deployment approach of each component

1. Source Code Repositories
    - Map every component to a repository
    - Git hooks examples setup in all repos
    - README.md’s written explaining the project
    - Project icon added
    - Integrate with Slack
    - Setup Keys

1. Jenkins (Continuous Integration / Deployment)
    - Connect to all repos above

1. Monitoring & Alerting
    - AWS Costs
    - Endpoints
    - Hosts

## Establish Communications
### Setup the standup
The standup is *the* most important communication tool available to projects.  Zero cost, little effort, and suddenly everyone is working on the same page.  Setup the meeting as the first task to ensure immediate communications and set the tone for the project, even if there is little to initially discuss.  Stick to 15 mins, aggressively offline inappropriate conversation, and always start on time.  If there is one time to crack the whip and enforce discipline in a project its in the timely attendance to the standup.  Make it an LME (low mental exercise) by setting a consistent time and place for the meeting that doesn’t change.  If some people have to dial in prefer that video conferencing is used (seeing their faces is crucial).

And please, its called standup for a reason, standup! even if you're on the end of video conference. It will be over quicker.

The format or agenda of a standup can vary, I’m not a fan of going through the backlog in the meeting but having it on the Information radiator to hand is a definite bonus.

### Define collaboration hub
A collaboration hub is the tool used to do the majority of communicating outside of face to face.  Typically this is slack, ms teams, rocketchat etc.  Tools that people can't setup their own rooms in, or tools that don't allow easy copy and pasting of code, images, etc should be avoided like the plague.  Once development starts at pace, the simple ability to paste a screenshot to the entire team easily is a simple but massive boon to productivity.

Ensure that people know how to write code snippets in the tool.  Dropping code in that the tool thinks is text makes reading it and copying it back out frought with errors as hidden control characters break config files in non-obvious ways.

Choosing a tool that isn’t easy to integrate with is a mistake.  The benefit of these tools outside of human -> human interaction and into computer -> team interaction shouldn’t be underestimated.  Easy integrations where plenty of people have done it before are key to this, low friction gets stuff done.

### Backlog
The backlog will store all of the tasks.  It should be integrated where necessary with your collaboration hub, and everyone should be able to access and add backlog issues.

My preference is to view the tasks in a Kanaban style tool which enables the easy tracking of tasks.  For some reason having a tool which lets you drag and drop your tasks between various states seems to empower the team to update the status with less badgering than updating an individual ticket without the ability to conceptualise where it sits in the greater chain of events.  

Having this available for the whole team to see at the Information radiator is a plus.

Allowing users to add tasks in the simplest possible way, with as fewer key strokes as possible and without having to add all of the data makes it more likely that all required tasks will be captured.  This comes at the expense of increased effort for the team lead to ensure that these tasks get fleshed out in a timely fashion, however the trade off is worth it.  An example is a security group that is opened up temporarily to ensure it isn’t the cause of an issue.  If the tasks to secure the security group isn’t captured immediately then it could be forgotten and captured at best in the next security scan, and at worst when a hacker dumps your user database on the internet.  A reminder that can be created in a couple of clicks and can then be picked up by anyone and fixed when appropriate.  If the tools is complex and slow to use the temptation is to try to remember to close down that security group, which won’t _allways_ work.

### Information radiator
This, this, this.

If there’s one thing (standup aside) that can focus a group it’s the information radiator.  There’s a reason for dashboards in cars, instrument panels in planes and the bridges on the starship enterprise.  Everyone can get together and see the same dashboard.

Information radiators should be visible to everyone in the team when they are together (with the minimum knock straining), and also available over http for those that are remote working and for checking on your mobile whilst toasting a successful sprint down the pub.

SUGGESTIONS FOR WHAT TO PUT ON IT
SUGGEST THAT 

## Architecture
### Define project name
So this is where the _real_ work begins
### Agree technology stack
### Give _everything_ clear, concise names
### Create & share diagram(s)
using a tool that’s viewable by everyone (preferably print it out and place near the information radiator)
### Agree environments
### Agree naming standards
### Agree standard logging levels

## Environments
### Agree Environments (Names, purpose, ephemeral nature etc)
### Add to diagrams

## Deployments
### Agree deployment approach of each component

## Source Code Repositories
### Map every component to a repository
### Git hooks examples setup in all repos
### README.md’s written explaining the project
### Project icon added
### Integrate with Slack
### Setup Keys

## Jenkins (Continuous Integration / Deployment)
### Connect to all repos above

## Monitoring & Alerting
### AWS Costs
### Endpoints
### Hosts

 
