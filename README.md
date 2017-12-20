# PLAEME_current
### A Parsed Linguistic Atlas of Early Middle English

###### Robert Truswell, Rhona Alcorn, James Donaldson, and Joel Wallenberg

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

This is the working version of the Parsed Linguistic Atlas of Early Middle English (PLAEME), based on the [Linguistic Atlas of Early Middle English][LAEME], compiled by Meg Laing at the University of Edinburgh.  PLAEME takes LAEME texts from 1250&ndash;1325 and adds syntactic annotation in the format of the [Penn Parsed Corpora of Historical English][PPCHE].  As with other Penn-format corpora, the standard way of using PLAEME is to download the psd files and search them with Beth Randall's [CorpusSearch][CS].

### Text selection

We have included a selection of LAEME texts which meet the following criteria:

- Dated to 1250&ndash;1325 (c13b1&ndash;c14a1);
- &gt;100 words long;
- Not already parsed in some form in the major Middle English parsed corpora, the [Penn&ndash;Helsinki Parsed Corpus of Middle English, 2nd edition][PPCME2] and the [Parsed Corpus of Middle English Poetry][PCMEP];
- Only one version of each text included. If multiple versions are included in LAEME:
    - select versions to maximize balance across dialects;
    - if all else fails, choose the longest.

By these criteria, we have included 68 files (172,624 words) in PLAEME. Basic details on the texts included can be found in [PLAEME_texts.csv](PLAEME_texts.csv). For fuller details, please search in [LAEME's Index of Sources][LAEME] for the filename listed in the &ldquo;LAEME file&rdquo; column of the spreadsheet.

PPCHE files mostly correspond to our contemporary understanding of a &ldquo;text&rdquo;, while LAEME files correspond to &ldquo;scribal languages&rdquo;. Neither of these units nests within the other: a scribal language can be represented in multiple texts, and a text can represent multiple scribal languages. For instance, the *Trinity Homilies* (parsed as one file in PPCME2) is split into three files in LAEME ([`trhomAt`](http://archive.ling.ed.ac.uk/ihd/laeme2_scripts/display_tagdataZ.php?fn=trhomAt.tag), [`trhomBt`](http://archive.ling.ed.ac.uk/ihd/laeme2_scripts/display_tagdataZ.php?fn=trhomBt.tag), [`trhom34ct`](http://archive.ling.ed.ac.uk/ihd/laeme2_scripts/display_tagdataZ.php?fn=trhom34ct.tag)), because three different scribes produced the manuscript. On the other hand, versions of *Harrowing of Hell*, *Le regret de Maximian*, *The Thrush and the Nightingale*, and *The Fox and the Wolf* are parsed as separate texts in PCMEP, but feature (along with 13 other poems) in the single LAEME file [`digby86mapt`](http://archive.ling.ed.ac.uk/ihd/laeme2_scripts/display_tagdataZ.php?fn=trhomAt.tag), because all of these poems represent the same scribal language.

To find a middle ground between these two approaches, we have parsed complete LAEME files where there is no overlap with other parsed material, but split LAEME files into their component parts where necessary to avoid overlap with PPCME2 and PCMEP, or with texts in other LAEME files. For instance, the PLAEME file [`corp145selt`](psd/corp145selt.psd) contains the same text as the LAEME file of the same name (the *South English Legendary*), but PLAEME files [`digby86bede`](psd/digby86bede.psd), [`digby86doomsday`](psd/digby86doomsday.psd), etc., correspond to subparts of the single LAEME file [`digby86mapt`](http://archive.ling.ed.ac.uk/ihd/laeme2_scripts/display_tagdataZ.php?fn=digby86mapt.tag): we did not parse the whole of [`digby86mapt`](http://archive.ling.ed.ac.uk/ihd/laeme2_scripts/display_tagdataZ.php?fn=digby86mapt.tag) because that would have led to overlap with PCMEP as documented above. As well as basic information about wordcount, date, and dialect, [PLAEME_texts.csv](PLAEME_texts.csv) also details correspondences between PLAEME files and LAEME files, indicating which PLAEME files constitute part of which LAEME files.

### Additions to the PPCHE format

The format of PLAEME is largely faithful to that of PPCHE, as documented in [Beatrice Santorini's guidelines][Beatrice]: labelled brackets indicate constituency, within a &lsquo;flat&rsquo; syntactic structure (clauses are articulated into `CP` and `IP`, but there is generally no `VP`), with further specification of grammatical function through suffixal &lsquo;dash tags&rsquo;, for example distinguishing matrix and subordinate IPs as `IP-MAT` vs. `IP-SUB`.  An example of the format (the first sentence of [`digby86doomsday`](psd/digby86doomsday.psd)) below illustrates the distinction between `IP-MAT` and `IP-SUB`, and the absence of `VP`. We will describe aspects of the format that are specific to PLAEME below.

```
( (IP-MAT (PP (P Uuen-when)
              (CODE {COM_LAEME:Two-line_coloured_initial_*U_with_guide_letter_V_in_the_left_margin._A_pointing_hand_with_index_finger_touching_the_initial_is_in_the_left_margin})
              (CP-ADV (C 0)
                      (IP-SUB (NP-SBJ (PRO I-I))
                              (VBP +tenke-think)
                              (PP (P on-on{re})
                                  (NP (NPR$+NPR dom=es=dai-doomsday))))))
          (ADVP (ADV wel-well{v})
                (ADV sore-sore))
          (MD ma-may)
          (NP-SBJ (PRO i-I))
          (CODE {ORIGINAL~ma=i})
          (NP-OB2 (PRO me-me))
          (VB-RH dred=e-dread)
          (LINEBREAK \)))
```

We have not implemented certain recent additions to that format. Specifically, we make no distinction between `CP-QUE-MAT` and `CP-QUE-SUB`, and we differentiate noun phrases on the basis of grammatical function (`NP-SBJ`, `NP-OB1`, `NP-OB2`), as opposed to the most recent version of PPCME2, which frequently differentiates on the basis of case (`NP-NOM`, `NP-ACC`, `NP-DTV`).

We also have not yet added `ID` tags to each sentence, as is mandated by the PPCHE format.  We will add these imminently.

The format of LAEME preserves a level of textual detail not seen in PPCHE, largely as a consequence of the fact that LAEME is built from diplomatic transcriptions of manuscripts, while PPCHE is built from published editions. We have preserved as much of this additional information as possible in PLAEME, which has necessitated several additions to the established PPCHE format.

#### Lexels and lemmas

LAEME provides &lsquo;lexels&rsquo; for almost all words. In PLAEME, we have preserved all LAEME lexels with minor exceptions detailed below, and added more.

Although lexels are not identical to lemmas, they can be used for many of the same purposes.  Following the convention established in [IcePaHC][IcePaHC], we place lexels after the word form, separated by a hyphen. So `(P Uuen-when)` indicates that the preposition *Uuen* is a form of *when*.

[The LAEME documentation][LAEME] provides a list of lexels, and also of &lsquo;lexel specifiers&rsquo;, which are suffixed to lexels to disambiguate different senses of a single lexeme. Above, `(P on-on{re})` indicates that *on* is used here in the sense of *re*, or *concerning*.

The principles governing choice of lexels are set out in [Ch.4 of the LAEME documentation][LAEME_Ch4].  Lexels are drawn from four different sources. Modern English is the most common, followed by Old English or Old Scandinavian etyma, and Middle English forms (including for loanwords, e.g. from French). There are also composite lexels for compound forms.

Some of the choices of lexel are quite subtle.  For instance, `but` is used as a lexel 403 times in the sample of LAEME which forms the basis of PLAEME.  `bu:tan`, the OE ancestor of *but*, is used as a lexel a further 276 times, usually with a suffixed lexel specifier. In cases like this, reliance on Modern English lexels will lead to some examples being missed. The list of lexels included with [the LAEME documentation][LAEME] can be of some use in avoiding this problem. We also found the online versions of [the Bosworth&ndash;Toller Anglo-Saxon dictionary][BosworthToller] and the [Middle English Dictionary][MED] to be particularly useful when working with lexels.

LAEME does not have standardized lexels for proper names, Roman numerals, and certain other words. We have not yet added these to PLAEME, but we have added lexels for function words such as articles or pronouns.  Instead of LAEME's practice of using Arabic numbers as lexels for numerals, we have written out the lexels as words (that is, we have `(NUM six-six)` rather than `(NUM six-6)`), to avoid potential confusion with PPCHE's use of numeral dash tags for coindexation of categories.

Finally, in some cases where we have split a word (see below), we have not yet added lexels for the split forms.  These will be added in due course.

#### Orthographic conventions in LAEME and in PPCHE

##### Wordforms

For the wordforms in PLAEME, we have adopted the orthographic conventions of PPCHE rather than of LAEME.  This choice has been made mainly to maximize compatibility with queries designed for PPCHE.  This leads to correspondences like the following, where the values in PLAEME are identical to those in PPCHE:

LAEME | PLAEME | value
------|--------|------
\*A-\*Z| A-Z   | A-Z
A-Z   | a-z    | a-z
a/\*a | +a/+A  | &aelig;/&AElig;
d/\*d | +d/+D  | &eth;/&ETH;
y/\*y | +t/+T  | &thorn;/&THORN;
z/\*z | +g/+G  | &#541;/&#540;

LAEME also uses several characters which do not feature in PPCHE.  We have expanded the PPCHE orthographic conventions in appropriate ways, as follows:

LAEME | PLAEME | value
------|--------|------
cT    | +ct    | &lsquo;ct&rsquo; ligature
g/\*g | +g2/+G2| &#7545;/&#42877;
w/\*w | +w/+W  | &#447;/&#503;
x     | '      | accent
&     | &      | &#8266;
^     | ^      | superscript
\+    | =      | morpheme boundary
=     | =      | morpheme boundary    

LAEME reserves other lower-case letters for spelling out abbreviations in the text.  In PLAEME, we use upper-case letters for this, because we reserve lower-case letters for representing actual lower-case letters.

In other cases, we preserve LAEME conventions:

LAEME/PLAEME | value
-------------|------
[...]        | manuscript damage
\>...\>      | insertion
<...<        | deletion
\\           | mid-word linebreak
~            | abbreviation mark
.            | abbreviation mark

##### Lexels
LAEME's orthography for lexels mainly uses lower-case letters, with the main exceptions being *Y* for &thorn; and *:* as a long vowel marker in OE lexels.  We have preserved this orthography as is.

##### Other materials
In passages of Latin, French, or other languages, and in textual comments (see below), PLAEME preserves LAEME's original orthography (the left-hand column in the above tables).

#### Splitting of words
LAEME only rarely splits orthographic words.  We have split many more in PLAEME, partly for consistency with PPCHE conventions and partly because annotation with indication of constituent structure sometimes forced us to.  There is some inconsistency in the way in which splits have been marked.  Most have been marked by *@*: word-initially or word-finally, it indicates that there was no space between this and the preceding or following word respectively.  However, in some cases, a separate `CODE` label has been added, as below.

```
(IP-MAT (NP-SBJ (PRO ich-I))
        (MD ulle-will)
        (CODE {ORIGINAL~ich=ulle})
```
We aim to eliminate the use of these labels in favour of the *@* convention in due course.

As noted above, some split forms do not yet have lexels added.  We aim to fix this in due course.

#### Punctuation, nontextual material, etc.

LAEME contains a very detailed [diplomatic transcription](http://www.lel.ed.ac.uk/ihd/laeme2/laeme_intro_ch3.html) of the manuscript material, along with copious notes. We have aimed to preserve as much of this as possible in PLAEME, without compromising interpretability. This has led us to introduce several new tags in comparison with PPCHE, as detailed below.  However, we stress that some amount of the LAEME annotations (in particular, the metadata at the start of each file) has not been included, for reasons of readability.  The interested reader is encouraged to consult [LAEME's Index of Sources][LAEME] for this material.

Because many of the tags documented below will interfere with CorpusSearch queries involving immediate precedence, it is often a good idea to include a line like the following in queries: 

```
add_to_ignore: LINEBREAK|PUNC|MISC|CNJCTR
```

##### Single tags without CODE

LAEME | PLAEME | value
------|--------|------
`{\}` | `(LINEBREAK \)`| Linebreak
`{...}` | `(PUNC ...)`| Punctuation
`!_...` | `(MISC ...)`| Untagged material
`{rh}` | `-RH` (dash tag) | Rhyme

We preserved rhyme information because it may help with quantitative investigation of the possibility that word order in verse texts is affected by metre.

##### Single tags with CODE

LAEME | PLAEME | value
------|--------|------
`{~...~}` | `(CODE {PAGE~...})` | Page number
`{=...=}` | `(CODE {COM_LAEME:...})` | Comment included in LAEME
`{"..."}` | `(CODE {GLOSS~...})` | Gloss provided in LAEME
`{)...)}` | `(CODE {INTERPOLATION~...})` | Interpolation by another hand
`{[...[{` | `(CNJCTR ...)` | Conjectured material missing from ms.

We follow LAEME in making a distinction between insertions (in the same hand) and interpolations (usually in a different hand). Because LAEME is first and foremost a tool for investigating scribal languages, interpolations do not have the same status as material written by the main scribe.

The same goes for conjectures, supplied by the compiler of LAEME on the basis of deduction or sources such as editions or other manuscripts.  Neither conjectures nor interpolations are searched by CorpusSearch for these reasons.

##### Paired tags with CODE

LAEME | PLAEME | value
------|--------|------
`{<}` | `(CODE DEL)` | deletion (full word or longer)
`{>}` | `(CODE {INSSTART})` | Begin insertion
`{>}` | `(CODE {INSEND})` | End insertion
`{'}` | `(CODE {TITLESTART})` | Begin title
`{'}` | `(CODE {TITLEEND})` | End title

Paired tags for insertions and titles indicate that part of the text has a special status without rendering it invisible to CorpusSearch, which will by default ignore the `(CODE ...)` tags and search the intervening material.

Deletions are different: we typically don't want CorpusSearch to search them. Accordingly, we enclose the entire deletion in a `(CODE ...)` tag, and include a second `(CODE DEL)` tag indicating that this is a deletion.  In most cases, there is also a third `(CODE {COM_LAEME:...})` tag indicating the nature of the deletion.  The complete structure looks like this: the example below represents the PP *in him* with the miscellaneous form *is* deleted.

```
(PP (P in-in{p})
    (CODE (CODE DEL)
          (MISC IS))
    (CODE {COM_LAEME:del,_by_erasure})
    (NP (PRO him-him)))
```

#### Fragmentary text

LAEME includes manuscripts which are damaged to such an extent that syntactic structure cannot be directly inferred. For instance, [vitelld3t](psd/vitelld3t.psd) is badly damaged by fire, with many folios completely lost and much of what remains completely illegible.  In annotating such texts with information about syntactic structure, we necessarily have to extrapolate beyond the text to a greater extent than usual.

We have tried to use LAEME as a guide in this respect, sticking to the following principles:

- We do not provide a lexel or POS tag which is not provided in LAEME, except as noted above.
- Projecting phrasal nodes:
    - a P can project a PP even if its complement is missing.
    - a D or N can project an NP.
    - ADJ and ADV can project ADJP and ADVP as usual.
    - Otherwise, don't project a phrasal node.
- Projecting clausal nodes. The following are sufficient for projecting an IP:
    - A finite verb/auxiliary + at least one argument.
    - A nonfinite verb + conjectured auxiliary + at least one argument.
    - A bare nonfinite or imperative verb can project an `IP-INF` or `IP-IMP` node respectively when appropriate
- Project `CP-QUE` when there is a clear indication of question status (e.g. inversion or a *wh*-phrase).
- If none of the above apply, tag as a `FRAG`.

We attempt to draw fragment boundaries roughly as for sentence boundaries: coordination aside, a `FRAG` should not contain:

- multiple finite elements;
- multiple `NP-SBJ`, multiple `NP-OB1`, etc.

If neither of these conditions are violated, we do not insert boundaries between fragments.  In some cases this leads to very long fragments, and in others to insertion of boundaries between matrix and subordinate clauses, but it is at least a nearly-objective method, grounded in the textual material

#### Morphosyntactic information in LAEME but not in PLAEME

Much of the syntactic structure in PLAEME was projected from the information in LAEME's &lsquo;grammels&rsquo; annotations similar to POS tags.  LAEME's grammels are more informative than the tags used in PPCHE, including information on mood (indicative vs. subjunctive), person and number inflection on pronouns, verbs, etc., and nonlocal dependencies such as negative concord.

None of this material is currently available in PLAEME, because an attempt to preserve all of the information in LAEME quickly led to incomprehensible annotations.  In future, it would be very useful to include at least annotations of subjunctive mood in PLAEME.  For now, we note that interpretation of results from PLAEME can be enhanced by reference to the corresponding annotation in LAEME.

### Work in progress

PLAEME is due for completion in December 2017.  We are releasing this working version because it is now quite big and quite useful, and we would like feedback.  At the same time, it is incomplete and/or inaccurate in many ways, as documented above. If you spot issues other than those described here, please report them via github or to <rob.truswell@ed.ac.uk>.

### Acknowledgements

This work is funded by a British Academy/Leverhulme Small Research Grant (Robert Truswell PI).  It has benefitted enormously from Meg Laing's textual advice.  The project was conceived during a British Council researcher links workshop in Campinas, Brazil, organized by Susan Pintzuk and Charlotte Galves.  Susan Pintzuk and Aaron Ecay provided invaluable advice on the early stages during a research visit to York (August 2015).  Beatrice Santorini shared her revision queries and provided guidance on the PPCHE format.

### Licence

This work is licenced under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/).

[Beatrice]: http://www.ling.upenn.edu/~beatrice/annotation/
[BosworthToller]: http://bosworthtoller.com/
[CS]: http://corpussearch.sourceforge.net/
[IcePaHC]: http://linguist.is/icelandic_treebank/Icelandic_Parsed_Historical_Corpus_(IcePaHC)
[LAEME]: http://www.lel.ed.ac.uk/ihd/laeme2/laeme2_framesZ.html
[LAEME_Ch4]: http://www.lel.ed.ac.uk/ihd/laeme2/laeme_intro_ch4.html
[MED]: https://quod.lib.umich.edu/m/med/fullregexp.html
[PPCHE]: https://www.ling.upenn.edu/hist-corpora/
[PPCME2]: http://www.ling.upenn.edu/histcorpora/PPCME2-RELEASE-4/
[PCMEP]: http://pcmep.net/
