# Voices in Amazon Polly<a name="voices-in-polly"></a>

Amazon Polly provides a variety of different voices in multiple languages for use when synthesizing speech from text\.

## Available Voices<a name="availablevoice-vip"></a>


| Language | Female Names/ID | Male Names/ID | 
| --- | --- | --- | 
| **Chinese, Mandarin \(cmn\-CN\)** | Zhiyu |  | 
| **Danish \(da\-DK\)** | Naja | Mads | 
|  **Dutch \(nl\-NL\)** | Lotte | Ruben | 
|  **English \(Australian\) \(en\-AU\)** | Nicole | Russell | 
|  **English \(British\) \(en\-GB\)** | Amy Emma | Brian | 
|  **English \(Indian\) \(en\-IN\)** | Aditi \(bilingual with Hindi\) Raveena |  | 
|  **English \(US\) \(en\-US\)** | Ivy Joanna Kendra Kimberly Salli | Joey Justin Matthew | 
|  **English \(Welsh\) \(en\-GB\-WLS\)** |  | Geraint | 
|  **French \(fr\-FR\)** | Céline/Celine | Mathieu | 
|  **French \(Canadian\) \(fr\-CA\)** | Chantal |  | 
|  **German \(de\-DE\)** | Marlene Vicki | Hans | 
|  **Hindi \(hi\-IN\)** | Aditi \(bilingual with Indian English\) |  | 
|  **Icelandic \(is\-IS\)** | Dóra/Dora | Karl | 
|  **Italian \(it\-IT\)** | Carla Bianca | Giorgio | 
|  **Japanese \(ja\-JP\)** | Mizuki | Takumi | 
|  **Korean \(ko\-KR\)** | Seoyeon |  | 
|  **Norwegian \(nb\-NO\)** | Liv |  | 
|  **Polish \(pl\-PL\)** | Ewa Maja | Jacek Jan | 
|  **Portuguese \(Brazilian\) \(pt\-BR\)** | Vitória/Vitoria | Ricardo | 
|  **Portuguese \(European\) \(pt\-PT\)** | Inês/Ines | Cristiano | 
|  **Romanian \(ro\-RO\)** | Carmen |  | 
|  **Russian \(ru\-RU\)** | Tatyana | Maxim | 
|  **Spanish \(European\) \(es\-ES\)** | Conchita Lucia | Enrique | 
|  **Spanish \(Mexican\) \(es\-MX\)** | Mia |  | 
|  **Spanish \(US\) \(es\-US\)** | Penélope/Penelope | Miguel | 
|  **Swedish \(sv\-SE\)** | Astrid |  | 
|  **Turkish \(tr\-TR\)** | Filiz |  | 
|  **Welsh \(cy\-GB\)** | Gwyneth |  | 

To ensure continuous support for customers, we don't plan to retire any voices\. This applies to both currently available and future voices\.

## Listening to the Voices<a name="listening-voices"></a>

You can use the Amazon Polly console to hear a sample from any of the voices available in Amazon Polly

**To listen to a voice in Amazon Polly**

1. Sign in to the **AWS Management Console** and open the [Amazon Polly console](https://console.aws.amazon.com/polly/)\.

1. Choose the **Text\-to\-Speech** tab\.

1. Choose a language and region, then choose a voice

1. Enter text for the voice to speak or use the default phrase and then choose **Listen to speech**\.

You can choose any of the languages offered by Amazon Polly and the console will display the voices available for that language\. In most cases, there will be at least one male and one female voice, often more than one of each\. One voice is bilingual \(Hindi and Indian English\) and a few only have a single voice\.

**Note**  
The inventory of voices and the number of languages included is continually being updated to include additional choices\. To suggest a new language or voice, feel free to provide feedback on this page\. Unfortunately, we are not able to comment on plans for specific new languages be they are released\.

Each voice is created using native language speakers, so there are variations from voice to voice, even within the same language\. When selecting a voice for your project, you should test each of the possible voices with a passage of text to see which best suits your needs\.

## Voice Speed<a name="voice-speed-vip"></a>

Because of the natural variation between voices, each available voice will speak the text at slightly different speeds\. For instance, with US English voices, Ivy and Joanna are slightly faster than Matthew when saying "Mary had a little lamb," and considerably faster than Joey\.

Since there is so much variation between voices, and the degree of that variation can depend on the text being spoken, no standard speed \(words per minute\) is available for Amazon Polly voices\. However, you can find how long it takes for your voice to say the selected text using SpeechMarks\. For more information on using speechmarks in Amazon Polly, see [Using Speech Marks ](using-speechmarks.md)

**To see approximately how long it takes to speak a text passage**

1. Open the AWS CLI\.

1. Run the following code, filling in as needed

   ```
        aws polly synthesize-speech \
             --language-code optional language code if needed
             --output-format json \
             --voice-id [name of desired voice] \
             --text '[desired text]' \
             --speech-mark-types='["viseme"]' \
             LengthOfText.txt
   ```

1. Open LengthOfText\.txt

If the text were "Mary had a little lamb," the last few lines returned by Amazon Polly would be:

```
     {"time":882,"type":"viseme","value":"t"}
     {"time":964,"type":"viseme","value":"a"}
     {"time":1082,"type":"viseme","value":"p"}
```

The last viseme, essentially the sound for the final letters in "lamb" starts 1082 milliseconds after the beginning of the speech\. While this is not exactly the length of the audio, it's close and can serve as the basis for comparison between voices\. 

 For certain applications, you may find that you'd prefer the voice you like be slowed down, or speeded up\. If the speed of the voice is a concern, Amazon Polly provides the ability to modify this using SSML tags\.

For example, if your intended audience speaks English, but not fluently, you might consider slowing the rate of speech in order to give them a little more time for comprehension\.

Amazon Polly helps you slow down the rate of speech using the SSML <prosody> tag, as in: 

```
     <prosody rate="slow">Mary had a little lamb.</prosody>
```

Five different speed options are available to you: `x-slow`, `slow`, `medium`, `fast`, and `x-fast`\. The speed of each option is approximate, depending on your preferred voice, so we recommend that test the voice to see if it meets your needs\. The `medium` option is the normal speed of the voice\.