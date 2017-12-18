# PLAEME_current
### A Parsed Linguistic Atlas of Early Middle English

###### Robert Truswell, Rhona Alcorn, James Donaldson, and Joel Wallenberg

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

This is the working version of the Parsed Linguistic Atlas of Early Middle English (PLAEME), based on the [Linguistic Atlas of Early Middle English](http://www.lel.ed.ac.uk/ihd/laeme2/laeme2.html), compiled by Meg Laing at the University of Edinburgh.  PLAEME takes LAEME texts from 1250&ndash;1325 and adds syntactic annotation in the format of the [Penn Parsed Corpora of Historical English](https://www.ling.upenn.edu/hist-corpora/). For information on this format, see [Beatrice Santorini's annotation guidelines](http://www.ling.upenn.edu/~beatrice/annotation/).  As with other Penn-format corpora, the standard way of using PLAEME is to download the psd files and search them with Beth Randall's [CorpusSearch](http://corpussearch.sourceforge.net/).

### Text selection

We have included a selection of LAEME texts which meet the following criteria:

- Dated to 1250&ndash;1325;
- >100 words long;
- Not already parsed in some form in the major Middle English parsed corpora, the [Penn&ndash;Helsinki Parsed Corpus of Middle English, 2nd edition](http://www.ling.upenn.edu/histcorpora/PPCME2-RELEASE-4/) and the [Parsed Corpus of Middle English Poetry](http://pcmep.net/);
- Only one version of each text included. If multiple versions are included in LAEME:
    - select versions to maximize balance across dialects;
    - if all else fails, choose the longest.

By these criteria, we have included 68 files (172,624 words) in PLAEME. Basic details on the texts included can be found in [PLAEME_texts.csv](PLAEME_texts.csv). For fuller details, please search in [LAEME's Index of Sources](http://www.lel.ed.ac.uk/ihd/laeme2/laeme2_framesZ.html) for the filename listed in the &ldquo;LAEME file&rdquo; column.

PPCHE files mostly correspond to our contemporary understanding of a &ldquo;text&rdquo;, while LAEME files correspond to &ldquo;scribal languages&rdquo;. Neither of these units nests within the other: a scribal language can be represented in multiple texts, and a text can represent multiple scribal languages. For instance, the *Trinity Homilies* (parsed as one file in PPCME2) is split into three files in LAEME (`trhomAt`, `trhomBt`, `trhom34ct`), because three different scribes produced the manuscript. On the other hand, versions of *Harrowing of Hell*, *Le regret de Maximian*, *The Thrush and the Nightingale*, and *The Fox and the Wolf* are parsed as separate texts in PCMEP, but feature (along with 13 other poems) in the single LAEME file `digby86mapt`, because all of these poems represent the same scribal language.

To find a middle ground between these two approaches, we have parsed complete LAEME files where there is no overlap with other parsed material, but split LAEME files into their component parts where necessary to avoid overlap with PPCME2 and PCMEP, or with texts in other LAEME files. For instance, the PLAEME file `corp145selt` contains the same text as the LAEME file of the same name (the *South English Legendary*), but PLAEME files `digby86bede`, `digby86doomsday`, etc., correspond to subparts of the single LAEME file `digby86mapt`: we did not parse the whole of `digby86mapt` because that would have led to overlap with PCMEP as documented above. As well as basic information about wordcount, date, and dialect, [PLAEME_texts.csv](PLAEME_texts.csv) also details correspondences between PLAEME files and LAEME files: which PLAEME files constitute part of which LAEME files?

### Additions to the PPCHE format

The format of PLAEME is largely faithful to that of PPCHE, as documented in [Beatrice Santorini's guidelines](http://www.ling.upenn.edu/~beatrice/annotation/). However, we have not implemented certain recent additions to that format. Specifically, we make no distinction between `CP-QUE-MAT` and `CP-QUE-SUB`, and we differentiate noun phrases on the basis of grammatical function (`NP-SBJ`, `NP-OB1`, `NP-OB2`), as opposed to the most recent version of PPCME2, which frequently differentiates on the basis of case (`NP-NOM`, `NP-ACC`, `NP-DTV`).

However, the format of LAEME preserves a level of textual detail not seen in PPCHE, largely as a consequence of the fact that LAEME is built from diplomatic transcriptions of manuscripts, while PPCHE is built from published editions. We have preserved as much of this additional information as possible in PLAEME, which has necessitated several additions to the established PPCHE format.

#### Orthographic conventions in LAEME and in PPCHE

#### Lexels and lemmatization

#### Punctuation etc.

#### Fragmentary text

#### Nontextual material

### Work in progress

PLAEME is due for completion in December 2017.  We are releasing this working version because it is now quite big and quite useful, and we would like feedback.  At the same time, it is incomplete and/or inaccurate in many ways.  These are some of the things still on the to-do list:

- There is currently no documentation, beyond this.  For the time being, please refer to PPCHE, LAEME, and CorpusSearch documentation.
- ID nodes need to be added.
- Several forms are missing lemmas (or more precisely, lexels in the LAEME sense), or need better lemmas (for numerals and proper names).
- Splitting and joining of words needs to be made more uniform.
- Formatting of languages other than English is currently incorrect.

If you spot issues other than these, please let us know.

### Acknowledgements

This work is funded by a British Academy/Leverhulme Small Research Grant (Robert Truswell PI).  It has benefitted enormously from Meg Laing's textual advice.  The project was conceived during a British Council researcher links workshop in Campinas, Brazil, organized by Susan Pintzuk and Charlotte Galves.  Susan Pintzuk and Aaron Ecay provided invaluable advice on the early stages during a research visit to York (August 2015).  Beatrice Santorini shared her revision queries and provided guidance on the PPCHE format.

### Licence

This work is licenced under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/).
