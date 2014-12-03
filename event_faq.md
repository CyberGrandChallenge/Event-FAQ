# FAQ

The Cyber Grand Challenge will communicate with teams via this FAQ during the challenge events. The content will be copied into the master CGC FAQ post-event.

# Scored Event 1

Scheduled for December 2, 2014.

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

# Scored Event 2

Tentatively scheduled for April 16, 2015.

# CGC Qualification Event

Scheduled for June 3, 2015.
