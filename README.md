# Java CI/CD — Teaching Example

A minimal Java project demonstrating **Maven**, **JUnit 5**, **GitHub Actions**, CI artifacts, and GitHub Releases.

## Requirements
JDK 21 and Maven 3.9+.

## Run locally
```sh
mvn clean verify
java -jar target/edu-java-ci-cd-1.0.0.jar
```

The program computes the hypotenuse of a right triangle. Its JUnit test checks the result.

## Continuous integration
On pushes and pull requests targeting `main`, the [CI workflow](.github/workflows/maven.yml) checks out the code, sets up Java 21, runs `mvn clean verify`, and uploads the JAR under **Actions → workflow run → Artifacts**.

## Release delivery
When a GitHub Release is published, the [release workflow](.github/workflows/maven-publish.yml) builds and tests the project, then attaches the JAR to that release. To demonstrate, create tag `v1.0.0` and publish a release for it.

**CI artifacts** are attached to workflow runs; **release assets** are attached to published releases.

## Student exercises
1. Break the calculation intentionally and inspect the failing CI test.
2. Add tests for zero and decimal inputs.
3. Add another method and test it.
4. Compare workflow artifacts with release assets.
5. Explore macOS `jpackage` using the historical, inactive `.github/workflows/old.txt` as a starting point.

This is a teaching example, not a production application. The historical workflow notes remain unmodified for reference.
