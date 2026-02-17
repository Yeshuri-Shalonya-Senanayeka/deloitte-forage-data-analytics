# Task 02 – Gender Pay Equality Classification (Excel)

## Background
Daikibo Industrials received internal complaints regarding gender-based salary inequality.  
The Forensic Tech team developed an algorithm to calculate an **Equality Score** for job roles across all factories.

The Equality Score ranges from **-100 to +100**, where:
- **0** represents ideal equality
- Negative and positive values indicate imbalance

## Objective
Classify each job role’s Equality Score into clear risk categories to support forensic investigation.

## Dataset
The provided Excel file contained:
- Factory
- Job Role
- Equality Score (-100 to +100)

## Method (Excel)

1. Added a new column: **Equality Class**
2. Classified scores into three categories:

   - **Fair:** -10 to +10  
   - **Unfair:** -20 to -11 OR +11 to +20  
   - **Highly Discriminative:** <= -21 OR >= +21  

3. Used the following Excel formula:

   =IF(ABS(C2)<=10,"Fair",IF(ABS(C2)<=20,"Unfair","Highly Discriminative"))

4. Applied **Conditional Formatting**:
   - 🟢 Green → Fair
   - 🟡 Yellow → Unfair
   - 🔴 Red → Highly Discriminative

This allowed quick visual identification of high-risk roles.

## Results
- Multiple roles fell into **Unfair** and **Highly Discriminative** categories.
- Conditional formatting highlighted areas requiring priority review.
- The classification provides a structured way to guide further forensic investigation.

## Deliverable
- Updated file: `equality_table.xlsx`
