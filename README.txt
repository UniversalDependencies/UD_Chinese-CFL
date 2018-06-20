# Summary

The Chinese-CFL UD treebank is manually annotated by Keying Li with minor manual revisions by Herman Leung and John Lee at City University of Hong Kong, based on essays written by learners of Mandarin Chinese as a foreign language. The data is in Simplified Chinese.

# Introduction

.CONLLUX (extension files)

[NOTE: This is a temporary measure for procedures whose descriptions are not yet available in the UD guidelines.]

Included is an additional `.conllux` file for the `.conllu` file of the same name.  The `.conllux` counterpart file contains extra information not ordinarily stored in any of the 10 columns in the CONLL-U format. The non-duplicate columns in `.conllux` for this treebank are columns 3 (distributional tag), 6 (distributional head), 7 (distributional relation), and 10 (alignment). [If data in columns 3, 6, and 7 in the `.conllux` file are the same as their counterparts in `.conllu`, that means the distributional annotation is the same as the morphological annotation. For more information on "distributional" vs. "morphological" annotation, see descriptions further below.]

ALIGNMENTS

Alignments are linked to native-Chinese-speaker corrections (by Keying Li) of the learner sentences; storage of the corrected sentences are to be determined. All sentences pertaining to the learner corpus have a sent_id beginning with `CFL-`; original learner sentences have the parallel-treebank extension `/ori` in the sent_id, whereas the corrected sentences have the extension `/crr` in the sent_id. Each alignment includes the full sent_id followed by '#' and the index of the token aligned. Additional alignments in a one-to-many alignment is offset by commas (e.g. `CFL_A_1-5/crr#5,CFL_A_1-5/crr#6` means the token is aligned to tokens 5 and 6 of the corrected ('crr') sentence of 'CFL_A_1-5').

BASIC STATISTICS

Tree count:  451
Word count:  7256
Token count: 7256
Dep. relations: 45 of which 13 language specific
POS tags: 15
Category=value feature pairs: 0

GENERAL COMMENTS

A "literal annotation" is preferred, i.e., one should annotate "as if the sentence were as syntactically well-formed as it can be, possibly ignoring meaning" (Ragheb and Dickinson, 2014).

WORD SEGMENTATION

Non-words are allowed only when there are spelling errors resulting from orthographic or phonetic confusion. An orthographic confusion must involve characters with similar appearance, e.g., between 了 and 子 in *花花公了.

Phonetic confusion must involve characters with the same pronunciation but different tones, e.g., between 關 and 管 in the sentence *不關多貴我也買; or, characters with easily confusable pairs such as {j, zh} and {x, sh}.

In these cases, the lemma of the misspelt word is its corrected version. For example, the lemma of *花花公了 is 花花公子, and the lemma of 不關 is 不管.

LEMMA

The lemma is the same as the word, except when the word contains a spelling error.

POS TAGGING

POS tagging is performed on the basis of the lemma, rather than the word. Hence, in the sentence *不關多貴我也買, 不關 is not tagged as VERB but rather as SCONJ, on account of its lemma 不管.

When determining the POS, one usually considers both the "morphological evidence", i.e., the linguistic form of the word, as well as the "distributional evidence", i.e., its syntactic use in the sentence. In a well-formed sentence, these two kinds of evidence should agree; in learner text, however, they may conflict (Ragheb and Dickinson, 2014).

Consider the word 可怕 _kepa_ "scary" in the sentence *我可怕他 "*I scary him". Morphological evidence suggests the word 可怕 _kepa_ "scary" should be tagged as an adjective (ADJ), reflecting its normal usage. Distributional evidence suggests it should be tagged as a verb, since the trailing pronoun 他 _ta_ "him" implies its use as a verb with a direct object.

When these two kinds of evidence contradict one another, the morphological evidence prevails. The example sentence is thus tagged as:

我/PN 可怕/ADJ 他/PN

However, we also include the "distributional POS tag" in column 3 of the `.conllux` file.

DEPENDENCY RELATIONS

Missing words

When a word seems missing in the learner sentence, we annotate according to the UD guidelines on promotion by head elision. For example, in the sentence fragment 在中國最近幾年 _zai zhongguo zuijin ji nian_ "in China recent few years", we promote 年 _nian_ "year" to be the root. Although both 中國 _zhongguo_ "China" and 年 _nian_ "year" would be `obl` dependents if a verb was present, 年 _nian_ "year" is promoted because it is closer to the expected location of the verb.

Word-order errors

The annotation should assume no word order error. For example, in the sentence *我被了他打一頓. The aspect particle 了 _le_ usually modifies the verb that precedes it immediately, and is probably misplaced in this sentence. It is most likely intended to modify 打 _da_ "hit", and should immediately follow da rather than 被 _bei_, the passive marker.

To adhere to the principle of "literal annotation", rather than annotating le as the child of 打 _da_ "hit" with the `aux` relation, we annotate 了 _le_ as the child of 被 _bei_ with the `dep` relation.

`dep` (unspecified dependency)

When learner errors make it difficult to characterize the grammatical relation between a word and the rest of the sentence, we use the `dep` relation. Typically, when the POS tag differs from the distributional POS tag, the `dep` relation is needed.

Consider the sentence *我可怕他 "*I scary him". From the point of view of its POS tag, it is unclear how the word 可怕 _kepa_ "scary", as an adjective, relates to the pronoun. We thus consider kepa as the head of 他 _ta_ "him" with the `dep` relation.

When a word has a different distributional POS tag, we also include a "distributional" dependency relation on the basis of the word's distributional POS tag. This relation is stored in column 4 of the `.conllux` file. In the example sentence above, the word 可怕 _kepa_ "scary", as a verb, is the head of 他 _ta_ "him" with the `obj` relation.

REFERENCES
Marwa Ragheb and Markus Dickinson. 2014. Developing a Corpus of Syntactically-annotated Learner Language for English. Proceedings of the 13th International Workshop on Treebanks and Linguistic Theories (TLT).

# Acknowledgments
This work is partially supported by a Strategic Research Grant (Project no. 7004494) from City University of Hong Kong.

# References

When using this treebank, please cite at least one paper from the following references:
John Lee, Herman Leung, Keying Li. 2017. Towards Universal Dependencies for Learner Chinese. In Proc. Workshop on Universal Dependencies.

# Changelog

* 2018-04-15 v2.2
  * ?
* 2017-11-15 v2.1
  * Initial UD release.


=== Machine-readable metadata =================================================
Data available since: UD v2.1
License: CC BY-SA 4.0
Includes text: yes
Genre: learner-essays
Lemmas: not available
UPOS: manual native
XPOS: not available
Features: not available
Relations: manual native
Contributors: Lee, John; Leung, Herman; Li, Keying
Contributing: elsewhere
Contact: keyingli3-c@my.cityu.edu.hk, tswong-c@my.cityu.edu.hk, jsylee@cityu.edu.hk
===============================================================================
