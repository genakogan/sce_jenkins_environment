## Setup

### Jenkins is deployed and managed by one of the course staff.

### Steps we need to do:
1.	Get a server department engineer to deploy jenkins (IP address, user, password)
2.	Connect to the server remotely (putty)
3.	Create a new folder for our deployment in the server and enter it.
4.	Clone the github repository
5.	In the casc_config/staff_users.yaml change and add the staff users don't change the password it is encrypted to be SceAdmin99!
6.	In the casc_config/staff_users.yaml change the user name and to real user and there there id.
7.	In the casc_config/student_group_mapping.yaml divide students to their groups, change to real student names.
8.	Run the docker image in the same way mentioned in the README.md
a.	docker run -d --name scejenkins2021 -v /home/sce-admin/pm_course_bs_2021/sce_ci_environment/sce_jenkins_home:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock -p 80:8080 -p 50000:50000 shurikg/sce_jenkins:2.190.3
9.	Run the next command (copy the new student_users.yaml into container )
a.	sudo docker cp student_users.yaml containerID:/usr/share/jenkins/ref
10.	Run the next command (copy the new staff_users.yaml into container )
a.	sudo docker cp staff_users.yaml containerID:/usr/share/jenkins/ref
11.	Run the next command (copy the new student_group_mapping.yaml into container )
a.	sudo docker cp student_group_mapping.yaml containerID:/usr/share/jenkins/ref
