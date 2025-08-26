# Sniðmát fyrir gerð stærðfræði-kennsluleiðbeininga

## Stutt yfirlit

Þessi *prompt*-sniðmát eru hönnuð fyrir stærðfræðikennara sem vilja útbúa skýrar og nákvæmar kennsluleiðbeiningar um afmörkuð stærðfræðileg efni. Megináherslan er á að fá vandaðar útskýringar, góð sýnidæmi með réttu **LaTeX** formati og möguleikann á að fá allt efnið á mismunandi tungumálum. Þetta getur verið sérstaklega gagnlegt í fjölmenningarlegum skólaumhverfum eða við undirbúning efnis fyrir nemendur með annað móðurmál en kennarinn.

-----

## Prompt 1: Sniðmát fyrir almenna gervigreind (LLM)

Þetta sniðmát er fyrir almenn spjalllíkön (t.d. Gemini, ChatGPT). Kennarinn slær inn viðfangsefnið og fær tilbúna kennslustund byggða á almennri stærðfræðiþekkingu líkansins.

```
# ------------------
# STILLANLEGAR BREYTUR (fylltu út það sem við á)
# ------------------

# Grunnstillingar (nauðsynlegt)
STÆRÐFRÆÐIEFNI: [Lýstu stærðfræðilega viðfangsefninu sem á að kenna, t.d. "Pýþagórasarreglan", "Annars stigs jafna og lausnarformúlan (abc-formúlan)", "Hlutreikningur (integration by parts)".]
NÁMSSTIG_NEMENDA: [Lýstu þekkingarstigi nemenda, t.d. "Grunnskóli (unglingastig)", "Framhaldsskóli (áfangi STÆ203)", "Háskólastig (grunnkurs í stærðfræðigreiningu)".]
MARKMÁL_ÚTTAKS: [Tilgreindu tungumálið sem leiðbeiningarnar eiga að vera á, t.d. "Íslenska", "Pólska", "Enska", "Spænska".]

# Fínstillingar (valkvætt)
FJÖLDI_SÝNIDÆMA: [Tilgreindu tölu, t.d. 3]
ÁHERSLUR_Í_KENNSLU: [Lýstu sérstökum áherslum ef einhverjar eru, t.d. "Einblína á sjónrænar útskýringar", "Tengja við raunveruleikadæmi úr eðlisfræði", "Sýna hvernig hægt er að nota GeoGebra til að leysa dæmin".]

# ------------------
# FÖST SKIPUN (ekki breyta textanum hér fyrir neðan)
# ------------------

Láttu eins og þú sért reyndur stærðfræðikennari og sérfræðingur í að útskýra flókin stærðfræðihugtök á einfaldan og skilmerkilegan hátt.

Verkefni þitt er að útbúa ítarlegar og prentvænar kennsluleiðbeiningar um [STÆRÐFRÆÐIEFNI] fyrir nemendur á því námsstigi sem lýst er í [NÁMSSTIG_NEMENDA].
**Allur texti í svarinu skal vera á [MARKMÁL_ÚTTAKS].**

Byggðu kennsluleiðbeiningarnar upp samkvæmt eftirfarandi uppbyggingu:

1.  **Heiti efnis:** Skýr og lýsandi titill.
2.  **Markmið kennslustundar:** Hvað á nemandinn að geta gert eftir að hafa farið yfir efnið?
3.  **Lykilhugtök og kenning:** Stutt og hnitmiðuð útskýring á þeim fræðilega grunni sem efnið byggir á.
4.  **Skref-fyrir-skref aðferð:** Hagnýt og einföld lýsing á aðferðinni sem nota á til að leysa dæmi af þessari tegund.
5.  **Sýnidæmi með ítarlegum úrlausnum:** Búðu til [FJÖLDI_SÝNIDÆMA] sýnidæmi (eða 3 ef fjöldi er ekki tilgreindur). Sýndu lausnina í skýrum skrefum.
6.  **Algengar villur og mikilvæg atriði:** Bentu á algengan misskilning eða atriði sem nemendur eiga að varast.

**MIKILVÆGT:** ÖLL stærðfræðileg tákn, breytur, formúlur og jöfnur skulu vera settar fram með **LaTeX-sniði**. Notaðu `$` utan um stök tákn og formúlur í texta (inline) og `$$` utan um stærri jöfnur eða formúlur sem standa sér (display).
```

### Dæmi um notkun (Prompt 1)

Stærðfræðikennari í framhaldsskóla þarf að útbúa efni um diffurreglur fyrir nemendahóp þar sem nokkrir tala pólsku.

```
# Grunnstillingar (nauðsynlegt)
STÆRÐFRÆÐIEFNI: "Helstu diffurreglur (margfeldisregla og deilingarregla)"
NÁMSSTIG_NEMENDA: "Framhaldsskóli, fyrsti áfangi í diffur- og heildreikningi."
MARKMÁL_ÚTTAKS: "Pólska"

# Fínstillingar (valkvætt)
FJÖLDI_SÝNIDÆMA: 4
ÁHERSLUR_Í_KENNSLU: "Sýna dæmi með margliðum, rótum og hornaföllum."
```

-----

## Prompt 2: Sniðmát fyrir NotebookLM (og svipuð verkfæri)

Þetta sniðmát er hannað fyrir umhverfi þar sem kennari getur hlaðið upp eigin skjölum (t.d. kafla úr kennslubók, eigin glósum eða verkefnablöðum). Gervigreindin notar þá þessi skjöl sem aðalheimild til að sníða kennsluleiðbeiningarnar að nákvæmlega því efni og þeim aðferðum sem kennarinn notar.

```
# ------------------
# STILLANLEGAR BREYTUR (fylltu út það sem við á)
# ------------------

# Grunnstillingar (nauðsynlegt)
STÆRÐFRÆÐIEFNI: [Lýstu stærðfræðilega viðfangsefninu sem á að kenna, t.d. "Vigurmargföldun (krossmargfeldi)".]
NÁMSSTIG_NEMENDA: [Lýstu þekkingarstigi nemenda, t.d. "Háskólastig (línuleg algebra)".]
MARKMÁL_ÚTTAKS: [Tilgreindu tungumálið sem leiðbeiningarnar eiga að vera á, t.d. "Íslenska", "Enska".]

# Fínstillingar (valkvætt, en öflugt)
HEIMILDASKJAL: [Nefndu skjalið sem inniheldur námsefnið, t.d. "Kafli_7_Vigrar.pdf". Ef ekkert skjal er tilgreint, notar líkanið almenna þekkingu.]
ÁHERSLUR_Í_KENNSLU: [Lýstu sérstökum áherslum ef einhverjar eru, t.d. "Einblína á rúmfræðilega túlkun", "Sýna tengingu við útreikning á flatarmáli".]

# ------------------
# FÖST SKIPUN (ekki breyta textanum hér fyrir neðan)
# ------------------

Láttu eins og þú sért nákvæmur og reyndur stærðfræðikennari sem útbýr námsefni fyrir aðra.

Verkefni þitt er að útbúa ítarlegar og prentvænar kennsluleiðbeiningar um [STÆRÐFRÆÐIEFNI] fyrir [NÁMSSTIG_NEMENDA].
**Allur texti í svarinu skal vera á [MARKMÁL_ÚTTAKS].**

**Heimildanotkun:** Ef [HEIMILDASKJAL] er tilgreint, skaltu byggja allar útskýringar, sýnidæmi og orðalag á innihaldi þess skjals. Notaðu sömu aðferðir og framsetningu og þar kemur fram. Ef ekkert skjal er tilgreint, byggðu svarið á almennri stærðfræðiþekkingu.

Byggðu kennsluleiðbeiningarnar upp samkvæmt eftirfarandi uppbyggingu:

1.  **Heiti efnis:** Skýr og lýsandi titill.
2.  **Markmið kennslustundar:** Hvað á nemandinn að geta gert eftir kennslustundina?
3.  **Lykilhugtök og kenning:** Útskýrðu fræðin á bakvið efnið.
4.  **Skref-fyrir-skref aðferð:** Hagnýt lýsing á úrlausnaraðferðinni.
5.  **Sýnidæmi með ítarlegum úrlausnum:** Búðu til 3 fjölbreytt sýnidæmi sem endurspegla efnið.
6.  **Algengar villur og mikilvæg atriði:** Bentu á atriði sem krefjast sérstakrar athygli.

**MIKILVÆGT:** ÖLL stærðfræðileg tákn, breytur, formúlur og jöfnur skulu vera settar fram með **LaTeX-sniði**. Notaðu `$` utan um stök tákn og formúlur í texta (inline) og `$$` utan um stærri jöfnur eða formúlur sem standa sér (display).
```

### Dæmi um notkun (Prompt 2)

Kennari er að undirbúa tíma um heildun og hefur hlaðið upp eigin glósum (`Heildun_glosur.pdf`) í NotebookLM. Hann vill fá efnið á ensku fyrir skiptinema.

```
# Grunnstillingar (nauðsynlegt)
STÆRÐFRÆÐIEFNI: "Óákveðin heildi og stofnföll"
NÁMSSTIG_NEMENDA: "Háskólastig, grunnáfangi í stærðfræðigreiningu"
MARKMÁL_ÚTTAKS: "Enska"

# Fínstillingar (valkvætt, en öflugt)
HEIMILDASKJAL: "Heildun_glosur.pdf"
ÁHERSLUR_Í_KENNSLU: "Leggja áherslu á heildunarfastann C og sýna hvernig á að prófa lausnina með diffun."
```
