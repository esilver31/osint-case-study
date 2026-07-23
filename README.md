# osint-case-study
This case study demonstrates the application of Open Source Intelligence (OSINT), data validation constraints, and contextual deduction to reconstruct an obfuscated telephone number from a public dataset (social media/meme). By cross-referencing systemic telecom regulations against structural behavioral patterns, the complete dataset was successfully recovered without brute-force enumeration.


1. Objective and Problem Statement

Target Data: (512) 3*1-2*04
The Challenge: Identify the missing digits represented by the asterisks (*) to determine the valid 10-digit North American Numbering Plan (NANP) phone number.
Hypothesis: Structural telecom allocation databases contain strict regulatory constraints that can systematically eliminate invalid combinations, leaving only the true original number.


2. Technical Methodology

Phase 1: Database Querying and Structural Filtering

The Numbering Plan Area (NPA) code 512 covers Austin, Texas and surrounding areas. To narrow down the central office code (NXX or prefix) formatted as 3*1, the public NPA-NXX Database was queried for all prefixes fitting the pattern 3[0-9]1.

Phase 2: Applying Regulatory Constraints

National assignment rules allow for immediate reduction of the search space:

Constraint 1 (N11 Info Codes): Under NANP rules, the second and third digits of a prefix cannot both be 1 (e.g., X11 codes like 311, 411, 911 are strictly reserved for service codes). This eliminated 311 as a valid candidate.
Constraint 2 (Carrier Assignment Block): Valid entries remaining in the 512 area code for the 3*1 pattern within the modern operating blocks were cross-referenced for assignment types.

Phase 3: Contextual Behavioral Deduction

The database query revealed that almost all prefixes matching 3[0-9]1 within the relevant allocation blocks were historically or currently assigned exclusively as landlines.

Logic: Given the social context of the dataset (a mobile phone number provided in a casual social environment), it is highly improbable that an individual would port a legacy landline number to a mobile device under these specific prefix blocks.
The Exception: The prefix 351 stood out as the mathematically and operationally viable mobile-capable assignment matching the pattern constraints.


3. Conclusion & Findings

By applying strict technical filters to the NPA-NXX registry, the obfuscated prefix was confidently resolved to 351.

This exercise proves the efficacy of using architectural constraints and data analytics over blind brute-forcing to solve complex data puzzles—a core capability directly transferable to threat intelligence, digital forensics, and network asset discovery.


4. Evidence Portfolio

