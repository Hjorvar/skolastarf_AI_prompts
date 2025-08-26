# Sniðmát fyrir gerð frumlegra námsverkefna

## Stutt yfirlit

Þessi *prompt*-sniðmát eru hönnuð til að aðstoða kennara við að brjótast út úr vananum og fá fjölbreyttar og skapandi hugmyndir að námsverkefnum. Markmiðið er að fá tillögur sem höfða til ólíkra styrkleika og áhugasviða nemenda, og fara lengra en hefðbundnar ritgerðir eða kynningar. Sniðmátin eru tvískipt: annað fyrir almenn spjalllíkön og hitt sérsniðið að verkfærum eins og NotebookLM sem vinna með eigin gögn kennarans.

-----

## Prompt 1: Sniðmát fyrir almenna gervigreind (LLM)

Þetta sniðmát er fyrir almenn spjalllíkön (t.d. Gemini, ChatGPT). Þú lýsir námsefninu og færð til baka úrval af ólíkum verkefnahugmyndum byggðum á almennri þekkingu líkansins. Það er öflugt tæki til að fá hugmyndir sem þér hefði kannski ekki dottið í hug sjálfum/sjálfri.

```
# ------------------
# STILLANLEGAR BREYTUR (fylltu út það sem við á)
# ------------------

# Grunnstillingar (nauðsynlegt)
NÁMSEFNI: [Lýstu námsefninu eða þemanu sem verkefnin eiga að snúast um, t.d. "Franska byltingin", "Ljóstillífun", "Íslenskir jólasveinar", "Almannaréttur á Íslandi".]
SKÓLASTIG: [Tilgreindu skólastig og/eða aldur nemenda, t.d. "Grunnskóli (miðstig)", "Framhaldsskóli", "10. bekkur".]
FJÖLDI_HUGMYNDA: [Tilgreindu hversu margar ólíkar hugmyndir þú vilt fá, t.d. 5]

# Fínstillingar (valkvætt)
ÁHERSLUR_Á_VERKEFNAGERÐ: [Tilgreindu hvers konar verkefni þú ert helst að leita að, t.d. "Stafræn miðlun", "Hagnýt/skapandi verkefni", "Hópverkefni", "Verkefni sem reyna á gagnrýna hugsun".]
TAKMARKANIR: [Lýstu því sem þú vilt forðast, t.d. "Engar hefðbundnar ritgerðir", "Engin verkefni sem krefjast flókins tækjabúnaðar", "Forðast munnlegar kynningar".]

# ------------------
# FÖST SKIPUN (ekki breyta textanum hér fyrir neðan)
# ------------------

Láttu eins og þú sért sambland af reyndum kennara, skapandi hugsuði og sérfræðingi í námshönnun.

Verkefni þitt er að búa til [FJÖLDI_HUGMYNDA] fjölbreyttar og frumlegar verkefnahugmyndir sem tengjast [NÁMSEFNI] og henta fyrir nemendur á [SKÓLASTIG].

Markmiðið er að fá hugmyndir sem eru ólíkar innbyrðis og reyna á mismunandi færni og hæfileika nemenda. Taktu mið af [ÁHERSLUR_Á_VERKEFNAGERÐ] og [TAKMARKANIR] ef þær eru skilgreindar.

Fyrir **hverja einustu hugmynd** skaltu skila eftirfarandi upplýsingum:

1.  **Heiti verkefnis:** Grípandi og lýsandi titill.
2.  **Verkefnalýsing:** Hvað gengur verkefnið út á? Hvað eiga nemendur að gera?
3.  **Tenging við námsefnið:** Hvernig sýna nemendur skilning sinn á [NÁMSEFNI] með þessu verkefni?
4.  **Helstu námsmarkmið:** Hvaða færni er verið að meta? (t.d. sköpun, samvinna, rannsóknarvinna, gagnrýnin hugsun, tæknilæsi).
5.  **Afurð:** Hverju skila nemendur inn? (t.d. hlaðvarpsþáttur, vefsíða, líkan, myndasaga, handrit, herferðarplan).
6.  **Hugmynd að námsmati:** Hvernig væri hægt að meta verkefnið? (t.d. með matsramma, jafningjamati, sýningu).
```

### Dæmi um notkun (Prompt 1)

Sögukennari vill fá nýjar hugmyndir fyrir verkefni um frönsku byltinguna og er orðinn þreyttur á ritgerðum.

```
# Grunnstillingar (nauðsynlegt)
NÁMSEFNI: "Orsakir og afleiðingar frönsku byltingarinnar."
SKÓLASTIG: "Framhaldsskóli (Saga 203)"
FJÖLDI_HUGMYNDA: 4

# Fínstillingar (valkvætt)
ÁHERSLUR_Á_VERKEFNAGERÐ: "Stafræn miðlun og verkefni sem reyna á skapandi hugsun."
TAKMARKANIR: "Engar hefðbundnar ritgerðir eða kynningar fyrir framan bekkinn."
```

-----

## Prompt 2: Sniðmát fyrir NotebookLM (og svipuð verkfæri)

Þetta sniðmát er hannað fyrir umhverfi þar sem þú hefur hlaðið upp námsefninu þínu (t.d. lesefni, glærum, verkefnalýsingum). Gervigreindin notar þá þín eigin gögn til að búa til verkefnahugmyndir sem eru fullkomlega sniðnar að því efni sem þú ert að kenna.

```
# ------------------
# STILLANLEGAR BREYTUR (fylltu út það sem við á)
# ------------------

# Grunnstillingar (nauðsynlegt)
HEIMILDASKJÖL: [Nefndu skjalið/skjölin sem innihalda námsefnið, t.d. "Kafli_5_Vistkerfi.pdf", "Glærur_um_ljóstillífun.pptx".]
NÁMSEFNI_INNAN_HEIMILDA: [Tilgreindu hvaða hluta námsefnisins þú vilt leggja áherslu á, t.d. "Fæðukeðjur og fæðuvefir", "Hringrás kolefnis".]
SKÓLASTIG: [Tilgreindu skólastig og/eða aldur nemenda.]
FJÖLDI_HUGMYNDA: [Tilgreindu hversu margar ólíkar hugmyndir þú vilt fá, t.d. 3]

# Fínstillingar (valkvætt)
ÁHERSLUR_Á_VERKEFNAGERÐ: [Tilgreindu hvers konar verkefni þú ert helst að leita að, t.d. "Hagnýt úrlausn vandamála", "Listræn túlkun", "Verkefni sem tengjast närmarkinu".]
TAKMARKANIR: [Lýstu því sem þú vilt forðast, t.d. "Verkefni sem krefjast mikillar hópavinnu", "Einungis einstaklingsverkefni".]

# ------------------
# FÖST SKIPUN (ekki breyta textanum hér fyrir neðan)
# ------------------

Láttu eins og þú sért sambland af reyndum kennara, skapandi hugsuði og sérfræðingi í námshönnun.

**Notaðu eingöngu upplýsingar og samhengi úr völdum [HEIMILDASKJÖL] til að byggja hugmyndirnar.**

Verkefni þitt er að búa til [FJÖLDI_HUGMYNDA] fjölbreyttar og frumlegar verkefnahugmyndir. Hugmyndirnar eiga að byggja á [NÁMSEFNI_INNAN_HEIMILDA] eins og því er lýst í heimildunum og henta fyrir nemendur á [SKÓLASTIG].

Markmiðið er að fá hugmyndir sem eru ólíkar innbyrðis og nýta efnið úr heimildunum á skapandi hátt. Taktu mið af [ÁHERSLUR_Á_VERKEFNAGERÐ] og [TAKMARKANIR] ef þær eru skilgreindar.

Fyrir **hverja einustu hugmynd** skaltu skila eftirfarandi upplýsingum:

1.  **Heiti verkefnis:** Grípandi titill sem tengist efninu.
2.  **Verkefnalýsing:** Hvað eiga nemendur að gera, byggt á efninu í heimildunum?
3.  **Tenging við námsefnið:** Hvernig endurspeglar verkefnið beint þær upplýsingar eða hugtök sem koma fram í [HEIMILDASKJÖL]?
4.  **Helstu námsmarkmið:** Hvaða færni er verið að meta?
5.  **Afurð:** Hverju skila nemendur inn?
6.  **Hugmynd að námsmati:** Hvernig væri hægt að meta verkefnið?
```

### Dæmi um notkun (Prompt 2)

Líffræðikennari hefur hlaðið upp kafla úr kennslubók um vistfræði og vill fá hugmyndir að verkefnum sem tengjast íslenskri náttúru.

```
# Grunnstillingar (nauðsynlegt)
HEIMILDASKJÖL: "Lífríkið_Kafli_8_Vistfræði.pdf"
NÁMSEFNI_INNAN_HEIMILDA: "Samspil lífvera og samfélög í vistkerfum."
SKÓLASTIG: "Framhaldsskóli, Líffræði 103"
FJÖLDI_HUGMYNDA: 3

# Fínstillingar (valkvætt)
ÁHERSLUR_Á_VERKEFNAGERÐ: "Verkefni sem tengjast närmarkinu og nýta stafræna tækni."
TAKMARKANIR: "Forðast verkefni sem krefjast ferðalaga út fyrir skólalóðina."
```
