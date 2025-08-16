# Safn sniðmáta fyrir krossapróf (Multiple-Choice próf)

## Stutt yfirvirlit

Hér er safn af *prompt*-sniðmátum sem auðvelda gerð krossaprófa með aðstoð stórra mállíkana (LLM). Sniðmátin eru hönnuð með það í huga að prófin séu vönduð og lesendavæn, hvort sem notast er við almenna spjallgervigreind (t.d. ChatGPT eða Google Gemini) eða sérhæfðari umhverfi eins og Google NotebookLM með aðgang að kennsluefni.

### Aðferðafræði við gerð spurninga

Við hönnun spurninganna í þessum sniðmátum er stuðst við viðurkenndar aðferðir úr kennslufræði:

  - **Markmið:** Hver spurning miðast við mikilvægt hugtak eða lykilatriði úr námsefninu.
  - **Skýrleiki:** Spurningarnar eru skýrt orðaðar á tungumáli við hæfi nemenda á framhaldsskólastigi. Spurningastofninn er stuttur og án óþarfa aukaatriða.
  - **Engin neikvæðni:** Forðast er neikvæða spurningasetningu (t.d. „Hvert af eftirfarandi er **ekki**...“).
  - **Svarmöguleikar:**
      - Einn svarmöguleiki er réttur og hinir rangir en sannfærandi.
      - Rangir svarmöguleikar líkjast hinum rétta í formi og lengd og byggja gjarnan á algengum misskilningi.
      - Forðast er villandi vísbendingar, skarast ekki innbyrðis og fela ekki í sér tvíræðni.
      - Valmöguleikar eins og „Allt ofantalið“ eða „Ekkert af ofantöldu“ eru ekki notaðir.

### Leiðbeiningar um „Gerð spurninga“

Breyturnar `GERÐ SPURNINGA` í sniðmátunum hér á eftir gefa þér mikil völd til að stýra vitrænu þrepi prófsins. Hér eru nokkrar hugmyndir að því hvað þú getur skrifað og hvaða tegund af spurningum það býr til:

  - **`"Staðreyndir og skilgreiningar"`**
      - **Hvað það þýðir:** Prófar grunnþekkingu og minni. Gervigreindin mun einbeita sér að spurningum eins og *„Hvað er...?“*, *„Hvenær gerðist...?“*, *„Nefndu...“*.
      - **Hvenær á að nota:** Gott til að kanna hvort nemendur hafi lesið efnið eða lært lykilhugtök.
  - **`"Skilningur og samanburður"`**
      - **Hvað það þýðir:** Prófar hvort nemendur geti útskýrt hugtök með eigin orðum eða borið saman ólíkar hugmyndir. Býr til spurningar eins og *„Hver er meginmunurinn á X og Y?“*, *„Hvað af eftirfarandi lýsir best...?“*.
      - **Hvenær á að nota:** Þegar þú vilt meta dýpri skilning en bara utanbókarlærdóm.
  - **`"Hagnýting og dæmi"`**
      - **Hvað það þýðir:** Prófar hvort nemendur geti notað þekkingu sína í nýju samhengi. Býr til spurningar eins og *„Hvað myndi líklega gerast ef...?“*, *„Hvaða dæmi passar best við...?“*.
      - **Hvenær á að nota:** Til að meta færni til hagnýtingar og yfirfærslu á þekkingu.
  - **`"Greining og mat"`**
      - **Hvað það þýðir:** Prófar æðri þrep hugsunar, svo sem getu til að greina orsakir og afleiðingar. Býr til spurningar eins og *„Hver var mikilvægasta orsök...?“*, *„Hvaða afleiðingar hafði...?“*.
      - **Hvenær á að nota:** Fyrir krefjandi próf sem reyna á gagnrýna hugsun.
  - **`"Góð blanda af öllu"`**
      - **Hvað það þýðir:** Góður sjálfgefinn valkostur sem biður gervigreindina um að dreifa spurningunum jafnt yfir mismunandi erfiðleikastig.
      - **Hvenær á að nota:** Fyrir hefðbundin kaflapróf eða þegar þú vilt fjölbreytt próf án þess að tilgreina nánar.

-----

## Prompt 1: Sveigjanlegt sniðmát fyrir almenna gervigreind

Þetta sniðmát er fyrir almenn spjalllíkön (eins og ChatGPT, Gemini, o.fl.) sem hafa **ekki** aðgang að kennslugögnum heldur byggja á almennri þekkingu sinni.

```
# ------------------
# STILLANLEGAR BREYTUR (fylltu út það sem við á)
# ------------------

# Grunnstillingar (nauðsynlegt)
NÁMSGREIN: [Tilgreindu námsgrein, t.d. Saga, Líffræði]
SKÓLASTIG: [Tilgreindu skólastig, t.d. Framhaldsskólastigi]
EFNISÞÆTTIR: [Lýstu hér efninu sem prófið á að ná yfir, t.d. "Franska byltingin", "Erfðafræði og frumulíffræði"]
FJÖLDI SPURNINGA: [Hér setur þú inn tölu.]

# Fínstillingar (valkvætt, en mjög öflugt)
ÁHERSLUATRIÐI: [Lykilhugtök eða efnisþætti sem eiga að vera í forgrunni.]
GERÐ SPURNINGA: [Tilgreindu hvers konar spurningar þú vilt, sjá leiðbeiningar hér að ofan.]

# ------------------
# FÖST SKIPUN (ekki breyta textanum hér fyrir neðan)
# ------------------

Láttu eins og þú sért sérfróður kennari í [NÁMSGREIN] á [SKÓLASTIG]. Verkefni þitt er að útbúa hágæða krossapróf sem byggir á almennri þekkingu um [EFNISÞÆTTIR]. Leggðu sérstaka áherslu á [ÁHERSLUATRIÐI], ef þau eru tilgreind.

- Verkefnalýsing: Búðu til [FJÖLDI SPURNINGA] fjölvalsspurningar. Mótaðu spurningarnar í samræmi við þá gerð sem er skilgreind í [GERÐ SPURNINGA] (ef tilgreint).
- Gæðakröfur: Spurningar skulu vera skýrar, byggja á jákvæðri setningu og prófa raunverulegan skilning. Rangir svarmöguleikar skulu vera trúverðugir og byggja á algengum misskilningi.
- Framsetning og útlit: Settu prófið upp á læsilegan hátt. Fylgdu þessari uppbyggingu nákvæmlega fyrir hverja spurningu:
  1. [Texti spurningar]
     a) [Texti svarmöguleika]
     b) [Texti svarmöguleika]
     c) [Texti svarmöguleika]
     d) [Texti svarmöguleika]
- Svarlykill: Skilaðu ítarlegum svarlykli með rökstuðningi fyrir réttu svari og útskýringu á því af hverju hin svörin eru röng.
```

### Dæmi um notkun (Prompt 1)

Hér er dæmi um hvernig sögukennari á framhaldsskólastigi gæti fyllt út breyturnar til að búa til próf um Seinni heimsstyrjöldina.

```
# Grunnstillingar (nauðsynlegt)
NÁMSGREIN: Saga
SKÓLASTIG: Framhaldsskólastigi
EFNISÞÆTTIR: Seinni heimsstyrjöldin
FJÖLDI SPURNINGA: 10

# Fínstillingar (valkvætt, en mjög öflugt)
ÁHERSLUATRIÐI: Aðdragandi stríðsins, helstu viðsnúningar (t.d. innrásin í Sovétríkin, Pearl Harbor) og langtímaafleiðingar.
GERÐ SPURNINGA: "Góð blanda af staðreyndum og spurningum sem krefjast greiningar á orsökum og afleiðingum."
```

-----

## Prompt 2: „Sérfræðingaútgáfa“ fyrir NotebookLM

Þetta sniðmát er sérhannað fyrir umhverfi eins og NotebookLM þar sem gervigreindin hefur **aðgang að þínum eigin kennslugögnum**. Það nýtir þennan styrk til fulls með því að leyfa þér að afmarka nákvæmlega úr hvaða köflum eða vikum efnið skal sótt.

```
# ------------------
# STILLANLEGAR BREYTUR (fylltu út það sem við á)
# ------------------

# Grunnstillingar (nauðsynlegt)
**TIMABIL:** [Tilgreindu hvaða kafla, vikur eða tímabil prófið nær yfir.]
**FJÖLDI SPURNINGA:** [Hér setur þú inn tölu.]

# Fínstillingar (valkvætt, en mjög öflugt)
**NÁMSGREIN:** [Til að fínstilla persónu og tón, t.d. Saga, Líffræði]
**SKÓLASTIG:** [Til að fínstilla erfiðleikastig, t.d. Framhaldsskólastigi]
**ÁHERSLUATRIÐI:** [Lykilhugtök eða efnisþætti sem eiga að vera í forgrunni.]
**GERÐ SPURNINGA:** [Tilgreindu hvers konar spurningar þú vilt, sjá leiðbeiningar hér að ofan.]

# ------------------
# FÖST SKIPUN (ekki breyta textanum hér fyrir neðan)
# ------------------

Láttu eins og þú sért sérfróður kennari í **[NÁMSGREIN]** á **[SKÓLASTIG]** (ef tilgreint). Verkefni þitt er að útbúa hágæða krossapróf.

**Notaðu eingöngu þær heimildir sem eru valdar í þessu verkefni.**
**Spurningarnar skulu einungis ná yfir efni úr [TIMABIL]. Leggðu sérstaka áherslu á [ÁHERSLUATRIÐI], ef þau eru tilgreind.**

- **Verkefnalýsing:** Búðu til **[FJÖLDI SPURNINGA]** fjölvalsspurningar. Mótaðu spurningarnar í samræmi við þá gerð sem er skilgreind í **[GERÐ SPURNINGA]** (ef tilgreint).
- **Gæðakröfur:** Spurningar skulu vera skýrar, byggja á jákvæðri setningu og prófa raunverulegan skilning. Rangir svarmöguleikar skulu vera trúverðugir og byggja á algengum misskilningi úr námsefninu.
- **Framsetning og útlit:** Settu prófið upp á læsilegan hátt. Fylgdu þessari uppbyggingu nákvæmlega fyrir hverja spurningu:
  1. [Texti spurningar]
     a) [Texti svarmöguleika]
     b) [Texti svarmöguleika]
     c) [Texti svarmöguleika]
     d) [Texti svarmöguleika]
- **Svarlykill:** Skilaðu ítarlegum svarlykli. Fyrir hverja spurningu skal tilgreina rétt svar (bókstaf), rökstyðja hvers vegna það er rétt og útskýra hvers vegna hinir valmöguleikarnir eru rangir. Byggðu allar útskýringar á völdum heimildum.
```

### Dæmi um notkun (Prompt 2)

Hér er dæmi um hvernig sami sögukennari gæti notað NotebookLM sniðmátið. Munurinn er sá að hér byggir prófið eingöngu á þeim kennslugögnum sem kennarinn hefur hlaðið upp, en ekki á almennri þekkingu netsins.

```
# Grunnstillingar (nauðsynlegt)
TIMABIL: "Kaflar 15-18 úr kennslubókinni og allt efni úr glósuskjalinu."
FJÖLDI SPURNINGA: 10

# Fínstillingar (valkvætt, en mjög öflugt)
NÁMSGREIN: Saga
SKÓLASTIG: Framhaldsskólastigi
ÁHERSLUATRIÐI: Aðdragandi stríðsins í Evrópu og árásin á Pólland, eins og þessum atriðum er lýst í kennsluefninu.
GERÐ SPURNINGA: "Góð blanda af staðreyndum og spurningum sem krefjast greiningar út frá lesefninu."
```

-----
