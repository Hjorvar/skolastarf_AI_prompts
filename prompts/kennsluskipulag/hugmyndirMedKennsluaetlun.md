# Sniðmát fyrir gerð kennsluskipulags

## Stutt yfirlit

Hér er safn af *prompt*-sniðmátum sem hjálpa kennurum að umbreyta almennri kennsluáætlun í ítarlega og hagnýta **kennsluhandbók**, viku fyrir viku. Markmiðið er að spara tíma við skipulagningu og fá nýjar hugmyndir að uppbyggingu kennslustunda, verkefnum og umræðum. Sniðmátin henta bæði fyrir almenna spjallgervigreind og sérhæfðari umhverfi eins og Google NotebookLM.

-----

## Prompt 1: Sniðmát fyrir almenna gervigreind

Þetta sniðmát er fyrir almenn spjalllíkön (eins og ChatGPT, Gemini, o.fl.). Það er hannað til að geta lesið meðfylgjandi skjal (t.d. PDF eða textaskrá) með kennsluáætluninni. Textasvæðið fyrir kennsluáætlunina er hugsað sem vara-lausn ef skjalalesturinn virkar ekki sem skyldi.

```
# ------------------
# STILLANLEGAR BREYTUR (fylltu út það sem við á)
# ------------------

# Grunnstillingar (nauðsynlegt)
NÁMSGREIN: [Tilgreindu námsgrein, t.d. Gagnasafnsfræði, Stærðfræði]
SKÓLASTIG: [Tilgreindu skólastig, t.d. Framhaldsskólastigi]
FJÖLDI KENNSLUTÍMA_Á_VIKU: [Tilgreindu tölu, t.d. 2]
LENGD_HVERS_TÍMA_Í_MIN: [Tilgreindu tölu, t.d. 80]

# Fínstillingar (valkvætt)
ÁHERSLUR_Í_KENNSLU: [Lýstu þínum áherslum, t.d. "Verkefnamiðað nám", "Hagnýt sýnidæmi", "Umræður í tímum", "Virkni nemenda"]

# Gögn (nauðsynlegt)
KENNSLUÁÆTLUN: """
[Ef skjal með kennsluáætlun fylgir ekki með eða er ekki lesið rétt, afritaðu og límdu textann úr kennsluáætluninni hér.]
"""

# ------------------
# FÖST SKIPUN (ekki breyta textanum hér fyrir neðan)
# ------------------

Láttu eins og þú sért sérfræðingur í kennslufræði og námskipulagi með sérþekkingu í [NÁMSGREIN] á [SKÓLASTIG].

Verkefni þitt er að greina ítarlega kennsluáætlunina sem fylgir með sem skjal (eða er límd inn í [KENNSLUÁÆTLUN]). Byggt á þeirri greiningu skaltu útbúa fullbúna og hagnýta **kennsluhandbók fyrir kennarann**, viku fyrir viku. Taktu mið af [ÁHERSLUR_Í_KENNSLU] ef þær eru skilgreindar.

Fyrir **hverja einustu viku** í áætluninni skaltu útbúa eftirfarandi yfirlit:

**Vika [Númer]: [Heiti efnistímabils]**
* **1. Markmið vikunnar:** Hvað eiga nemendur að geta gert í lok vikunnar? Tengdu markmiðin við heildarmarkmið áfangans.
* **2. Lykilhugtök og færni:** Listi yfir mikilvægustu hugtökin og þá tæknilegu/hagnýtu færni sem farið er yfir.
* **3. Tillaga að kennsluskipulagi:** Búðu til ítarlega tillögu að uppbyggingu fyrir [FJÖLDI KENNSLUTÍMA_Á_VIKU] kennslustund(ir) sem hver er [LENGD_HVERS_TÍMA_Í_MIN] mínútur. Skiptu hverri kennslustund niður í:
    * **Upphaf (ca. 10-15% af tíma):** Hugmynd að kveikju, upprifjun úr síðasta tíma eða hvernig tengja megi efnið við fyrri þekkingu nemenda.
    * **Aðalhluti (ca. 70-80% af tíma):** Tillögur að framsetningu á námsefni. Blandaðu saman aðferðum, s.s. stutt innlegg kennara, sýnidæmi (t.d. "live coding"), umræðuspurningar, eða stuttum verkefnum fyrir nemendur.
    * **Lok (ca. 10-15% af tíma):** Hvernig á að draga saman efnið, kynna heimavinnu og gefa forskot á næsta tíma.
* **4. Tenging við námsmat:** Útskýrðu hvernig efni vikunnar tengist beint komandi námsmati (t.d. "Þessi færni er grunnur að Áfanga 1 í lokaverkefni" eða "Undirbýr nemendur fyrir styttra próf #1").
* **5. Gátlisti fyrir kennara:** Hvað þarf kennarinn að undirbúa fyrir vikuna? (t.d. "Útbúa gagnagrunn með sýnigögnum", "Finna 3 dæmi um slæma hönnun", "Semja 5 krossaprófsspurningar til upprifjunar").
```

### Dæmi um notkun (Prompt 1)

Kennari í gagnasafnsfræði hleður upp PDF-skjali með kennsluáætluninni og fyllir svo út breyturnar á þennan hátt.

```
# Grunnstillingar (nauðsynlegt)
NÁMSGREIN: "Gagnasafnsfræði"
SKÓLASTIG: "Framhaldsskólastigi"
FJÖLDI KENNSLUTÍMA_Á_VIKU: "2"
LENGD_HVERS_TÍMA_Í_MIN: "80"

# Fínstillingar (valkvætt)
ÁHERSLUR_Í_KENNSLU: "Hagnýt forritun og stöðugur undirbúningur fyrir lokaverkefni."

# Gögn (nauðsynlegt)
KENNSLUÁÆTLUN: """
[Kennsluáætlun er meðfylgjandi sem skjal, því er þetta svæði látið autt.]
"""
```

-----

## Prompt 2: Sniðmátið fyrir NotebookLM (og svipuð verkfæri)

Þetta sniðmát er sérhannað fyrir umhverfi eins og NotebookLM þar sem gervigreindin er byggð til að vinna beint með þín eigin skjöl. Það er afar einfalt í notkun: þú hleður upp kennsluáætluninni, hakar við hana sem heimild og keyrir svo promptið. Líkanið byggir allt sitt svar á þeim upplýsingum sem það finnur í þínu skjali.

```
# ------------------
# STILLANLEGAR BREYTUR (fylltu út það sem við á)
# ------------------

# Grunnstillingar (nauðsynlegt)
TÍMABIL: [Tilgreindu hvaða vikur þú vilt skipuleggja, t.d. "Allar vikur áætlunarinnar", "Vika 1-4", "Aðeins vika 8"]
FJÖLDI KENNSLUTÍMA_Á_VIKU: [Tilgreindu tölu, t.d. 2]
LENGD_HVERS_TÍMA_Í_MIN: [Tilgreindu tölu, t.d. 80]

# Fínstillingar (valkvætt)
NÁMSGREIN: [Tilgreindu námsgrein til að fínstilla tón og nálgun, t.d. Gagnasafnsfræði]
SKÓLASTIG: [Tilgreindu skólastig, t.d. Framhaldsskólastigi]
ÁHERSLUR_Í_KENNSLU: [Lýstu þínum áherslum, t.d. "Virk þátttaka nemenda", "Tenging við lokaverkefni í hverri viku", "Undirbúningur fyrir miðannarpróf"]

# ------------------
# FÖST SKIPUN (ekki breyta textanum hér fyrir neðan)
# ------------------

Láttu eins og þú sért sérfræðingur í kennslufræði og námskipulagi með sérþekkingu í [NÁMSGREIN] á [SKÓLASTIG] (ef tilgreint).

**Notaðu eingöngu upplýsingar úr meðfylgjandi heimildum (kennsluáætluninni).** Allar tillögur þínar verða að vera beintengdar við þá áætlun sem er í heimildunum.

Verkefni þitt er að útbúa fullbúna og hagnýta **kennsluhandbók fyrir kennarann** fyrir það [TÍMABIL] sem tilgreint er hér að ofan. Taktu mið af [ÁHERSLUR_Í_KENNSLU] ef þær eru skilgreindar.

Fyrir **hverja viku** á því tímabili skaltu útbúa eftirfarandi yfirlit:

**Vika [Númer]: [Heiti efnistímabils]**
* **1. Markmið vikunnar:** Dragðu saman hvaða heildarmarkmið áfangans eiga sérstaklega við í þessari viku, byggt á efni hennar.
* **2. Lykilhugtök og færni:** Byggt á efni vikunnar í áætluninni, listaðu upp þau hugtök og þá færni sem mestu máli skipta.
* **3. Tillaga að kennsluskipulagi:** Búðu til ítarlega tillögu að uppbyggingu fyrir [FJÖLDI KENNSLUTÍMA_Á_VIKU] kennslustund(ir) sem hver er [LENGD_HVERS_TÍMA_Í_MIN] mínútur. Skiptu hverri kennslustund niður í:
    * **Upphaf (ca. 10-15% af tíma):** Hugmynd að kveikju eða upprifjun sem tengist beint efni síðustu viku samkvæmt áætlun.
    * **Aðalhluti (ca. 70-80% af tíma):** Tillögur að hvernig megi kenna efni vikunnar. Leggðu áherslu á aðferðir sem henta efninu (t.d. ef um SQL er að ræða, stingdu upp á "live coding" sýnidæmum).
    * **Lok (ca. 10-15% af tíma):** Hvernig á að draga saman efnið og tengja það við næstu viku samkvæmt áætlun.
* **4. Tenging við námsmat:** Vísaðu beint í námsmatið í kennsluáætluninni. Tilgreindu hvaða verkefni eða próf er framundan og hvernig þessi vika undirbýr nemendur.
* **5. Gátlisti fyrir kennara:** Búðu til lista yfir það sem kennarinn þarf að undirbúa, byggt á efni vikunnar.
```

### Dæmi um notkun (Prompt 2)

Kennarinn hefur hlaðið upp kennsluáætluninni `GAGN1_Haust25.pdf` í NotebookLM og hakað við skjalið sem heimild. Hann vill fá yfirlit yfir kennsluna fram að miðannarprófi.

```
# Grunnstillingar (nauðsynlegt)
TÍMABIL: "Vika 1-8"
FJÖLDI KENNSLUTÍMA_Á_VIKU: "2"
LENGD_HVERS_TÍMA_Í_MIN: "80"

# Fínstillingar (valkvætt)
NÁMSGREIN: "Gagnasafnsfræði"
SKÓLASTIG: "Framhaldsskólastigi"
ÁHERSLUR_Í_KENNSLU: "Góður grunnur fyrir miðannarpróf og skil á fyrsta áfanga lokaverkefnis."
```
