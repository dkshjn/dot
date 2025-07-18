# dot

```bash
🟦 Slide 1: Problem Statement
Level One
Managing dependencies across large projects is messy, redundant, and hard to scale.

Level Two
Challenges faced in real development workflows:

• High redundancy due to repeated or unused libraries
• Manual tracking of dependencies is error-prone and time-consuming
• No system-wide visibility into dependency usage across repositories
• Absence of categorization limits auditability and optimization
• Risk of bloat, version conflicts, and unnecessary transitive inclusion

🟦 Slide 2: Objective
Level One
Automate and standardize dependency analysis across Maven-based repositories.

Level Two
Goals of the ASPEN Dependency Analysis tool:

• Analyze repositories using pom.xml and Maven CLI
• Identify unused or redundant declared dependencies
• Classify libraries into meaningful functional categories
• Provide project-wide and repository-level insights
• Integrate with Bitbucket, enable refresh, and support cross-team usage

🟦 Slide 3: Tech Stack
Level One
Tools and technologies used:

Level Two
Core Technologies
• Python (Backend Logic)
• Streamlit (UI and Interaction Layer)
• Maven CLI (dependency:tree, analyze)
• Oracle SQL Developer (8-table schema)

Level Two
Ecosystem & Integration
• Bitbucket (Repo Fetching with Auth)
• OpenShift + Harness (CI/CD pipeline)
• SonarQube + PyTest (Testing and Static Analysis)

🟦 Slide 4: Proposed Solution
Level One
Architecture (End-to-End Workflow)

• User inputs CSI App ID and selects mode
• DB is checked for existing analysis
• If not found or force-refresh triggered → Git clone repo
• Run Maven commands → extract direct dependencies
• Classify libraries based on rule-based engine
• Compute repo/project metrics and store results in DB
• Display metrics or suggestions via Streamlit

Level One
Key Features

Level Two
Classification
• Rule-based engine using keyword heuristics
• 30+ functional categories (JSON, DB, Testing, etc.)
• Extensible structure with fallback category ("Unknown")

Level Two
Analysis Modes
• Project-Level: Aggregates metrics across all repos under project key
• Repo-Level: Individual repo insights with library sizes and suggestions

Level Two
Refresh Support
• Smart caching with force-refresh option (within 10 minutes)
• Prevents redundant analysis and minimizes DB churn

🟦 Slide 5: Demo
Level One
Demonstrating key capabilities of the tool

Level Two
Screenshots (static in slides + shown live):

• Repository selection with project key input
• Project-wide category-wise library breakdown (size, frequency)
• Repo-specific suggestions for unused dependencies
• Force-refresh logic and cache-aware notifications
• Bitbucket auth + analysis logs

🟦 Slide 6: Challenges and Learning
Level One
Technical and Design Challenges

Level Two
• Handling Maven output parsing across inconsistent repo structures
• Reducing false positives in keyword-based classification
• Designing a reusable schema for cross-repo metrics
• Managing refresh vs cache logic without hitting performance bottlenecks

Level One
Key Learnings

Level Two
• Built scalable backend pipelines integrated with Bitbucket
• Developed modular, extensible classification and analysis logic
• Learned practical CI/CD tooling (OpenShift, Harness)
• Enhanced backend testing and coverage through SonarQube and unit tests
• Focused on engineering for long-term reusability, not just a one-off script
```
