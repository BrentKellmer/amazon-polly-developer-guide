# GetLexicon<a name="API_GetLexicon"></a>

Returns the content of the specified pronunciation lexicon stored in an AWS Region\. For more information, see [Managing Lexicons](http://docs.aws.amazon.com/polly/latest/dg/managing-lexicons.html)\.

## Request Syntax<a name="API_GetLexicon_RequestSyntax"></a>

```
GET /v1/lexicons/LexiconName HTTP/1.1
```

## URI Request Parameters<a name="API_GetLexicon_RequestParameters"></a>

The request requires the following URI parameters\.

 ** [Name](#API_GetLexicon_RequestSyntax) **   <a name="polly-GetLexicon-request-Name"></a>
Name of the lexicon\.  
Pattern: `[0-9A-Za-z]{1,20}` 

## Request Body<a name="API_GetLexicon_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_GetLexicon_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "[Lexicon](#polly-GetLexicon-response-Lexicon)": { 
      "[Content](API_Lexicon.md#polly-Type-Lexicon-Content)": "string",
      "[Name](API_Lexicon.md#polly-Type-Lexicon-Name)": "string"
   },
   "[LexiconAttributes](#polly-GetLexicon-response-LexiconAttributes)": { 
      "[Alphabet](API_LexiconAttributes.md#polly-Type-LexiconAttributes-Alphabet)": "string",
      "[LanguageCode](API_LexiconAttributes.md#polly-Type-LexiconAttributes-LanguageCode)": "string",
      "[LastModified](API_LexiconAttributes.md#polly-Type-LexiconAttributes-LastModified)": number,
      "[LexemesCount](API_LexiconAttributes.md#polly-Type-LexiconAttributes-LexemesCount)": number,
      "[LexiconArn](API_LexiconAttributes.md#polly-Type-LexiconAttributes-LexiconArn)": "string",
      "[Size](API_LexiconAttributes.md#polly-Type-LexiconAttributes-Size)": number
   }
}
```

## Response Elements<a name="API_GetLexicon_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [Lexicon](#API_GetLexicon_ResponseSyntax) **   <a name="polly-GetLexicon-response-Lexicon"></a>
Lexicon object that provides name and the string content of the lexicon\.   
Type: [Lexicon](API_Lexicon.md) object

 ** [LexiconAttributes](#API_GetLexicon_ResponseSyntax) **   <a name="polly-GetLexicon-response-LexiconAttributes"></a>
Metadata of the lexicon, including phonetic alphabetic used, language code, lexicon ARN, number of lexemes defined in the lexicon, and size of lexicon in bytes\.  
Type: [LexiconAttributes](API_LexiconAttributes.md) object

## Errors<a name="API_GetLexicon_Errors"></a>

 **LexiconNotFoundException**   
Amazon Polly can't find the specified lexicon\. This could be caused by a lexicon that is missing, its name is misspelled or specifying a lexicon that is in a different region\.  
Verify that the lexicon exists, is in the region \(see [ListLexicons](API_ListLexicons.md)\) and that you spelled its name is spelled correctly\. Then try again\.  
HTTP Status Code: 404

 **ServiceFailureException**   
An unknown condition has caused a service failure\.  
HTTP Status Code: 500

## See Also<a name="API_GetLexicon_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/polly-2016-06-10/GetLexicon) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/polly-2016-06-10/GetLexicon) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/polly-2016-06-10/GetLexicon) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/polly-2016-06-10/GetLexicon) 
+  [AWS SDK for Java](https://docs.aws.amazon.com/goto/SdkForJava/polly-2016-06-10/GetLexicon) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/polly-2016-06-10/GetLexicon) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/polly-2016-06-10/GetLexicon) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/polly-2016-06-10/GetLexicon) 
+  [AWS SDK for Ruby V2](https://docs.aws.amazon.com/goto/SdkForRubyV2/polly-2016-06-10/GetLexicon) 