# Storing Audio Files<a name="pollycast"></a>

When you publish content on your site, it's sent to Amazon Polly for synthesis\. By default, Amazon Polly stores new audio files on your web server\. You can also store the files on Amazon Simple Storage Service \(Amazon S3\) or on Amazon CloudFront, which is a global content delivery network \(CDN\)\. 

Users have the same listening experience regardless of where you store your audio files\. Only the broadcast location changes:: 

1. For audio files stored on the WordPress server, files are broadcast directly from the server\.

1. For files stored in an S3 bucket, files are broadcast from the bucket\. 

1. If you use CloudFront, the files are stored on Amazon S3 and are broadcast with CloudFront\. 

 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/polly/latest/dg/images/chart.png)

You can choose where to store your files when you install the Amazon Polly plugin\.  

## Positioning the HTML Player<a name="pollycast-html"></a>

When you install the Amazon Polly plugin, it displays an HTML player at the top of your WordPress website by default unless you choose to display it under your site's text or to not display it\. 

 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/polly/latest/dg/images/htmlplayer.png)

You can reposition the player, remove it, or add it \(if you chose not to display it\) at any time\.

**To reposition the player, remove it, or add it to your WordPress website**

1. On the **WordPress Admin** page, choose **Settings**\.

1. On the **Amazon Polly Settings** page, for **Player position**, choose the appropriate option\.

For more information about setting configuration options, see [Install and Configure the Plugin](plugin-install.md#wp-install)\.

## Podcasting with Amazon Pollycast<a name="pollycast-podcast"></a>

With Amazon Pollycast feeds\., your visitors can listen to your audio content using standard podcast applications\. RSS 2\.0\-compliant *Pollycast feeds* provide the XML data needed to aggregate podcasts by popular mobile podcast applications, such as iTunes, and podcast directories\. 

When you install the Amazon Polly plugin, choose the ****ITunes explicit**** option to automatically add Amazon Pollycast endpoints to all WordPress archive URLs\. This lets you syndicate both site\-wide or targeted podcasts\. If you didn't choose the ****ITunes explicit**** option when you installed the plugin, follow these steps:

1. On the **WordPress Admin** page, choose **Settings**\.

1. On the **Amazon Polly Settings** page, choose ****ITunes explicit****\.

You can add Amazon Pollycast endpoints manually by adding `/amazon-pollycast/` to the URL for a page in a podcasting application\. For example:

```
example.com/amazon-pollycast/
example.com/category/news/amazon-pollycast/
example.com/author/john/amazon-pollcast/
```