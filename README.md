# Project Cost Optimization with AWS Lambda for Deleting Unattached EBS Snapshots

![Screenshot](/assets/first.png)


This project aims to optimize costs by automatically deleting EBS snapshots that are not attached to any volume or are associated with volumes not attached to running instances. The solution is implemented using Python and AWS Lambda.

## AWS IAM Policy and Permission Setup

To enable the Lambda function to perform the necessary operations, you need to create an IAM policy with the required permissions and attach it to the IAM role associated with the Lambda function.

### IAM Policy

1. Log in to your AWS Management Console.
2. Go to the IAM service.
3. Click on "Policies" in the left navigation pane.
4. Click on "Create policy".
5. Choose the "JSON" tab.
6. Paste the following policy document:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "ec2:DescribeSnapshots",
                "ec2:DescribeInstances",
                "ec2:DescribeVolumes",
                "ec2:DeleteSnapshot"
            ],
            "Resource": "*"
        }
    ]
}
```

7. Click on "Review policy".
8. Enter a name and description for the policy (e.g., "EBS_Snapshot_Deletion_Policy").
9. Click on "Create policy".

![Screenshot](/assets/permisson.png)
### IAM Role

1. Go to the IAM service.
2. Click on "Roles" in the left navigation pane.
3. Click on the IAM role associated with your Lambda function.
4. Under "Permissions", click on "Attach policies".
5. Search for and select the policy you created earlier (e.g., "EBS_Snapshot_Deletion_Policy").
6. Click on "Attach policy".

## Lambda Function Configuration

Now that the IAM policy with the required permissions is set up, you can configure the Lambda function to use this IAM role.

1. Log in to your AWS Management Console.
2. Go to the Lambda service.
3. Click on your Lambda function.
4. Scroll down to the "Execution role" section.
5. Ensure that the IAM role associated with the Lambda function is the one you attached the policy to in the previous steps.

## Usage

Once the Lambda function is configured with the appropriate IAM permissions, it will automatically delete EBS snapshots that meet the specified criteria (not attached to any volume or associated with volumes not attached to running instances) when triggered.

You can manually test the Lambda function by invoking it from the AWS Lambda console or schedule it to run at specific intervals using CloudWatch Events.

## Video Link

Here is the video link demonstrating the completion of the task: [Video Link](https://youtu.be/cbPoJQCiUfg)

## Disclaimer

Make sure to thoroughly test the Lambda function in a staging environment before deploying it to production. Deleting snapshots irreversibly removes backup data, so use caution and ensure that only unnecessary snapshots are deleted.

## About Me

I'm a passionate developer driven by Full Stack Web Development, Cloud and DevOps Technologies, and solving problems through software innovation. Let's connect!

## Let's Connect
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/prince-prasad/)
[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/PRINCE__PRASAD)
[![github](https://img.shields.io/badge/github-3d4653?style=for-the-badge&logo=github&logoColor=white)](https://github.com/PRINCE-PRASAD)
