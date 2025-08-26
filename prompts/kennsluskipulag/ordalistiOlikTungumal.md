# Sniðmát fyrir gerð fjöltyngdra orðalista (stafrófsraðað)

## Stutt yfirlit

Þessi *prompt*-sniðmát eru hönnuð til að hjálpa kennurum að búa til einfalda og hagnýta, fjöltyngda orðalista. Megináherslan er á að fá nákvæmar, samhengisbundnar þýðingar á faghugtökum án þess að birta skýringar á íslensku. Lokaúttakinu er **alltaf raðað í stafrófsröð** eftir íslensku hugtökunum til að tryggja yfirsýn og auðvelda notkun. Þetta er tilvalið þegar listinn er notaður sem verkfæri fyrir nemendur til að læra orðaforðann fyrir próf eða verkefni.

-----

## Prompt 1: Sniðmát fyrir almenna gervigreind (LLM)

Þetta sniðmát er hannað fyrir almenn spjalllíkön (t.d. Gemini, ChatGPT). Þú hleður upp skjali sem inniheldur lista af íslenskum orðum, tilgreinir námsgrein og hvaða tungumál þú vilt fá þýðingar á.

```
# ------------------
# STILLANLEGAR BREYTUR (fylltu út það sem við á)
# ------------------

# Grunnstillingar (nauðsynlegt)
NÁMSGREIN: [Tilgreindu námsgreinina sem orðin tilheyra, t.d. "Stærðfræði", "Saga", "Gagnasafnsfræði".]
TUNGUMÁL: [Skrifaðu tungumálin sem þú vilt fá þýðingu á, aðskilið með kommu, t.d. "Enska, Pólska", "Úkraínska, Spænska, Enska".]

# Fínstillingar (valkvætt)
SKÓLASTIG: [Tilgreindu skólastig, t.d. "Grunnskóli (unglingastig)", "Framhaldsskólastigi".]

# ------------------
# FÖST SKIPUN (ekki breyta textanum hér fyrir neðan)
# ------------------

Láttu eins og þú sért nákvæmur og fjöltyngdur sérfræðingur í [NÁMSGREIN] sem útbýr námsefni.

Verkefni þitt er að lesa íslensku orðin úr meðfylgjandi skjali og búa til hágæða, fjöltyngdan orðalista sem er tilbúinn til útprentunar.

Fylgdu þessu ferli nákvæmlega:
1.  **Greindu samhengi:** Fyrir hvert íslenskt orð á listanum, greindu merkingu þess og notkun **sérstaklega innan námsgreinarinnar [NÁMSGREIN]**. Þetta er nauðsynlegt til að tryggja rétta þýðingu.
2.  **Finndu nákvæmar þýðingar:** Byggt á þeirri greiningu, finndu nákvæma faglega þýðingu fyrir hvert orð yfir á þau [TUNGUMÁL] sem tilgreind eru.
3.  **Settu upp úttak:** Skilaðu niðurstöðunni sem snyrtilegri og prentvænni Markdown töflu, **röðuðu í stafrófsröð eftir íslenska hugtakinu**.
    * Gefðu skjalinu skýra fyrirsögn: "Orðalisti úr [NÁMSGREIN]".
    * Hafðu dálk fyrir "Íslenskt hugtak" og síðan einn dálk fyrir hvert tungumál sem beðið var um (t.d. "Ensk þýðing", "Pólsk þýðing").

Útkoman á að vera fagleg, villulaus og tilbúin til að afrita beint yfir í Word skjal eða prenta út. **EKKI birta neinar skýringar á orðunum, aðeins þýðingarnar.**
```

### Dæmi um notkun (Prompt 1)

Kennari í gagnasafnsfræði hleður upp textaskjali (`gagnasafn_ord.txt`) með lista af faghugtökum og þarf að fá þýðingar fyrir enska og pólska nemendur.

```
# Grunnstillingar (nauðsynlegt)
NÁMSGREIN: "Gagnasafnsfræði"
TUNGUMÁL: "Enska, Pólska"

# Fínstillingar (valkvætt)
SKÓLASTIG: "Framhaldsskólastigi"
```

-----

## Prompt 2: Sniðmát fyrir NotebookLM (og svipuð verkfæri)

Þetta sniðmát er fyrir umhverfi þar sem þú hleður upp bæði orðalistanum og námsefninu sjálfu. Gervigreindin notar námsefnið til að tryggja fullkomlega rétta, samhengisbundna þýðingu og raðar niðurstöðunni í stafrófsröð.

```
# ------------------
# STILLANLEGAR BREYTUR (fylltu út það sem við á)
# ------------------

# Grunnstillingar (nauðsynlegt)
ORÐALISTI_SKJAL: [Nefndu skjalið sem inniheldur listann af íslenskum orðum, t.d. "hugtokalisti.txt".]
KENNSLUEFNIS_SKJÖL: [Nefndu skjalið/skjölin sem innihalda námsefnið þar sem orðin koma fyrir, t.d. "Kafli_3_Erfðafræði.pdf".]
NÁMSGREIN: [Tilgreindu námsgreinina.]
TUNGUMÁL: [Skrifaðu tungumálin sem þú vilt fá þýðingu á, aðskilið með kommu.]

# Fínstillingar (valkvætt)
SKÓLASTIG: [Tilgreindu skólastig.]

# ------------------
# FÖST SKIPUN (ekki breyta textanum hér fyrir neðan)
# ------------------

Láttu eins og þú sért nákvæmur og fjöltyngdur sérfræðingur í [NÁMSGREIN] sem útbýr námsefni.

Verkefni þitt er að búa til hágæða, fjöltyngdan orðalista sem er tilbúinn til útprentunar.

**Notaðu [KENNSLUEFNIS_SKJÖL] sem aðalheimild til að skilja merkingu og notkun orðanna sem listuð eru upp í [ORÐALISTI_SKJAL].**

Fylgdu þessu ferli nákvæmlega:
1.  **Greindu samhengi í heimild:** Fyrir hvert orð í [ORÐALISTI_SKJAL], finndu notkun þess í [KENNSLUEFNIS_SKJÖL] til að skilja nákvæma merkingu þess í námsefninu.
2.  **Finndu nákvæmar þýðingar:** Finndu faglega þýðingu fyrir hvert orð yfir á þau [TUNGUMÁL] sem tilgreind eru, sem passar fullkomlega við notkun orðsins í námsefninu.
3.  **Settu upp úttak:** Skilaðu niðurstöðunni sem snyrtilegri og prentvænni Markdown töflu, **röðuðu í stafrófsröð eftir íslenska hugtakinu**.
    * Gefðu skjalinu skýra fyrirsögn: "Orðalisti úr [NÁMSGREIN]".
    * Hafðu dálk fyrir "Íslenskt hugtak" og síðan einn dálk fyrir hvert tungumál sem beðið var um (t.d. "Ensk þýðing", "Pólsk þýðing").

Útkoman á að vera fagleg, villulaus og fullkomlega samræmd við meðfylgjandi námsefni. **EKKI birta neinar skýringar á orðunum, aðeins þýðingarnar.**
```

### Dæmi um notkun (Prompt 2)

Sami kennari í gagnasafnsfræði notar núna NotebookLM. Hann hleður upp orðalistanum sínum (`hugtök_gagn1.txt`) OG kennsluáætluninni fyrir áfangann (`gagn1_Sniðmát námsáætlunar H25.pdf`) til að fá enn nákvæmari þýðingar.

```
# Grunnstillingar (nauðsynlegt)
ORÐALISTI_SKJAL: "hugtök_gagn1.txt"
KENNSLUEFNIS_SKJÖL: "gagn1_Sniðmát námsáætlunar H25.pdf"
NÁMSGREIN: "Gagnasafnsfræði"
TUNGUMÁL: "Enska, Pólska, Víetnamska"

# Fínstillingar (valkvætt)
SKÓLASTIG: "Framhaldsskólastigi"
```
