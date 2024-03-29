# Ultimate Words Unleashed

**Ultimate Words Unleashed** (**UWU**) is an open-source word list for word
games. It aims to be comparable to the current word lists used for
competitive English-language Scrabble, NWL and CSW. We also seek to include
definitions for each word in the list.

## Getting started

`UWU.txt` is the word list with definitions in Zyzzyva format.

`removed.txt` is a list of words that are in one of the source lexica but are
excluded from UWU, along with reasons for removal. This is for informational
use only and is not intended as a supplement to UWU.

## Methodology

UWU is based on the following existing word lists:

* [**Yet Another Word List**](https://gtoal.com/wordgames/yawl/) (**YAWL**) 0.2
  by Mendel Cooper, which is in turn based on the ENABLE2K list. Quite
  expansive at 263,533 words but hasn’t been updated since 2000.
* In the future, [**Common English Lexicon**](https://github.com/Fj00/CEL)
  (**CEL**) by Eric Smith (Fj00) and Kenji Matsumoto (strataji), a list
  intended to contain common words only.

Unlike NWL and CSW, UWU includes words longer than 15 letters, which are
playable in some games other than standard Scrabble, such as Super Scrabble,
Anagrams, or WildWords.

UWU excludes slurs from the list of valid words for the following reasons:

* Both NWL and CSW have had slurs removed in the NWL2020 and the CSW21 updates,
  respectively.
* Woogles [will no longer support any lexica containing slurs](https://docs.google.com/document/d/1JBAABsOPif3bydqhDcbsT_8s3PfhVfyNYw3-VVIvD5Y/edit),
  and we agree with their reasoning in their announcement.

We use NASPA’s definition of a slur as given in their [NWL2020 report](https://scrabbleplayers.org/words/nwl2020/NWL2020-final-report.pdf):
“at a minimum, one of the known senses of the word applies solely to protected
categories of personal identity as covered by the NASPA Code of Conduct: ‘race,
color, creed or religion, sex, sexual orientation, gender identity, national
origin, age, marital status, military status, or disability.’”

## Contributing

Feel free to send pull requests to add new words or to add definitions for
existing words. All newly added words should include definitions.

A definition of a lemma word consists of the actual definitions, followed by
the part-of-speech tag. The part-of-speech tag also contains a list of
inflected forms. An example definition might look like this:

```txt
ETAERIO an aggregate fruit [n ETAERIOS]
```

Note that unlike in CSW, we always list the full inflected form.

* For nouns (`[n …]`), list the plural form. If there’s more than one, then
  separate them with a comma, listing the regular plural form first:

  ```txt
  OCTOPUS an eight-limbed mollusk of the order Octopoda [n OCTOPUSES, OCTOPI, OCTOPODES]
  ```

  If the noun is uncountable or a *plurale tantum*, then don’t list any plural
  forms. If otherwise the plural form is the same as the singular, then list
  that as the plural.
* For verbs (`[v …]`), list the forms in the following order:
  **3rd person singular present**, **past simple**, **past participle** (if
  different from the past), **gerund**:

  ```txt
  LIFT to move to a higher place [v LIFTS, LIFTED, LIFTING]
  SING to produce musical sounds with one’s voice [v SINGS, SANG, SUNG, SINGING]
  ```
  
  (Irregular verbs with additional forms might need to be examined case by case.)
* For adjectives (`[adj …]`), list the forms in the following order (insofar
  as they exist):
  **comparative**, **superlative**, **adverb** (-ly):

  ```txt
  BRIGHT emitting a large amount of light [adj BRIGHTER, BRIGHTEST, BRIGHTLY]
  ```

* For pronouns (`[pron …]`), the lemma form is the nominative form. The other
  forms should be listed in the following order:
  **objective**, **possessive determiner**, **possessive pronoun** (if
  different from the determiner).

  As an exception, each form of *I* is treated as a lemma form, since *I* is
  too short to be included.

* Other parts of speech, which typically do not inflect: prepositions
  (`[prep]`), conjunctions (`[conj]`), interjections (`[interj]`), articles
  (`[art]`), numerals (`[num]`)

A definition of an inflected form looks like this:

```txt
ETAERIOS <etaerio=n> [n]
```

(For adverbial forms of adjectives, the part-of-speech tag should be `[adv]`,
not `[adj]`.)

Multiple definitions are separated with a slash.

If a word has multiple current spellings, then refer to the alternate spellings
for each one. List only the inflected forms that pertain to the current
spelling:

```txt
IONISER a device that ionizes, also IONIZER [n IONISERS]
IONIZER a device that ionizes, also IONISER [n IONIZERS]
```

(TODO: should these be tagged with `(UK)`, `(US)`?)

(TODO: additional field-specific guidelines)
