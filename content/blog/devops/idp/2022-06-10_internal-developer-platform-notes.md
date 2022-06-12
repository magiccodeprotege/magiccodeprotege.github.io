```
title = "Internal Developer Platform notes"
date = "2022-06-07"
author = "scotbran"
```
# Internal Developer Platform (IDP)
> A modern way run engineering teams

An IDP is a layer on top of the tech tooling an engineering team has in place already. It helps Ops teams structure their 
setup and enable developer self-service

IDPs are configured by the Ops teams and used by developers. Ops teams specify what resources stat up with what environment
or at what request. They also set baseline templates for application configurations and govern permissions. This helps them
automate recurring tasks such as spinning up environments and resources and makes their setup eaiser to maintain by enforcing
standards. devs teams gain automany by changing configurations, deploying, spinning up fully provisioned environments, and rollback.

## The 5 Core Components of an IDP
- Application Configuration Management: Manage application configs in a scalable and reliable way
- Infrastructure Orchestration: Integrate with your existing and future infrastructure
- Environment Management: Enable developers to create new environments whenever needed
- Deployment Management: Implement a Continous Delivery or even Continous Deployment approach
- Role-Based Access Control: Manage who can do what in a scalable way

## How are IDPs are used by Ops, DevOps, or Platform teams
- Ops team run and configured the IDP. Teams running IDPs concentrate on infrastructure, service level agreements and workflow optimization and configure the IDP to abstract way any recurring or repetitive tasks, such as spinning up resources or enviroments for developers.
- Ops teams set the baseline templates for configuration and avoids unstrcutured scripting to prevent excessive maintenance time. 
- A modern developer needs three pans of glass; the IDE to code in, git to merge and an IDP to ship


