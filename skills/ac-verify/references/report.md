# Report contract

Use Markdown locally and an explicitly supported table format for Azure DevOps posting. Keep a complete local copy if the API payload limit requires a shortened comment. Do not upload attachments without authorization.

## Header

- Work item URL/ID, title, revision and retrieval timestamp.
- Repository, PR URL/ID or local comparison, base/head SHAs, merge base where applicable, dirty working tree inclusion.
- Report timestamp and evidence environment.
- Summary counts for Met, Partially met, Not met, Not verifiable. Count parent AC once; show subcriteria in the details. Do not treat Not verifiable as passed.

## Tables

Create an **Acceptance criteria** table with these columns:

`ID | Requirement | Verdict | Implementation evidence | Execution evidence | Confidence and reason | Gap / next check`

Include every active criterion, even those covered by linked test cases. Retain source wording or a faithful excerpt with its conditions. Long evidence may be placed in numbered notes referenced from cells.

Create a separate **Linked test cases** table when cases exist:

`TC ID | Steps / expected result | AC mapping | Verdict | Evidence / tested version | Gap`

Record unmapped cases and uncovered AC explicitly. If no cases were linked, say so; do not invent test cases. If case retrieval failed, distinguish that from having no linked cases.

For each evidence reference, use verified file paths and line numbers at the inspected version or a test run/result link. Local file references are not clickable to Azure DevOps readers: include repository-relative paths and the commit SHA, or verified repository links. Never invent line numbers or URLs.

## Footer

List commands actually run and outcomes; evidence not available; excluded struck-through requirements; assumptions; unresolved questions; and manual/runtime checks required. Avoid claims about environments or commits that were not inspected.

For posting, include an audit label such as `ac-verify: WI 123 rev 7; base abc; head def` and timestamp. It is a deduplication aid, not authorization to edit existing comments.
