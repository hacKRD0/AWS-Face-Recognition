# AWS-Face-Recognition

## Steps to create the App Tier AMI

### 1. Create base ubuntu ec2 instance from console

### 2. Connect remotely to the instance

```console
ssh -i C:\Users\datta\.aws\cloud_project1.pem ubuntu@ec2-18-209-1-148.compute-1.amazonaws.com
```

### 3. Copy the \model folder https://github.com/visa-lab/CSE546-Cloud-Computing/tree/main/model to the instance

```console
scp -i ".\.aws\my_key_pair.pem" -r "D:\ASU\CSE 546 Cloud Computing\Project\CSE546-Cloud-Computing-main\model" ubuntu@ec2-18-209-1-148.compute-1.amazonaws.com:/home/ubuntu/
```

### 4. Update and upgrade source list

```console
sudo apt-get update

sudo-apt-get upgrade
```

### 5. Install python3 and python3-pip if not already installed

```console
sudo apt install python3

sudo apt install python3-pip3
```

### 6. Install the venv package and create a virtual environment in the instance

```console
sudo apt install python3.10-venv

python3 -m venv myenv
```

### 7. Activate virtual environment and download required packages for the model to run

```console
source myenv/bin/activate

pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu
```
