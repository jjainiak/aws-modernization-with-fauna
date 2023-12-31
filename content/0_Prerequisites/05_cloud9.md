+++
title = "Cloud9 IDE setup"
chapter = false
weight = 5
+++

## Cloud9 IDE Setup

{{% notice note %}}
You can deploy the workshop from your local machine if you want
(skip this section and over to the <a href="06_own_workstation.html">Own Workshop Setup</a> for this), 
but we recommend using AWS Cloud9 integrated development environment (IDE).
{{% /notice %}}

### Cloud9

1. In your AWS Management Console navigate to Cloud9 service, by searching Cloud9 in the search bar.
    ![Cloud9](/images/Cloud9.png?width=800)
2. Click on create environment.
3. Provide a name, description and select environment type as "New EC2 instance".
4. Then under "New EC2 instance" select "Additional instance types" and we recommend that you choose a "t3.large" or higher configuration. You can leave other options as default and click "Create".
    ![Cloud9 Instance Type](/images/Cloud9_InstanceType.png?width=700)
5. To launch the Cloud9 IDE, select Cloud9 instance you created and then click **Open in Cloud9**


## Clone the project

* Run the following command to clone the workshop
  ```
  git clone https://github.com/fauna-labs/fauna-serverless-saas-workshop.git
  ```

## Install the pre-requisites
1. Use the script below to increase the disk size of your Cloud9 instance to 50 GB. This is needed to be able to build our workshop.
   ```
   cd ~/environment/fauna-serverless-saas-workshop/Cloud9Setup/
   ./increase-disk-size.sh 
   ```
2. Run the script below to install the project dependencies.
   ```
    cd ~/environment/fauna-serverless-saas-workshop/Cloud9Setup/
    ./pre-requisites.sh
   ```

## Setup the environment

* **cd** into the **Lab1/scripts** folder
  ```
  cd ~/environment/aws-serverless-saas-workshop/Lab1/scripts
  ```
  
* A template file **.env.template** is located in this folder. Make a copy and name it **.env**, and edit in the value for **FAUNA_API_KEY**

  * Update the **FAUNA_API_KEY** variable to the value you previously saved when you generated an API Key using
    the web shell
  * Leave **AWS_PROFILE** as **default**

    The following shows an example **.env** file entries:
    ```
    STACK_NAME="serverless-saas-fauna-workshop-lab1"
    FAUNA_API_KEY="<the API Key>"
    AWS_PROFILE="default"
    ```

## Next stop: Lab1

The setup is now complete. Now, head over to <a href="/1_lab1.html">Lab1</a> to begin the workshop.