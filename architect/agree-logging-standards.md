# Logging

Agree amongst the developers what the standard logging levels they will use, and what they mean.

Projects that have many components and many teams working on them will have variation in the importance of logging, what to log, and what log levels to use for what events.

For the sanity of the support team, and to make alerting and automation easier every team should be implement logging consistently. It matters less on the detail and more on the general agreement that the levels will be followed.

I worked on a service that had many micro service components. These were all implemented at different times by different teams. Not a single micro service implemented them the same. One service had several thousand ERROR and WARNINGS an hour and was running perfectly happily, another didn’t log a single thing and was failing consistently.

If you are a developer always log an attempt to try something before you log the success or failure of that event. For example some log files I’ve seen log an ERROR when a push to an S3 bucket failed. This wasn’t that useful though as it didn’t log what file it was trying to copy, what bucket and what key it was trying to copy to. That additional information would have been perfect as an INFO log line just before the ERROR of it failing.

This absence of detail necessitated a call to the developer late at night to get them to look through the source code. You don’t want that.

Finally Log levels should be exposed as a parameter for containers or applications. This allows a bug fix or dev environment to be run with debug logging and the environments to have standard levels of logging that doesn’t swamp the monitoring platform. The debug levels should be set automatically for each environment by the deployment pipeline to ensure the correct level for the correct environment.  


