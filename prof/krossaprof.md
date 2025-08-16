# Safn sniðmáta fyrir krossapróf (Multiple-Choice próf)

## Stutt yfirlit

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

-----

## Prompt 1: Sveigjanlegt sniðmát fyrir almenna gervigreind

Þetta sniðmát er hannað til að vera sveigjanlegt og einfalt í notkun. Efst í því er kafli fyrir **„Stillanlegar breytur“** þar sem notandinn getur auðveldlega skilgreint námsgrein, skólastig og efni prófsins. Með því að breyta aðeins upplýsingum á þessum eina stað er hægt að útbúa próf fyrir hvaða námsgrein sem er.

Sniðmátið biður einnig um ítarlegan og rökstuddan svarlykil sem gerir prófið að hagnýtu kennslutæki fyrir bæði kennara og nemendur.

```
# ------------------
# STILLANLEGAR BREYTUR (breyttu aðeins textanum hér)
# ------------------

**NÁMSGREIN:** [Hér setur þú inn námsgrein, t.d. Saga, Stærðfræði, Líffræði]
**SKÓLASTIG:** [Hér setur þú inn skólastig, t.d. Framhaldsskólastigi, Grunnskólastigi]
**FJÖLDI SPURNINGA:** [Hér setur þú inn tölu, t.d. 10]
**NÁNARI LÝSING Á EFNISÞÁTTUM:** [Lýstu hér efninu sem prófið á að ná yfir.]

# ------------------
# FÖST SKIPUN (ekki breyta textanum hér fyrir neðan)
# ------------------

Ég vil að þú látir eins og þú sért kennari í **[NÁMSGREIN]** á **[SKÓLASTIG]**. Útbúðu krossapróf (fjölvalsspurningar) úr efni námskeiðs í **[NÁMSGREIN]**.

- **Fjöldi spurninga:** **[FJÖLDI SPURNINGA]** spurningar (með fjórum svarmöguleikum hver).
- **Tungumál:** Spurningarnar og svarmöguleikarnir skulu vera á íslensku.
- **Innihald prófs:** **[NÁNARI LÝSING Á EFNISÞÁTTUM]**
- **Gæði spurninga:** Orðaðu hverja spurningu skýrt og forðastu tvíræðni eða flókin orðalag. Notaðu EKKI neikvæða spurningauppsetningu. Hver spurning skal prófa mikilvæga staðreynd eða hugtak úr kennsluefninu.
- **Svarmöguleikar:** Fyrir hverja spurningu skal einn svarmöguleiki vera réttur og hinir þrír rangir. Gerðu ranga svarmöguleika sannfærandi og fjölbreytta, en þannig að vel að sér nemandi geti greint rétt svar. Forðastu svarmöguleika eins og "Allt ofantalið" eða "Ekkert af ofantöldu". Gættu þess að svarmöguleikarnir séu á sömu formi (svipaðir að lengd og gerð).
- **Útlit úttaks:** Settu spurningarnar upp á snyrtilegan hátt með númeruðum lista (1., 2., 3, ...). Tilgreindu svarmöguleika við hverja spurningu með bókstaf (a, b, c, d).

**Í svarlyklinum skaltu birta rétt svar fyrir hverja spurningu. Fyrir hvert svar skaltu einnig skrifa stutta útskýringu sem rökstyður hvers vegna svarið er rétt og gefur stutta skýringu á því hvers vegna hinir svarmöguleikarnir eru rangir.**
```

### Dæmi um úttak (með rökstuddum svarlykli)

*Hér er dæmi um hvernig svarlykillinn myndi líta út fyrir eina spurningu:*

**Svarlykill**

**1. Svar: b**

  * **Rökstuðningur:** Hvatberar eru þekktir sem „orkuver“ frumunnar vegna þess að þeir framkvæma frumuöndun. Í því ferli er glúkósa og súrefni breytt í ATP, sem er aðalorkugjafi frumunnar.
  * **Af hverju hitt er rangt:**
      * **a) Leysikorn:** Eru „ruslaverksmiðjur“ frumunnar sem brjóta niður úrgangsefni.
      * **c) Netkorn (ríbósóm):** Sjá um próteinmyndun.
      * **d) Frymisnet:** Er flutningskerfi innan frumunnar.

### Aðlögun og notkun

Að nota sniðmátið er einfalt. Fylltu aðeins út upplýsingarnar í **STILLANLEGAR BREYTUR** hlutanum efst og afritaðu síðan allt sniðmátið (bæði breytur og föstu skipun) yfir í spjalllíkanið.

**Dæmi fyrir sagnfræðipróf:**

```
**NÁMSGREIN:** Saga
**SKÓLASTIG:** Framhaldsskólastigi
**FJÖLDI SPURNINGA:** 5
**NÁNARI LÝSING Á EFNISÞÁTTUM:** Spurningarnar eiga að fjalla um lykilatriði í seinni heimsstyrjöldinni, með áherslu á helstu orsakir, viðsnúninga og afleiðingar stríðsins.
```

-----

## Prompt 2: NotebookLM (með aðgang að námsáætlun/kennsluefni)

Þetta sniðmát er sérsniðið fyrir umhverfi þar sem gervigreindin hefur aðgang að tilteknum gögnum, t.d. Google NotebookLM. Markmiðið er að spurningarnar taki mið af því efni sem raunverulega hefur verið kennt. Sniðmátið leggur ríka áherslu á að **nota eingöngu upplýsingar úr fyrirliggjandi kennslugögnum** til að forðast að spyrja úr efni sem nemendur hafa ekki kynnt sér.

> Gefið er að hér sé til staðar námsáætlun og kennsluefni fyrir áfanga í **líffræði** á framhaldsskólastigi (sem gervigreindin hefur aðgang að). Þú ert beðinn um að semja krossapróf úr því námi.
>
> **Notaðu eingöngu upplýsingar sem koma fram í fyrirliggjandi námsgögnum.**
>
>   - **Lýsing:** Búðu til 10 spurninga fjölvalspróf úr efni þessarar líffræðinámsáætlunar. Spurningarnar eiga að taka mið af þeim hugtökum, staðreyndum og lögmálum sem koma fram í námsefninu.
>   - **Miðað við:** Að spurningarnar séu á framhaldsskólastigi í erfiðleika og orðalagi. Forðastu að spyrja út fyrir efnið sem kennt hefur verið.
>   - **Uppsetning spurninga:** Hver spurning skal vera skýr og afmörkuð. Notaðu jákvæða fullyrðingu eða spurningu. Láttu fylgja fjóra svarmöguleika (a, b, c, d) við hverja spurningu, þar sem einn er réttur en hinir rangir.
>   - **Rangir svarmöguleikar:** Eiga að byggja á algengum miskilningi eða tengjast efninu þannig að ólíklegt sé að nemandi geti giskað rétt nema hafa raunþekkingu.
>   - **Tungumál:** Skrifa skal spurningar og svarmöguleika á íslensku.
>   - **Skil:** Skilaðu spurningunum 10 með númeraðri upplistun og tilheyrandi bókstafsmerktum svarmöguleikum. Í lokin skaltu taka saman stuttan **svarlykil**.

### Aðlögun fyrir aðrar greinar/kennslugögn

  - **Námsgrein:** Skiptu út tilvísunum í **líffræði** fyrir aðra grein.
  - **Aðlaga að gögnum:** Nefndu skjölin sem AI hefur aðgang að. Dæmi: `“...hefur aðgang að námsáætlun (Námsáætlun_Saga.pdf) og kennslubók (KennslubókSaga2025.pdf)...”`.
  - **Efnisafmörkun:** Tilgreindu hvaða hluta efnisins á að prófa úr ef þarf. Dæmi: `“... úr efni 1.–5. kafla kennslubókarinnar ...”`.
  - **Endurskoðun:** Farðu alltaf yfir útkomuna til að tryggja að spurningar séu innan efnis og svör rétt túlkuð. Fínstilltu *promptið* ef þörf krefur fyrir sérhæft efni.
