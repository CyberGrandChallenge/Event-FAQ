# FAQ

The Cyber Grand Challenge will communicate with teams via this FAQ during the challenge events. The content will be copied into the master CGC FAQ post-event.

# CGC Final Event Trials

Q2: the "feedback/poll" TI-API has new functionality.  It returns 4 values (instead of the documented 3):  success:,  timeout:,  connect:, and function:. Where is the new functionality (“function:”) documented?

A2: Functionality data for poll/feedback is reported as four percentages:
 (1) percentage  of successful polls
 (2) percentage of polls that failed as a result of a timeout
 (3) percentage of polls that failed because a connect call failed
 (4) percentage of polls that failed due to CS functionality

This update will be reflected in an update to:
https://github.com/CyberGrandChallenge/cgc-release-documentation/blob/master/ti-api-spec.txt#L377


Q1: Are jumbo-frames supported in the DARPA cloud and CFE APIs?

A1: The CRS switch supports jumbo frames. The team gateway, which provides VPN and Internet access, does not support jumbo frames. The IDS tap and TI-API host do not support jumbo frames.



# CGC Qualification Event

Scheduled for June 3, 2015.

Q12: How do I verify my submissions?

A12: [The procedure is documented in the CGC Qualifier Event API Walk-though](https://github.com/CyberGrandChallenge/cgc-release-documentation/blob/master/walk-throughs/cgc-qualifier-event-api.md#verify-solution-submission). The referenced script can be downloaded from [Github](https://github.com/CyberGrandChallenge/cgc-release-documentation/blob/master/scripts/cqe_verify_solution_package.py).

Example:
```
cqe_submission_verification.py -c credentials.json -f "${csid}_${hash}.ar.enc" -e cgc_qualifier_event
```


Q11: As with all CGC scored events, CQE allows multiple submissions to the same csid, correct?

A11: Yes. Submit early; submit often. Only the latest valid submission to each csid will be considered for ranking purposes. For more information on ranking, see Section 3.1.3 of the CGC Rules.

Q10: What is the duration of CQE?

A10: CQE is a 24-hour event which concludes on June 4th, 2015, at 12:00 noon EDT (1600 UTC).

Q9: What is the name of the S3 submission bucket?

A9: Submissions should be uploaded to the "cgc_qualifier_event" bundle as documented in the [cgc-qualifier-event walkthrough](https://github.com/CyberGrandChallenge/cgc-release-documentation/blob/master/walk-throughs/cgc-qualifier-event-api.md). All teams should double check their submission bucket.


~~Q8: What is the name of the S3 submission bucket?~~

~~A8: Submissions should be uploaded to the "cqe_qualifier_event" bundle as documented in the [cgc-qualifier-event walkthrough](https://github.com/CyberGrandChallenge/cgc-release-documentation/blob/master/walk-throughs/cgc-qualifier-event-api.md). All teams should double check their submission bucket.~~

The Q8/A8 Event-FAQ entry contained a typo in the bucket name. See A9 for the correct bucket name.

Q7: What is the decryption key to the CQE challenge bundle?

A7: The key is: Ultimately, what separates a winner from a loser at the grandmaster level is the willingness to do the unthinkable. 5844659ce9891a09

The challenge bundle can be decrypted with the following command as found on [github](https://github.com/CyberGrandChallenge/cgc-release-documentation/tree/master/scripts): 

```
cqe_unpack_event_bundle.py -e cgc_qualifier_event.ar.gz.enc -p "Ultimately, what separates a winner from a loser at the grandmaster level is the willingness to do the unthinkable. 5844659ce9891a09"
```

Q6: Is the test_event bucket closed?

A6: Yes; All uploads are shuttered until 12:00 noon EST. Good luck to all our teams!

Q5: When we use netcat to connect to CADET_00001 and write a large number of characters it crashes, but when we create a POVML file which writes the same string to CADET_00001 it doesn't crash. Can you explain this behavior?

A5: The POVML format grants fine grained control of reads and writes to a CRS. The CADET_00001 protocol is a "server speaks first" protocol; a race condition occurs when the POVML transmits data to the server and then exits. When the race is "won" by the PoV, the PoV will close the socket first causing the CB's transmit to fail and thus exit cleanly before the PoV input can be received, processed or cause a crash. As with many race conditions, the result of this race is difficult to predict.

Q4: Which Challenge Sets will be excluded from computing CQE ranking?

A4: See [FAQ](https://cgc.darpa.mil/documents.aspx) A117. The proof of excluded CS selection is:

```
U2FsdGVkX1/21aa4u0ZhcTCAyGr8oX7aCimSvKfGG3HFvjy5sCWi7Dh0dY9mb2nizlldmCCeB7g2RbUv3R0PkvFVp+EeTeWj8MpTiBCP0cVS3/uXy2rWIZtkFpOYBXIqYdybwpawzlRshJ8BeA2/WCWBeupEhCWFjJT7XigmLyEZqIujQ/rsWJTLOTfWFWC0
```

Q3: An empty write in a PoV XML passes poll-validate but causes an exception in cb-replay; will this be fixed?

A3: A fix will be released in a future version of DECREE. During CQE, competitors are encouraged to refer to [FAQ](https://cgc.darpa.mil/documents.aspx) entry A111 with respect to debugging their CRS during the event. Prior to CQE, competitors are encouraged to ensure their CRS does not generate a PoV with an empty write statement similar to the below:

```
<write><data></data></write>
```


Q2: What is the official Twitter feed for the CGC Qualification Event?

A2: https://twitter.com/DARPA_CGC_CQE


Q1: How do I confirm that I am running the latest version of DECREE?

A1: In the last DECREE release email, a test [1] was issued to check the vagrant version. If your current system responds with the output cited below [1] [2], there is no need to update. If your system responds with different output, DARPA/CGC advises that you update.

[1] The expected output of vagrant ssh of an upgraded VM will be:
Linux cgc-linux-packer 3.13.2-cgc #1 SMP Mon Apr 13 18:33:57 UTC 2015 i686

[2] vagrant@cgc-linux-packer $ cat /etc/decree_version
cqe_development-vm-61


# Scored Event 2

Scheduled for April 16, 2015.

Q3: Can you confirm our observation that many PCAP files in the SE2 bundle appear to have extra, empty connections?

A3: Empty connections may be present. Services may occasionally receive no transport layer data. See also FAQ A85 at cgc.darpa.mil.

Q2: What is the decryption key to the second scored event challenge bundle?

A2: The key is: The will to succeed is important, but what's more important is the will to prepare.

The challenge bundle can be decrypted with the following command as found on [github](https://github.com/CyberGrandChallenge/cgc-release-documentation/tree/master/scripts): 

```
cqe_unpack_event_bundle.py -e scored_event_2.ar.gz.enc -p "The will to succeed is important, but what's more important is the will to prepare."
```

Q1: What is the official Twitter feed for CGC Scored Event 2?

A1: https://twitter.com/DARPACGCSEtwo



# Scored Event 1

FAQ entries from Scored Event 1 on December 2, 2014 have been moved into the official Cyber Grand Challenge FAQ hosted on https://cgc.darpa.mil/documents.aspx

Q12: What is the tiebreaker algorithm for CQE?

A12: DARPA is holding a period of public comment to discuss the proposed CQE tiebreaker algorithm contained in this FAQ entry as well as Scored Event scoring. Feedback should be addressed to cybergrandchallenge@darpa.mil. This will be open for a period of public comment concluding on February 26th, 2015. At the conclusion of the period of public comment, DARPA will announce the tiebreaker algorithm to be used in Scored Event #2.

This non-final CQE tiebreaker algorithm was used to break a tie in Scored Event #1.

The CQE tiebreaker algorithm will be applied in Scored Events and CQE. The tiebreaker algorithm will only be used:

On the scores of teams compliant with the CGC Rules including section 3.1.3
To rank a set of teams whose scores are equal prior to tiebreaking, and whose position occludes the 7th place slot in the event. For example, a tie for 1st and 2nd would not be subject to the tiebreaker, nor would a tie for 10th and 11th. A tie for rank 6th, 7th, 8th and 9th would be subject to the tiebreaker algorithm for ranking.

The tiebreaker algorithm will be executed in rounds (see below). At the conclusion of each round, teams will be ranked according to the results of that tiebreak round; a set of teams which are still tied per b) will be ranked using the next tiebreak round. For example if three teams are tied for 6th, 7th, and 8th, and tiebreak round one puts a team in 6th place but 7th and 8th are still tied, the second tiebreak round will apply only to the teams in 7th and 8th place.

Round One:

CQE scoring is recomputed per [A59](https://cgc.darpa.mil/documents.aspx) with the following modification: file size will be ignored when calculating Performance.

Round Two:

CQE scoring is recomputed per [A59](https://cgc.darpa.mil/documents.aspx) with the following modification: file size and memory usage will be ignored when calculating Performance.

Round Three: 

CQE scoring is recomputed per [A59](https://cgc.darpa.mil/documents.aspx) with the following modification: Performance will be ignored when calculating Availability.

Round Four: 

CQE scoring is recomputed per [A59](https://cgc.darpa.mil/documents.aspx) with the following modification: Performance will be ignored when calculating Availability. In addition, Evaluation will be set to 1.

Round Five:

CQE scoring is recomputed per [A59](https://cgc.darpa.mil/documents.aspx) with the following modification: Only the Evaluation score will be considered. The Availability and Security will be set to 1.

Round Six:

In the highly unlikely event that the tiebreaker reaches Round Six, DARPA will issue a ranking by expert judgment.

Q11: Our CRS submitted PoV XML which is incorrectly formatted. What will happen?

A11: Due to the "debug" nature of the Scored Events, DARPA will attempt to correct these formatting errors where possible for teams prior to SE1 scoring. Teams will also be notified of such errors. By CQE all such errors should be remediated.

Q10: Do you think you'll share source from the SE1 binaries?

A10: Yes. An upcoming DECREE release will contain an SE1 source release similar to the source release of the original example binaries. We expect a similar paragidm for SE2.

Q9: Is there a bug in the documentation for the cqe-package-solution.py script regarding use of the -f flag?

A9: Yes. Documentation specifies one -f flag per file argument, but the script actually requires a single -f flag followed by a whitespace separated list of files. Competitors please be advised of this error; we will update the documentation in an upcoming release.

Q8: Will the newly uploaded solutions overwrite the old ones in S3?

A8: The CGC FAQ hosted at cgc.darpa.mil in A67 provides for multiple submissions during Scored Event 1 and indicates which submission will be used for ranking. The CGC submission naming format prevents filename collisions between non-identical uploads.

Q7: Why were the scored event CBs' PT_LOAD headers merged into a single header?

A7: CGC Documentation has indicated (see: [cgc_executable_format](https://github.com/CyberGrandChallenge/libcgcef/blob/master/cgc_executable_format.md)) that the PT_GNU_STACK header is deprecated and will be removed. This change is live in the Scored Event 1 CB Corpus. As an artifact of this change, PT_LOAD header layout was affected: multiple PT_LOAD headers were merged into a single header.

Competitors are correct to be concerned about Challenge Binary linker choices. CB authors have a degree of freedom when interacting with the linker per the CGC executable specification. DARPA will release a Build Freeze Corpus prior to CQE including the sample CBs, Scored Event 1 CBs, and Scored Event 2 CBs, inclusive, prior to CQE; the Build Freeze Corpus will be built using the same publicly released build toolchain that will be used in CQE. Please bear with us as we develop the DECREE platform.

Q6: When will scoring be available for Scored Event 1?

A6: Careful examination of the CQE scoring mechanism reveals that scoring cannot begin until all submissions have been received, due to the interaction of all competitor PoVs and all competitor replacement Challenge Binaries. The interaction matrix between these sets will be very large. Scoring work will proceed with all possible urgency beginning Dec 3rd and scoring information will be released as soon as possible. The expected timeframe is "days". We appreciate your patience!

Q5: I'm having trouble decrypting the scored event challenge bundle. What OS should I use?

A5: The first scored event challenge bundle should be decrypted on the DECREE VM per A4.

Q4: What is the decryption key to the first scored event challenge bundle?

A4: The key is: who at the best knows in the end the triumph of high achievement and who at the worst fails while daring greatly

The challenge bundle can be decrypted with the following command as found on [github](https://github.com/CyberGrandChallenge/cgc-release-documentation/tree/master/scripts): 
```
cqe-unpack-event-bundle.py -e scored_event_1.ar.gz.enc -p "who at the best knows in the end the triumph of high achievement and who at the worst fails while daring greatly"
```

Q3: What is the official Twitter feed for CGC Scored Event 1?

A3: https://twitter.com/DARPACGCSEone


Q2: What is the thumbprint of the signing certificate for emails from cybergrandchallenge@darpa.mil?

A2: a7 20 cd 85 7a a4 6c a3 a3 84 8d 5b 0c 22 17 6c 64 2b 44 ea


Q1: When will questions and answers appear here.

A1: During the scored event.

