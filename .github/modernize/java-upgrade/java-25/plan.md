# Upgrade Plan: student-management (java-25)

- **Generated**: 2026-11-14T10:49:03+05:30
- **HEAD Branch**: N/A
- **HEAD Commit ID**: N/A

## Available Tools

**JDKs**
- JDK 21: not available (baseline skipped)
- JDK 25: to be installed locally for validation

**Build Tools**
- Maven: not available; Maven 3.9.x will be installed locally for validation

## Guidelines

- Upgrade only the Java runtime target and necessary documentation/build configuration.
- Do not create commits.

> Note: You can add any specific guidelines or constraints for the upgrade process here if needed, bullet points are preferred.

## Options

- Working branch: N/A (not a git repository)
- Run tests before and after the upgrade: true

## Upgrade Goals

- Java 25

## Technology Stack

| Technology/Dependency | Current | Min Compatible | Why Incompatible |
|---|---:|---:|---|
| Java | 21 | 25 | User requested Java 25 LTS |
| Spring Boot | 3.3.5 | 3.3.5 | No framework change required for this runtime-only upgrade |
| Maven | unavailable | 3.9+ | Required to validate Java 25 compilation |

## Derived Upgrades

- Install JDK 25 for compilation and runtime validation.
- Use Maven 3.9.x for validation because Maven is not installed and no wrapper is present.

## Impact Analysis

### Dependency Changes

| File | Dependency | Current | Action | Target | Reason |
|---|---|---:|---|---:|---|
| pom.xml | `java.version` | 21 | upgrade | 25 | Sets Maven compiler release and Spring Boot runtime target |

### Source Code Changes

No source changes required; the project uses standard Java/Spring APIs compatible with Java 25.

### Configuration Changes

No application configuration changes required.

### CI/CD Changes

No CI/CD files are present.

### Risks & Warnings

- Java 25 validation depends on locally installing JDK 25 and Maven because neither is currently available.
- Existing Spring Boot 3.3.5 is retained to minimize unrelated changes; compilation and tests will validate compatibility.

## Upgrade Steps

- Step 1: Setup Environment
  - **Rationale**: Provide JDK 25 and Maven for validation.
  - **Changes to Make**: Install local tools only; do not modify project dependencies.
  - **Verification**: `java -version` and `mvn -version`, expected Java 25 and Maven 3.9+.

- Step 2: Setup Baseline
  - **Rationale**: Baseline is skipped because the current JDK 21 and Maven are unavailable.
  - **Changes to Make**: None.
  - **Verification**: Skipped with documented blocker.

- Step 3: Upgrade Java Target
  - **Rationale**: Change the Maven Java target and user-facing runtime prerequisite.
  - **Changes to Make**: Apply the dependency and documentation changes above.
  - **Verification**: `mvn clean test-compile`.

- Step 4: Final Validation
  - **Rationale**: Confirm main/test compilation and full test pass rate on Java 25.
  - **Changes to Make**: Fix any Java 25 compatibility failures discovered by validation.
  - **Verification**: `mvn clean test`.
