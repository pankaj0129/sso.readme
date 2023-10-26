# Assignment 4:
 
Topics Covered:  (User Authentication, User Authorization)
[Part-1]
Their is an organization which has 3 teams
            - Developer
            - Devops
            - Testing
First you need to create 9 dummy jenkins jobs distributed into 3 views. Each job will print their jobname, build number.

For Developer create 3 dummy jobs.In developer view
                job1:- dev-1
                job2:- dev-2
                job3:- dev-3
For Testing create 3 dummy jobs. In testing view
                job1:- test-1
                job2:- test-2
                job3:- test-3
For Devops create 3 dummy jobs. In devops view
                job1:- devops-1
                job2:- devops-2
                job3:- devops-3
Users in each team: 
Developer: ( They can see only dev jobs, can build it, see workspace and configure it )
                - developer-1 
                - developer-2 
Testing: ( They can see all test jobs ,can build it, see workspace and can configure it, | They can also view dev jobs )
                - testing-1 
                - testing-2 
Devops:  ( They can see all devops jobs ,can build it, see workspace and can configure it, | They can also view dev and test jobs  )
                - devops-1 
                - devops-2
admin
                -  admin-1 ( It will have full access )
        
See what Authorization strategy suits it and implement it.
Also go through all authorization strategy
        Legacy mode
        Project Based
        Matrix Based
        Role-Based
        
[Part 2]
        Enable SSO with Goggle"

Steps to achive the goal:-

[Part-1]
Step-1:
Create 3 roles & view in the name:
- Developer
- Devops
- Testing


## Global read permission for roles

![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/Manage_roles_overall_read_permission.GIF?raw=true)

## Item role permission for roles

![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/Item_roles_view.GIF?raw=true)

## Developer Roles view

![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/Developer-view.GIF?raw=true)

## Devops Roles view
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/Devops-view.GIF?raw=true)

## Testing Roles view
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/Testing-view.GIF?raw=true)




Step-2:
Create the respective jobs for the view:

## Devops job console output
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/Job_devops-2.GIF?raw=true)

## Developer job console output
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/job_dev-1.GIF?raw=true)

## Testing job console output
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/Job_test-3.GIF?raw=true)

Step-3:
Create the user for respective group/roles

## Global role view for the users
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/Assign_roles_global_roles.GIF?raw=true)

## Assign role for the users
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/Assign_roles_item_roles.GIF?raw=true)

## developer-1 view from dashboard
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/usersnap/developer-1_dashboard_1.1.GIF?raw=true)

## developer-1 view for console output
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/usersnap/developer-1_job_build_1.2.GIF?raw=true)

## devops-1 view from dashboard
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/usersnap/devops-1_dashboard_1.1.GIF?raw=true)

## devops-1 view from Developer view
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/usersnap/devops-1_devops_view_1.3.GIF?raw=true)

## devops-1 view from console output
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/usersnap/devops-1_job_build_1.2.GIF?raw=true)

## devops-1 view from Testing view
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/usersnap/devops-1_test_view_1.4.GIF?raw=true)

## testing-1 view from dashboard
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/usersnap/test-1_dashborad_1.1.GIF?raw=true)

## testing-1 view from Developer view
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/usersnap/test-1_dev_view_job_1.3.GIF?raw=true)

## testing-1 view for console job output
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/usersnap/test-1_job_build_1.2.GIF?raw=true)


[Part-2]
Step-4:
Here we are using the Role-Based method to achive the condition.

## Jenkins setup from security session for sso
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/sso_jenkins_security.GIF?raw=true)

Step-5:
We need to go to Google Developer console for setting up the SSO. Add details in the credentials sessions, once you get the ID & password, need to provide it in the jenkins credentials session.

## Google Developer console setup
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/google_developer_console.GIF?raw=true)

## Install the Google Plugin for SSO in jenkins
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/google_plugin.GIF?raw=true)

## Prompting for the sign in option using the google credentials
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/image%20(2).png?raw=true)

 
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/image%20(3).png?raw=true)
 

![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/image%20(4).png?raw=true)

## Login using SSO 
![App Screenshot](https://github.com/OT-MyGurukulam/Jenkins_batch_22/blob/raldin_jenkins/raldin/assignment4/A4Screenshots/image%20(5).png?raw=true)



