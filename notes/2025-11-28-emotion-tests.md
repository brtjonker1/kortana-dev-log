Emotional Inference Tests

Today I ran a set of small tests to observe how Kortana handles emotional language.
These were simple sandbox cycles, but they already show useful behavior and some clear next steps.

Test 1 — “Ik voel me verdrietig”

Observed behavior:

Kortana correctly detected the emotion verdrietig

Normalized it to verdriet

Added the tag “emotie: verdriet”

Marked it as self-generated, meaning it wasn’t pulled from a fixed dictionary

Tag set became:
['voel', 'emotie verdrietig', 'verdrietig', 'verdriet', 'emotie: verdriet']

Compression + reconstruction:

Reconstruction hypothesis: “Ik voel me verdrietig.”

Similarity score: 0.9846

This is extremely high confidence and indicates a stable meaning-pipeline path

Additional output:

Kortana responded empathically (“Ik hoor je, Bart…”) which confirms that the emotional-response module hooks in correctly after tagging.

Test 2 — “Ik ben gewoon een beetje moe”

Observed behavior:

Sentence was detected correctly

But emotional tagging did not match as strongly as in the sadness test

Reconstruction outcome was unclear

Results:

Similarity: 55.92%

Reconstruction: “Ik.”

Marked as insufficiently accurate

Interpretation:

This shows that the “moe / moeheid” emotion tokens need more robust mapping in the tag-injection stage.
It also shows that the reconstruction module struggles with low-confidence tags.

Summary of both tests

Sadness inference works surprisingly well, even producing a normalized emotional tag that wasn’t directly coded

Fatigue inference is weaker, both in tagging and reconstruction

The meaning pipeline is clearly working, but consistency varies by emotion category

