# jira-github
Have you faced these issues before?
1. Started working on an issue, but failed to update the status to in-progress
2. Created the PR, but failed to update the status to build-pending
3. PR is merged by bade bhaiya, but the status is still build-pending
4. Last, but the most painful one, moved the story to Ready-for-QA, but forgot to assign it to a QA :P

Well, well, well I have solved all of these by writing a python script in AWS Lambda which responds to github webhooks and talks to jira using their python sdk. I created this project to refresh and learn some of the latest backend technologies. If someone else is also interested, please contribute :) <br />
(PS: You will not get any jira points for this :P)

## So, here is how to use it.

### 1. Starting a new task/sub-task/bug
Whenever a dev is starting with a task, please follow the format of naming a branch in this way "feature/<issue-id>". For example, if I am working on MB-6519, then I will create a branch with name - "feature/MP-6519" and push it to origin as soon as you start the work. This will movee the task to **in-progress**
 
### 2. When you are done with a task/sub-task/bug
Once you are done with the task, create the PR with development branch. with following things in the description.
```known_issues``` and ```impact_area```. For example a description will look like this <br/>

@subham.tyagi please review this PR. bla bla bla....... ```known_issues="The app crashes as soon as it is opened :-/"``` bla bla bla bla...... ```impact_area="This little code affects the entire app."```. Please make sure you use the exact keywords ```impact_area``` and ```known_issues``` followed by ```=``` and ```"``` - double qoutes. There should be no space between the equal to sign and double qoutes. You may also update the description after creating the PR

### 3. When everything is done
Once the PR is approved and merged with the development, the issue with automatically be moved to "Ready for QA" and it's gonna be assigned to Vipul bhai


The code is live on aws-lambda. Once bade bhaiyya will add the lambda's url to our github's webhook everything will work like a charm. Will update you once it is done. I will be updating the entire code in this repository once I start reading credentials from properties file and update dependencies using virtual env. 


  



