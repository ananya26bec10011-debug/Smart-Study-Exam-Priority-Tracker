# Study Priority Planner

A command-line Python tool that helps you decide **what to study today** by ranking your subjects based on exam proximity, revision status, practice completion, and past performance.

## How It Works

For each subject you enter, the tool asks for:

- **Previous marks / quiz score (%)**
- **Practice completion (%)**
- **Revision completion (%)**
- **Last revision completion (%)**
- **Overall topic completion (%)**
- **Exam date** (`YYYY-MM-DD`)
- **2–3 topics** in that subject
- **The weakest topic** needing the most attention

From this, it calculates a **priority score** using weighted "deficits" (i.e. how far each metric is from 100%):

| Metric                     | Weight |
|-----------------------------|--------|
| Marks deficit                | 15%    |
| Practice deficit             | 25%    |
| Revision deficit             | 25%    |
| Last revision deficit        | 20%    |
| Topic completion deficit     | 15%    |

The total deficit is then multiplied by an **urgency factor** based on how many days remain until the exam — the closer the exam, the higher the urgency multiplier.

Based on the final score, each subject is labeled:

-  **HIGH** priority → 2 hours of study
-  **MEDIUM** priority → 1 hour of study
-  **LOW** priority → 30 minutes of study

The tool also identifies the metric contributing most to a subject's deficit, and combines it with exam urgency or performance context to generate a short **reason** for the priority assigned.

## Output

Subjects are sorted (highest priority and score first) and printed as a daily study plan:


PRIORITY for today
Subject: <name>
Priority: HIGH / MEDIUM / LOW
Required study: 2 hours / 1 hour / 30 minutes
Focus topic: <weakest or first topic>
Reason: <driving factor>
```

## Usage

python study_priority.py

You'll be prompted to enter details for each subject interactively. The number of subjects is specified first, followed by the details for each one in turn.

### Example

How many subjects do you want to add? 2
Enter the subject name: Mathematics
Enter previous marks or quiz score (%): 72
Enter practice completion (%): 40
Enter revision completion (%): 30
Enter last revision completion (%): 20
Enter overall topic completion (%): 60
Enter exam date (YYYY-MM-DD): 2026-10-05
Enter 2 or 3 topics for this subject (separated by ,)
Topics: Calculus, Linear Algebra
Which topic needs the most attention in Mathematics? Linear Algebra


## Requirements

- Python 3.7+
- No external dependencies (uses only the standard library: `datetime`)

## Notes

- If an exam date is invalid or unparseable, the tool defaults to assuming 30 days remain.
- Urgency scaling ensures that even subjects with low deficits can be bumped to a higher priority if the exam is very close.

## Possible Improvements

- Save/load subject data to a file (JSON/CSV) instead of re-entering it every run
- Add a GUI or web interface
- Track study history over multiple days
- Export the daily plan to a file or calendar
