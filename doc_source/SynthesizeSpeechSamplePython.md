# SynthesizeSpeech<a name="SynthesizeSpeechSamplePython"></a>

The following Python code example uses the AWS SDK for Python \(Boto\) to list the lexicons in your account in the region specified in your local AWS configuration\. For information about creating the configuration file, see [Step 3\.1: Set Up the AWS Command Line Interface \(AWS CLI\)](setup-aws-cli.md)\. 

For more information on the API, see the reference for [https://docs.aws.amazon.com/polly/latest/dg/API_SynthesizeSpeech.html](https://docs.aws.amazon.com/polly/latest/dg/API_SynthesizeSpeech.html) API\. 

```
import boto3

polly_client = boto3.Session(
                aws_access_key_id=,                     
    aws_secret_access_key=,
    region_name='us-west-2').client('polly')

response = polly_client.synthesize_speech(VoiceId='Joanna',
                OutputFormat='mp3', 
                Text = 'This is a sample text to be synthesized.')

file = open('speech.mp3', 'w')
file.write(response['AudioStream'].read())
file.close()
```