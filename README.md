java c
COSC2759 Assignment 2 Specifications
Scenario
You have been assigned the following “story” on Jira:
AS A developer at Alpine Inc,
I WANT an automated deployment process for our Foo app, including infrastructure,
SO THAT we can avoid human errors during the deployment process.
Acceptance criteria:
GIVEN credentials for an AWS environment, and a docker image already built and hosted in an image registry,
WHEN we run the deployment script. in the repo (or, ideally, when a GitHub Actions workflow runs),
THEN we get the infrastructure we need, with the application running on it.
(For this “user story” format, see https://medium.com/@cash.lebrun/the-right-way-to-write-a-user- story-9626011c1b57)
So far, Alpine Inc’s production infrastructure and application deployments are managed manually which is prone to human error. They would like you to have a look at how to automate the infrastructure and application deployment.
The Foo app is a node.js web app with a PostgreSQL database backend. The dev team has built the app’s docker image and hosted it at mattcul/assignment2app (note: this is a docker pull URL, not a web address). They would like you to deploy this application to EC2. The current deployment process    is described in how-to-deploy.txt in the starter repo. When running correctly, the UI of the Foo app looks like this:

Ideally, they would like to achieve greater resiliency and automation, but as a minimum they need an automated process to get the app container and its database running on an EC2 instance. More details can be found in the ‘Deliverable’ section below.
The Approach
Alpine  Inc’s CTO  (Chief Technology Officer)  has  prescribed the following tools for  use  in this project:
•    GitHub (GitHub Org)
• GitHub Actions – used for creating the pipelines
• Terraform.
•    Ansible
•    AWS
• Docker
You may use additional tools, libraries, etc as long as their inclusion is explained and justified in your README.md.
Access GitHub Org
1.    Log in to GitHub, navigate to  ‘Your organizations’ and accept invite (should already be accepted from last
assignment). COSC2759 Sem 2, 2024 organisation (github.com)
2.    Create new repository, naming should be student_id-assignment-2
a.    If you are in pairs, please name student_id1-student_id2-assignment-2
b.    NOTE: you do NOT need to have same partners, you can change/ try to attempt this individually/ ask for a new partner
3.    Upload the zipped file found under the assignments section in canvas – happy coding!
a.    Download zip file
b.    Unzip to where you’d like to store code
c.    Follow steps o代 写COSC2759 Assignment 2 SpecificationsSQL
代做程序编程语言n GitHub to upload file
Deliverables
You are given a copy of the Foo app repo. Alpine Inc expects you to update this repo with the scripts and other files required for your solution. Whatever you put in your repo should be
explained by your README.md.Note that the `how-to-deploy.txt` file might not contain all the details you need. You may need to fill in some gaps using your judgment. Please use your README.md file to explain and justify your decisions.
Note: see the assignment rubric for additional details; the rubric is what your marks will be based on.
Section A
1.   In README.md, describe and justify your solution, including appropriate use of diagrams
(e.g. process diagram and infrastructure architecture diagram). (20 marks)
a.   Note: As you proceed through sections A-D, you should update your README file to
cover your whole solution, not just your solution for section A.
2.   Use Terraform. to deploy the required infrastructure e.g. EC2 instance(s). (10 marks)
3.   Use Ansible to configure the EC2 instance(s) to run the app and database containers. (10 marks)
4.   Write a shell script. to deploy the infrastructure and run the application on it. (10 marks)
Section B
5.   To improve the resiliency of the application, deploy the app container on two identical EC2
instances behind a load balancer, with the database running on a separate EC2 instance. (10 marks)
Section C
6.   In your Terraform. configuration, use an S3 bucket remote backend for state. (10 marks)
a.   Note: You can manually create the state bucket or you can use the Terraform.
configuration in `misc/state-bucket-infra.tf` (separate from your main Terraform. configuration).
b.   Note #2: Don’t get the Terraform. configurations mixed up. You can’t deploy the
state bucket with the configuration that is using the state bucket. If this last point is too confusing, just manually create the state bucket and ignore `state-bucket-infra.tf`.
Section D
Note: If you attempt this part of this assignment, also include a standalone deployment script. as per “Section A” . (The CTO wants to “avoid vendor lock-in”.)
7.   Create a GitHub Actions workflow which deploys the infrastructure and runs the application on it. (10 marks)
8.   Trigger GitHub Actions workflow run whenever the `main` branch is modified, and also able
to be triggered via the GitHub Actions REST API. (10 marks)
9.   Ensure that if the infrastructure is already deployed in the environment, then re-running
the GitHub Actions workflow results in no operations being performed (10 marks)







         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
