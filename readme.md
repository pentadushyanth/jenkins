## partition of disk 

lsblk
sudo growpart /dev/nvme0n1 4
sudo lvextend -L +10G /dev/mapper/RootVG-varVol
sudo lvextend -L +10G /dev/mapper/RootVG-rootVol
sudo lvextend -l +100%FREE /dev/mapper/RootVG-homeVol

sudo xfs_growfs /
sudo xfs_growfs /var
sudo xfs_growfs /home


## jenkins installation
sudo curl -o /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/rpm-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
# add required dependencies
sudo yum install fontconfig java-21-openjdk -y
sudo yum install jenkins -y
sudo systemctl daemon-reload
sudo systemctl start jenkins
sudo systemctl enable jenkins

# plugins used
stageview