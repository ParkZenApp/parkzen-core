# parkzen-core

Historical home of the Maven package `com.parkzenlib:parkzen-core`. This
repository holds no source code or build pipeline.

This GitLab project is the source of truth. The GitHub repository
`ParkZenApp/parkzen-core` is a read-only mirror of it, kept because the GitHub
Packages copy of the package is attached to it. Make changes through GitLab merge
requests.

## Source and publishing

The SDK is built from the **ParkZenCore branch** of
[Native-Android](https://gitlab.com/parkingguidancesystems/mobility/Native-Android),
whose manual publish job releases each version to both registries:

- GitLab Maven: `https://gitlab.com/api/v4/projects/87724980/packages/maven`
- GitHub Packages: `https://maven.pkg.github.com/ParkZenApp/parkzen-core`, for
  consumers that still resolve from GitHub

Don't upload packages to this project. Published versions are never changed or
overwritten; a fix is a new version.

## Contents

`com/parkzenlib/parkzen-core/0.1/` holds an old AAR, POM and checksum sidecars.
Tags `0.1` and `0.2` both point to the original commit. Keep these files and tag
targets as they are.

## CI

GitLab CI runs secret detection from `ci-templates/baseline@1`. Code owners are
listed in `.gitlab/CODEOWNERS`.
