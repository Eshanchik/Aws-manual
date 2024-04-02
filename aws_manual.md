## Creating an Amazon EC2 Instance

### 1. Select Region and EC2 Service

1. Go to the Amazon Web Services website ([https://aws.amazon.com/](https://aws.amazon.com/)) and sign in to your account.
2. In the top menu, select the region where you want to create the instance.
3. In the navigation pane on the left, choose **Services** > **EC2**.

### 2. Launch New Instance

1. On the **EC2 Dashboard** page, click the **Launch Instance** button.

### 3. Choose Amazon Machine Image (AMI)

1. In the **Application and OS Images (Amazon Machine Image)** section, enter **debian-10-amd64-20240114-1626** and click **Search**.
2. From the search results, select the desired AMI from **Community AMIs**.

### 4. Select Instance Type

1. In the **Instance Type** section, select **t3.small**.

### 5. Create Key Pair

1. In the **Key Pair** section, click **Create new key pair**.
2. Enter a name for the key pair (e.g., **my-key-pair**) and click **Download Key Pair**.
3. Save the key file in a secure location. You will need this file to connect to the instance using SSH.

### 6. Configure Network Settings

1. In the **Network Settings** section, leave all defaults.

### 7. Configure Storage

1. In the **Configure Storage** section, select **gp2** as the disk type.
2. Set the disk size to **80 GB**.

### 8. Review and Launch Instance

1. Review all selected options and click **Review** and **Launch Instance**

### 9. Connecting to the virtual machine

1. Once the instance is started, you can connect to it via SSH using the root username and the key file you created earlier.
2. Command to connect:
   ```shell
    ssh -i my-key-pair.pem root@public-ip-address  
    or  
    ssh -i my-key-pair.pem admin@public-ip-address  

### 10. Install docker

1. Connect to the instance via SSH as described in step 9.
2. Once connected, update the package index and install the necessary dependencies for Docker installation:
  ```shell
  sudo apt update
  sudo apt install apt-transport-https ca-certificates curl software-properties-common
  ```
3. Add the Docker GPG key to ensure package integrity:





