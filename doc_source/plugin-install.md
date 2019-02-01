# Installing the Plugin<a name="plugin-install"></a>

To install and configure the plugin, use the WordPress **Add Plugins** page\. After you install and activate the plugin, navigate to the Amazon Polly **Settings** page and connect the plugin to your AWS account\. 

To install the Amazon Polly plugin for WordPress, you need an AWS account and a working WordPress installation\. If you don't have an account, see [Step 1\.1: Sign up for AWS](setting-up.md#setting-up-signup)\. 

When you have an AWS account, follow these steps to install the plugin: 

1. [Create a Permissions Policy](#wp-permissions)

1. [Create an IAM User for the Plugin](#wp-account)

1. [Install and Configure the Plugin](#wp-install)

## Create a Permissions Policy<a name="wp-permissions"></a>

In the [AWS Management Console](https://console.aws.amazon.com/), create an AWS Identity and Access Management \(IAM\) permissions policy called *PollyForWordPressPolicy*\. A *permissions policy* is a document that defines permissions that apply to a user \(or group or role\)\. The *permissions* determine what users can do in AWS\.Copy and paste the following code:

```
{

    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Permissions1",
            "Effect": "Allow",
            "Action": [
                "s3:HeadBucket",
                "polly:SynthesizeSpeech",
                "polly:DescribeVoices"
            ],
           "Resource": "*"
        },
        {
            "Sid": "Permissions2",
            "Effect": "Allow",
            "Action": [
                "s3:ListBucket",
                "s3:GetBucketAcl",
                "s3:GetBucketPolicy",
                "s3:PutObject",
                "s3:DeleteObject",
                "s3:CreateBucket",
                "s3:PutObjectAcl"
            ],
            "Resource": [
                "arn:aws:s3:::audio_for_wordpress*",
                "arn:aws:s3:::audio-for-wordpress*"
            ]    
        }
    ]
}
```

For more information about creating a permissions policy, see [Creating Customer\-Managed Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_managed-policies.html)\.

## Create an IAM User for the Plugin<a name="wp-account"></a>

Before connecting the plugin to your AWS account, you need to create an IAM user, then attach the permissions policy that you created in [Create a Permissions Policy](#wp-permissions) to that user\. An *IAM user* is a person or application under an AWS account that needs to make API calls to AWS products\. 

If you deployed WordPress on Amazon Elastic Compute Cloud \(Amazon EC2\), you can skip this step and use the IAM role instead of an IAM user\. For more information, see [IAM Roles for Amazon EC2](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/iam-roles-for-amazon-ec2.html) in the *Amazon EC2 User Guide*\. 

**To create an IAM user**

1. Sign in to the AWS Management Console and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. Choose **Users**\. 

1. Choose **Add User**\.

1. For **User Name**, type **WordPress**\. 

1. For **Access Type**, choose **Programmatic access**, then choose **Next: Permissions**\.

1. Choose **Attach existing policies direction**, choose your newly created policy \(*PollyForWordPressPolicy*\) from the list, then choose **Next: Review**\.

1. Choose **Create User**\.

1. Record the access key ID and secret access key\. You need them to configure the plugin\.
**Important**  
This is the only time you can access these keys, so be sure to record them\.

## Install and Configure the Plugin<a name="wp-install"></a>

Install the plugin from GitHub, then configure it to enable podcasting, alternative storage locations, and other options\. 

**Note**  
In the following procedure, command and field names might differ slightly from the names used in WordPress\. 

**To install and configure the plugin**

1. Download the Amazon Polly plugin for WordPress from the [Amazon Polly plugin GitHub site](https://github.com/awslabs/amazon-polly-wordpress-plugin)\. 

1. On the **WordPress Admin** page, choose **Add New Plugin**, then install and activate the plugin\. 

1. On the **WordPress Admin** page, choose **Settings**\. 

1. Configure the plugin using the following **Amazon Polly Settings** options: 
   + ****AWS access key and AWS secret key****—These AWS credentials allow the plugin to use Amazon Polly and Amazon Simple Storage Service \(Amazon S3\)\. Type the AWS access and secret keys that you created in [Create an IAM User for the Plugin](#wp-account)\. If you are hosting your WordPress site on Amazon EC2, you can use IAM roles instead of credentials\. In that case, leave these two fields blank\.
   + ****Sample rate****—The sample rate for the audio files that will be generated, in Hz\. Higher sampling rates produce higher\-quality audio\.
   + ****Voice name****—The Amazon Polly voice to use in the audio file\.
   + ****Player position****—Where to position the audio player on the website\. You can put it before or after the post, or not use it at all\. If you want to make your files available as podcasts by using Amazon Pollycast, don't display the audio player\. 
   + ****New post default****—Specifies whether Amazon Polly should automatically create an audio file for all new posts\. Choose this option if you want Amazon Polly to use the configuration settings to create an audio file for each new post\.
   + ****Autoplay****—Specifies whether the audio player automatically starts playing the audio for a post when a visitor visits it\. 
   + ****Store audio in Amazon S3****—If you want to store audio files in an S3 bucket instead of on your web server, choose this option\. Amazon Polly creates the bucket for you\. For more information and pricing, see [Amazon S3](https://aws.amazon.com/s3)\.
   + ****Amazon CloudFront** **\(CDN\) domain name****—If you want to broadcast your audio files with Amazon CloudFront, provide the name of your CloudFront domain\. The plugin uses the domain to stream audio\. If you don't already have a domain, create one in Amazon CloudFront\. 
   + ****ITunes category****—The category for your podcast\. Choosing a category makes it easier for podcast users to find your podcast in the podcast catalog\.
   + ****ITunes explicit****—Specifies whether to enable Amazon Pollycast podcasting\. 
   + ****Bulk update all posts****—If you want to convert all posts to use the new plugin settings, choose this option\. 

1. Choose **Save Changes**\.