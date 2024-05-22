# Unified Speech-Text Pretraining for Spoken Dialog Modeling

## Abstract
While recent work shows promising results in expanding the capabilities of large language models (LLM) to directly understand and synthesize speech, an LLM-based strategy for modeling spoken dialogs remains elusive and calls for further investigation. This paper introduces an extensive speech-text LLM framework, the Unified Spoken Dialog Model (USDM), designed to generate coherent spoken responses with naturally occurring prosodic features relevant to the given input speech without relying on explicit automatic speech recognition (ASR) or text-to-speech (TTS) systems. We have verified the inclusion of prosody in speech tokens known to predominantly contain semantic information and have used this foundation to construct a prosody-infused speech-text model. Additionally, we propose a generalized speech-text pretraining scheme that enhances the capture of cross-modal semantics. To construct USDM, we fine-tune our speech-text model on spoken dialog data using a multi-step spoken dialog template that stimulates the chain-of-reasoning capabilities exhibited by the underlying LLM. Automatic and human evaluations on the DailyTalk dataset demonstrate that our approach effectively generates natural-sounding spoken responses, surpassing previous and cascaded baselines. We will make our code and checkpoints available.

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
