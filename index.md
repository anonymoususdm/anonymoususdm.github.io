# Unified Speech-Text Pretraining for Spoken Dialog Modeling

## Abstract

TO DO


## Model Comparison (DailyTalk)

**All samples for DailyTalk resampled to 16kHz.**

### Model-generated responses

#### Sample 1
Input User Audio
<audio controls>
  <source src="wavs/DailyTalk_model_generated/1_user.wav" type="audio/wav">
</audio>

User: Not everyone. But a lot of people do, especially the young. It's a fine place to spend an evening with friends or to make some new friends.

<table>
	<thead>
		<tr>
			<th style="text-align: center">Ground Truth</th>
			<th style="text-align: center">UDSM </th>
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

User: I’m very well, Thank you. And you?

<table>
	<thead>
		<tr>
			<th style="text-align: center">Ground Truth</th>
			<th style="text-align: center">UDSM </th>
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

User: Yes, do you like it?

<table>
	<thead>
		<tr>
			<th style="text-align: center">Ground Truth</th>
			<th style="text-align: center">UDSM </th>
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

### Ground-truth text responses
#### Sample 1
Input User Audio
<audio controls>
  <source src="wavs/DailyTalk_ground_truth_text/1_user.wav" type="audio/wav">
</audio>

User: Linda? Is that you? I haven't seen you in ages!

Text to generate: **Hi George! It's good to see you!**

<table>
	<thead>
		<tr>
			<th style="text-align: center">Ground Truth</th>
			<th style="text-align: center">UDSM </th>
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
User: We are all very proud of you.

Text to generate: **I am very happy, too. It was a big game and I won.**

<table>
	<thead>
		<tr>
			<th style="text-align: center">Ground Truth</th>
			<th style="text-align: center">UDSM </th>
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
User: Ah, that's all part of the fun. What do you think of these shorts?

Text to generate: **They look really good on you. They look comfortable too.**

<table>
	<thead>
		<tr>
			<th style="text-align: center">Ground Truth</th>
			<th style="text-align: center">UDSM </th>
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

## Multi-Turn Scenarios (Fisher)
 **All the speakers below are now seen during training.**

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

**Generated Spoken Response** 
<audio controls>
  <source src="wavs/Fisher_model_generated/4_usdm.wav" type="audio/wav">
</audio>
<br><br>

## Unit-to-Speech Reconstruction Analysis
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
