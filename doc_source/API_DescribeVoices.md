# DescribeVoices<a name="API_DescribeVoices"></a>

Returns the list of voices that are available for use when requesting speech synthesis\. Each voice speaks a specified language, is either male or female, and is identified by an ID, which is the ASCII version of the voice name\. 

When synthesizing speech \( `SynthesizeSpeech` \), you provide the voice ID for the voice you want from the list of voices returned by `DescribeVoices`\.

For example, you want your news reader application to read news in a specific language, but giving a user the option to choose the voice\. Using the `DescribeVoices` operation you can provide the user with a list of available voices to select from\.

 You can optionally specify a language code to filter the available voices\. For example, if you specify `en-US`, the operation returns a list of all available US English voices\. 

This operation requires permissions to perform the `polly:DescribeVoices` action\.

## Request Syntax<a name="API_DescribeVoices_RequestSyntax"></a>

```
GET /v1/voices?IncludeAdditionalLanguageCodes=IncludeAdditionalLanguageCodes&LanguageCode=LanguageCode&NextToken=NextToken HTTP/1.1
```

## URI Request Parameters<a name="API_DescribeVoices_RequestParameters"></a>

The request requires the following URI parameters\.

 ** [IncludeAdditionalLanguageCodes](#API_DescribeVoices_RequestSyntax) **   <a name="polly-DescribeVoices-request-IncludeAdditionalLanguageCodes"></a>
Boolean value indicating whether to return any bilingual voices that use the specified language as an additional language\. For instance, if you request all languages that use US English \(es\-US\), and there is an Italian voice that speaks both Italian \(it\-IT\) and US English, that voice will be included if you specify `yes` but not if you specify `no`\.

 ** [LanguageCode](#API_DescribeVoices_RequestSyntax) **   <a name="polly-DescribeVoices-request-LanguageCode"></a>
 The language identification tag \(ISO 639 code for the language name\-ISO 3166 country code\) for filtering the list of voices returned\. If you don't specify this optional parameter, all available voices are returned\.   
Valid Values:` ar-XX | cmn-CN | cy-GB | da-DK | de-DE | en-AU | en-GB | en-GB-WLS | en-IN | en-US | es-ES | es-MX | es-US | fr-CA | fr-FR | hi-IN | is-IS | it-IT | ja-JP | ko-KR | nb-NO | nl-NL | pl-PL | pt-BR | pt-PT | ro-RO | ru-RU | sv-SE | tr-TR` 

 ** [NextToken](#API_DescribeVoices_RequestSyntax) **   <a name="polly-DescribeVoices-request-NextToken"></a>
An opaque pagination token returned from the previous `DescribeVoices` operation\. If present, this indicates where to continue the listing\.

## Request Body<a name="API_DescribeVoices_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_DescribeVoices_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "[NextToken](#polly-DescribeVoices-response-NextToken)": "string",
   "[Voices](#polly-DescribeVoices-response-Voices)": [ 
      { 
         "[AdditionalLanguageCodes](API_Voice.md#polly-Type-Voice-AdditionalLanguageCodes)": [ "string" ],
         "[Gender](API_Voice.md#polly-Type-Voice-Gender)": "string",
         "[Id](API_Voice.md#polly-Type-Voice-Id)": "string",
         "[LanguageCode](API_Voice.md#polly-Type-Voice-LanguageCode)": "string",
         "[LanguageName](API_Voice.md#polly-Type-Voice-LanguageName)": "string",
         "[Name](API_Voice.md#polly-Type-Voice-Name)": "string"
      }
   ]
}
```

## Response Elements<a name="API_DescribeVoices_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [NextToken](#API_DescribeVoices_ResponseSyntax) **   <a name="polly-DescribeVoices-response-NextToken"></a>
The pagination token to use in the next request to continue the listing of voices\. `NextToken` is returned only if the response is truncated\.  
Type: String

 ** [Voices](#API_DescribeVoices_ResponseSyntax) **   <a name="polly-DescribeVoices-response-Voices"></a>
A list of voices with their properties\.  
Type: Array of [Voice](API_Voice.md) objects

## Errors<a name="API_DescribeVoices_Errors"></a>

 **InvalidNextTokenException**   
The NextToken is invalid\. Verify that it's spelled correctly, and then try again\.  
HTTP Status Code: 400

 **ServiceFailureException**   
An unknown condition has caused a service failure\.  
HTTP Status Code: 500

## See Also<a name="API_DescribeVoices_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/polly-2016-06-10/DescribeVoices) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/polly-2016-06-10/DescribeVoices) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/polly-2016-06-10/DescribeVoices) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/polly-2016-06-10/DescribeVoices) 
+  [AWS SDK for Java](https://docs.aws.amazon.com/goto/SdkForJava/polly-2016-06-10/DescribeVoices) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/polly-2016-06-10/DescribeVoices) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/polly-2016-06-10/DescribeVoices) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/polly-2016-06-10/DescribeVoices) 
+  [AWS SDK for Ruby V2](https://docs.aws.amazon.com/goto/SdkForRubyV2/polly-2016-06-10/DescribeVoices) 