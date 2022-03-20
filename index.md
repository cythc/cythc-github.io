
<html lang="en-US">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="theme-color" content="#157878">
    <link rel="stylesheet" href="/assets/css/style.css?v=e27bf585b9c641a881074e09853cb11204774c97">
  </head>
  <body>

<h2>MRMI-TTS: Multi-reference Audios and Mutual Information-Based Zero-shot Speech Synthesis<a name="abstract"></a></h2>
    
<h2>Abstract<a name="abstract"></a></h2>

<p>Zero-shot text-to-speech aims to clone target speaker’s voice with only a few data of any target speakers even unseen in training set. Existing multi-speaker systems are capable of preforming high-fidelity speech generation, but clone unseen speakers’ voices is still a challenging task. To generalize to new speakers, previous works use speaker encoder to obtain fixed-size speaker embedding from single reference audio. However single reference audio dose not contain sufficient timbre information of the target speaker, and ignores the correlation between different speech representations during training, which causes leakage of content information into the speaker representation and thus degrades text-to-speech performances. In this paper, we propose to mitigate these two problems by using multiple reference audios and use content encoder and speaker encoder to obtain content embedding and speaker embedding of reference audios. To get more disentangled representations, the proposed method further uses mutual information minimization between the two embeddings to remove entangled information within each embedding. Experiments on VCTK dataset indicate that our method can improve synthesized speech both in similarity and naturalness even unseen people.</p>

<h2>Contents</h2>
<ol>
  <li><a href="#samples-seen">Synthesized samples - Seen Speakers</a></li>
  <li><a href="#samples-unseen">Synthesized samples – Unseen Speakers</a></li>
  <li><a href="#samples-number">Synthesized samples – Different number of reference audios</a></li>
</ol>

<h2>1. Synthesized samples -- Seen Speakers<a name="samples-seen"></a></h2>
<h3> Using three reference audios </h3>
<table>
    <tr>
      <th style="text-align: left">Models</th>
      <td style="text-align: left">p259: Behind him was his brother.</td>
      <td style="text-align: left">P261: You have to see the work.</td>
    </tr>
  
    <tr>
      <th style="text-align: left"><strong>reference audios</strong></th>
      <td style="text-align: left"><audio src="wavs\GT\seen\If that's the case , he will struggle ._p259.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\GT\seen\It was a poor performance ._p261.wav" controls="" preload=""></audio></td>
    </tr>
  
    <tr>
      <th style="text-align: left"><strong>Ground Truth</strong></th>
      <td style="text-align: left"><audio src="wavs\GT\seen\Behind him was his brother ._p259.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\GT\seen\You have to see the work ._p261.wav" controls="" preload=""></audio></td>
    </tr>
    <tr>
      <th style="text-align: left"><strong>FS2+speaker ID</strong></th>
      <td style="text-align: left"><audio src="wavs\FS2-speakerID\Behind him was his brother ._p259.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\FS2-speakerID\You have to see the work ._p261.wav" controls="" preload=""></audio></td>
    </tr>
    <tr>
      <th style="text-align: left"><strong>StyleSpeech</strong></th>
      <td style="text-align: left"><audio src="wavs\StyleSpeech\seen\Behind him was his brother .-p259.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\StyleSpeech\seen\You have to see the work .-p261.wav" controls="" preload=""></audio></td>
    </tr>
    <tr>
      <th style="text-align: left"><strong>Meta-StyleSpeech</strong></th>
      <td style="text-align: left"><audio src="wavs\Meta-StyleSpeech\seen\Behind him was his brother .-p259.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\Meta-StyleSpeech\seen\You have to see the work .-p261.wav" controls="" preload=""></audio></td>
    </tr>
    <tr>
      <th style="text-align: left"><strong>MRMI-TTS w/o discriminator</strong></th>
      <td style="text-align: left"><audio src="wavs\withou_D\seen\Behind him was his brother ._p259.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\withou_D\seen\You have to see the work ._p261.wav" controls="" preload=""></audio></td>      
    </tr>
    <tr>
      <th style="text-align: left"><strong>MRMI-TTS w/o MI</strong></th>
      <td style="text-align: left"><audio src="wavs\without_MI\Behind him was his brother ._p259.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\without_MI\You have to see the work ._p261.wav" controls="" preload=""></audio></td>      
    </tr>
    <tr>
      <th style="text-align: left"><strong>MRMI-TTS</strong></th>
      <td style="text-align: left"><audio src="wavs\ours\seen\Behind him was his brother ._p259.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\ours\seen\You have to see the work ._p261.wav" controls="" preload=""></audio></td>      
    </tr>
</table>
    
<h2>2. Synthesized samples -- Unseen Speakers<a name="samples-unseen"></a></h2>
<h3> Using three reference audios, reference audios from VCTK. </h3>
<table>
    <tr>
      <th style="text-align: left">Models</th>
      <td style="text-align: left">P238: She can scoop these things into three red bags , and we will go meet her Wednesday at the train station .</td>
      <td style="text-align: left">P237:We're in the premier division and we intend to stay there .</td>
    </tr>
  
    <tr>
      <th style="text-align: left"><strong>reference audios</strong></th>
      <td style="text-align: left"><audio src="wavs\GT\unseen\Frankly , it was worth the booking ._p238.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\GT\unseen\The project has already secured the support of Sir Sean Connery ._p237.wav" controls="" preload=""></audio></td>
    </tr>
  
    <tr>
      <th style="text-align: left"><strong>Ground Truth</strong></th>
      <td style="text-align: left"><audio src="wavs\GT\unseen\She can scoop these things into three red bags , and we will go meet her Wednesday at the train station ._p238.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\GT\unseen\We're in the premier division and we intend to stay there ._p237.wav" controls="" preload=""></audio></td>
    </tr>
    <tr>
      <th style="text-align: left"><strong>StyleSpeech</strong></th>
      <td style="text-align: left"><audio src="wavs\StyleSpeech\unseen\She can scoop these things into three red bags , and we will go meet her Wednesday at the train station ._p238.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\StyleSpeech\unseen\We're in the premier division and we intend to stay there ._p237.wav" controls="" preload=""></audio></td>
    </tr>
    <tr>
      <th style="text-align: left"><strong>Meta-StyleSpeech</strong></th>
      <td style="text-align: left"><audio src="wavs\Meta-StyleSpeech\unseen\VCTK\She can scoop these things into three red bags , and we will go meet her Wednesday at the train station ._p238.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\Meta-StyleSpeech\unseen\VCTK\We're in the premier division and we intend to stay there ._p237.wav" controls="" preload=""></audio></td>
    </tr>
    <tr>
      <th style="text-align: left"><strong>MRMI-TTS w/o discriminator</strong></th>
      <td style="text-align: left"><audio src="wavs\withou_D\unseen\She can scoop these things into three red bags , and we will go meet her Wednesday at the train station ._p238.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\withou_D\unseen\We're in the premier division and we intend to stay there ._p237.wav" controls="" preload=""></audio></td>      
    </tr>
  <tr>
      <th style="text-align: left"><strong>MRMI-TTS w/o MI</strong></th>
      <td style="text-align: left"><audio src="wavs\without_MI\She can scoop these things into three red bags , and we will go meet her Wednesday at the train station ._p238.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\without_MI\We're in the premier division and we intend to stay there ._p237.wav" controls="" preload=""></audio></td>      
    </tr>
    <tr>
      <th style="text-align: left"><strong>MRMI-TTS</strong></th>
      <td style="text-align: left"><audio src="wavs\ours\unseen\She can scoop these things into three red bags , and we will go meet her Wednesday at the train station ._p238.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\ours\unseen\We're in the premier division and we intend to stay there ._p237.wav" controls="" preload=""></audio></td>      
    </tr>
</table>

<h3> Using three reference audios, reference audios from LibriTTS </h3>
<table>
    <tr>
      <th style="text-align: left">Models</th>
      <td style="text-align: left">P3570:Wednesday night was a difficult time for Britton .</td>
      <td style="text-align: left">P4077:Wednesday night was a difficult time for Britton .</td>
    </tr>
  
    <tr>
      <th style="text-align: left"><strong>reference audios</strong></th>
      <td style="text-align: left"><audio src="wavs\GT\unseen\3570_5696_000002_000000.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\GT\unseen\4077_13751_000019_000005.wav" controls="" preload=""></audio></td>
    </tr>
  
    <tr>
      <th style="text-align: left"><strong>StyleSpeech</strong></th>
      <td style="text-align: left"><audio src="wavs\StyleSpeech\unseen\Wednesday night was a difficult time for Britton . -LibriTTS-3570.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\StyleSpeech\unseen\Wednesday night was a difficult time for Britton . -LibriTTS-4077.wav" controls="" preload=""></audio></td>
    </tr>
  
    <tr>
      <th style="text-align: left"><strong>Meta-StyleSpeech</strong></th>
      <td style="text-align: left"><audio src="wavs\Meta-StyleSpeech\unseen\LibriTTS\Wednesday night was a difficult time for Britton . -LibriTTS-3570.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\Meta-StyleSpeech\unseen\LibriTTS\Wednesday night was a difficult time for Britton . -LibriTTS-4077.wav" controls="" preload=""></audio></td>
    </tr>
  
    <tr>
      <th style="text-align: left"><strong>MRMI-TTS w/o discriminator</strong></th>
      <td style="text-align: left"><audio src="wavs\withou_D\unseen\Wednesday night was a difficult time for Britton . _LibriTTS-3570.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\withou_D\unseen\Wednesday night was a difficult time for Britton . _LibriTTS-4077.wav" controls="" preload=""></audio></td>      
    </tr>
    <tr>
      <th style="text-align: left"><strong>MRMI-TTS w/o MI</strong></th>
          <td style="text-align: left"><audio src="wavs\without_MI\Wednesday night was a difficult time for Britton ._P3570.wav" controls="" preload=""></audio></td>
          <td style="text-align: left"><audio src="wavs\without_MI\Wednesday night was a difficult time for Britton ._P4077.wav" controls="" preload=""></audio></td>      
    </tr>
  
    <tr>
      <th style="text-align: left"><strong>MRMI-TTS</strong></th>
      <td style="text-align: left"><audio src="wavs\ours\unseen\Wednesday night was a difficult time for Britton . _LibriTTS-3570.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\ours\unseen\Wednesday night was a difficult time for Britton . _LibriTTS-4077.wav" controls="" preload=""></audio></td>      
    </tr>
</table>

 <h3> Using three reference audios, reference audios from AISHELL3 </h3>
<table>
    <tr>
      <th style="text-align: left">Models</th>
      <td style="text-align: left">SSB0005:Wednesday night was a difficult time for Britton .</td>
      <td style="text-align: left">SSB0535:Wednesday night was a difficult time for Britton .</td>
    </tr>
  
    <tr>
      <th style="text-align: left"><strong>reference audios</strong></th>
      <td style="text-align: left"><audio src="wavs\GT\unseen\SSB00050001.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\GT\unseen\SSB05350003.wav" controls="" preload=""></audio></td>
    </tr>
    <tr>
      <th style="text-align: left"><strong>StyleSpeech</strong></th>
      <td style="text-align: left"><audio src="wavs\StyleSpeech\unseen\Wednesday night was a difficult time for Britton . -SSB0005.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\StyleSpeech\unseen\Wednesday night was a difficult time for Britton .-SSB0535.wav" controls="" preload=""></audio></td>
    </tr>
    <tr>
      <th style="text-align: left"><strong>Meta-StyleSpeech</strong></th>
      <td style="text-align: left"><audio src="wavs\Meta-StyleSpeech\unseen\AISHELL3\Wednesday night was a difficult time for Britton . -SSB0005.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\Meta-StyleSpeech\unseen\AISHELL3\Wednesday night was a difficult time for Britton .-SSB0535.wav" controls="" preload=""></audio></td>
    </tr>
    <tr>
      <th style="text-align: left"><strong>MRMI-TTS w/o discriminator</strong></th>
      <td style="text-align: left"><audio src="wavs\withou_D\unseen\Wednesday night was a difficult time for Britton . _SSB0005.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\withou_D\unseen\Wednesday night was a difficult time for Britton ._SSB0535.wav" controls="" preload=""></audio></td>      
    </tr>
  <tr>
      <th style="text-align: left"><strong>MRMI-TTS w/o MI</strong></th>
      <td style="text-align: left"><audio src="wavs\without_MI\Wednesday night was a difficult time for Britton ._SSB0005.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\without_MI\Wednesday night was a difficult time for Britton ._SSB0535.wav" controls="" preload=""></audio></td>      
    </tr>
    <tr>
      <th style="text-align: left"><strong>MRMI-TTS</strong></th>
      <td style="text-align: left"><audio src="wavs\ours\unseen\Wednesday night was a difficult time for Britton . _SSB0005.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\ours\unseen\Wednesday night was a difficult time for Britton ._SSB0535.wav" controls="" preload=""></audio></td>      
    </tr>
</table>
    
    
<h2>3. Synthesized samples -- different number of reference audios <a name="samples-unseen"></a></h2>
<table>
  <tr>
      <th style="text-align: left"><strong>models</strong></th>
      <td style="text-align: left">1 ref</td>
      <td style="text-align: left">3 ref</td>     
      <td style="text-align: left">5 ref</td>
  </tr>
  
  <tr>
      <th style="text-align: left"><strong>MIMR-TTS</strong></th>
      <td style="text-align: left"><audio src="wavs\ours\multi\p230_002.wav" controls="" preload=""></audio></td>    
  </tr>
  
  <tr>
      <th style="text-align: left"><strong>ours</strong></th>
      <td style="text-align: left"><audio src="wavs\ours\multi\Ask her to bring these things with her from the store.  _P230_1.wav" controls="" preload=""></audio></td>
      <td style="text-align: left"><audio src="wavs\ours\multi\Ask her to bring these things with her from the store.  _P230_3.wav" controls="" preload=""></audio></td> 
      <td style="text-align: left"><audio src="wavs\ours\multi\Ask her to bring these things with her from the store.  _P230_5.wav" controls="" preload=""></audio></td> 
    </tr>
  
</table>
  </body>
</html>


