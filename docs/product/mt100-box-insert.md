# MT-100 quick-start box insert

This sample is the printed quick-start card that ships in the MT-100 box. It is written for a driver or fleet manager
with no installation training, so it uses short steps and plain words.

## Print specification

| Item | Value |
|------|-------|
| Part number | MF-DOC-100-QSG rev. B |
| Format | A6 (105 × 148 mm), folded from A5, double-sided |
| Colour | 2 colour (black + MyFleet blue, Pantone 2728 C) |
| Paper | 120 gsm uncoated, FSC certified |
| Bleed / safe area | 3 mm bleed, 5 mm safe area |
| Languages | EN (UK), ES (Spain) on one card, one language per side |
| Text expansion | Layout leaves 30% extra space for Spanish |
| Artwork source | `MF-DOC-100-QSG_revB.indd`, text exported to XLIFF for translation |
| Digital version | Same content as an accessible PDF and a knowledge base page |
| Linked to release | Firmware 3.8 / Release 4.2 |

!!! note "Why it's built this way"
    One language per side keeps the card short and lets the same layout serve EN/ES markets now and FR later.
    Icons carry the meaning of each step, so the card still works if a reader skips the text.

## Side A: English

=== "Rendered card (EN)"

    ### MyFleet MT-100 · Quick start

    **Set up your tracker in 5 minutes. No tools needed.**

    **In the box:** MT-100 tracker · this card

    ---

    **1. Find the diagnostic port**
    Look under the dashboard, near the steering column. The port has 16 pins.
    *Not sure where it is? Check your vehicle handbook for "OBD port".*

    **2. Plug in the tracker**
    Turn the ignition off. Push the MT-100 firmly into the port until it stops.

    **3. Turn on the ignition**
    Wait for the lights:

    | Light | Meaning |
    |-------|---------|
    | 🟢 Green | Power is on |
    | 🔵 Blue | Connected to the mobile network |

    Both lights should be on within 3 minutes.

    **4. Check your vehicle in MyFleet**
    Open the MyFleet Dashboard or Driver App. Your vehicle appears on the live map within 5 minutes.

    ---

    ⚠ **Safety:** Do not install the tracker while driving. Make sure it does not touch the pedals or block your legs.

    **Vehicle not showing?** Scan the QR code or go to **help.myfleet.example/KB-0142**

    `[QR code]`  MF-DOC-100-QSG rev. B · © MyFleet

=== "Source text (Markdown)"

    ```markdown
    # MyFleet MT-100 · Quick start
    **Set up your tracker in 5 minutes. No tools needed.**
    **In the box:** MT-100 tracker · this card

    1. **Find the diagnostic port**
       Look under the dashboard, near the steering column. The port has 16 pins.
    2. **Plug in the tracker**
       Turn the ignition off. Push the MT-100 firmly into the port until it stops.
    3. **Turn on the ignition**
       Green light = power is on. Blue light = connected to the mobile network.
       Both lights should be on within 3 minutes.
    4. **Check your vehicle in MyFleet**
       Open the MyFleet Dashboard or Driver App. Your vehicle appears on the live map within 5 minutes.

    > Safety: Do not install the tracker while driving. Make sure it does not touch the pedals or block your legs.

    Vehicle not showing? help.myfleet.example/KB-0142
    ```

## Side B: Spanish (Spain)

=== "Rendered card (ES)"

    ### MyFleet MT-100 · Guía rápida

    **Instale su localizador en 5 minutos. No necesita herramientas.**

    **Contenido de la caja:** localizador MT-100 · esta tarjeta

    ---

    **1. Busque el puerto de diagnóstico**
    Mire debajo del salpicadero, cerca de la columna de dirección. El puerto tiene 16 pines.
    *¿No sabe dónde está? Busque «puerto OBD» en el manual del vehículo.*

    **2. Conecte el localizador**
    Apague el contacto. Introduzca el MT-100 en el puerto hasta el fondo.

    **3. Encienda el contacto**
    Espere a que se enciendan las luces:

    | Luz | Significado |
    |-----|-------------|
    | 🟢 Verde | El localizador recibe alimentación |
    | 🔵 Azul | Conectado a la red móvil |

    Las dos luces deberían encenderse en menos de 3 minutos.

    **4. Compruebe su vehículo en MyFleet**
    Abra el MyFleet Dashboard o la Driver App. Su vehículo aparecerá en el mapa en tiempo real en menos de 5 minutos.

    ---

    ⚠ **Seguridad:** No instale el localizador mientras conduce. Asegúrese de que no toque los pedales ni moleste a las piernas.

    **¿No aparece el vehículo?** Escanee el código QR o visite **help.myfleet.example/es/KB-0142**

    `[Código QR]`  MF-DOC-100-QSG rev. B · © MyFleet

=== "Translator notes"

    | Source | Decision | Reason |
    |--------|----------|--------|
    | tracker | *localizador* | Approved glossary term |
    | ignition off / on | *apague / encienda el contacto* | Standard Spain usage; *ignición* sounds technical and literal |
    | dashboard (car) | *salpicadero* | Spain. Mexico variant uses *tablero* |
    | live map | *mapa en tiempo real* | Approved glossary term |
    | you | *usted* | Formal register for customer-facing hardware docs |
    | MyFleet Dashboard, Driver App | Not translated | Product names stay in English (style guide) |
    | Quotation marks | « » | Spain typographic convention |

## Review and sign-off

| Check | Owner | Status |
|-------|-------|--------|
| Technical accuracy (LED behaviour, timings) | Hardware engineering | ✓ Approved |
| Safety wording | Compliance | ✓ Approved |
| Spanish linguistic review (LQA) | Vendor reviewer + in-market reviewer | ✓ 0 critical, 1 minor fixed |
| Print proof (colour, fold, QR scan test) | Print vendor | ✓ Approved |
| Matches KB-0142 and Release 4.2 | Technical writer | ✓ Approved |
