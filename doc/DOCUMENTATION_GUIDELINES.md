# Documentation Guidelines

## 1. Purpose

This document defines principles and conventions for documentation used in studies, tools, and software projects.

The objectives are to:

- Make information easy to find.
- Avoid duplicated information.
- Minimize maintenance effort.
- Clearly define the responsibility of each document.
- Improve long-term maintainability.

---

## 2. General Principles

### 2.1 Single Source of Truth

Each piece of information shall exist in one place only.

Other documents should reference the original source instead of duplicating the information.

---

### 2.2 Minimal Change Principle

Documentation should evolve gradually.

Before creating a new document, first consider whether the existing documentation can be extended while preserving its overall structure.

Avoid introducing new documents or reorganizing the documentation hierarchy unless there is a clear long-term benefit.

A stable documentation structure makes information easier to find, simplifies maintenance, and allows users to become familiar with where information belongs.
---

### 2.3 Separation of Concerns

Each document has a single, well-defined purpose.

Avoid combining user documentation, design descriptions, development notes, and reports into the same document.

---

### 2.4 Progressive Disclosure

Present information in increasing levels of detail.

A reader should be able to stop reading once sufficient information has been obtained.

---

### 2.5 Preferred Document Formats

Documentation format should be selected according to the intended audience.

| Document Type | Preferred Format |
|---------------|------------------|
| Repository overview | Markdown |
| Developer documentation | Markdown |
| Technical design | Markdown |
| User documentation | Microsoft Word |
| Reports | Microsoft Word |
| Analysis Notes | Microsoft Word |
| Experimental Data | Microsoft Excel |

Markdown is preferred for documentation maintained primarily by software developers and stored together with the source code.

Microsoft Word is preferred for documentation intended for users, engineers, reviewers, and project stakeholders.

Microsoft Excel is preferred for experimental data, measurements, calculations, and other structured numerical information.

---

### 2.6 Document Naming

Within a project, documentation files should use standardized names.

Examples:

| Document Type | Standard Filename |
|---------------|-------------------|
| Project overview | README.md |
| User documentation | USER_GUIDE.docx |
| Technical design | DESIGN.md |
| Development documentation | DEVELOPMENT.md |
| Change history | CHANGELOG.md |

The project directory provides the context, making project-specific prefixes unnecessary.

For example:

```
kalman-filter-validation/
    README.md
    USER_GUIDE.docx
    DESIGN.md

train-model-characterizer/
    README.md
    USER_GUIDE.docx
    DESIGN.md
```

When documentation is distributed outside the project directory (for example by e-mail or document management systems), descriptive filenames may be used.

Examples:

```
Kalman Filter Validation - User Guide.docx
Train Model Characterizer - User Guide.docx
```

This naming convention combines the advantages of predictable filenames within a project with descriptive filenames when documents are shared externally.

---

### 2.7 Documentation Minimalism

Documentation should be kept as simple as possible.

Do not introduce new documents unless they serve a clear and lasting purpose that cannot reasonably be fulfilled by an existing document.

Every document should have a well-defined responsibility. If that responsibility becomes too broad, the document may be split. Otherwise, prefer extending the existing documentation.

A small, stable documentation set is easier to maintain and easier for users to navigate.

---

## 3. Document Types

### README.md

**Purpose**

Introduce the project.

**Typical contents**

- Project overview
- Scope
- Quick start
- Repository structure
- Links to additional documentation

**Should not contain**

- Detailed user instructions
- Internal architecture
- Developer procedures

---

### USER_GUIDE.md

**Purpose**

Describe how to use the software.

**Typical contents**

- Installation
- Configuration
- Running programs
- Common workflows
- Troubleshooting

---

### DESIGN.md

**Purpose**

Describe the technical design.

**Typical contents**

- Architecture
- Components
- Data model
- Interfaces
- Design decisions
- Limitations

---

### DEVELOPMENT.md

**Purpose**

Support software development.

**Typical contents**

- Build instructions
- Testing
- Coding conventions
- Git workflow
- Release procedure

---

### REPORTS/

Contains project-specific reports and supporting material.

Typical contents:

- Final reports
- Analysis Notes
- Figures
- Supporting spreadsheets

---

## 4. Documentation Hierarchy

Documentation should be organized as a hierarchy.

```
README
    ↓
USER_GUIDE
    ↓
DESIGN
    ↓
DEVELOPMENT
```

Higher-level documents may reference lower-level documents.

Lower-level documents should not depend on higher-level documents.

This avoids circular references and makes navigation intuitive.

---

## 5. Avoid Duplication

Instead of copying information between documents:

❌

> See Section 7 below.

Prefer:

✅

> See USER_GUIDE.md.

Duplicated information eventually becomes inconsistent.

---

## 6. Naming Convention

Use consistent filenames.

Preferred names:

```
README.md
USER_GUIDE.md
DESIGN.md
DEVELOPMENT.md
CHANGELOG.md
```

Avoid ambiguous names such as:

```
Guide.docx
Manual.docx
Notes.docx
Misc.docx
```

---

## 7. Documentation Lifecycle

Different documents evolve for different reasons.

| Document | Updated when |
|-----------|--------------|
| README | Project purpose changes |
| USER_GUIDE | User workflow changes |
| DESIGN | Architecture changes |
| DEVELOPMENT | Development process changes |
| REPORTS | New studies are completed |

---

# Study Documentation

Studies benefit from separating conclusions from observations and raw data.

The recommended structure is:

```
Report
    ↓
Analysis Notes
    ↓
Experimental Data
```

## Report

Communicates conclusions.

Contains:

- Background
- Motivation
- Results
- Interpretation
- Conclusions

The report tells the story.

---

## Analysis Notes

Documents observations made during the study.

Contains:

- Purpose
- Experiment
- Figures
- Observations
- Open questions

Analysis Notes intentionally avoid premature conclusions.

---

## Experimental Data

Contains reproducible evidence.

Examples:

- Excel workbooks
- CSV files
- Logs
- Configuration files
- Scripts

Experimental data should remain unchanged after publication whenever possible.

---

# Summary

Good documentation is characterized by:

- Clear responsibilities
- Minimal duplication
- Stable structure
- Easy navigation
- Easy maintenance
- Reproducibility