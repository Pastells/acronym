# ACRONYM (Acronym CReatiON for You and Me)

=====

A python-based tool for creating (Catalan/Spanish/English)-ish Acronyms from
your fancy project

The original (english-only) `ACRONYM` is described in this paper released on the
arXiv: https://arxiv.org/abs/1903.12180 and can be installed using
`pip install acronym`.

If you want it for Catalan and Spanish, you can just clone this repository and
run it as follows (must have nltk `pip install nltk`):

```bash
$ python acronym.py --language catalan "Mecànica Quàntica de N-cossos i Sistemes Ultrafreds"
Collecting word corpus
Identifying matching acronyms
Process Complete
(Score) ACRONYM   : Spelling
=======================================================================
(   44) MANCANCES : MecànicA quàNtiCA de N-Cossos i sistemes ultrafrEdS
(   41) MATANCES  : MecànicA quànTicA de N-Cossos i sistemes ultrafrEdS
(   37) MUNTADORS : Mecànica qUàNTicA De n-cossOs i sistemes ultrafRedS
(   36) MÀQUINES  : MecÀnica QUàntIca de N-cossos i sistemes ultrafrEdS
(   35) MENTIDERS : MEcàNica quànTIca De n-cossos i sistemEs ultrafRedS
(   34) MEDITAR   : MEcànica quàntica De n-cossos I sistemes ulTrAfReds
(   34) MENUDERS  : MEcàNica qUàntica De n-cossos i sistemEs ultrafRedS
(   34) MAQUETES  : MecànicA QUàntica de n-cossos i sistemEs ulTrafrEdS
(   34) MUNTADES  : Mecànica qUàNTicA De n-cossos i sistemes ultrafrEdS
(   34) MANTINC   : MecànicA quàNTIca de N-Cossos i sistemes ultrafreds
(   34) MANTENIR  : MecànicA quàNTica dE N-cossos i sIstemes ultrafReds
(   34) MANTENIA  : MecànicA quàNTica dE N-cossos i sIstemes ultrAfreds
(   33) MASSIU    : MecànicA quàntica de n-coSsos i SIstemes Ultrafreds
(   32) MECANISME : MECànicA quàNtica de n-cossos i sISteMes ultrafrEds
(   32) MUNTADOR  : Mecànica qUàNTicA De n-cossOs i sistemes ultrafReds
(   32) MENDIETA  : MEcàNica quàntica De n-cossos i sIstemEs ulTrAfreds
(   32) MENTIDES  : MEcàNica quànTIca De n-cossos i sistemes ultrafrEdS
(   31) MIQUES    : MecànIca Quàntica de n-cossos i sistemes UltrafrEdS
(   31) MATENIR   : MecànicA quànTica dE N-cossos i sIstemes ultrafReds
(   31) MÀQUINA   : MecÀnica QUàntIca de N-cossos i sistemes ultrAfreds
(   31) MECENES   : MECànica quàntica dE N-cossos i sistemes ultrafrEdS
(   30) MENTIDER  : MEcàNica quànTIca De n-cossos i sistemEs ultrafReds
(   29) MANACOR   : MecànicA quàNticA de n-CossOs i sistemes ultrafReds
(   29) MATUTES   : MecànicA quànTica de n-cossos i sistemes UlTrafrEdS
(   29) MANDOLA   : MecànicA quàNtica De n-cossOs i sistemes uLtrAfreds
(   29) MESURES   : MEcànica quàntica de n-coSsos i sistemes UltrafREdS
(   29) MANCADA   : MecànicA quàNtiCA De n-cossos i sistemes ultrAfreds
(   29) MUNTADA   : Mecànica qUàNTicA De n-cossos i sistemes ultrAfreds
(   29) MAQUETA   : MecànicA QUàntica de n-cossos i sistemEs ulTrAfreds
(   28) MADUR     : MecànicA quàntica De n-cossos i sistemes UltrafReds
```

Acronym Scoring System _New in Version 2.0.0_

```
For each capitalized letter in the acronym:
   * 10 points if first letter in a word (with exception of first letter)
   * 3 point if second or last letter in a word
   * 1 point otherwise
   * N bonus points if begins an N-length valid sub-word
       (ex: multiVariable -> 8 bonus points)
   * 2 bonus points if immediately following another capitalizd letter
```

optional arguments:

```
  -h, --help            show this help message and exit
  --min-length MIN_LENGTH
                        minimum length acronym to generate (default: 4)
  --max-length MAX_LENGTH
                        maximum length acronym to generate (default: 9)
  --max-results MAX_RESULTS
                        maximum number of options to generate (default: 30)
  --output OUTPUT       file to save results (prints to STDOUT if not given)
                        (default: STDOUT)
  --strict, -s          How strictly should the words be related to real
                        English? (-s for strict, -ss for very strict)
                        (default: None)
  --language LANGUAGE   Choose between catalan, spanish or english (default: english)
```
