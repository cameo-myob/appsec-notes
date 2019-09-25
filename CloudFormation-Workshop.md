# CloudFormation Workshop
### Taken from [Ops-Workshops](https://github.com/MYOB-Technology/ops-workshops/tree/master/cloudformation)


## Review the AWS CloudFormation Console
**What are the default columns displayed in the CloudFormation console?**

- Stack Name
- Status
- Created Time
- Description

**What are some of the different statuses displayed in the console?**
- `CREATE_COMPLETE`
- `UPDATE_COMPLETE`
- `ROLLBACK_COMPLETE`

**What do you think each one means?**
- `CREATE_COMPLETE` - successfully created stack
- `UPDATE_COMPLETE` - successfully updated stack
- `ROLLBACK_COMPLETE` - successfully rolled back to previous configuration after an unsuccessful create/update attempt


**Where in the documentation can you find details on the different stack status?**
Documentation on stack status codes can be found in the [CloudFormation Docs](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-describing-stacks.html#w2ab1c15c15c17c11).


**What is the difference between the Events tab and the Resources tab?**
The `Events` tab shows every event that has occurred, the `Resources` tab shows all of the provisioned resources.

---

## Create Your First Stack
**What are the Outputs of your stack?**

A `PublicIp`, a `PrivateIp` and an `InstanceId`. 

**What Resources were created for your stack?**

An EC2 instance.

**What is the instance ID of the EC2 instance created as part of your stack?**
The instance ID is `i-06398d9f89ba06f7f`.


**Can you find your instance in the EC2 console?**
Yes.


---
**Is there a way to find your deleted stack?**
By selecting `Deleted` from the drop-down filter.


**Has CloudFormation removed all resources it created?**
Yes it deleted all of the resources it had created.


**What happens when you delete a stack?**
It deletes all of the resources associated with it.

---

## Updating CloudFormation Stacks and Remote Access

**Why did the IP address of the machine change?**
The EC2 instance was replaced, not updated.


**Under what circumstances does this happen?**
Updating the name of the key pair causes the instance to be replaced by a new one.


**Do you lose the information on the machine?**

Unsure.

**How can you test your findings?**

Unsure.

---
## The AWS Command Line
**What tasks do you currently do with AWS console that would be easier via the CLI?**

Creating/updating a CF stack.

**If you received an error message attempting this step, do you know why it happened?**

I didn't get an error.

**What other commands are there in the aws cloudformation tool?**

Many, *many* commands. The list include `create-stack`, `delete-stack`, `describe-stack-resource`, `get-template`, `list-stacks`, `update-stack` and `validate-template` to name a few.

**How might you get access to help on parameters and other commands?**
The [AWS CloudFormation Docs](https://docs.aws.amazon.com/cli/latest/reference/cloudformation/index.html#cli-aws-cloudformation) list the available commands and parameters.


**What other AWS services could you access with the cli tool?**

Using the AWS cli tool, you can also access `cloudfront`, `cloudwatch`, `ec2`, `ecr`, `elasticbeanstalk`, `guardduty`, `iam`, `kafka`, `lambda`, `rds`, `route53` and `s3` to name a few.

**Is there any way to see the deleted stacks using the aws cli?**
Yes, using `aws cloudformation list-stacks --stack-status-filter DELETE_COMPLETE`.
