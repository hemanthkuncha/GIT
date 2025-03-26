for configuring software path , the path should have "bin" folder that script of software/tool.

jenkins by default creates its own user "jenkins" with no-password

we cant login to it / if we assign password i dont know what happens

##Assigning PATH to EC2 Instance only:

this can be system wide or user wide, we can opt my choosing the ~.bash_profile, ~.profile, ~.bashrc, ~.bash_logout

nano ~/.bash_profile 

source ~/.bash_profile

--------------------------------------------------------------------------------------------------------------------

##Asigning PATH to Jenkins Manually

add PATH in Jenkins using web access > http://<PUBLIC IP >:8080  >> NODE CONFIGURATION >>> ENV VARIABLE >>>> Name (PATH+"path we assigned in .bash_profile ") & Value "location to home/bin that we assigned .bash_profile "
