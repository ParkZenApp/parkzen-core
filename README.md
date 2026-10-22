# parkzen-core

Historical Maven distribution and GitHub Packages host for `com.parkzenlib:parkzen-core`. This repository does not contain the Android SDK's source code or build pipeline.

## Source and publishing

The Java SDK is developed and built from the **ParkZenCore branch** of [Native-Android](https://gitlab.com/parkingguidancesystems/mobility/Native-Android), not this repository. Its README describes releasing through the manual GitLab publishing job.

New releases are published to both registries while existing consumers still use GitHub:

- GitLab Maven: `https://gitlab.com/api/v4/projects/87724980/packages/maven`, in the Native-Android project.
- GitHub Packages: `https://maven.pkg.github.com/ParkZenApp/parkzen-core`, associated with this GitHub repository.

The GitLab project for **this** repository is not the destination for SDK package uploads. Existing versions and package coordinates must not be changed or overwritten.

## Contents and migration

`com/parkzenlib/parkzen-core/0.1/` contains an old AAR/POM and checksum sidecars. The repository also has tags `0.1` and `0.2`; both point to the original commit. Preserve these files, versions and tag targets.

[PGS-107](https://parkingguidancesystems.atlassian.net/browse/PGS-107) migrates this repository privately to [mobility/parkzen-core](https://gitlab.com/parkingguidancesystems/mobility/parkzen-core), using the [Mobility migration runbook](https://gitlab.com/groups/parkingguidancesystems/mobility/-/wikis/GitHub-migration-runbook). GitHub remains the development source until cutover. Afterwards, GitLab is the source of truth and GitHub remains a locked mirror; changes use GitLab merge requests.

The migration also copies native core versions 0.0.11.75, 0.0.11.85, 0.0.11.86 and 0.0.11.88 unchanged into **Native-Android's** GitLab registry. This is a package backfill, not a rebuild. Compare original and downloaded checksums before considering it complete, and disable duplicate Maven uploads during registry setup.

Modo still resolves native core 0.0.11.86 from GitHub Packages. Its current URLs and access remain until the coordinated switch in [PGS-490](https://parkingguidancesystems.atlassian.net/browse/PGS-490); GitHub retirement belongs to [PGS-118](https://parkingguidancesystems.atlassian.net/browse/PGS-118). The complete Android repository ZIP is implemented in [PGS-105](https://parkingguidancesystems.atlassian.net/browse/PGS-105).

## CI and ownership

GitLab CI includes `ci-templates/baseline@1` for secret detection on the shared pipeline rules. There is no SDK build or package publication in this repository. Code owners are defined in `.gitlab/CODEOWNERS`; code-owner approval must also be enabled on the protected `master` branch during import setup.

Merge the CI change on GitHub after import/pull-mirror setup, sync it, and manually start the first GitLab pipeline: mirrored commits do not start pipelines automatically. Repository settings, package copying and the final cutover are separate steps; adding these files does not perform them.
