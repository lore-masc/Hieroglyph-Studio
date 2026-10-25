# 𓋹 Hieroglyph Studio
### *Epigrafia Digitale Computazionale & Laboratorio Filologico di Medio Egizio*

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live%20Demo-f9e2af?style=for-the-badge&logo=github&logoColor=11111b)](https://your-username.github.io/your-repo-name/)
[![Client-Side](https://img.shields.io/badge/Architecture-100%25%20Client--Side-a6e3a1?style=for-the-badge)](hieroglyph_studio.html)
[![Unicode](https://img.shields.io/badge/Unicode%2015.0-1074%20Hieroglyphs-89b4fa?style=for-the-badge)](hieroglyph_studio.html)
[![License: MIT](https://img.shields.io/badge/License-MIT-cba6f7?style=for-the-badge)](LICENSE)

---

**Hieroglyph Studio** è una piattaforma web scientifica open-source progettata per l'analisi epigrafica, il riconoscimento computazionale di glifi e lo studio filologico del **Medio Egizio** (Egiziano Classico). 

L'applicazione è **100% statica e client-side**: non richiede server backend o database esterni, funziona interamente nel browser garantendo la massima velocità di calcolo, privacy assoluta dei dati archeologici e piena usabilità **offline**.

---

## 🏛️ Struttura & Metodologia in 10 Fasi

Hieroglyph Studio integra due ambienti di lavoro complementari collegati in tempo reale (alternabili con <kbd>Alt + G</kbd>):

```
                      ┌──────────────────────────────────────────────┐
                      │            HIEROGLYPH STUDIO                 │
                      └──────────────────────┬───────────────────────┘
                                             │
                  ┌──────────────────────────┴──────────────────────────┐
                  ▼                                                     ▼
     ┌─────────────────────────────┐                       ┌─────────────────────────────┐
     │  PARTE 1: STUDIO EPIGRAFICO │                       │ PARTE 2: LAB. FILOLOGICO    │
     │      (5 Fasi di Analisi)    │                       │    (5 Fasi di Grammatica)   │
     ├─────────────────────────────┤                       ├─────────────────────────────┤
     │ 1. Esaltazione Bordi        │                       │ 1. Sequenza Parole          │
     │ 2. Snap & Modellazione      │◄─────────────────────►│ 2. Correzione Traslitteraz. │
     │ 3. Catalogo Gardiner        │      (Alt + G)        │ 3. Analisi Morfologica      │
     │ 4. Segmentazione Parole     │                       │ 4. Verifica Concordanza     │
     │ 5. Analisi & Salvataggio    │                       │ 5. Prontuario & Interlineare│
     └─────────────────────────────┘                       └─────────────────────────────┘
```

---

### 1. Studio Epigrafico (Le 5 Fasi di Acquisizione e Riconoscimento)

1. **Fase 1: Modalità Esaltazione Bordi & Auto-Edge**
   - Algoritmi di visione computazionale per far risaltare solchi incisi su pietra o pigmenti su papiro: *Automatica Adattiva (Multi-Scala)*, *Ibrido Classico (Pietra + Contorni Dorati)*, *Gradiente Normalizzato*, *Luce Radente Direzionale a 135°* e *Facsimile Epigrafico B/N*.
   - Controlli di guadagno contrasto ($0.5\times - 3.5\times$), soglia bordi e soppressione automatica di vernici/marcatori moderni.

2. **Fase 2: Modifica Snap & Modellazione Vettoriale**
   - Suite di strumenti di tracciamento e selezione: **Rettangolo Snap** (<kbd>R</kbd>), **Pennello Area Glifo** (<kbd>B</kbd>), **Lazo a Mano Libera** (<kbd>L</kbd>) e **Bacchetta Magica Epigrafica** (<kbd>W</kbd>).
   - Modellazione poligonale su misura (rettangolare, cartiglio reale a 16 vertici, ottagono e suddivisione densa vertici) con micro-regolazione bordo ($\pm 2\text{px}$).

3. **Fase 3: Riconoscimento & Sostituzione Glifo (Catalogo Gardiner)**
   - Riconoscimento geometrico basato sul confronto tra silhouette estratta e database vettoriale.
   - Oltre **1074 caratteri Unicode** e **508 forme curate** ad alta frequenza epigrafica con filtri per classe (A–Z), unilitteri (alfabeto fonetico), bilitteri, trilitteri, logogrammi e determinativi.

4. **Fase 4: Parole Raggruppate, Cadrat & Word Segmentation**
   - Ordinamento interattivo della sequenza di lettura numerando i glifi direttamente sulla foto con click in successione (`#1`, `#2`, `#3`...).
   - Raggruppamento in unità lessicali (cadrat), codifica *Manuel de Codage* (MdC) combinata e gestione della direzione del testo (destra $\to$ sinistra, righe o colonne).

5. **Fase 5: Analisi di Primo Livello & Progetti `.hiero.json`**
   - Scheda epigrafica con trascrizione Unicode esadecimale e valori fonetici.
   - Salvataggio e caricamento dello stato completo nel formato aperto `.hiero.json` con immagini incorporate in base64, cronologia Undo/Redo e vettori poligonali.

---

### 2. Laboratorio Filologico & Grammaticale (Le 5 Fasi di Medio Egizio)

1. **Fase 1: Sequenza Parole, Flusso di Lettura & Traduzione Continua**
   - Gestore a colonna della proposizione con riordinamento interattivo ($\blacktriangle$ / $\blacktriangledown$), conteggio lemmi e riquadro di traduzione contestuale aggiornato in tempo reale.

2. **Fase 2: Correzione Traslitterazione & Complementi Fonetici**
   - Normalizzazione automatica dei complementi ridondanti (es. $nfr + f + r \to nfr$) e marcatura determinativi su $\emptyset$.
   - Gestione dell'**Anteposizione Onorifica** (`👑 Onorifico`) per formule regali o divine (*ḥtp-dỉ-nsw*, *ḥm-nṯr*, *sꜣ-nsw*).
   - Supporto nativo per i caratteri scientifici egittologici: `ꜣ, ỉ, ˁ, ḥ, ḫ, ẖ, š, q, ṯ, ḏ`.

3. **Fase 3: Analisi Morfologica: Tempi Verbali, Generi, Numeri & Sintassi**
   - Riconoscimento delle forme verbali della grammatica classica: *sḏm.f* (Perfettivo / Imperfettivo), *sḏm.n.f* (Passato narrativo), Stativo / Pseudoparticipio, Participi e Forme Relative.
   - Flessione nominale: Maschile/Femminile (desinenza `-t`), Singolare/Duale (`-wy`/`-ty`)/Plurale (`-w`/`-wt`), aggettivi *Nisba* e pronomi suffissi.

4. **Fase 4: Verifica Regole & Concordanza (Linter Sintattico)**
   - Diagnostica automatica di concordanza soggetto-verbo, reggenze preposizionali e verifica di coerenza dei determinativi.

5. **Fase 5: Prontuario Regole Medio Egizio & Scheda Interlineare**
   - Compendio grammaticale interattivo (Gardiner / Allen / Grandet-Mathieu) applicabile con 1 clic.
   - **Esportazione Scheda Interlineare a 4 livelli**:
     1. Geroglifici Unicode
     2. Codici Gardiner
     3. Traslitterazione Scientifica
     4. Glossa Grammaticale & Traduzione Italiana

---

## ⌨️ Scorciatoie da Tastiera Rapide

| Tasto | Funzione Epigrafica / Filologica |
| :--- | :--- |
| <kbd>R</kbd> | Strumento Rettangolo Snap |
| <kbd>B</kbd> | Pennello Area Glifo (*Shift = Aggiungi, Alt = Gomma*) |
| <kbd>L</kbd> | Lazo a Mano Libera |
| <kbd>W</kbd> | Bacchetta Magica Epigrafica |
| <kbd>V</kbd> | Seleziona / Modifica Snap e Vertici |
| <kbd>H</kbd> | Modalità Mano / Trascina Foto (Pan) |
| <kbd>Alt + G</kbd> | **Alterna Studio Epigrafico ⟷ Laboratorio Grammaticale** |
| <kbd>Ctrl + S</kbd> | Salva Progetto `.hiero.json` (sovrascrittura locale) |
| <kbd>Ctrl + Shift + S</kbd> | Salva con nome nuovo file `.hiero.json` |
| <kbd>Ctrl + O</kbd> | Carica Progetto salvato |
| <kbd>Ctrl + Z</kbd> / <kbd>Ctrl + Y</kbd> | Annulla / Ripeti (Cronologia Undo/Redo) |
| <kbd>Canc</kbd> | Elimina Snap / Glifo selezionato |

---

## 📂 Struttura del Repository

```
.
├── index.html               # Landing page di presentazione per GitHub Pages
├── hieroglyph_studio.html   # Applicazione web completa (Studio Epigrafico & Grammatica)
├── .hiero_bridge_state.json # File di stato e configurazione
└── README.md                # Documentazione del progetto
```

---

## 📚 Riferimenti Bibliografici & Standard Egittologici

- **Gardiner, Alan H.** — *Egyptian Grammar: Being an Introduction to the Study of Hieroglyphs* (3rd ed., Griffith Institute, Oxford).
- **Allen, James P.** — *Middle Egyptian: An Introduction to the Language and Culture of Hieroglyphs* (Cambridge University Press).
- **Grandet, Pierre & Mathieu, Bernard** — *Corso di Egiziano Geroglifico* (Ananke Edizioni).
- **Buurman, J. et al.** — *Inventaire des signes hiéroglyphiques en vue de leur saisie informatique: Manuel de Codage (MdC)*.
- **The Unicode Consortium** — *The Unicode Standard, Egyptian Hieroglyphs Block (U+13000–U+1342F)*.

---

## 📄 Licenza

Distribuito sotto licenza **MIT**. Consulta il file `LICENSE` per ulteriori dettagli.

Realizzato per studenti, ricercatori, egittologi e appassionati di epigrafia antica.
