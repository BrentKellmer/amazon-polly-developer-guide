# Voice<a name="API_Voice"></a>

Description of the voice\.

## Contents<a name="API_Voice_Contents"></a>

 **AdditionalLanguageCodes**   <a name="polly-Type-Voice-AdditionalLanguageCodes"></a>
Additional codes for languages available for the specified voice in addition to its default language\.   
For example, the default language for Aditi is Indian English \(en\-IN\) because it was first used for that language\. Since Aditi is bilingual and fluent in both Indian English and Hindi, this parameter would show the code `hi-IN`\.  
Type: Array of strings  
Valid Values:` ar-XX | cmn-CN | cy-GB | da-DK | de-DE | en-AU | en-GB | en-GB-WLS | en-IN | en-US | es-ES | es-MX | es-US | fr-CA | fr-FR | hi-IN | is-IS | it-IT | ja-JP | ko-KR | nb-NO | nl-NL | pl-PL | pt-BR | pt-PT | ro-RO | ru-RU | sv-SE | tr-TR`   
Required: No

 **Gender**   <a name="polly-Type-Voice-Gender"></a>
Gender of the voice\.  
Type: String  
Valid Values:` Female | Male`   
Required: No

 **Id**   <a name="polly-Type-Voice-Id"></a>
Amazon Polly assigned voice ID\. This is the ID that you specify when calling the `SynthesizeSpeech` operation\.  
Type: String  
Valid Values:` Aditi | Amy | Astrid | Bianca | Brian | Carla | Carmen | Celine | Chantal | Conchita | Cristiano | Dora | Emma | Enrique | Ewa | Filiz | Geraint | Giorgio | Gwyneth | Hans | Ines | Ivy | Jacek | Jan | Joanna | Joey | Justin | Karl | Kendra | Kimberly | Lea | Liv | Lotte | Lucia | Mads | Maja | Marlene | Mathieu | Matthew | Maxim | Mia | Miguel | Mizuki | Naja | Nicole | Penelope | Raveena | Ricardo | Ruben | Russell | Salli | Seoyeon | Takumi | Tatyana | Vicki | Vitoria | Zhiyu | Abbey | Alicia | Camila | Candela | Charlotte | Chloe | Ella | Fernanda | Giulia | Ira | Lupe | Mariana | Nina | Silke | Yumiko | Zeina`   
Required: No

 **LanguageCode**   <a name="polly-Type-Voice-LanguageCode"></a>
Language code of the voice\.  
Type: String  
Valid Values:` ar-XX | cmn-CN | cy-GB | da-DK | de-DE | en-AU | en-GB | en-GB-WLS | en-IN | en-US | es-ES | es-MX | es-US | fr-CA | fr-FR | hi-IN | is-IS | it-IT | ja-JP | ko-KR | nb-NO | nl-NL | pl-PL | pt-BR | pt-PT | ro-RO | ru-RU | sv-SE | tr-TR`   
Required: No

 **LanguageName**   <a name="polly-Type-Voice-LanguageName"></a>
Human readable name of the language in English\.  
Type: String  
Required: No

 **Name**   <a name="polly-Type-Voice-Name"></a>
Name of the voice \(for example, Salli, Kendra, etc\.\)\. This provides a human readable voice name that you might display in your application\.  
Type: String  
Required: No

## See Also<a name="API_Voice_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/polly-2016-06-10/Voice) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/polly-2016-06-10/Voice) 
+  [AWS SDK for Java](https://docs.aws.amazon.com/goto/SdkForJava/polly-2016-06-10/Voice) 
+  [AWS SDK for Ruby V2](https://docs.aws.amazon.com/goto/SdkForRubyV2/polly-2016-06-10/Voice) 