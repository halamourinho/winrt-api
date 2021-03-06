---
-api-id: T:Windows.Media.SpeechSynthesis.SpeechSynthesisStream
-api-type: winrt class
---

<!-- Class syntax.
public class SpeechSynthesisStream : Windows.Foundation.IClosable, Windows.Media.Core.ITimedMetadataTrackProvider, Windows.Media.SpeechSynthesis.ISpeechSynthesisStream, Windows.Storage.Streams.IContentTypeProvider, Windows.Storage.Streams.IInputStream, Windows.Storage.Streams.IOutputStream, Windows.Storage.Streams.IRandomAccessStream, Windows.Storage.Streams.IRandomAccessStreamWithContentType
-->

# Windows.Media.SpeechSynthesis.SpeechSynthesisStream

## -description
Supports reading and writing audio data generated by the speech synthesis engine (voice) to/from a random access stream.

## -remarks

### Version history

| Windows version | SDK version | Value added |
| -- | -- | -- |
| 1703 | 15063 | TimedMetadataTracks |

## -examples
Your UWP app can use a [SpeechSynthesizer](../windows.devices.humaninterfacedevice/hiddevice_getdeviceselector_1541481733.md) object to create an audio stream and output speech based on a plain text string.

```csharp
// The media object for controlling and playing audio.
MediaElement mediaElement = this.media;

// The object for controlling the speech synthesis engine (voice).
var synth = new Windows.Media.SpeechSynthesis.SpeechSynthesizer();

// Generate the audio stream from plain text.
SpeechSynthesisStream stream = await synth.SynthesizeTextToStreamAsync("Hello World");

// Send the stream to the media object.
mediaElement.SetSource(stream, stream.ContentType);
mediaElement.Play();
```

[!code-cpp[SpeechSynthesizerText](../windows.media.speechsynthesis/code/SpeechSynthesis/cpp/MainPage.xaml.cpp#SnippetSpeechSynthesizerText)]


```csharp
// The string to speak with SSML customizations.
string Ssml =
    @"<speak version='1.0' " +
    "xmlns='http://www.w3.org/2001/10/synthesis' xml:lang='en-US'>" +
    "Hello <prosody contour='(0%,+80Hz) (10%,+80%) (40%,+80Hz)'>World</prosody> " + 
    "<break time='500ms'/>" +
    "Goodbye <prosody rate='slow' contour='(0%,+20Hz) (10%,+30%) (40%,+10Hz)'>World</prosody>" +
    "</speak>";

// The media object for controlling and playing audio.
MediaElement mediaElement = this.media;

// The object for controlling the speech synthesis engine (voice).
var synth = new Windows.Media.SpeechSynthesis.SpeechSynthesizer();

// Generate the audio stream from plain text.
SpeechSynthesisStream stream = await synth.synthesizeSsmlToStreamAsync(Ssml);

// Send the stream to the media object.
mediaElement.SetSource(stream, stream.ContentType);
mediaElement.Play();
```

[!code-cpp[SpeechSynthesizerSSML](../windows.media.speechsynthesis/code/SpeechSynthesis/cpp/MainPage.xaml.cpp#SnippetSpeechSynthesizerSSML)]

## -see-also
[Windows.Media.SpeechSynthesis](windows_media_speechsynthesis.md), [IRandomAccessStreamWithContentType](../windows.storage.streams/irandomaccessstreamwithcontenttype.md), [IRandomAccessStream](../windows.storage.streams/irandomaccessstream.md), [IClosable](../windows.foundation/iclosable.md), [IInputStream](../windows.storage.streams/iinputstream.md), [IOutputStream](../windows.storage.streams/ioutputstream.md), [IContentTypeProvider](../windows.storage.streams/icontenttypeprovider.md), [Speech interactions](/windows/uwp/design/input/speech-interactions), [Speech recognition and speech synthesis sample](https://github.com/Microsoft/Windows-universal-samples/tree/master/Samples/SpeechRecognitionAndSynthesis)
