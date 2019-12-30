# Deploy passive relay on Google Compute Engine using CentOS 8 and Docker Swarm

1. Create a GCE VM with at least one vCPU, 4 GiB of RAM and 16 GiB of disk space
2. Add EPEL and Docker CE repositories:
```
sudo dnf install -y epel-release
sudo dnf config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo
```
3. Install Docker
```
sudo dnf install docker-ce --nobest -y
```
4. Start and enable Docker
```
sudo systemctl start docker
sudo systemctl enable docker
```

5. Add your user to Docker group
```
sudo usermod -aG docker $USER
```

6. Initialize single-node Docker Swarm cluster
```
docker swarm init
```
