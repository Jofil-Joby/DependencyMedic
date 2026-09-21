## Decision and Reasoning

DependencyMedic decides whether the project exposes a recognizable dependency manifest. It reports the evidence and recommends verifying or adding the appropriate manifest when none is detected.

## Inputs and Data Sources

It uses the project file list and common manifest names such as package.json, requirements.txt, pyproject.toml, pom.xml, and build.gradle. Its decision is based on observable repository structure.

## Limits and Constraints

It does not perform a complete dependency graph, vulnerability, freshness, or license audit. Custom build systems and manifests outside the recognized set may be missed.
