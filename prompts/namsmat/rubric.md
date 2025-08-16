# Sniðmát fyrir gerð matsramma (Rubrics)

## Stutt yfirlit

Hér er safn af *prompt*-sniðmátum sem auðvelda kennurum gerð á skýrum og vönduðum matsrömmum (e. *rubrics*). Góður matsrammi er lykiltæki til að tryggja sanngjarnt og gagnsætt námsmat og veita nemendum hagnýta endurgjöf. Sniðmátin henta bæði fyrir almenna spjallgervigreind og sérhæfðari umhverfi eins og Google NotebookLM.

-----

## Prompt 1: Sniðmát fyrir almenna gervigreind

Þetta sniðmát er fyrir almenn spjalllíkön (eins og ChatGPT, Gemini, o.fl.) sem byggja á almennri þekkingu sinni. Það er einfalt í notkun og notar staðlaðan hæfnikvarða til þæginda, en leyfir sérsniðna aðlögun ef þörf krefur.

```
# ------------------
# STILLANLEGAR BREYTUR (fylltu út það sem við á)
# ------------------

# Grunnstillingar (nauðsynlegt)
VERKEFNISLÝSING: [Lýstu verkefninu sem meta á, t.d. "5 blaðsíðna ritgerð um orsakir frönsku byltingarinnar", "10 mínútna munnleg kynning um ljóstillífun".]
MATSÞÆTTIR: [Tilgreindu þá þætti sem á að meta, aðskilið með kommu, t.d. "Innihald og rökstuðningur, Bygging og flæði, Málfar og stafsetning, Heimildanotkun".]

# Fínstillingar (valkvætt)
HÆFNISTIG: [Skilgreindu þinn eigin kvarða ef þú vilt ekki nota sjálfgefna kvarðann. T.d. "A, B, C, D"]
NÁMSGREIN: [Tilgreindu námsgrein, t.d. Saga, Líffræði]
SKÓLASTIG: [Tilgreindu skólastig, t.d. Framhaldsskólastigi]

# ------------------
# FÖST SKIPUN (ekki breyta textanum hér fyrir neðan)
# ------------------

Láttu eins og þú sért reyndur kennari í [NÁMSGREIN] á [SKÓLASTIG] (ef tilgreint). Verkefni þitt er að útbúa hágæða greinandi matsramma fyrir eftirfarandi verkefni: [VERKEFNISLÝSING].

- Uppbygging: Búðu til matsramma sem byggir á matsþáttunum: [MATSÞÆTTIR]. Notaðu eftirfarandi hæfnisstig sem dálka: "Framúrskarandi", "Gott", "Sæmilegt", "Þarfnast úrbóta". Ef önnur stig eru tilgreind í [HÆFNISTIG], notaðu þau í staðinn.
- Gæðakröfur: Fyrir hvern reit í matsrammanum skaltu skrifa skýra, hlutlæga og uppbyggilega lýsingu á frammistöðu. Textinn á að vera auðskilinn fyrir nemendur.
- Framsetning og útlit: Skilaðu matsrammanum sem Markdown töflu.
```

### Dæmi um notkun (Prompt 1)

Hér er dæmi um hvernig sögukennari gæti fyllt út breyturnar til að búa til matsramma fyrir ritgerð um Kalda stríðið.

```
# Grunnstillingar (nauðsynlegt)
VERKEFNISLÝSING: "3-5 blaðsíðna ritgerð um upphaf Kalda stríðsins og helstu áhrifaþætti."
MATSÞÆTTIR: "Innihald og söguleg nákvæmni, Rökstuðningur og greining, Bygging ritgerðar, Málfar og frágangur, Heimildanotkun."

# Fínstillingar (valkvætt)
HÆFNISTIG:
NÁMSGREIN: Saga
SKÓLASTIG: Framhaldsskólastigi
```

-----

## Prompt 2: „Sjálfvirka“ sniðmátið fyrir NotebookLM

Þetta sniðmát er sérhannað fyrir umhverfi eins og NotebookLM þar sem gervigreindin hefur aðgang að þínum eigin skjölum. Það er afar einfalt í notkun: þú bendir aðeins á skjalið með verkefnalýsingunni og líkanið finnur og dregur út þær upplýsingar sem þarf til að búa til matsrammann.

```
# ------------------
# STILLANLEGAR BREYTUR (fylltu út það sem við á)
# ------------------

# Grunnstilling (nauðsynlegt)
VERKEFNISHEIMILD: [Nefndu skjalið sem inniheldur verkefnalýsinguna, t.d. "Verkefni3-Ritgerd.pdf"]

# Fínstillingar (valkvætt)
HÆFNISTIG: [Skilgreindu þinn eigin kvarða ef þú vilt ekki nota sjálfgefna kvarðann. T.d. "A, B, C, D"]
NÁMSGREIN: [Tilgreindu námsgrein til að fínstilla tón]
SKÓLASTIG: [Tilgreindu skólastig til að fínstilla flækjustig]

# ------------------
# FÖST SKIPUN (ekki breyta textanum hér fyrir neðan)
# ------------------

Láttu eins og þú sért reyndur og nákvæmur kennari í [NÁMSGREIN] á [SKÓLASTIG] (ef tilgreint). Þitt verkefni er að útbúa hágæða greinandi matsramma.

Notaðu eingöngu þær heimildir sem eru valdar í þessu verkefni.

1.  Greindu heimildirnar: Lestu valdar heimildir og finndu meginverkefnalýsinguna í skjalinu sem heitir [VERKEFNISHEIMILD].
2.  Dragðu út matsþætti: Ályktaðu út frá markmiðum og lýsingu í textanum hverjir helstu matsþættir verkefnisins eiga að vera. Þetta verða raðirnar í matsrammanum.
3.  Búðu til matsrammann: Notaðu eftirfarandi hæfnisstig sem dálka: "Framúrskarandi", "Gott", "Sæmilegt", "Þarfnast úrbóta". Ef önnur stig eru tilgreind í [HÆFNISTIG], notaðu þau í staðinn.
4.  Skrifaðu lýsingar: Fyrir hvern reit í rammanum skaltu skrifa skýra, hlutlæga lýsingu sem endurspeglar beint þær kröfur sem komu fram í upprunalegu verkefnalýsingunni.
5.  Skilaðu niðurstöðu: Skilaðu fullbúnum matsramma sem Markdown töflu.
```

### Dæmi um notkun (Prompt 2)

Hér er dæmi um hvernig sami sögukennari notar sjálfvirka sniðmátið. Hann hefur hlaðið upp skjali með verkefnalýsingunni í NotebookLM og hakað við það.

```
# Grunnstilling (nauðsynlegt)
VERKEFNISHEIMILD: "Ritgerd_Kaldastridid.pdf"

# Fínstillingar (valkvætt)
HÆFNISTIG: "A (9-10), B (7-8), C (5-6), D (Fall)"
NÁMSGREIN: Saga
SKÓLASTIG: Framhaldsskólastigi
```

-----
