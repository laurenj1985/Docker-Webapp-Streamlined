# Docker-Webapp-Streamlined
Using AWS and Docker to put a small wedding application online.

This project essentially has 3 main steps.
1. Creating the server, pem key, and modifying the security group for the instance.
2. Syncing/moving the application files to the server/EC2.
3. Installing Docker on EC2, creating the Docker image, and Docker container within the EC2.

Top sticking points/issues with the project:
1. Making sure that your pem key has the correct permissions (chmod 400).

If you are using a PC, VS Code, GitBash, or sometimes Ubuntu won't allow you to make direct changes to the permissions of the pem file directly. Even with "sudo". I had to use Ubuntu and then move my pem file from the Downloads folder to the Ubuntu Home Directory first. Only then, could I modify the file's permissions and log into the EC2.

2. Ensuring that the path to your files is correct before running scp or rync commands.

It never hurts to double check. One character being wrong can throw everthing off.

3. Double check your Security Groups.

You can complete all the steps and commands to create your Docker image and run your Docker container and the application still will not load because you did not correctly configure the rules in your Security Group.
