# Sniðmát fyrir hönnun námsmats

## Stutt yfirlit

Þessi *prompt*-sniðmát eru hönnuð til að aðstoða kennara við að þróa heildstætt, sanngjarnt og markvisst námsmat fyrir áfanga. Gervigreindin, í hlutverki kennslusérfræðings, greinir kennsluáætlun og stingur upp á skiptingu matsþátta, aðferðum og tímasetningum sem endurspegla markmið áfangans. Þetta er öflug leið til að fá utanaðkomandi sjónarhorn á námsmatið og tryggja að það mæli þá þekkingu og færni sem lagt er upp með.

-----

## Prompt 1: Sniðmát fyrir almenna gervigreind (LLM)

Þetta sniðmát gerir ráð fyrir að þú hleður upp kennsluáætluninni þinni sem skjali (t.d. PDF, Word). Gervigreindin greinir skjalið og byggir tillögur sínar á þeim markmiðum og því efnisyfirliti sem þar kemur fram.

```
# ------------------
# STILLANLEGAR BREYTUR (fylltu út það sem við á)
# ------------------

# Grunnstillingar (nauðsynlegt)
NÁMSGREIN: [Tilgreindu námsgrein, t.d. "Gagnasafnsfræði", "Íslenska", "Líffræði".]
SKÓLASTIG: [Tilgreindu skólastig, t.d. "Framhaldsskólastig", "Grunnskóli (unglingastig)".]

# Fínstillingar (valkvætt)
ÁHERSLUR_KENNARA_Í_NÁMSMATI: [Lýstu þínum áherslum eða óskum, t.d. "Ég vil leggja meiri áherslu á verkefni en próf", "Ég vil nota fjölbreytt leiðsagnarmat", "Forðast stórt lokapróf", "Allt námsmat þarf að vera einstaklingsbundið".]

# ------------------
# FÖST SKIPUN (ekki breyta textanum hér fyrir neðan)
# ------------------

Láttu eins og þú sért sérfræðingur í kennslufræði og námsmati með áralanga reynslu af því að hanna og greina námskeið á [SKÓLASTIG].

Verkefni þitt er að greina ítarlega meðfylgjandi kennsluáætlun fyrir áfangann [NÁMSGREIN]. Byggt á þeirri greiningu skaltu útbúa tillögu að heildstæðu og réttlátu námsmati. Taktu mið af [ÁHERSLUR_KENNARA_Í_NÁMSMATI] ef þær eru tilgreindar.

Skilaðu svarinu á skipulagðan hátt með eftirfarandi köflum:

**1. Yfirlit og rökstuðningur:**
Stutt samantekt þar sem þú greinir helstu markmið áfangans og rökstyður heildarsýn þína á hvernig námsmatið ætti að endurspegla þau.

**2. Tillaga að skiptingu námsmats (%):**
Settu upp með skýrum punktalista hvernig heildareinkunnin gæti skiptst niður í prósentur. Dæmi:
* Verkefni: 40%
* Miðannarpróf: 25%
* Lokapróf: 35%

**3. Ítarleg útfærsla á hverjum matsþætti:**
Settu upp töflu eða lista sem útskýrir hvern matsþátt nánar:
* **Matsþáttur:** Heiti (t.d. "Hópverkefni", "Minni próf", "Verkefnamappa").
* **Hvað er metið?:** Hvaða þekking eða færni úr markmiðum áfangans er verið að meta með þessum þætti?
* **Hvernig er metið?:** Lýsing á matsaðferðinni (t.d. "Skýrslugerð með jafningjamati", "Verklegt próf í tölvuveri", "Munnleg vörn").
* **Tillaga að tímasetningu:** Hvenær á önninni væri best að leggja þennan matsþátt fyrir, byggt á efnisyfirliti kennsluáætlunar?

**4. Rökstuðningur fyrir tímasetningum:**
Útskýrðu stuttlega af hverju tímasetningar á stærri matsþáttum (prófum, stórum verkefnaskilum) eru valdar eins og þú leggur til.
```

### Dæmi um notkun (Prompt 1)

Kennari í gagnasafnsfræði hleður upp kennsluáætluninni sinni og vill fá hugmyndir að námsmati sem leggur meiri áherslu á verkefni en próf.

```
# Grunnstillingar (nauðsynlegt)
NÁMSGREIN: "Gagnasafnsfræði"
SKÓLASTIG: "Framhaldsskólastig"

# Fínstillingar (valkvætt)
ÁHERSLUR_KENNARA_Í_NÁMSMATI: "Ég vil leggja meiri áherslu á hagnýt verkefni sem byggjast upp yfir önnina og minna vægi á stökum prófum."
```

-----

## Prompt 2: Sniðmát fyrir NotebookLM (og svipuð verkfæri)

Þetta sniðmát er sérhannað fyrir umhverfi þar sem kennsluáætlunin er til staðar sem upphlaðin heimild. Gervigreindin mun þá byggja allar sínar ályktanir og tillögur **eingöngu** á innihaldi skjalsins, sem tryggir að svarið sé fullkomlega samstillt þínu efni.

```
# ------------------
# STILLANLEGAR BREYTUR (fylltu út það sem við á)
# ------------------

# Grunnstillingar (nauðsynlegt)
HEIMILDASKJAL: [Nefndu skjalið sem inniheldur kennsluáætlunina, t.d. "Kennsluáætlun_STÆ303.pdf".]
NÁMSGREIN: [Tilgreindu námsgrein til að fínstilla tón og nálgun.]
SKÓLASTIG: [Tilgreindu skólastig.]

# Fínstillingar (valkvætt)
ÁHERSLUR_KENNARA_Í_NÁMSMATI: [Lýstu þínum áherslum eða óskum, t.d. "Ég vil sjá hvernig hægt er að flétta meira leiðsagnarmati inn í áfangann", "Leggja áherslu á einstaklingsframtak".]

# ------------------
# FÖST SKIPUN (ekki breyta textanum hér fyrir neðan)
# ------------------

Láttu eins og þú sért sérfræðingur í kennslufræði og námsmati.

**Notaðu eingöngu upplýsingar úr [HEIMILDASKJAL] til grundvallar greiningu þinni og tillögum.** Allar ályktanir þínar verða að vera studdar beinum vísunum í markmið eða efnisyfirlit skjalsins.

Verkefni þitt er að greina kennsluáætlunina í heimildinni og útbúa tillögu að heildstæðu og réttlátu námsmati fyrir áfangann [NÁMSGREIN] á [SKÓLASTIG]. Taktu mið af [ÁHERSLUR_KENNARA_Í_NÁMSMATI] ef þær eru tilgreindar.

Skilaðu svarinu á skipulagðan hátt með eftirfarandi köflum:

**1. Yfirlit og rökstuðningur:**
Stutt samantekt þar sem þú greinir helstu markmið áfangans (og vitnar í þau) og rökstyður hvernig tillaga þín að námsmati mælir þau markmið á áhrifaríkan hátt.

**2. Tillaga að skiptingu námsmats (%):**
Settu upp með skýrum punktalista hvernig heildareinkunnin gæti skiptst niður í prósentur.

**3. Ítarleg útfærsla á hverjum matsþætti:**
Settu upp töflu eða lista sem útskýrir hvern matsþátt nánar:
* **Matsþáttur:** Heiti.
* **Hvað er metið?:** Hvaða þekking eða færni úr markmiðum áfangans (vitnaðu í þau) er metin?
* **Hvernig er metið?:** Lýsing á matsaðferðinni.
* **Tillaga að tímasetningu:** Hvenær á önninni er best að leggja þetta fyrir, byggt á vikuskipulagi kennsluáætlunarinnar (vitnaðu í viðeigandi viku/vikur)?

**4. Rökstuðningur fyrir tímasetningum:**
Útskýrðu stuttlega af hverju tímasetningar á stærri matsþáttum eru valdar, með beinni tilvísun í hvaða námsefni er búið að fara yfir á þeim tímapunkti samkvæmt heimildinni.
```

### Dæmi um notkun (Prompt 2)

Kennari notar kennsluáætlunina fyrir GAGN1QU05 sem heimild í NotebookLM og vill fá hugmyndir til að auka vægi leiðsagnarmats.

```
# Grunnstillingar (nauðsynlegt)
HEIMILDASKJAL: "gagn1_Sniðmát námsáætlunar H25.pdf"
NÁMSGREIN: "Gagnasafnsfræði 1"
SKÓLASTIG: "Framhaldsskólastig"

# Fínstillingar (valkvætt)
ÁHERSLUR_KENNARA_Í_NÁMSMATI: "Ég vil fá tillögur að því hvernig hægt er að auka vægi leiðsagnarmats (formative assessment) til viðbótar við það mat sem þegar er til staðar í áætluninni."
```
