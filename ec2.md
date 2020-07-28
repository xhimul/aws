## VPC Part:
- VPC Create
- Subnet Create
- Internet Gateway > Create internet gateway > Attach to a VPC
- Router Tables > Routes > Edit Routes > Add Route > Destination: 0.0.0.0/0, Target: igw


## EC2 Part:
#### Step 1: Choose AMI
- Launch Instance > Choose Image >

#### Step 2: Choose Instance Type
- Choose Instance Type

#### Step 3: Configure Instance
- Configure Instance Details:
- Auto-assign Public IP: Disable
- Enable termination protection

#### Step 4: Add Storage
- [X] Delete on Termination

#### Step 5: Add Tags

#### Step 6: Configure Security Group

#### Step 7: Review
- Select an existing key pair or create a new key pair > Download Key Pair
- Click on Launch Instace
- EC2 > Network & Security >Elastic IP addresses > Allocate Elastic IP address > Allocated
- Associate this Elastic IP address > Instance

## Connect to your instance:
- using PuTTY > Convert your private key using PuTTYgen


## Locating the public key on an instance


## Adding or replacing a key pair for your instance


## Create new user with sudo privilege
- `adduser laravel`
- Enter password and other information
- `usermod -aG sudo laravel`

## Enable Password from Server
- Find and set `PasswordAuthentication yes`
- Reload the SSH service `sudo systemctl reload sshd`

## Add swap memory
* https://www.digitalocean.com/community/tutorials/how-to-add-swap-space-on-ubuntu-16-04
