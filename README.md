# EC2 Instance CloudFormation Template

This repository contains a CloudFormation template to create an EC2 instance.

## Prerequisites

- An AWS account
- AWS CLI installed and configured
- An existing EC2 KeyPair

## Usage

1. Clone the repository:

    ```bash
    git clone https://github.com/MasiMasinga/EC2-Instance-CloudFormation-Template.git
    cd ec2-instance-cloudformation
    ```

2. Deploy the CloudFormation stack:

    ```bash
    aws cloudformation create-stack --stack-name my-ec2-stack --template-body file://ec2.template.yaml --parameters ParameterKey=KeyName,ParameterValue=your-key-name
    ```

    Replace `your-key-name` with the name of your existing EC2 KeyPair.

3. Wait for the stack to be created. You can check the status using:

    ```bash
    aws cloudformation describe-stacks --stack-name my-ec2-stack
    ```

4. Once the stack creation is complete, you can find the EC2 instance in the AWS Management Console.

## Cleanup

To delete the stack and all associated resources:

```bash
aws cloudformation delete-stack --stack-name my-ec2-stack
