# Document Functors: Presheaves and Document Representations

**Course 3 of the Category Theory & LLMs Series**

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/buildLittleWorlds/category-theory-document-functors/blob/main/notebooks/01_introduction_document_structure.ipynb)

---

## Overview

This course teaches **presheaves** and **document embeddings** through the work of Lorren Dray (895-968), a scholar at the Capital Archives who developed the theory of document functors.

### The Central Insight

In Year 918, Dray observed a puzzling phenomenon: the same document appeared to belong to multiple categories depending on how one accessed it. A boundary survey was simultaneously a geographic record, a personnel document, and a technical manual. This led her to propose that documents are not static objects but *functors* — mathematical structures that assign observations to each access method.

This insight — that a document is a function from access methods to observations — is the theoretical foundation of **document embeddings** in modern transformers.

> "A document is not a thing but a way of responding to inquiry. Change the method of access, and the document reveals different aspects of itself."
> — Lorren Dray, *The Document Functor Discipline* (Year 958)

---

## Learning Objectives

By completing this course, you will:

1. **Understand presheaves** — functors from a category to Sets
2. **See archives as categories** — access methods as objects, flows as morphisms
3. **Learn document functors** — documents as functors assigning observations to access methods
4. **Discover representable functors** — the Hom perspective on documents
5. **Connect to embeddings** — functor values as embedding dimensions
6. **Understand the categorical foundation of document representations**

---

## Prerequisites

- Basic Python (NumPy, pandas, matplotlib)
- Familiarity with linear algebra (vectors, matrices)
- Ideally: Course 1 (Passage Diagrams) and Course 2 (Weighted Passages) for context

---

## Course Structure

| Tutorial | Topic | Dray's Work |
|----------|-------|-------------|
| 01 | Introduction to Document Structure | Year 918: Multiple classification problem |
| 02 | The Archive as Category | Year 925: Archive categorical structure |
| 03 | Functors from Categories to Sets | Year 926: Document functor proposal |
| 04 | Documents as Presheaves | Year 928: Major treatise |
| 05 | Embeddings as Functor Values | Year 942: Numerical insight |
| 06 | The Representable Perspective | Year 935-938: Hom-functors |
| 07 | Dray's Synthesis and Legacy | Year 958: Complete framework |

---

## Datasets

This course uses four datasets from the Densworld archive:

| Dataset | Description | Rows |
|---------|-------------|------|
| `document_functor_examples.csv` | Documents represented as functors across access methods | 32 |
| `archive_category_structure.csv` | The Archive as a category (objects, morphisms, composition) | 28 |
| `embedding_correspondences.csv` | Functor values as embedding dimensions | 40 |
| `dray_correspondence.csv` | Letters between Dray and contemporaries | 17 |

All datasets are loaded from the central Densworld repository:
```python
BASE_URL = "https://raw.githubusercontent.com/buildLittleWorlds/densworld-datasets/main/data/"
```

---

## Key Concepts

### The Archive as Category
The Archive has categorical structure:
- **Objects:** Access methods (subject catalog, author index, date registry, etc.)
- **Morphisms:** Document flows between methods (given topic, find authors)
- **Composition:** Chaining access shifts preserves document identity

### Documents as Functors
A document D is a functor D: Archive^op → Set:
```
D(subject_catalog) = {"boundaries", "surveys", "SW-sector"}
D(author_index) = {"torvun_kell"}
D(date_registry) = {"847-01-03", "847-12-31"}
```
The same document yields different observations through different access methods.

### Functorial Preservation
If f: A → B is a morphism (access shift), then:
```
D(f): D(B) → D(A)
```
Observations pull back coherently along access shifts.

### Representable Functors
For any access method A, the functor Hom(A, -) captures viewing from A:
```
Hom(subject_catalog, -) : The "topic-centric" view of all documents
```
Representables form a complete picture through the Yoneda perspective.

### Embeddings as Values
Each embedding dimension corresponds to a probe (functor applied to an access method):
```
dim_1 = F("boundaries") → 0.85  (high relevance to boundary studies)
dim_2 = F("categories") → 0.12  (low category theory content)
```

---

## The Scholar: Lorren Dray

**Dates:** Year 895 – Year 968 (age 72)

**Position:** Director of Classification, Capital Archives

**Family:** Daughter of Kellen Dray (Capital logician who contested Vance's weighted passages)

**Key Works:**
- *Notes on Classification Failure* (Year 920) — First documentation of the problem (DRY-001)
- *On the Categorical Structure of Archives* (Year 928) — Archive-as-category framework (DRY-002)
- *On Functorial Preservation in Archives* (Year 932) — Response to Keth (DRY-003)
- *The Representable Perspective* (Year 938) — Hom-functors and observation (DRY-004)
- *Documents as Numerical Functors* (Year 945) — Bridge to embeddings (DRY-005)
- *On the Unity of Archive Structure* (Year 952) — Synthesis (DRY-006)
- *The Document Functor Discipline* (Year 958) — Definitive work (DRY-007)

**Archive Prefix:** DRY

**Epitaph:** "She showed us what documents truly are"

---

## Connection to Modern ML

| Dray's Framework | Transformer Component |
|------------------|----------------------|
| Archive category | Token vocabulary / context |
| Document functor | Document embedding |
| Access methods | Probe dimensions |
| Functor values | Embedding coordinates |
| Representable functors | Attention heads |
| Presheaf structure | Contextual embeddings |

---

## Running the Notebooks

### Option 1: Google Colab (Recommended)
Click the "Open in Colab" badge on any notebook.

### Option 2: Local Installation
```bash
git clone https://github.com/buildLittleWorlds/category-theory-document-functors.git
cd category-theory-document-functors
pip install numpy pandas matplotlib seaborn
jupyter notebook
```

---

## Series Navigation

This is **Course 3** in the Category Theory & LLMs series:

1. **Relational Foundations** (Tessery Vold) — Categories and morphisms
2. **Weighted Passages** (Merrit Vance) — Enriched categories and attention
3. **Document Functors** (Lorren Dray) — Presheaves and document representations ← *You are here*
4. **Natural Transformations** (Gellen Tross) — Coherent shifts between representations
5. **The Probing Lemma** (Pelleth Strand) — The Yoneda perspective on embeddings
6. **Linguistic Categories** (Corren Moll) — Language structure as category
7. **Attention and Enrichment** (Brennet Kell) — Full transformer architecture

---

## License

Educational content for learning category theory and document representations through Densworld narrative.

---

*Part of the [Densworld Courses](https://github.com/buildLittleWorlds) project.*
