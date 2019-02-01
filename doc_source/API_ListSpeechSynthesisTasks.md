# ListSpeechSynthesisTasks<a name="API_ListSpeechSynthesisTasks"></a>

Returns a list of SpeechSynthesisTask objects ordered by their creation date\. This operation can filter the tasks by their status, for example, allowing users to list only tasks that are completed\.

## Request Syntax<a name="API_ListSpeechSynthesisTasks_RequestSyntax"></a>

```
GET /v1/synthesisTasks?MaxResults=MaxResults&NextToken=NextToken&Status=Status HTTP/1.1
```

## URI Request Parameters<a name="API_ListSpeechSynthesisTasks_RequestParameters"></a>

The request requires the following URI parameters\.

 ** [MaxResults](#API_ListSpeechSynthesisTasks_RequestSyntax) **   <a name="polly-ListSpeechSynthesisTasks-request-MaxResults"></a>
Maximum number of speech synthesis tasks returned in a List operation\.  
Valid Range: Minimum value of 1\. Maximum value of 100\.

 ** [NextToken](#API_ListSpeechSynthesisTasks_RequestSyntax) **   <a name="polly-ListSpeechSynthesisTasks-request-NextToken"></a>
The pagination token to use in the next request to continue the listing of speech synthesis tasks\. 

 ** [Status](#API_ListSpeechSynthesisTasks_RequestSyntax) **   <a name="polly-ListSpeechSynthesisTasks-request-Status"></a>
Status of the speech synthesis tasks returned in a List operation  
Valid Values:` scheduled | inProgress | completed | failed` 

## Request Body<a name="API_ListSpeechSynthesisTasks_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_ListSpeechSynthesisTasks_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "[NextToken](#polly-ListSpeechSynthesisTasks-response-NextToken)": "string",
   "[SynthesisTasks](#polly-ListSpeechSynthesisTasks-response-SynthesisTasks)": [ 
      { 
         "[CreationTime](API_SynthesisTask.md#polly-Type-SynthesisTask-CreationTime)": number,
         "[Engine](API_SynthesisTask.md#polly-Type-SynthesisTask-Engine)": "string",
         "[LanguageCode](API_SynthesisTask.md#polly-Type-SynthesisTask-LanguageCode)": "string",
         "[LexiconNames](API_SynthesisTask.md#polly-Type-SynthesisTask-LexiconNames)": [ "string" ],
         "[OutputFormat](API_SynthesisTask.md#polly-Type-SynthesisTask-OutputFormat)": "string",
         "[OutputUri](API_SynthesisTask.md#polly-Type-SynthesisTask-OutputUri)": "string",
         "[RequestCharacters](API_SynthesisTask.md#polly-Type-SynthesisTask-RequestCharacters)": number,
         "[SampleRate](API_SynthesisTask.md#polly-Type-SynthesisTask-SampleRate)": "string",
         "[SnsTopicArn](API_SynthesisTask.md#polly-Type-SynthesisTask-SnsTopicArn)": "string",
         "[SpeechMarkTypes](API_SynthesisTask.md#polly-Type-SynthesisTask-SpeechMarkTypes)": [ "string" ],
         "[TaskId](API_SynthesisTask.md#polly-Type-SynthesisTask-TaskId)": "string",
         "[TaskStatus](API_SynthesisTask.md#polly-Type-SynthesisTask-TaskStatus)": "string",
         "[TaskStatusReason](API_SynthesisTask.md#polly-Type-SynthesisTask-TaskStatusReason)": "string",
         "[TextType](API_SynthesisTask.md#polly-Type-SynthesisTask-TextType)": "string",
         "[VoiceId](API_SynthesisTask.md#polly-Type-SynthesisTask-VoiceId)": "string"
      }
   ]
}
```

## Response Elements<a name="API_ListSpeechSynthesisTasks_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [NextToken](#API_ListSpeechSynthesisTasks_ResponseSyntax) **   <a name="polly-ListSpeechSynthesisTasks-response-NextToken"></a>
An opaque pagination token returned from the previous List operation in this request\. If present, this indicates where to continue the listing\.  
Type: String

 ** [SynthesisTasks](#API_ListSpeechSynthesisTasks_ResponseSyntax) **   <a name="polly-ListSpeechSynthesisTasks-response-SynthesisTasks"></a>
List of SynthesisTask objects that provides information from the specified task in the list request, including output format, creation time, task status, and so on\.  
Type: Array of [SynthesisTask](API_SynthesisTask.md) objects

## Errors<a name="API_ListSpeechSynthesisTasks_Errors"></a>

 **InvalidNextTokenException**   
The NextToken is invalid\. Verify that it's spelled correctly, and then try again\.  
HTTP Status Code: 400

 **ServiceFailureException**   
An unknown condition has caused a service failure\.  
HTTP Status Code: 500

## See Also<a name="API_ListSpeechSynthesisTasks_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/polly-2016-06-10/ListSpeechSynthesisTasks) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/polly-2016-06-10/ListSpeechSynthesisTasks) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/polly-2016-06-10/ListSpeechSynthesisTasks) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/polly-2016-06-10/ListSpeechSynthesisTasks) 
+  [AWS SDK for Java](https://docs.aws.amazon.com/goto/SdkForJava/polly-2016-06-10/ListSpeechSynthesisTasks) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/polly-2016-06-10/ListSpeechSynthesisTasks) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/polly-2016-06-10/ListSpeechSynthesisTasks) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/polly-2016-06-10/ListSpeechSynthesisTasks) 
+  [AWS SDK for Ruby V2](https://docs.aws.amazon.com/goto/SdkForRubyV2/polly-2016-06-10/ListSpeechSynthesisTasks) 