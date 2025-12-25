# Dataset Reference Card: Document Functors

**Course 3 of the Category Theory & LLMs Series**

---

## Datasets Overview

| Dataset | Description | Rows | Primary Entity |
|---------|-------------|------|----------------|
| `document_functor_examples.csv` | Documents as functors with access method observations | 32 | DOC-001 through DOC-010 |
| `archive_category_structure.csv` | The Archive as a category (objects, morphisms, composition) | 28 | Archive structure |
| `embedding_correspondences.csv` | Functor values as embedding dimensions | 40 | Probe-document pairs |
| `dray_correspondence.csv` | Letters between Dray and contemporaries | 17 | DRY-LET series |

---

## Dataset Details

### document_functor_examples.csv

**Purpose**: Demonstrates how the same document yields different observations through different access methods.

**Key Columns**:
- `document_id`: Document identifier (DOC-001 through DOC-010)
- `document_title`: Full document title
- `access_method`: The access method used (subject_catalog, author_index, etc.)
- `observation_type`: Type of observation (topic_keywords, contributor_name, etc.)
- `observation_value`: The observation returned
- `functor_notation`: F('AccessMethod') notation
- `year_recorded`: When documented by Dray
- `archive_section`: Which archive section
- `recorder`: Who recorded (lorren_dray)

**Example Row**:
```
DOC-001, Boundary Survey Report SW-6, subject_catalog, topic_keywords, "boundaries,surveys,SW-sector", F('Boundaries Survey'), 918, capital_archives, lorren_dray
```

**Technical Concept**: Demonstrates presheaves — documents as functors assigning sets to access methods.

---

### archive_category_structure.csv

**Purpose**: Defines the Archive as a category with objects, morphisms, and composition.

**Key Columns**:
- `object_id`: Identifier for objects and morphisms
- `object_name`: Name of the element
- `object_type`: Type (access_method, morphism, composite, identity, associative)
- `morphism_source`: Source object of morphism
- `morphism_target`: Target object of morphism
- `morphism_name`: Name of the morphism
- `morphism_type`: Type of morphism (natural, composite, identity, associative)
- `composition_rule`: Rule for composition
- `year_documented`: When Dray documented this structure

**Object Types**:
- 12 access methods (objects in the category)
- 10 morphisms (document flows)
- 3 composite morphisms (demonstrating composition)
- 3 identity morphisms (demonstrating identity law)
- 1 associativity verification

**Technical Concept**: Demonstrates the Archive has categorical structure — objects, morphisms, identity, composition, associativity.

---

### embedding_correspondences.csv

**Purpose**: Shows how functor values become embedding dimensions.

**Key Columns**:
- `document_id`: Document identifier
- `document_title`: Full document title
- `probe_id`: Probe identifier (PRB-001 through PRB-014)
- `probe_name`: Name of probe (topic_boundaries, author_kell, etc.)
- `probe_description`: What the probe measures
- `functor_value`: Categorical level (high, medium, low)
- `embedding_dimension`: Dimension in embedding space (dim_1 through dim_14)
- `numerical_value`: Numerical embedding value (0.0 to 1.0)
- `normalization`: Normalization method (softmax)
- `year_computed`: When Dray computed this

**Probe Categories**:
- Topic probes: topic_boundaries, topic_categories, topic_expeditions, topic_creatures
- Author probes: author_kell, author_vance, author_vold, author_dray
- Analytical probes: quantitative_score, abstraction_level, influence_score
- Archive probes: topic_archives, debate_score, practical_score

**Technical Concept**: Each embedding dimension is a functor value — the document's numerical response to a probe.

---

### dray_correspondence.csv

**Purpose**: Letters documenting the development of document functor theory.

**Key Columns**:
- `letter_id`: Letter identifier (DRY-LET-001 through DRY-LET-017)
- `date`: Date of letter (YYY-MM-DD format)
- `sender`: Who sent the letter
- `recipient`: Who received the letter
- `subject`: Subject line
- `excerpt`: Key excerpt from the letter
- `archive_id`: Archive reference
- `key_concepts`: Concepts discussed
- `response_letter`: ID of response (if any)
- `relationship_type`: Type of correspondence (family, professional, mentoring, memorial, institutional)

**Key Correspondents**:
- kellen_dray (father, 920-920)
- tessery_vold (mentor, 925-926)
- vornis_keth (critic, 930)
- merrit_vance (collaborator, 935-955)
- pelleth_strand (student, 942)
- gellen_tross (colleague, 958)

**Technical Concept**: Documents the historical development of theory through scholarly exchange.

---

## Loading Datasets

All datasets load from the central Densworld repository:

```python
import pandas as pd

BASE_URL = "https://raw.githubusercontent.com/buildLittleWorlds/densworld-datasets/main/data/"

# Load datasets
documents = pd.read_csv(BASE_URL + "document_functor_examples.csv")
archive = pd.read_csv(BASE_URL + "archive_category_structure.csv")
embeddings = pd.read_csv(BASE_URL + "embedding_correspondences.csv")
correspondence = pd.read_csv(BASE_URL + "dray_correspondence.csv")
```

---

## Key Dates in Densworld

| Year | Event |
|------|-------|
| 895 | Lorren Dray born |
| 918 | Multiple classification problem observed |
| 920 | First manuscript (DRY-001) |
| 925 | Archive-as-category insight |
| 926 | Document functor theory proposed |
| 928 | Major treatise (DRY-002) |
| 930 | Keth contests functoriality |
| 935 | Representable perspective discovered |
| 938 | Tessery Vold dies; Dray writes memorial |
| 940 | Dray-Vance debate published |
| 942 | Embedding-as-functor-values insight |
| 955 | Merrit Vance dies; Dray delivers eulogy |
| 958 | Definitive work (DRY-007) published |
| 962 | Dray retires |
| 968 | Dray dies; epitaph: "She showed us what documents truly are" |

---

## Technical Concepts Mapping

| Dray's Term | Modern ML Term | Dataset |
|-------------|----------------|---------|
| Access method | Embedding dimension | archive_category_structure.csv |
| Document functor | Document embedding | document_functor_examples.csv |
| Functor value | Embedding coordinate | embedding_correspondences.csv |
| Presheaf | Contextual representation | document_functor_examples.csv |
| Representable functor | Attention head | embedding_correspondences.csv |

---

## Archive Prefixes

| Scholar | Prefix | Description |
|---------|--------|-------------|
| Lorren Dray | DRY | Document functor manuscripts |
| Merrit Vance | VNC | Weighted passage manuscripts |
| Tessery Vold | VLD | Passage diagram manuscripts |

---

*Reference card for Course 3: Document Functors*
*Part of the [Category Theory & LLMs Series](https://github.com/buildLittleWorlds)*
