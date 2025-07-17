# dot

```bash
The ASPEN Dependency Analysis Tool is built to streamline and optimize dependency management across Maven-based repositories. It identifies unused or redundant libraries, classifies dependencies by functionality, and provides actionable insights through a user-friendly interface. The tool supports Bitbucket integration and a dedicated database, making it scalable for multi-repository, cross-team environments.

Overview
ASPEN automates the process of analyzing dependencies across repositories. It classifies libraries, flags potentially unused or redundant dependencies, and generates repository-level and project-wide metrics. Designed for large-scale systems, ASPEN helps development teams maintain clean, efficient, and consistent dependency usage.

Scope
Analyze Maven-based repositories for declared and transitive dependencies.

Classify libraries into functional categories (e.g., JSON, database, testing).

Detect unused or redundant dependencies and suggest candidates for removal.

Generate repository-wise and project-wide metrics for dependency usage.

Provide actionable insights based on size, frequency, and redundancy.

Support Bitbucket integration for repository management.

Store enriched dependency metadata in a centralized database for 5000+ libraries.

Present Features
Dependency Analysis
Parses pom.xml files to extract direct dependencies.

Executes Maven commands (e.g., mvn dependency:tree) to gather full dependency trees.

Identifies unused but declared dependencies with actionable suggestions like:

“This dependency appears unused in the source code. If it's not used at runtime (e.g., via reflection), it can likely be removed.”

Library Classification
Uses a rule-based classifier to categorize libraries into functional buckets (e.g., JSON, testing, I/O).

Supports both external libraries (e.g., from Maven Central) and internal libraries from private registries.

(Optional extension: Hybrid rule-based + ML classification planned.)

Repository Metrics
Displays dependency metrics per repository via an interactive Streamlit UI.

Includes library count per category, individual library sizes, and redundancy indicators.

Project-Wide Metrics
Aggregates dependency data across all repositories in a project (by CSI App ID or Project Key).

Tracks frequency of library usage (e.g., Library A used in 50 repositories).

Highlights common patterns and potential duplication.

Bitbucket Integration
Fetches repositories using API access for selected workspaces and project keys.

Supports local caching and optional refresh to update repository data on demand.

Database Integration
Centralized database stores classification and metadata for over 5000 libraries.

Enables quick access to historical results without rerunning analysis.

Stores metrics, classification, and library size for efficient querying and analytics.

Streamlit Application
Provides an intuitive UI for:

Viewing analysis per repository or aggregated at the project level.

Browsing dependency categories with size breakdown and counts.

Reviewing suggestions for unused or redundant dependencies.

Users can either:

Fetch fresh data from Bitbucket for reanalysis, or

View already processed results from the database.

Workflow
Repository Fetching

Repositories are fetched from Bitbucket or loaded from the internal database.

Optionally cloned and cached locally for efficient repeated analysis.

Dependency Extraction

Direct dependencies are parsed from pom.xml files.

Transitive trees are built using Maven commands.

Classification and Metrics

Dependencies are classified into functional categories.

Repository-level and project-wide metrics are generated and stored.

Insights & Suggestions

Unused or redundant dependencies are identified.

Actionable suggestions are provided to streamline project dependencies.

Visualization

All metrics, classifications, and suggestions are made available through the Streamlit dashboard.

Future Scope
Gradle and Multi-Build Tool Support: Extend support to Gradle and other popular build systems.

ML-Based Classification: Introduce machine learning to improve classification accuracy beyond rule-based methods.

Expanded Metrics: Include method-level usage statistics to detect bloated libraries (e.g., size vs. actual usage).

Cross-Project Analytics: Enable dependency analysis across organizational units and teams to identify shared trends.
```
