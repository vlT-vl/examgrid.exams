<p align="center">
  <img src="res/examgrid-exams-dark.svg#gh-dark-mode-only" alt="examgrid.exams" width="420" />
  <img src="res/examgrid-exams-light.svg#gh-light-mode-only" alt="examgrid.exams" width="420" />
</p>

<p align="center">
  Static, protected registry of exam content and user access data for examgrid<br/>
  <sub>Plain files · No backend</sub>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/version-0.1.0-blue?style=flat-square" alt="version"/>
  <img src="https://img.shields.io/badge/format-JSON-orange?style=flat-square" alt="format"/>
  <img src="https://img.shields.io/badge/license-proprietary-critical?style=flat-square" alt="license"/>
</p>

---

## Overview

**examgrid.exams** is the static registry that [examgrid](../examgrid) reads its real exam content and user/access data from — the same role that [nxget.packages](../nxget.packages) plays for `nxget-app-portal`: a plain, hand-maintained repository of files, no server, no API beyond raw file access.

This repository holds **no application backend and no plaintext exam content**. The exam catalog itself is public; the actual question content and the account list are protected and only readable by the app, not by browsing this repository directly.

## Content model

Each exam belongs to one macro-category folder under `exams/`. Categories map to broad technology domains (e.g. Red&nbsp;Hat, Nutanix, Proxmox, VMware vSphere) and grow over time as new exams are added — there is no fixed list. Each category also carries the vendor's own icon and brand color, read by the app instead of a fixed palette.

```
exams/
├── redhat/
│   └── <exam-id>
├── nutanix/
│   └── <exam-id>
├── proxmox/
│   └── <exam-id>
└── vmware/
    └── <exam-id>
users.*
```

`exams/index.json` is the authoritative source for each exam's code, duration and question count.

The user/access list sits outside `exams/`: it carries the accounts authorized to use examgrid and which exams each one can see.

Each account also carries per-user capabilities: `canRevealAnswers` controls access to correct
answers, `canRandomizeQuestions` controls question randomization, and `canChooseRange` controls
choosing the question range. The latter two are granted together with answer visibility; users
without answer visibility do not receive either capability.

## Architecture

The registry is produced by a maintainer-only local toolchain that is intentionally **not part of this repository**: the actual exam content and account list are prepared and published from the maintainer's own machine, never as part of any build or deploy step. Only the finished, protected files reach this repository.

## License

See [LICENSE](LICENSE).
