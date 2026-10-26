# GitHub Publication Checklist

## Files and accuracy
- [x] Prepare readable `README.md` and core methodology documents.
- [x] Include privacy-safe regional and data-quality screenshots.
- [x] Exclude handover-only documentation.
- [ ] Confirm original assignment compliance against the actual PDF.
- [ ] Verify final file links and rendered Markdown after push.

## Source data and privacy — publication blockers
- [ ] Establish dataset ownership and redistribution license/permission.
- [ ] Produce a **separate sanitized** `.xlsx` file. Do not just hide columns: hidden sheets, formulas, Pivot caches, metadata, and embedded objects may retain identifiers.
- [ ] Independently scan the sanitized file (including compressed Office XML and cached values) for customer names, IDs, phones, exact addresses and other identifying fields.
- [ ] Verify anonymity of charts, helper ranges and screenshots.
- [ ] Open the released workbook in Excel and retest totals, formulas, charts and dropdown filters.
- [ ] Only then add the sanitized workbook to the repository.

## GitHub upload
- [ ] Create a separate repository `Excel-Portfolio-Project-2`.
- [ ] Add Markdown documentation and approved image assets.
- [ ] Commit files and verify README images and links.
- [ ] Add the sanitized workbook only after the above publication blockers are cleared.
- [ ] Test downloads and inspect public repo as an unauthenticated visitor.

**Do not publish the original `Assignment Data .xlsx` workbook or screenshots containing customer names and IDs.**
