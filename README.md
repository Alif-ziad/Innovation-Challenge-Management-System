# Innovation Challenge Management System (ICMS)

Academic **Oracle SQL / PL/SQL database project** for managing innovation competitions and hackathons, including challenges, rounds, teams, submissions, judging, mentorship, sponsors, prizes, and results.

> This repository is a fork of the original group-project repository: [Samiha-Chowdhury-9/Innovation-Challenge-Management-System](https://github.com/Samiha-Chowdhury-9/Innovation-Challenge-Management-System). The fork preserves the original academic work and attribution while improving repository presentation and small script-hygiene issues.

## What is implemented

The public repository focuses on the **database layer**. It contains:

- a 16-table relational schema with primary, foreign, composite, unique, and check constraints
- Oracle sequences for generated identifiers
- sample data covering challenges, participants, teams, rounds, submissions, judging, mentorship, sponsors, and prizes
- SQL joins, subqueries, aggregate queries, locking examples, and data-manipulation examples
- PL/SQL functions, procedures, loops, conditionals, explicit cursors, records, triggers, packages, and exception handling
- ER, schema, class, use-case, and activity diagrams
- UI screenshots illustrating the intended system workflows
- written documentation covering the proposal, scenario, normalization, introduction, conclusion, and future work

The repository does **not** currently include the PHP/HTML/JavaScript source for the UI shown in the screenshots, so the published implementation should be treated primarily as an Oracle database/PLSQL project.

## Main data model

The schema covers:

- **Challenge** and **Round**
- **Participant**, **ParticipantPhone**, **Judge**, and **Mentor**
- **Team** and **TeamParticipant**
- **Submission**, **Tag**, and **SubmissionTag**
- **Criteria** and **Evaluation**
- **MentorshipSession**
- **Sponsor** and **Prize**

The design is documented as normalized through **Third Normal Form (3NF)**.

## Repository structure

```text
.
├── Database/
│   ├── schema.sql
│   ├── sequences.sql
│   ├── sample_data.sql
│   ├── plsql_basic.sql
│   ├── plsql_advanced.sql
│   └── locking_queries.sql
├── Diagrams/
│   ├── er-diagram.png
│   ├── Schema-diagram.png
│   ├── class-diagram.png
│   ├── use-case-diagram.jpg
│   └── activity-diagram.jpg
├── Documentaion/
│   ├── project-proposal.md
│   ├── scenario-description.md
│   ├── normalization.md
│   └── introduction-conclusion.md
├── Screenshots of UI/
│   ├── login.png
│   ├── registration.png
│   ├── organizer-dashboard.png
│   ├── participant-dashboard.png
│   ├── judge-dashboard.png
│   └── mentor-dashboard.png
└── README.md
```

`Documentaion/` keeps the original upstream directory name for compatibility with the existing project history.

## Running the database exercises

Use **Oracle Database** with a tool such as Oracle SQL Developer. For PL/SQL output, enable:

```sql
SET SERVEROUTPUT ON;
```

Start from a fresh schema and run the setup files in this order:

```text
1. Database/schema.sql
2. Database/sequences.sql
3. Database/sample_data.sql
```

Then use the exercise files as needed:

```text
4. Database/plsql_basic.sql
5. Database/plsql_advanced.sql
6. Database/locking_queries.sql
```

### Execution notes

- `plsql_basic.sql` and `plsql_advanced.sql` contain multiple independent coursework exercises and test statements. They are best executed **section by section** in an Oracle worksheet rather than treated as a production migration script.
- `locking_queries.sql` intentionally includes `UPDATE`, `DELETE`, row-locking, and table-locking examples. Run it only against disposable/sample data.
- `sample_data.sql` assumes a freshly created schema/sequences with the expected starting IDs. Re-running setup scripts without resetting the schema may produce constraint conflicts.
- No automated test suite, teardown script, or production deployment configuration is included.

## Diagrams

### ER diagram

<p align="center">
  <img src="Diagrams/er-diagram.png" width="750" alt="ICMS ER diagram" />
</p>

### Schema diagram

<p align="center">
  <img src="Diagrams/Schema-diagram.png" width="750" alt="ICMS schema diagram" />
</p>

## UI artifacts

The repository includes screenshots for login/registration and organizer, participant, judge, and mentor dashboards. These illustrate the intended workflows, but the corresponding frontend source is not part of the current public repository.

## Academic context and attribution

Developed as a group project for the **Advanced Database Management System** course at **American International University-Bangladesh (AIUB)**.

| Team member | GitHub |
|---|---|
| Tasfiah Tasnim Mrinmoyee | [tasfiahmrinmoyee](https://github.com/tasfiahmrinmoyee) |
| Samiha Chowdhury | [Samiha-Chowdhury-9](https://github.com/Samiha-Chowdhury-9) |
| MD Alif Ziad Sarkar | [Alif-ziad](https://github.com/Alif-ziad) |
| MD Tanvirul Islam Nayem | — |

No individual contribution percentages or roles are assigned here because the repository does not document them.

## Fork note

This fork is maintained under **Alif-ziad** for portfolio/reference purposes. Original group-project history and upstream attribution remain visible through GitHub's fork relationship. Documentation and repository-hygiene changes made in this fork should not be interpreted as sole authorship of the underlying academic project.
