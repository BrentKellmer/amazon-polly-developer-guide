# Creating Long Audio Files \(Console\)<a name="longer-console"></a>

You can use the Amazon Polly console to create long speeches using asynchronous synthesis with the same functionality as you can use with the AWS CLI\. This is done using the **Text\-to\-Speech** tab much like any other synthesis\. 

The other asynchronous synthesis functionality is also available via the console\. The **S3 synthesis tasks** tab reflects the `ListSpeechSynthesisTasks` functionality, displaying all tasks saved to the S3 bucket and enabling you to filter them if you want\. Clicking on a specific single task shows its details, reflecting `GetSpeechSynthesisTask` functionality\.

**To synthesize a large text using the Amazon Polly Console**

1. Sign in to the AWS Management Console and open the Amazon Polly console at [https://console\.aws\.amazon\.com/polly/](https://console.aws.amazon.com/polly/)\.

1. Choose the **Text\-to\-Speech** tab\. 

1. On either the **Plain Text** tab or the **SSML** tab, type or paste your text into the input box\. 

1. Choose the language, region, and voice for your text\. 

1. Choose **Synthesize to S3**\. 
**Note**  
Both the **Download** and **Listen to Speech** options will be greyed out if the text length is above the limits for the real\-time `SynthesizeSpeech` operation\.

1. If you haven't used asynchronous synthesis previously, the **Change S3 synthesis task settings** box will be displayed so you can choose where to store the output file\.

   1. Fill in the name of the destination Amazon S3 bucket\.

   1. Optionally, fill in the prefix key of the output\.
**Note**  
The output S3 bucket must be writable\.

   1. If you want to be notified when the synthesis task is complete, provide the optional SNS Topic identifier\.
**Note**  
The SNS must be open for publication by the current console user to use this option\. For more information, see [Amazon Simple Notification Service \(SNS\)](https://aws.amazon.com/sns/)

   1. Choose **Synthesize**\. 

**To change the S3 synthesis task settings**

1. In the console, on the **Test\-to\-Speech** tab, choose **Change S3 task settings**\.

1. Make any changes you want to the name of the destination Amazon S3 bucket, its prefix key, or the SNS topic identifier\.

1. Choose **Synthesize** when done\. 

**To retrieve information on your speech synthesis tasks**

1. In the console, choose the **S3 Synthesis Tasks** tab\.

1. The tasks are displayed in date order\. To filter the tasks, choose **Filter** and then choose what the filter to use\.

1. To view the details of a specific task, choose the linked **Task ID**\.