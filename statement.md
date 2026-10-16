PROJECT STATEMENT
Smart Study & Exam Priority Tracker Problem Statement
Students manage several subjects at once, each needing different attention depending on how close the exam is and how well the material is understood.
Without an objective method, they often spend too much time on subjects they already know and neglect weak topics or approaching deadlines.

Scope of the Project:-

The project is a command-line Python application that takes subject-level metrics
(marks, practice, revision, last revision, topic completion, exam date, topics and weak
topic), calculates a weighted priority score with an exam-proximity urgency factor, and
prints a ranked daily study plan.
Out of scope for this version: saving data between runs, a graphical interface, and
calendar integration.


Target Users
   • College and school students preparing for multiple exams
   • Anyone who needs a quick, objective decision on what to study today
   
High-Level Features
    • Subject data input with validation
    • Weighted deficit scoring across five metrics
    • Exam-proximity urgency scaling
    • HIGH / MEDIUM / LOW classification with recommended study time
    • Reason and focus topic for every subject
    • Sorted daily priority output
