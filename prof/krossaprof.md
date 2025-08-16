# Safn sniðmáta fyrir krossapróf (Multiple-Choice próf)

## Stutt yfirlit

Hér er safn af *prompt*-sniðmátum sem auðvelda gerð krossaprófa með aðstoð stórra mállíkana (LLM). Sniðmátin eru hönnuð með það í huga að prófin séu vönduð og lesendavæn, hvort sem notast er við almenna spjallgervigreind (t.d. ChatGPT eða Google Gemini) eða sérhæfðari umhverfi eins og Google NotebookLM með aðgang að kennsluefni.

Við uppsetningu skjalsins er fylgt bestu venjum fyrir Markdown til að tryggja skýra framsetningu: stuttar málsgreinar og skýrir undirkaflar auka læsileika og lykilatriði eru sett fram í punktalistum til að brjóta upp texta og draga fram meginpunkta.

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

---

## Prompt 1: Almennur LLM (án aðgangs að gögnum)

Þetta *prompt*-sniðmát er hugsað til að búa til krossapróf með almennri gervigreind eins og OpenAI ChatGPT eða Google Gemini, án þess að líkanið hafi aðgang að námsefni. Líkanið styðst því við innbyggða þekkingu sína til að semja spurningarnar. Lögð er áhersla á að spurningarnar endurspegli námsefni líffræðinnar á framhaldsskólastigi og séu orðaðar skýrt. Að lokum er beðið um svarlykil.

> Ég vil að þú látir eins og þú sért líffræðikennari á framhaldsskólastigi. Útbúðu krossapróf (fjölvalsspurningar) úr efni námskeiðs í **líffræði**.
>
> - **Fjöldi spurninga:** 10 spurningar (með fjórum svarmöguleikum hver).
> - **Tungumál:** Spurningarnar og svarmöguleikarnir skulu vera á íslensku.
> - **Innihald prófs:** Spurningarnar eiga að fjalla um lykilatriði úr námsefni líffræðinnar sem kennd eru á framhaldsskólastigi. Gefðu breiða yfirsýn yfir efnið – t.d. má prófið innihalda spurningar úr frumulíffræði, erfðafræði og vistfræði.
> - **Gæði spurninga:** Orðaðu hverja spurningu skýrt og forðastu tvíræðni eða flókin orðalag. Notaðu **ekki** neikvæða spurningauppsetningu. Hver spurning skal prófa mikilvæga staðreynd eða hugtak úr kennsluefninu.
> - **Svarmöguleikar:** Fyrir hverja spurningu skal einn svarmöguleiki vera réttur og hinir þrír rangir. Gerðu ranga svarmöguleika sannfærandi og fjölbreytta. Forðastu svarmöguleika eins og "Allt ofantalið" eða "Ekkert af ofantöldu". Gættu þess að svarmöguleikarnir séu á sömu formi (svipaðir að lengd og gerð).
> - **Útlit úttaks:** Settu spurningarnar upp á snyrtilegan hátt með númeruðum lista (1., 2., 3, ...). Tilgreindu svarmöguleika við hverja spurningu með bókstaf (a, b, c, d).
>
> Skilaðu að lokum **svarlykli** þar sem rétt svör við öllum spurningunum eru tilgreind.

### Dæmi um úttak

*Hér er dæmi um hvernig svar gæti litið út:*

**1. Hvert eftirtalinna frumulíffæra er oft nefnt "orkuver frumunnar"?**
   a. Leysikorn
   b. Hvatberi
   c. Netkorn
   d. Frymisnet

*... (og áfram þannig fyrir spurningar 1–10) ...*

**Svarlykill:**
1: b, 2: ..., ...

### Aðlögun fyrir aðrar námsgreinar eða stillingar

- **Námsgrein/efni:** Skiptu út orðinu "**líffræði**" og efnislýsingu fyrir aðra námsgrein (t.d. sögu, stærðfræði).
- **Efnisyfirlit/viðfangsefni:** Aðlagaðu lýsinguna á efni prófsins til að passa við nýju námsgreinina.
- **Fjöldi spurninga:** Breyttu fjölda spurninga og svarmöguleika eftir þörfum.
- **Tungumál:** Bættu við leiðbeiningu ef óskað er eftir tvítyngdu prófi, t.d.: `“Þýddu einnig hverja spurningu og svarmöguleika yfir á ensku og birtu samhliða íslensku útgáfunni.”`
- **Svarlykill:** Fjarlægðu skipunina um svarlykil ef prófið á að fara beint til nemenda.

---

## Prompt 2: NotebookLM (með aðgang að námsáætlun/kennsluefni)

Þetta sniðmát er sérsniðið fyrir umhverfi þar sem gervigreindin hefur aðgang að tilteknum gögnum, t.d. Google NotebookLM. Markmiðið er að spurningarnar taki mið af því efni sem raunverulega hefur verið kennt. Sniðmátið leggur ríka áherslu á að **nota eingöngu upplýsingar úr fyrirliggjandi kennslugögnum** til að forðast að spyrja úr efni sem nemendur hafa ekki kynnt sér.

> Gefið er að hér sé til staðar námsáætlun og kennsluefni fyrir áfanga í **líffræði** á framhaldsskólastigi (sem gervigreindin hefur aðgang að). Þú ert beðinn um að semja krossapróf úr því námi.
>
> **Notaðu eingöngu upplýsingar sem koma fram í fyrirliggjandi námsgögnum.**
>
> - **Lýsing:** Búðu til 10 spurninga fjölvalspróf úr efni þessarar líffræðinámsáætlunar. Spurningarnar eiga að taka mið af þeim hugtökum, staðreyndum og lögmálum sem koma fram í námsefninu.
> - **Miðað við:** Að spurningarnar séu á framhaldsskólastigi í erfiðleika og orðalagi. Forðastu að spyrja út fyrir efnið sem kennt hefur verið.
> - **Uppsetning spurninga:** Hver spurning skal vera skýr og afmörkuð. Notaðu jákvæða fullyrðingu eða spurningu. Láttu fylgja fjóra svarmöguleika (a, b, c, d) við hverja spurningu, þar sem einn er réttur en hinir rangir.
> - **Rangir svarmöguleikar:** Eiga að byggja á algengum misskilningi eða tengjast efninu þannig að ólíklegt sé að nemandi geti giskað rétt nema hafa raunþekkingu.
> - **Tungumál:** Skrifa skal spurningar og svarmöguleika á íslensku.
> - **Skil:** Skilaðu spurningunum 10 með númeraðri upplistun og tilheyrandi bókstafsmerktum svarmöguleikum. Í lokin skaltu taka saman stuttan **svarlykil**.

### Aðlögun fyrir aðrar greinar/kennslugögn

- **Námsgrein:** Skiptu út tilvísunum í **líffræði** fyrir aðra grein.
- **Aðlaga að gögnum:** Nefndu skjölin sem AI hefur aðgang að. Dæmi: `“...hefur aðgang að námsáætlun (Námsáætlun_Saga.pdf) og kennslubók (KennslubókSaga2025.pdf)...”`.
- **Efnisafmörkun:** Tilgreindu hvaða hluta efnisins á að prófa úr ef þarf. Dæmi: `“... úr efni 1.–5. kafla kennslubókarinnar ...”`.
- **Endurskoðun:** Farðu alltaf yfir útkomuna til að tryggja að spurningar séu innan efnis og svör rétt túlkuð. Fínstilltu *promptið* ef þörf krefur fyrir sérhæft efni.

---

## Samantekt

Ofangreind sniðmát ættu að nýtast kennurum og öðrum sem vilja nýta gervigreind til að útbúa vönduð krossapróf. Með því að fylgja leiðbeiningunum er einfalt að skipta út námsefni og námsgrein og búa til fjölbreytt og réttmæt krossapróf fyrir hvaða fag sem er. Með reglulegri endurskoðun má tryggja að prófin haldist í hæsta gæðaflokki og að nemendur séu prófaðir á sanngjarnan hátt.
