#you must run this command first to get your folder of files onto your EC2 Server:
rsync -avz -e "ssh -i ~/5152025.pem" /mnt/c/Users/admin/Documents/K8s-Supportfiles/code-files+++Efficient+webapp+deployment+using+Docker/code-files/source-code/wedding-main ubuntu@54.83.109.103:/home/ubuntu/

#after that you can run these commands for your Docker install on your Ubuntu server:
sudo apt update && sudo apt upgrade -y

sudo apt install -y ca-certificates curl gnupg lsb-release

sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) \
  signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

sudo docker --version

#allows you to run Docker without sudo
sudo usermod -aG docker $USER

#running a test container
docker run hello-world
