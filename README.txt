Z-OPTION PREFLIGHT CHECKER — V1

1. Extract the ZIP to a folder.
2. To run with vendor rules, host the folder as a static site (GitHub Pages or approved internal hosting). Both index.html and vendor-rules.json must be published together.
3. Open index.html on that site, select .xlsm files, and click Run preflight checks.
4. Export the exception report as CSV.

Requires internet access to load the SheetJS spreadsheet reader from jsDelivr. Uploaded Excel contents are parsed inside the browser; no upload endpoint is implemented. The app does not alter files.

For offline use, an approved locally hosted copy of the SheetJS reader and local server is needed. Opening index.html directly from disk can prevent vendor-rules.json from loading because browsers restrict file:// fetch requests.

Supported sheets: REL (KR), REL (KG), Direct Entry (KR), Direct Entry (KG).
Unsupported sheets are intentionally skipped.

Rules based on 10 historical CM Heating workbooks; vendor rules are statistical observations, not authoritative master data. Historical dates will fail today's posting date rule. Duplicate detection checks documents within all files selected in one run; uploading overlapping historical batches can cause legitimate repeated-history warnings.

Known limits:
- The historical rules are not independently verified and should be reviewed against the vendor master.
- Rebate identification uses the word "rebate" in descriptions/text; unlabeled rebates may not be recognized.
- Amounts are checked at document level; one-cent tolerance for rounding.
- Browser must be able to load the third-party JS library, subject to company policy.
- This does not compare to SAP posting history, and cannot catch duplicates already in SAP.
- No support yet for custom vendor-rule editing in the interface.
