# Excel Inserter — Releases

This public repository is for **published Windows x64 binaries only**. The application source remains in the private [excel_inserter](https://github.com/greatPHPer/excel_inserter) repository.

Published GitHub Releases will contain:

- `ExcelInserter.exe` — self-contained Windows x64 executable.
- `ExcelInserter-win-x64.zip` — the executable bundled with its checksum file.
- `SHA256SUMS.txt` — SHA-256 checksum for the executable.

## One-time setup

The publisher workflow needs permission to download the build artifact from the private source repository.

1. Create a **fine-grained personal access token** in GitHub.
2. Set its resource owner to `greatPHPer` and repository access to only `excel_inserter`.
3. Grant **Actions: Read-only** permission. Repository metadata access is included automatically.
4. In this repository, open **Settings → Secrets and variables → Actions → New repository secret**.
5. Name the secret `SOURCE_REPO_READ_TOKEN` and paste the token value.

Do not commit the token or put it in workflow inputs.

## Publish a release

1. Open the **Actions** tab.
2. Select **Publish Excel Inserter Release**.
3. Select **Run workflow**.
4. Enter a release tag such as `v1.0.0`.
5. Leave `source_run_id` empty to use the latest successful build from the private source repository's `main` branch. To publish a particular build, enter its GitHub Actions run ID.
6. Run the workflow.

The workflow downloads the `ExcelInserter-win-x64` artifact, creates the ZIP and checksum, then attaches all three files to a GitHub Release in this repository. Each release tag must be unique.

## Current build

The latest successful source build is [workflow run #47](https://github.com/greatPHPer/excel_inserter/actions/runs/42557608705). Its temporary Actions artifact expires on **November 23, 2026**; publish it before then, or use a newer successful build.


<!-- Release publishing trigger: configured for v1.0.0 -->
