# Workshop environment setup

This is the first section of the AWS KMS Workshop where we will get things ready to start with the workshop.
Please ensure you have read and understood the [prerequisites for the workshop](https://github.com/aws-samples/aws-kms-workshop#pre---requisites). 

Especially, though AWS KMS prior knowledge is not really needed, Workshop is more meaningful if you take a look at this introduction to AWS KMS:

* [What is Key Management Service?](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html)
* [Getting Started with AWS KMS](https://docs.aws.amazon.com/kms/latest/developerguide/getting-started.html)

---

When you are ready, please follow the following steps to create all the artifacts we will be using during the workshop:


1. Login into your AWS account and navigate to the region you want work in. 



2. Download the Workshop's Cloudformation template to setup the entire stack **CloudFormation template on the (Save Link As) [following link](https://raw.githubusercontent.com/mbarronaws/aws-kms-workshop/master/kms-workshop-stack.yml)**. This template will create two EC2 instances, instance profiles, and an Amazon S3 bucket named "**kmsworkshop-accountid**", where accountid is the identifier of your account.
 

   Go to the AWS Console, navigate to "**CloudFormation**" Service and select "**Create Stack**" as you can see in figure below:
   
   
   
![alt text](/res/S0F1.png)
   
   
3. Then, in the "**Specify Template**" area, select "**Upload Template**" and browse for the template we downloaded just        before. Click "**Next**" and give the stack a name, like "KMSWorkshop-Stack". Hit "**Next**". Leave the default values that appear in this new page and hit "**Next**" again. In this new page, make sure you click the checkbox "**The following  
   resource(s) require capabilities: [AWS::IAM::Role]**" at the botton, and click "**Create Stack**". 
   
   The stack is now being created. If you got lost in the process, please look into the [CloudFormation Stack Creation documentation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-console-create-stack.html)
   
   
   

4. Once the CloudFormation Stack is complete, open the IAM console in another tab (we'll use it later), and open the Systems Manager console, then navigate to Session Manager (on the left panel) and click Start Session. You should see 2 EC2 instances (a public and private) ready for you to connect and run CLI commands.

   If you need overall help with CloudFormation stacks, see [the CloudFormation documenation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacks.html).


6. Once the EC2 instance is up and running, open the other tab and in the IAM console, create a new IAM policy "**KMSWorkshop-KMSAdminPolicy**" and attach it to the instance profile associated with the private EC2 instance you have launched (kmslabrole2-accountid). We do it to ensure that the AWS CLI on the instance has enough permissions to run AWS KMS operations.


![alt text](/res/S0F0.png)



7. Once the instance is launched and contains the Role, and a policy associated that will allow administrative KMS CLI commands, open Session Manager and try running the following command: 

aws kms list-keys

The command should complete successfully.

If you can connect to your instance then **You should now be ready to start with the workshop**, let's [Go to first section of workshop](https://github.com/aws-samples/aws-kms-workshop/blob/master/Section-1-Operating-with-AWS-KMS.md)


