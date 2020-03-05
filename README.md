
# Rob's guide to bootstrapping a technology project

## Contents
1. Communications
    - Setup standup
    - Collaboration hub (Slack, Teams, RocketChat, etc)
    - Backlog
    - Information Radiator

1. Architecture
    - Define project name
    - Agree tech
    - Give _everything_ a clear concise name
    - Create Diagram using a tool that’s viewable by everyone (preferably print it out and place near the information radiator)
    - Agree Environments 
    - Agree naming standards
    - Agree standard Logging Levels

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

1. Monitoring
    - AWS Costs
    - Endpoints
    - node_exporter
