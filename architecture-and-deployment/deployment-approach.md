# Deployment Approach

With every identified component of the architecture time should now be taken to understand how to deploy this with no human effort. This includes the infrastructure code, application code and configuration.

This process can be complex if there are enough components with complex infrastructure interdependencies. And care should be taken to keep in mind the full chain from source code repository, potential branches of code, through to the specific environment.

The end goal is to get a deployment working “hands-off”. It’s acceptable to get to this place with each deployment more automated than the last, but if this is the case ensure that the manual steps are well documented with copy-and-paste commands documented well.

In an ideal world everyone from the team should be able to deploy the latest code to production.

Repeat to boredom. Ensure that a deployments become a mundane task not a highly stressed multi person event, that ends in everyone having to work till midnight.  


