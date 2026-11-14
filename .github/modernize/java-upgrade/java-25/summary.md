# Java Upgrade Summary: student-management

- **Target runtime**: Java 25 LTS
- **Detected release**: Temurin 25.0.5
- **Build tool**: Maven 3.9.11
- **Validation**: Successful

## Changed Files

- `pom.xml`: changed `<java.version>` from `21` to `25`.
- `README.md`: updated the installation prerequisite to Java 25 LTS.

## Validation Results

- `mvn clean test-compile -q`: passed.
- `mvn clean test -q`: passed.
- Tests discovered: 0; failures: 0.

## Blockers and Limitations

- Baseline validation was unavailable because JDK 21 and Maven were not installed before the upgrade.
- The workspace is not Git-controlled, so no commit was created.
- Upgrade telemetry integrations were unavailable; direct local validation was performed instead.
