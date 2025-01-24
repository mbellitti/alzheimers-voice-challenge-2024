# PREPARE Challenge - Phase 2: Acoustic Track
This is my submission for the [PREPARE challenge](https://www.drivendata.org/competitions/299/competition-nih-alzheimers-acoustic-2/announcements/), a competition created by the NIH and the National Institute of Aging to encourage the analysis of voice data in the study of Alzheimer's disease and related dementias.

The challenge ended on Dec 28th, 2024.

# The Dataset
The data consists of $N=1646$ voice recordings, in English[^1] (79%), Spanish (19%), and Chinese (2%). Most of the recordings (70%) are exactly 30 seconds long, with the remaning ones roughly uniformly distributed in length down to 1.15s. Basic demographic information -age and sex- is available for all participants.

The task performed by the study participants is not always the same:
- Most English speakers are heard describing the Cookie Theft picture from the Boston diagnostic aphasia examination, but in some cases we have recording of spontaneous speech (an unstructured phone call with an interviewer) or even short commands given to an electronic home assistant ("When is thanksgiving? What's the weather today?").
- Most Spanish speakers are reading the beginning of Don Quixote
- Most Chinese speakers are recorded during the Animal Naming Test.

As a consequence, the nature of the recorded speech is not uniform. This means that it is reasonably safe to use some acoustic voice features (but not pauses, for example), while we cannot use linguistic features.

# The Task
All the recordings are labeled as belonging to one of three classes: `control` cases, cases with mild cognitive impairment `mci`, and dementia due to Alzheimer's disease `adrd`. 

> **Warning:** all Chinese speakers are labeled as `mci`, which is probably a consequence of dataset construction. I suspect those participants were sampled from a study where mild cognitive impairment was part of the inclusion criteria.

[^1]: I automatically detected the language of the recording using [Whisper's](https://github.com/openai/whisper) `detect_language()` method.