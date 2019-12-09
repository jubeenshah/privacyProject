Overview
========

We highly recommend you to download the latest version of the corpus at https://www.usableprivacy.org/data.

This dataset includes annotations for opt-out choices types for sentences present in Website Privacy Policies. Opt-out choices enable users to opt-out of services such as e-mail communication, data sharing, targeted advertisement, analytics etc. An example of an opt-out hyperlink present in a website privacy policy is given below:

'��If you would like more information on how to opt out of information collection practices, go towww.aboutads.info'

For this dataset, we selected 102 sentence instances containing hyperlinks from 115 website privacy policies. The 115 privacy policies are the same as the ones present in the OPP-115 Corpus, which is is a corpus consisting of 115 website privacy policies and annotations (created by law students) for data practices that appear in them.

Annotation Scheme
=================
Each sentence instance was annotated by three annotators. Each of the 102 sentence instances was given labels for two independent categories.

Category 1 - Party Offering Choice. This indicates the party offering the opt-out choice and could be one of the following :-
(1) FI: First Party
(2) TH: Third Party
(3) BR: Browser

Category 2 - Purpose : This indicates the purpose of opt-out and could be one of the following :-
(1) AD: manage or opt-out of advertising, e.g., opt-out of some ads, all ads, targeted ads, ad tracking
(2) CM: manage or opt-out of communication
(3) SH: manage or opt-out of data sharing
(4) CK: manage or opt-out of cookies
(5) AN: manage or opt-out of analytics
(6) OT: other

In addition to these tags, we also had two tags for both categories:
NA: If the sentence instance was not an opt-out sentence
XX: If the sentence instance was not useful for training

Documentation
=============
This section explains the archive contents and the files included. The archive contains the following:

-SanitizedPrivacyPolicies: This folder contains html files of 115 privacy policies that were sanitized by removing all html content except hyperlink tags(<a>) and some other formatting tags such as <strong> etc. Further, these are divided into segments that are delimited by “|||”.

-PolicyDict.json: This is a python dictionary serialized using json format. The dictionary stores the mapping of the policy id to the policy file present in the SanitizedPrivacyPolicies Folder.

-SegmentDict.json: The privacy policies are divided into segments, roughly corresponding to paragraphs. This is a python dictionary serialized using json format. The dictionary stores the mapping of the unique segment id to the segment text. Segment id consists of the policy number, segment number in policy

-SentenceDict.json: Segments are further divided into sentences. This is a python dictionary serialized using json format. The dictionary stores the mapping of the unique sentence id to the sentence text. Sentence id consists of the policy number, segment number in policy, sentence number in segment.

-HyperlinkDict.json: This is a python dictionary serialized using json format. The dictionary stores the mapping of the unique hyperlink id to a list containing the hyperlink url and anchor text. The hyperlink id consists of the policy number, segment number in policy, sentence number in segment and the hyperlink number in sentence.

All the above numbers are 0 indexed.

-OptOutTypeDataset.csv: This stores the annotations for the two categories according the the schema presented above for 102 sentence instances containing hyperlinks.

-README.md

OptOutTypeDataset.csv
=====================
This section describes the format of the file OptOutTypeDataset.csv . This is a csv file with each line corresponding to once instance being annotated and contains the following values in the same order:
(1) Unique Hyperlink id: This is of the form '��Policy number, segment number in policy, sentence number in segment, hyperlink number in sentence' and is unique for all instances.
(2) Party Offering Choice-Annotator 1: This is the annotation for the category Party Offering Choice by Annotator 1.
(3) Party Offering Choice-Annotator 2: This is the annotation for the category Party Offering Choice by Annotator 2.
(4) Party Offering Choice-Annotator 3: This is the annotation for the category Party Offering Choice by Annotator 3.
(5) Party Offering Choice-Resolved: This is the resolved annotation for the category Party Offering Choice. This is based on the majority vote by the three annotators. In case of a tie, the three annotatores mutually agreed on one annotation after discussion.
(6) Purpose-Annotator 1: This is the annotation for the category Purpose by Annotator 1.
(7) Purpose-Annotator 2: This is the annotation for the category Purpose by Annotator 2.
(8) Purpose-Annotator 3: This is the annotation for the category Purpose by Annotator 3.
(9) Purpose-Resolved: This is the resolved annotation for the category Purpose. This is based on the majority vote by the three annotators. In case of a tie, the three annotators mutually agreed on one annotation after discussion.
(10) Sentence: This is the content of the sentence being annotated.
(11) Anchor Text: This is the anchor text associated with the hyperlink present in the sentence that is being annotated
(12) Hyperlink: This is the hyperlink url in the sentence being annotated.
(13) Segment Text: This is the text from the segment in which the sentence being annotated is present.
(14) Policy Name: This is the name of the policy which the sentence is part of.

Licensing Terms
=============
The dataset is made available for research, teaching, and scholarship purposes only, with further parameters in the spirit of a Creative Commons Attribution-NonCommercial License. Contact Prof. Norman Sadeh (sadeh@cs.cmu.edu) with any questions.

If you use this dataset as part of a publication, you must cite the following paper:

"Identifying the Provision of Choices in Privacy Policy Text. Kanthashree Mysore Sathyendra, Shomir Wilson, Florian Schaub, Sebastian Zimmeck and Norman Sadeh. In Proceedings of the 2017 Conference on Empirical Methods in Natural Language Processing September 7-11, 2017. Copenhagen, Denmark."

END
