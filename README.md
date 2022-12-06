# cloudflared
cloudflared setup notes


Cloudflared packages

    Debian Buster (stable)
    Debian Bullseye (stable)
    Debian Bookworm (testing)
    Ubuntu Focal (LTS)
    Ubuntu 22.04 LTS (Jammy Jellyfish)
    Amazon Linux
    RHEL Generic
    Centos 7
    Centos 8
    Centos Stream

Please Note:

If you see the following error when running apt-get update:

    E: The repository 'https://pkg.cloudflare.com buster Release' does not have a Release file.

This is due to a recent update we made to our cloudflared repository which now points to pkg.cloudflare.com/cloudflared instead of pkg.cloudflare.com. To resolve, please follow the instructions below based on your Debian release and run apt-get update.

Debian Buster (stable)

```
# Add cloudflare gpg key
sudo mkdir -p --mode=0755 /usr/share/keyrings
curl -fsSL https://pkg.cloudflare.com/cloudflare-main.gpg | sudo tee /usr/share/keyrings/cloudflare-main.gpg >/dev/null

# Add this repo to your apt repositories
echo 'deb [signed-by=/usr/share/keyrings/cloudflare-main.gpg] https://pkg.cloudflare.com/cloudflared buster main' | sudo tee /etc/apt/sources.list.d/cloudflared.list

# install cloudflared
sudo apt-get update && sudo apt-get install cloudflared
```

Debian Bullseye (stable)

```
# Add cloudflare gpg key
sudo mkdir -p --mode=0755 /usr/share/keyrings
curl -fsSL https://pkg.cloudflare.com/cloudflare-main.gpg | sudo tee /usr/share/keyrings/cloudflare-main.gpg >/dev/null

# Add this repo to your apt repositories
echo 'deb [signed-by=/usr/share/keyrings/cloudflare-main.gpg] https://pkg.cloudflare.com/cloudflared bullseye main' | sudo tee /etc/apt/sources.list.d/cloudflared.list

# install cloudflared
sudo apt-get update && sudo apt-get install cloudflared
```

Debian Bookworm (testing)

```
# Add cloudflare gpg key
sudo mkdir -p --mode=0755 /usr/share/keyrings
curl -fsSL https://pkg.cloudflare.com/cloudflare-main.gpg | sudo tee /usr/share/keyrings/cloudflare-main.gpg >/dev/null

# Add this repo to your apt repositories
echo 'deb [signed-by=/usr/share/keyrings/cloudflare-main.gpg] https://pkg.cloudflare.com/cloudflared bookworm main' | sudo tee /etc/apt/sources.list.d/cloudflared.list

# install cloudflared
sudo apt-get update && sudo apt-get install cloudflared
```

Ubuntu 20.04 LTS (Focal Fossa)

```
# Add cloudflare gpg key
sudo mkdir -p --mode=0755 /usr/share/keyrings
curl -fsSL https://pkg.cloudflare.com/cloudflare-main.gpg | sudo tee /usr/share/keyrings/cloudflare-main.gpg >/dev/null

# Add this repo to your apt repositories
echo 'deb [signed-by=/usr/share/keyrings/cloudflare-main.gpg] https://pkg.cloudflare.com/cloudflared focal main' | sudo tee /etc/apt/sources.list.d/cloudflared.list

# install cloudflared
sudo apt-get update && sudo apt-get install cloudflared
```

Ubuntu 22.04 LTS (Jammy Jellyfish)

```
# Add cloudflare gpg key
sudo mkdir -p --mode=0755 /usr/share/keyrings
curl -fsSL https://pkg.cloudflare.com/cloudflare-main.gpg | sudo tee /usr/share/keyrings/cloudflare-main.gpg >/dev/null

# Add this repo to your apt repositories
echo 'deb [signed-by=/usr/share/keyrings/cloudflare-main.gpg] https://pkg.cloudflare.com/cloudflared jammy main' | sudo tee /etc/apt/sources.list.d/cloudflared.list

# install cloudflared
sudo apt-get update && sudo apt-get install cloudflared
```

Amazon Linux

```
# Add cloudflared-ascii.repo to /etc/yum.repos.d/ 
curl -fsSl https://pkg.cloudflare.com/cloudflared-ascii.repo | sudo tee /etc/yum.repos.d/cloudflared-ascii.repo

#update repo
sudo yum update

# install cloudflared
sudo yum install cloudflared
```

RHEL Generic

```
# Add cloudflared.repo to /etc/yum.repos.d/ 
curl -fsSl https://pkg.cloudflare.com/cloudflared-ascii.repo | sudo tee /etc/yum.repos.d/cloudflared.repo

#update repo
sudo yum update

# install cloudflared
sudo yum install cloudflared
```

Centos 7

```
# This requires yum config-manager
sudo yum install yum-utils

# Add cloudflared.repo to config-manager
sudo yum-config-manager --add-repo https://pkg.cloudflare.com/cloudflared-ascii.repo

# install cloudflared
yum install cloudflared
```

Centos 8

```
# This requires dnf config-manager
# Add cloudflared.repo to config-manager
sudo dnf config-manager --add-repo https://pkg.cloudflare.com/cloudflared-ascii.repo

# install cloudflared
sudo dnf install cloudflared
```

Centos Stream

```
# This requires dnf config-manager
# Add cloudflared.repo to config-manager
sudo dnf config-manager --add-repo https://pkg.cloudflare.com/cloudflared-ascii.repo

# install cloudflared
sudo dnf install cloudflared
```

Gokeyless Packages

```
sudo mkdir -p --mode=0755 /usr/share/keyrings
curl -fsSL https://pkg.cloudflare.com/cloudflare-main.gpg | sudo tee /usr/share/keyrings/cloudflare-main.gpg >/dev/null

# Add this repo to your apt repositories
echo 'deb [signed-by=/usr/share/keyrings/cloudflare-main.gpg] https://pkg.cloudflare.com buster main' | sudo tee /etc/apt/sources.list.d/cloudflare.list

# install gokeyless
sudo apt-get update && sudo apt-get install gokeyless
```
