## Step 1: Connect to your EC2 instance
```sh
ssh -i your-key.pem ec2-user@your-public-ip
```
## Step 2: Update the system
```sh
sudo yum update -y
```
## Step 3: Download kubectl binary
```sh
curl -LO https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl
```
## Step 4: Make it executable
```sh
chmod +x kubectl
```
## Step 5: Move to system path
```sh
sudo mv kubectl /usr/local/bin/
```
## Step 6: Verify installation
```sh
kubectl version --client
```
