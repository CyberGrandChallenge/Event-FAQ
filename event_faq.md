# FAQ

The Cyber Grand Challenge will communicate with teams via this FAQ during the challenge events. The content will be copied into the master CGC FAQ post-event.

# Scored Event 2

Scheduled for April 16, 2015.

Q2: What is the decryption key to the second scored event challenge bundle?

A2: The key is: The will to succeed is important, but what's more important is the will to prepare.

The challenge bundle can be decrypted with the following command as found on [github](https://github.com/CyberGrandChallenge/cgc-release-documentation/tree/master/scripts): 

```
cqe_unpack_event_bundle.py -e scored_event_2.ar.gz.enc -p "The will to succeed is important, but what's more important is the will to prepare."
```

Q1: What is the official Twitter feed for CGC Scored Event 2?

A1: https://twitter.com/DARPACGCSEtwo



# CGC Qualification Event

Scheduled for June 3, 2015.

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

