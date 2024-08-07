# Integrating Paralinguistics in Speech-Empowered Large Language Models for Natural Conversation

## Abstract
Recent work shows promising results in expanding the capabilities of large language models (LLM) to directly understand and synthesize speech. However, an LLM-based strategy for modeling spoken dialogs remains elusive, calling for further investigation. This paper introduces an extensive speech-text LLM framework, the Unified Spoken Dialog Model (USDM), designed to generate coherent spoken responses with naturally occurring prosodic features relevant to the given input speech without relying on explicit automatic speech recognition (ASR) or text-to-speech (TTS) systems. We have verified the inclusion of prosody in speech tokens that predominantly contain semantic information and have used this foundation to construct a prosody-infused speech-text model. Additionally, we propose a generalized speech-text pretraining scheme that enhances the capture of cross-modal semantics. To construct USDM, we fine-tune our speech-text model on spoken dialog data using a multi-step spoken dialog template that stimulates the chain-of-reasoning capabilities exhibited by the underlying LLM. Automatic and human evaluations on the DailyTalk dataset demonstrate that our approach effectively generates natural-sounding spoken responses, surpassing previous and cascaded baselines. We will make our code and checkpoints publicly available.

---

## Additional Samples For Rebuttal 
### Some listening examples of zero-shot TTS are recommeneded (Reviewer 4xzH)
**We performed zero-shot TTS using the emotional dataset from the TextrolSpeech dataset, which was unseen during training, as the reference audio.**

<details>
<summary><span style="color:black">Click here to view the transcript. </span></summary>
Sample 1 Transcript: it is our doom the great sacrifice at the end of the dark season <br>
Sample 2 Transcript: it was as if the good god himself intervened to save you <br>
Sample 3 Transcript: you are not going in blind <br>
Sample 4 Transcript: sending him into panic stricken flight <br>
Sample 5 Transcript: i looked for some great change <br>
Sample 6 Transcript: dick stepped into the narrow path cut in the side of the ravine and inhaled more draughts of the fresh air <br>
Sample 7 Transcript: dick stepped into the narrow path cut in the side of the ravine and inhaled more draughts of the fresh air <br>
Sample 8 Transcript: but were to be on their guard <br>
Sample 9 Transcript: it was as if the good god himself intervened to save you <br>
</details>

<table>
   <thead>
      <tr>
         <th style="text-align: center"></th>
         <th style="text-align: center">Sample 1</th>
         <th style="text-align: center">Sample 2</th>
         <th style="text-align: center">Sample 3</th>
         <th style="text-align: center">Sample 4</th>
         <th style="text-align: center">Sample 5</th>
         <th style="text-align: center">Sample 6</th>
         <th style="text-align: center">Sample 7</th>
         <th style="text-align: center">Sample 8</th>
         <th style="text-align: center">Sample 9</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <th style="text-align: center">Reference</th>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/1_ref.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/2_ref.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/3_ref.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/4_ref.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/5_ref.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/6_ref.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/7_ref.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/8_ref.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/9_ref.wav" type="audio/wav"></audio></td>
      </tr>
   </tbody>
   <tbody>
      <tr>
         <th style="text-align: center">Generated Sample</th>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/1_gen.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/2_gen.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/3_gen.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/4_gen.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/5_gen.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/6_gen.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/7_gen.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/8_gen.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Emotional_dataset_zero-shot/9_gen.wav" type="audio/wav"></audio></td>
      </tr>
   </tbody>
</table>
<br>

### Emotional Control Exploration (Reviewer yvFi)
**We fine-tuned USDM using the MultiDialog dataset. To add emotion controllability, we modified our template from speech1 -> text1 -> text2 -> speech2 to speech1 -> text1 \<emotion1\> -> \<emotion2\> text2 -> speech2. Emotion control is achieved by setting \<emotion2\> to our desired emotion during inference.** <br>

**Upon our review, we found that MultiDialog contains many instances where the speech and ground truth emotion labels are not well aligned, or the emotion labels are only reflected in the text, which hinders the model's ability to accurately reflect emotions in the generated spoken responses. Currently, the only publicly available dialog dataset we can explore the possibility of emotional control is MultiDialog, so we used it to demonstrate the potential of our model. We ask for your understanding if the emotions in the generated samples appear subtle.**

#### Sample 1
Input User Audio
<audio controls>
  <source src="wavs/Multidialog_model_generated/1_user.wav" type="audio/wav">
</audio>

User (Ground Truth): what was the score to that eighty - zero?<br>

<br>**Generated Text Response (Surprised)**: \<Surprised\> Wow! I haven't heard a score like that since World War two.
<br>**Generated Text Response (Sad)**: \<Sad\> What a score! I wish I could have been the one to receive that payout!
<br>**Generated Text Response (Disgusted)**: \<Disgusted\> Something like that! How can a team not score for over four hours?

<table>
   <thead>
      <tr>
         <th style="text-align: center">Surprised </th>
         <th style="text-align: center">Sad</th>
         <th style="text-align: center">Disgusted</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Multidialog_model_generated/1_surprised.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Multidialog_model_generated/1_sad.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Multidialog_model_generated/1_disgusted.wav" type="audio/wav"></audio></td>
      </tr>
   </tbody>
</table>
<br>

#### Sample 2
Input User Audio
<audio controls>
  <source src="wavs/Multidialog_model_generated/3_user.wav" type="audio/wav">
</audio>

User (Ground Truth): Yeah I guess. How about that seventies show, did you ever watch it? <br>

<br>**Generated Text Response (Happy)**: \<Happy\> I used to watch it all the time when I was a kid. I love Jim Carrey and the role he played in it.
<br>**Generated Text Response (Sad)**: \<Sad\> I used to watch it all the time and it's sad to think that there will be no more new episodes.
<br>**Generated Text Response (Fearful)**: \<Fearful\> I remember it being on, we watched a season or two but lost interest in later shows. This is scary: Netflix has one hundred and fifty movies with a one hundred percent rating on Rotten Tomatoes. What's with Netflix? Are they a monster?

<table>
   <thead>
      <tr>
         <th style="text-align: center">Happy </th>
         <th style="text-align: center">Sad</th>
         <th style="text-align: center">Fearful</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Multidialog_model_generated/3_happy.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Multidialog_model_generated/3_sad.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Multidialog_model_generated/3_fearful.wav" type="audio/wav"></audio></td>
      </tr>
   </tbody>
</table>
<br>

#### Sample 3
Input User Audio
<audio controls>
  <source src="wavs/Multidialog_model_generated/2_user.wav" type="audio/wav">
</audio>

User (Ground Truth): I know that just does not make sense at all. I wonder why they do that <br>

<br>**Generated Text Response (Angry)**: \<Angry\> They are the highest paid athletes in the world by annual salary. They also have the most expensive team in the NFL. Yet they don't have the best record in the league...
<br>**Generated Text Response (Neutral)**: \<Neutral\> Who knows? It's been around since the sixties. Maybe it was easier to control the women back then?
<br>**_FAILURE CASE_, Generated Text Response (Surprised)**: \<Surprised\> The Saints cheerleaders in New Orleans have a separate restaurant than the players. They also have a separate room at the stadium to eat in.

<table>
   <thead>
      <tr>
         <th style="text-align: center">Angry</th>
         <th style="text-align: center">Neutral</th>
         <th style="text-align: center">Surprised</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Multidialog_model_generated/2_angry.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Multidialog_model_generated/2_neutral.wav" type="audio/wav"></audio></td>
         <td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/Multidialog_model_generated/2_surprised.wav" type="audio/wav"></audio></td>
      </tr>
   </tbody>
</table>
<br>

---

## Additional Samples For Various Scenarios (Appendix A.1)
### Expressive Spoken Dialog Dataset (Expresso)
 **Since there were no transcripts for Expresso, we used _whisper-large-v3_ to obtain transcripts corresponding to the dataset and used them for training.**

#### Sample 1
Input User Audio
<audio controls>
  <source src="wavs/Expresso_model_generated/1_user.wav" type="audio/wav">
</audio>

User (Ground Truth): It's a very good way to put it. Yeah. He was he was part of the family. No other there's no other cat like like him. I don't. don't. Really imagine who's ever. been replacing him.<br>

<br>**Generated Text Response**: Yeah. I mean, I know he was a bit of a pain in the butt, but, I mean, I don't think anybody could ever replace him. He was just that one of a kind of

**Generated Spoken Response**

<audio controls>
  <source src="wavs/Expresso_model_generated/1_usdm.wav" type="audio/wav">
</audio>
<br>

#### Sample 2
Input User Audio
<audio controls>
  <source src="wavs/Expresso_model_generated/2_user.wav" type="audio/wav">
</audio>

User (Ground Truth): Oh my gosh. Could he? Tell me about it. Remember when you used to make cookies and he would intentionally bat it around with his paws? He'd he'd get in the dough, and we'd have to throw everything out again.<br>

<br>**Generated Text Response**: Yeah. That was a lot of wasted dough and a lot of waste time and energy. That was not a good stretch of our resources here on Earth. Yeah.

**Generated Spoken Response**

<audio controls>
  <source src="wavs/Expresso_model_generated/2_usdm.wav" type="audio/wav">
</audio>
<br>

#### Sample 3
Input User Audio
<audio controls>
  <source src="wavs/Expresso_model_generated/3_user.wav" type="audio/wav">
</audio>

User (Ground Truth): Does anybody want to hear about this? This is not a good thing to tell people about.<br>

<br>**Generated Text Response**: I don't think it does sound like a good thing to tell people about.

**Generated Spoken Response**

<audio controls>
  <source src="wavs/Expresso_model_generated/3_usdm.wav" type="audio/wav">
</audio>
<br>

### Multi-Turn Scenarios (Fisher)
 **All the speakers below are not seen during training.**

#### Sample 1
Input Multi-turn Spoken Dialogues

<audio controls>
  <source src="wavs/Fisher_model_generated/1_user.wav" type="audio/wav">
</audio>
A: Oh.<br>
B: Yeah. So when we were in Florida, Orlando Magic, basketball was the big thing because of Shaquille O'Neil.<br>
A: I see.<br>
B: But then he got mad at everybody and left us and went to the Lakers. [LAUGH].<br>
A: [LAUGH]. So you were kinda involved in basketball too, then?<br>

<br>**Generated Text Response**: Yeah, yeah. And um, but then when he went to the Lakers, that was kinda sad. It's like, oh, no. [LAUGH].

**Generated Spoken Response**

<audio controls>
  <source src="wavs/Fisher_model_generated/1_usdm.wav" type="audio/wav">
</audio>
<br>

#### Sample 2
Input Multi-turn Spoken Dialogues
<audio controls>
  <source src="wavs/Fisher_model_generated/2_user.wav" type="audio/wav">
</audio>
B: Oh no [LAUGH] Did you switch over or try to press another thing?<br>
A: No, it we were talking, and boom, she was gone and I was gone off her line.<br>
B: Oh go- maybe she did something.<br>
A: Oh.<br>
B: Maybe she hung up or did something happened with her phone so they probably disconnected the both of you.<br>
A: So I gotta start all over again. [LAUGH]<br>
B: Yeah. [LAUGH] Oh gosh. Um, so what did you talk about last time was it just<br>

<br>**Generated Text Response**: Oh, it was about sports.

**Generated Spoken Response**
<audio controls>

  <source src="wavs/Fisher_model_generated/2_usdm.wav" type="audio/wav">
</audio>
<br>

#### Sample 3 
Input Multi-turn Spoken Dialogues
<audio controls>
  <source src="wavs/Fisher_model_generated/3_user.wav" type="audio/wav">
</audio>
B: How did you get into it?<br>
A: Ah, I was in a forum and, ah, some guys were talking about it, so I checked it out and I just signed up for it. Thought, "What the heck". Um, man this thing is, ah I can barely hear you. Can you hear me all right?<br>
B: Yeah. [COUGH] But I'm on a cell phone, so maybe that's why.<br>

<br>**Generated Text Response**: Oh, okay. Yeah, maybe because I keep getting disconnected.

**Generated Spoken Response**
<audio controls>

  <source src="wavs/Fisher_model_generated/3_usdm.wav" type="audio/wav">
</audio>
<br>

#### Sample 4
Input Multi-turn Spoken Dialogues
<audio controls>
  <source src="wavs/Fisher_model_generated/4_user.wav" type="audio/wav">
</audio>
A: Oh.<br>
B: So that's been from Chapel Hill so it's been a it's been a big move for me and, you know, I guess the conversations kind of, ah, you know, it the friendship thing is it kind of connects here because I left a lot of friends behind. But, you know, I still try to keep in touch with them and I've made some new friends in LA and I've got a lot of friends up in San- San Francisco.<br>
A: Okay. Are you mo- are you moving there for a job?<br>

<br>**Generated Text Response**: No. I just kinda I just kinda wanted to go to college up there. I wanted to go to college in San Jose. So.

**Generated Spoken Response** 
<audio controls>
  <source src="wavs/Fisher_model_generated/4_usdm.wav" type="audio/wav">
</audio>
<br><br>

---

## Model Comparison (DailyTalk, Section 4.1.2)

**All samples for DailyTalk resampled to 16kHz.**

### Spoken Response (with model-generated text response)

#### Sample 1
Input User Audio
<audio controls>
  <source src="wavs/DailyTalk_model_generated/1_user.wav" type="audio/wav">
</audio>

User: thank you. so what do you think? would we have a good time?

<table>
	<thead>
		<tr>
			<th style="text-align: center">Ground Truth</th>
			<th style="text-align: center">USDM </th>
			<th style="text-align: center">From Scratch</th>
			<th style="text-align: center">Cascaded</th>
			<th style="text-align: center">SpeechGPT</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_model_generated/1_ground_truth.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_model_generated/1_usdm.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_model_generated/1_from_scratch.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_model_generated/1_cascaded.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_model_generated/1_speechgpt.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>
<br>

#### Sample 2
Input User Audio
<audio controls>
  <source src="wavs/DailyTalk_model_generated/2_user.wav" type="audio/wav">
</audio>

User: the stone is a prehistoric log. it was turned to stone millions of years ago.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Ground Truth</th>
			<th style="text-align: center">USDM </th>
			<th style="text-align: center">From Scratch</th>
			<th style="text-align: center">Cascaded</th>
			<th style="text-align: center">SpeechGPT</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_model_generated/2_ground_truth.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_model_generated/2_usdm.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_model_generated/2_from_scratch.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_model_generated/2_cascaded.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_model_generated/2_speechgpt.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>
<br>

#### Sample 3
Input User Audio
<audio controls>
  <source src="wavs/DailyTalk_model_generated/3_user.wav" type="audio/wav">
</audio>

User: great. shall i meet you there around seven forty-five tomorrow night?

<table>
	<thead>
		<tr>
			<th style="text-align: center">Ground Truth</th>
			<th style="text-align: center">USDM </th>
			<th style="text-align: center">From Scratch</th>
			<th style="text-align: center">Cascaded</th>
			<th style="text-align: center">SpeechGPT</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_model_generated/3_ground_truth.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_model_generated/3_usdm.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_model_generated/3_from_scratch.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_model_generated/3_cascaded.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_model_generated/3_speechgpt.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>
<br>

### Spoken responses (with ground-truth text response)
#### Sample 1
Input User Audio
<audio controls>
  <source src="wavs/DailyTalk_ground_truth_text/1_user.wav" type="audio/wav">
</audio>

User: are you even glad that we get to buy new clothes too?

Text to generate: **ah, that's all part of the fun. what do you think of these shorts?**

<table>
	<thead>
		<tr>
			<th style="text-align: center">Ground Truth</th>
			<th style="text-align: center">USDM </th>
			<th style="text-align: center">From Scratch</th>
			<th style="text-align: center">Cascaded</th>
			<th style="text-align: center">SpeechGPT</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_ground_truth_text/1_ground_truth.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_ground_truth_text/1_usdm.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_ground_truth_text/1_from_scratch.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_ground_truth_text/1_cascaded.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_ground_truth_text/1_speechgpt.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

<br>

#### Sample 2
Input User Audio
<audio controls>
  <source src="wavs/DailyTalk_ground_truth_text/2_user.wav" type="audio/wav">
</audio>
User: the checkroom is just behind the front door.

Text to generate: **ok. i will deposit my bag right now.**

<table>
	<thead>
		<tr>
			<th style="text-align: center">Ground Truth</th>
			<th style="text-align: center">USDM </th>
			<th style="text-align: center">From Scratch</th>
			<th style="text-align: center">Cascaded</th>
			<th style="text-align: center">SpeechGPT</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_ground_truth_text/2_ground_truth.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_ground_truth_text/2_usdm.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_ground_truth_text/2_from_scratch.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_ground_truth_text/2_cascaded.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_ground_truth_text/2_speechgpt.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

<br>

#### Sample 3
Input User Audio
<audio controls>
  <source src="wavs/DailyTalk_ground_truth_text/3_user.wav" type="audio/wav">
</audio>
User: a garage sale... that's where people check out cars, right?

Text to generate: **what? cars? umm are you serious?**

<table>
	<thead>
		<tr>
			<th style="text-align: center">Ground Truth</th>
			<th style="text-align: center">USDM </th>
			<th style="text-align: center">From Scratch</th>
			<th style="text-align: center">Cascaded</th>
			<th style="text-align: center">SpeechGPT</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_ground_truth_text/3_ground_truth.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_ground_truth_text/3_usdm.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_ground_truth_text/3_from_scratch.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_ground_truth_text/3_cascaded.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/DailyTalk_ground_truth_text/3_speechgpt.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>
<br>

---

## Unit-to-Speech Reconstruction Analysis (Section 3.1)
 **We extracted XLS-R based unit from the original audio, and then only those units to reconstruct the audio 3 times.** <br>
 **Through that sample, we can understand what information is contained in the units.** <br>
 **We used speech from Expresso (Nguyen et al., 2023), Fisher (Cieri et al., 2004), and GigaSpeech (Chen et al., 2021) datasets.**
 
#### Sample 1
<table>
	<thead>
		<tr>
			<th style="text-align: center">Ground Truth</th>
			<th style="text-align: center">Reconstructed Audio 1 </th>
			<th style="text-align: center">Reconstructed Audio 2</th>
			<th style="text-align: center">Reconstructed Audio 3</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/unit-based-Voicebox/1_ground_truth.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/unit-based-Voicebox/1_reconstructed_1.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/unit-based-Voicebox/1_reconstructed_2.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/unit-based-Voicebox/1_reconstructed_3.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table> 

#### Sample 2
<table>
	<thead>
		<tr>
			<th style="text-align: center">Ground Truth</th>
			<th style="text-align: center">Reconstructed Audio 1 </th>
			<th style="text-align: center">Reconstructed Audio 2</th>
			<th style="text-align: center">Reconstructed Audio 3</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/unit-based-Voicebox/2_ground_truth.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/unit-based-Voicebox/2_reconstructed_1.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/unit-based-Voicebox/2_reconstructed_2.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/unit-based-Voicebox/2_reconstructed_3.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table> 

#### Sample 3
<table>
	<thead>
		<tr>
			<th style="text-align: center">Ground Truth</th>
			<th style="text-align: center">Reconstructed Audio 1 </th>
			<th style="text-align: center">Reconstructed Audio 2</th>
			<th style="text-align: center">Reconstructed Audio 3</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/unit-based-Voicebox/3_ground_truth.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/unit-based-Voicebox/3_reconstructed_1.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/unit-based-Voicebox/3_reconstructed_2.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/unit-based-Voicebox/3_reconstructed_3.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>
