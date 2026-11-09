# Case study: Localizing the MT-100 launch from English to Spanish

**Scope:** box insert, knowledge base article KB-0142, Driver App release strings · **Markets:** Spain
**Role:** technical writer and localization owner · **Result:** shipped on launch day with zero critical errors

!!! note "Portfolio sample"
    MyFleet is fictional. This case study shows the process I would run, using realistic numbers and decisions.

## The challenge

The MT-100 was launching in Spain on the same day as Release 4.2. Three things had to be ready in Spanish at launch:

- the printed box insert, which had a print deadline 3 weeks before launch
- the troubleshooting article KB-0142
- 140 new Driver App strings for defect alerts

The earlier MT-200 launch had shipped its Spanish insert 2 weeks late, and one term ("caja negra" for tracker) caused customer confusion.

## My approach

### 1. Fixed the source first

Before sending anything to translation, I edited the English source against the [style guide](../about/style-guide.md):

- cut average sentence length from 21 to 13 words
- replaced 3 different words for the device ("unit", "box", "device") with one: *tracker*
- removed an idiom ("plug and play, no sweat")
- confirmed timings (3 minutes for LEDs, 5 minutes for the map) with hardware engineering

**Why:** every unclear source sentence becomes an unclear sentence in every language, and costs money to fix in each one.

### 2. Updated the termbase

I added 6 new terms to the [glossary](../about/glossary.md) with approved Spanish translations and loaded them into the translation platform
so the vendor saw them as mandatory. *Localizador* replaced *caja negra*.

### 3. Intake and routing

| Request | Requested by | Content type | Words | Route | Due |
|---------|-------------|--------------|------:|-------|-----|
| LOC-231 | Hardware product | Box insert (XLIFF from InDesign) | 180 | Vendor A, print priority | Day 5 |
| LOC-232 | Support | KB-0142 | 420 | Vendor A | Day 10 |
| LOC-233 | Engineering | Driver App strings (JSON) | 960 | Vendor A + in-market review | Day 12 |

Translation memory matched 38% of the words from earlier projects, which cut cost and kept wording consistent with the MT-200 docs.

### 4. Review cycle

1. **Vendor translation and self-review** in the translation platform.
2. **Automated QA:** terminology, numbers, tags, and untranslated segments.
3. **In-market review** by a Spain-based fleet support agent, who checked that the instructions matched real vehicles.
4. **My review** of the box insert in context (the PDF proof, not just the strings), because truncation and line breaks only show up in layout.
5. **Sign-off** using the scorecard below.

### 5. Quality scorecard (LQA)

| Category | Critical | Major | Minor |
|----------|:-------:|:----:|:----:|
| Accuracy | 0 | 0 | 1 |
| Terminology | 0 | 0 | 0 |
| Language (grammar, spelling) | 0 | 0 | 2 |
| Style and register | 0 | 1 | 0 |
| Layout (truncation, line breaks) | 0 | 0 | 1 |
| **Total** | **0** | **1** | **4** |

**Pass rule:** 0 critical, at most 2 major per 1,000 words. All issues fixed before release.

## Examples of decisions

| English source | First translation | Final | Why it changed |
|----------------|------------------|-------|----------------|
| Turn the ignition off. | Apague la ignición. | Apague el contacto. | *Ignición* is a literal calque; drivers in Spain say *contacto*. |
| Push the MT-100 firmly into the port until it stops. | Empuje firmemente el MT-100 en el puerto hasta que se detenga. | Introduzca el MT-100 en el puerto hasta el fondo. | Shorter, natural, and fits the card without shrinking the font. |
| Your vehicle appears on the live map. | Tu vehículo aparece en el mapa en vivo. | Su vehículo aparecerá en el mapa en tiempo real. | Formal *usted* for hardware docs; approved glossary term. |
| Defect reported | Defecto reportado | Avería notificada | *Reportar* is a common anglicism; *avería* is what fleet managers in Spain use. (Mexico variant: *Falla reportada*.) |

## Results

| Measure | MT-200 launch (before) | MT-100 launch (after) |
|---------|:---------------------:|:--------------------:|
| Spanish content ready on launch day | No (2 weeks late) | Yes |
| Critical errors reaching market | 1 | 0 |
| Translation cost per word (with TM) | baseline | 22% lower |
| Spanish support tickets about installation, first month | 41 | 17 |

## What I'd do next

- Add Spanish (Mexico) as a variant, reusing the Spain translation memory and changing only market-specific terms.
- Add French using the same source and termbase, with the box insert layout already sized for it.
