# Assignment: Service Fabric CI/CD Assignment

The assignment is intentionally big and open so you can implement as much as you want to demonstrate your skills. Read the whole assignment first and decide upfront which parts you want to implement and which you want to simply explain. **Don't attempt to complete everything from start to finish as it could result in some steps fully completed and others fully left undone. It is better if you partially cover most parts.**

We would like you to  demonstrate the parts you did finish and present potential solutions and approaches for the parts that you didn't do. Please prepare a 15 minutes presentation, explaining what you did and especially how you would take it further to completion: we want you to not only demonstrate how you implement your solutions, but also how you communicate them. The rest of the time (40-45 minutes) we will talk about the assignment, how you did it and what are other ways of approaching the problem.

We will evaluate your skills in the following areas:
- Understanding of the problem
- Azure knowledge
- Azure DevOps knowledge
- Service Fabric knowledge (if you don't have previous SF knowledge we'll evaluate how quickly you can understand it and produce a working solution)
- CI knowledge
- CD knowledge
- Monitoring/alerting
- Operations

You will need:
In order to complete the assignment, you will need:
* an Azure Subscription. You can get a [free account and some free credit here](https://azure.microsoft.com/en-gb/free/)
* Visual Studio
* Service Fabric SDK

## Fallback Option
If you don't know Service Fabric, you can't get the sample project to work, or you simply believe that you can better demonstrate your knowledge using other code and tools than the ones described in this assignment, feel free to use a different sample application and/or tools, while making sure that your solution correlates with what we are asking in the assignment.

## Case description

To complete the assignment you need a working Service Fabric application. You can use the following one (disclaimer, this is a public demo project not developed by Chama): [Here's the code](https://github.com/Azure-Samples/service-fabric-dotnet-getting-started)

## Part 1: Code set up
Download the code and upload it into a private repository on github owned by you. Invite user **chamareview** with Write permissions to the repository.

_Tips to run the code locally_
* Have Visual Studio and Service Fabric SDK installed
* Open the solution in Visual Studio
* Restore Packages
* Build the solution
* Run the Service Fabric application (F5)
* Navigate to [the web application] (http://localhost:8081/)
* Check that the application is working

## Part 2: Environment set up
In order to run the application in Azure, set up a new Cluster with all the required resources.

_Questions:_
1. How could you automate the creation of all environment resources to allow to easily create new environments for development and testing?
2. What could you parametrize to give the environment creation automation more flexibility?

## Part 3: Continuous Integration
Create a build pipeline (ideally in Azure DevOps) that builds the code from the repository you created with the fork.


Options:
* Create the pipeline in yaml. (Demonstrate Pipelines as Code)
* Trigger the builds automatically after each commit on master and potentially any other branch.
* Run unit tests for every build


_Questions:_
1. What kind of reporting would you generate for this pipeline?
2. What kind of notifications would you generate?
3. What is a good strategy to trigger automatic builds for feature, release and hotfix branches, in your opinion?

## Part 4: Continuous Delivery
Create a release pipeline (ideally in Azure DevOps) that allows to deploy to the Azure environment the buils created in the previous point.

Options:
* Create the release automatically after a build in master is successfully finished
* Deploy the release automatically after the master build

_Questions:_
1. If the company has 4 teams, describe a proposed environment and release pipeline that allows them to test and release to production the software they produce. Note that we don't specify if each team works on a single service or they work on the whole solution, which might impact your proposed set up. Feel free to define a workflow that you thing works correctly.
2. What kind of reporting would you generate for this pipeline?
3. What kind of notifications would you generate?

## Part 5: Production Operations
Trigger an alert whenever CPU exceeds a %.
Configure autoscaling so that when the average CPU exceeds a % the cluster increases its capacity.

_Questions:_
1. What kind of monitoring would you create for a system like this?
2. What kind of alerts would you create?
3. What kind of dashboard would you create?
4. What metrics and strategies would you use to control the system capacity/scaling?

## Part 6: Decomposition/Composition
Assume the code base becomes very big to manage in a single repository. 
Split the code in 2 or more repositories based on the strategy you decide.
Create the required strategies in order to be able to compose the full system again (hint: this could be achieved in many ways, depending on how you splitted the code, for example, some code could be published as nuget packages and other parts could be deployed directly in production). 

## Wrapping up
Prepare few slides for your presentation (pdf, ppt, keynote, google slides link) and send it at least 24 hours before the interview.

Explain:
- Your solutions and decisions
- List the tools and technologies you used
- Why you decided to use X and not Y
- The problems and challenges that you have faced
- What you think that it can be improved and how

