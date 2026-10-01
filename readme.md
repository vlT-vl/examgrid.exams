<p align="center">
  <img src="res/examgrid-exams-dark.svg#gh-dark-mode-only" alt="examgrid.exams" width="420" />
  <img src="res/examgrid-exams-light.svg#gh-light-mode-only" alt="examgrid.exams" width="420" />
</p>

<p align="center">
  Static registry of exam content, catalog metadata and user access data for examgrid<br/>
  <sub>JSON files · No backend</sub>
</p>

---

## Purpose

**examgrid.exams** is the static data registry consumed by [examgrid](../examgrid).
It provides the portal with the exam catalog, exam question data and the user access
configuration required to decide which content and capabilities are available to each account.

The repository is data-only: it contains no application backend, API or runtime service.
The portal reads the published files and uses them as its source of truth for catalog and access
metadata.

## Repository structure

```text
exams/
├── <category>/
│   └── <exam-file>
└── index.json
users.enc.json
```

Exam files are grouped by broad technology category. The category structure is extensible and
does not depend on a fixed set of vendors or certifications.

`exams/index.json` is the catalog manifest. It exposes the metadata needed to render the exam
catalog, including each exam's identifier, official code, title, category, duration, question
count and localized description.

## User access model

The user registry defines which exams an account can access and which portal capabilities are
enabled for that account. Capabilities are independent boolean permissions:

- `canRevealAnswers`: permits viewing correct answers;
- `canRandomizeQuestions`: permits randomizing the question order;
- `canChooseRange`: permits selecting a question range;
- `canReviewQuestions`: permits the final review of answered questions and correct answers.

An optional `avatarUrl` can be associated with an account for presentation in the portal.

## Data contract

The portal should treat the JSON structures and field names in this repository as the data
contract. New categories and exams can be added without changing the repository's role: add the
exam data, expose its catalog metadata in the manifest, and assign access through the user
registry when required.

## License

See [LICENSE](LICENSE).
