
# Rob's Tactical Guide to Bootstrapping Technology Projects

## Contents
1. Rules
    - Automate everything
    - 2am test
    - Milestone Visibility
    - Low mental excercise
    - Face-to-face
    - Low friction gets stuff done
    - Repeat to boredom (clearing your mask)
    - No hero’s

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
    - Agree Environments (Names, purpose, ephemeral nature etc)
    - Add to diagrams

1. Deployments
    - Branching Strategy
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

If there’s one thing (standup aside) that can focus a group it’s the information radiator.  There’s a reason for dashboards in cars, instrument panels in planes and the bridge of the starship enterprise.  Everyone can get together when somethings going wrong and see the same set of information. It will improve the chances of making good decisions to fix the problem.

Information radiators should be visible to everyone in the team when they are together (with the minimum knock straining), and also available over http for those that are remote working and for checking on your mobile whilst toasting a successful sprint down the pub.

Information radiators are for a mix of information.  Project and technical.
SUGGESTIONS FOR WHAT TO PUT ON IT
SUGGEST THAT 

## Architecture
### Define project name
I’ve been involved in a few projects that didn’t have a name.  Or the name slightly different depending on who was asked in the project team.  This is a recipe for confusion and extra work straight off.  Without a consistent project name automating even the most basic task will be a frustrating and unreliable endeavour.  The project name will be used almost immediately in the project lifecycle to name cloud environments, prepend to server names, used as database names, provide access in ldap/ad, used to tag resources, source code repositories, folder structures, metric names, storage buckets, prepend to meeting appointments and subject lines in emails and filenames for the project plan to name just a few.

If there isn’t an agreed internal name for the project a great way to move on quickly is to assign it a codename.  Codenames have the benefit that it can be chosen by the team without any interaction with management or marketing.  The team picking the name also gives a sense of ownership of the project to them.

The codename can live for the entire lifecycle of the project and makes it easy for the service to be rebranded if the business requires without it causing a legacy of mismatched names at the technical level.  And if the requirement should ever come to _have_ to change the name, searching and replacing a single codename will prove much easier.

### Agree technology stack
On a large project the idea of being able to define the full tech stack up front is optimistic.  But effort should be given at the point to white board up the entire end to end solution and drill into each component refining the technology to be used.

It’s not uncommon for certain components to be add or changed, as the project matures and you shouldn’t be concerned with that happening.  The effort at this time is to understand your teams abilities and skill levels vs the technology you hope to use.  Solutions Architects, myself included, will often gravitate towards the latest technology released only a few months before.  This is generally positive, but care should be taken to ensure that the operations and development teams can support and effectively work with the technology proposed.

### Agree Environments (Names, purpose, ephemeral nature etc)
This discussion is often missed early on.  Again this doesn’t need to be 100% correct at this point, but everyone knowing that you intend to have your developers develop locally on laptops and then push straight up to a production environment, or if you are going to have ephemeral dev, stage, UAT and production environments with automated deployments of infrastructure triggered by code changes is an important difference!

Understanding your options here and choosing a path now, means that your branching strategy will be easier to define.
  
### Give _everything_ clear, concise names
Once the outline of the high level architect and associated technologies has been firmed up, and it’s known what environments you are going to choose, you should give _everything_ a name.

_Everything_.

Automation depends on this, sanity of the team depends on this.

Prepending the project/codename and environment (now they have been given) is vital as you will probably have several instances of these systems deployed at any one time.  Telling the difference clearly between them (2am test) could mean the difference between deleting the dev environment and deleting production (in reality safeguards should be in place but you get my point).

CodeName-Environment-Resource.

### Create & share diagram(s)
At a minimum the High-Level architecture and Environments should be captured in a diagraming tool at this point.  It’s not okay to continue with memory and whiteboard scribbles as its surprising how quickly everyones idea of the environment will deviate from this point in.

Choose a tool that’s viewable by everyone.  If you are using Visio or similar that outputs files, consider committing those files to a source code repository.  This has the advantage over a shared file of being able to be “pipelined” so the entire team can be notified of an update to the diagrams.

Extra credit if your pipeline can generate a PDF from the diagrams and push that to your collaboration hub.  Obvious benefits to this is that it’s highly visible to _everyone_ in the team with no specialised tools to hand.

An updated diagram should be kept on or near the information radiator.  Always ensure that it is up to date.  Discussions that benefit from an overview of the platform can simply walk up to the information radiator and use the diagrams to ensure accurate understanding.  This only works if people know it’s up to date.  Low friction is key here: if your documents are kept in a source code repository then a pipeline that can check them out on change and send them to a printer situated near to the information repository makes it effortless to just pick it off the printer and blu tac it in place.

### Agree logging standards
Agree amongst the developers what the standard logging levels they will use, and what they mean.

Projects that have many components and many teams working on them will have variation in the importance of logging, what to log, and what log levels to use for what events.

For the sanity of the support team, and to make alerting and automation easier every team should be implement logging consistently. It matters less on the detail and more on the general agreement that the levels will be followed.

I worked on a service that had many micro service components.  These were all implemented at different times by different teams.  Not a single micro service implemented them the same.  One service had several thousand ERROR and WARNINGS an hour and was running perfectly happily, another didn’t log a single thing and was failing consistently.

If you are a developer always log an attempt to try something before you log the success or failure of that event.  For example some log files I’ve seen log an ERROR when a push to an S3 bucket failed.  This wasn’t _that_ useful though as it didn’t log what file it was trying to copy, what bucket and what key it was trying to copy to.  That additional information would have been perfect as an INFO log line just before the ERROR of it failing.

This absence of detail necessitated a call to the developer late at night to get them to look through the source code.  You don’t want that.

Finally Log levels should be exposed as a parameter for containers or applications.  This allows a bug fix or dev environment to be run with debug logging and the environments to have standard levels of logging that doesn’t swamp the monitoring platform.  The debug levels should be set automatically for each environment by the deployment pipeline to ensure the correct level for the correct environment.


## Deployments
### Agree deployment approach of each component
With every identified component of the architecture time should now be taken to understand how to deploy this with no human effort.  This includes the infrastructure code, application code and configuration.

This process can be complex if there are enough components with complex infrastructure interdependencies.  And care should be taken to keep in mind the full chain from source code repository, potential branches of code, through to the specific environment.

The end goal is to get a deployment working “hands-off”.  It’s acceptable to get to this place with each deployment more automated than the last, but if this is the case ensure that the manual steps are well documented with copy-and-paste commands documented well.

In an ideal world everyone from the team should be able to deploy the latest code to production.

Repeat to boredom.  Ensure that a deployments become a mundane task not a highly stressed multi person event, that ends in everyone having to work till midnight.

## Source Code Repositories
### Map every component to a repository
Every deployable piece of code should be stored in it’s own repository that follows the naming convention for that component.


### Git hooks examples setup in all repos
Setup pre-commit git hooks straight away and symlink them to the  root of your repo so people can easily find them and add to them.  Add some pre-commit tests to prevent the crawl which is committing your code and it failing due to a simple syntax error or similar.


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

 
