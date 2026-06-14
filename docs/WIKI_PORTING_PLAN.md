# Hondatabase - Wiki Porting Assessment & Progress Plan

This plan assesses all **513 topics** in the `library` web of the `pgmfi` wiki archive database. It categorizes them, identifies valuable articles vs stubs, and establishes a clear path to complete the porting process.

## 1. Overall Progress Summary

| Status | Count | Percentage | Description |
| :--- | :---: | :---: | :--- |
| **Completed** | 493 | 96.1% | Topics with local article bundles |
| **Pending Porting** | 0 | 0% | Relevant content articles remaining to be ported |
| **Stubs / Ignored** | 20 | 3.9% | Wiki pages with < 100 characters of text (empty templates, personal placeholders) |
| **Total** | **513** | **100%** | All topics in `library` web |

## 2. Category Breakdown

| Category | Total | Completed | Pending | Stubs |
| :--- | :---: | :---: | :---: | :---: |
| Unclassified/Other | 252 | 238 | **0** | 14 |
| Electronics/Sensors & solenoids | 71 | 71 | **0** | 0 |
| Electronics/ECU hardware & chipping | 88 | 88 | **0** | 0 |
| Diagnostics & troubleshooting | 11 | 11 | **0** | 0 |
| Electronics/Wiring & conversion | 17 | 17 | **0** | 0 |
| Tuning & ROM editing | 43 | 42 | **0** | 1 |
| Fueling & Injectors | 5 | 5 | **0** | 0 |
| General Info & History | 15 | 11 | **0** | 4 |
| Engine & Drivetrain mechanical | 11 | 10 | **0** | 1 |

## 3. Prioritized Pending Articles by Category

No substantive archived topics remain in the automated pending queue. Remaining work is post-port source-fidelity, attachment, and presentation review.

## 4. Batch Porting Quality Gate

A local article bundle counts as completed in the tables above, but a port is not editorially complete until it passes this workflow:

1. **Capture the source:** retain the raw archived page, attachment inventory, and generated draft long enough to compare them during review.
2. **Adapt the presentation:** remove wiki boilerplate and forum chatter; add a useful lead, clear sections, tables, captions, and supported Markdown.
3. **Preserve the evidence:** do not invent component functions, compatibility claims, missing table labels, procedures, or recommendations. Keep uncertainty and source contradictions visible.
4. **Label legacy guidance:** describe old software settings, tuning defaults, supplier numbers, and community procedures as archived examples rather than current recommendations.
5. **Bring the attachments:** compare archive attachment records with the article bundle, copy every useful recovered image and download, remove broken legacy links, and explicitly note important referenced files that were not recovered.
6. **Compare source to article:** verify all values, formulas, addresses, pinouts, units, filenames, and retained assets against the raw page after the rewrite.
7. **Check rendering and URLs:** remove unsupported syntax and verify every retained image and download through its rendered article asset URL.
8. **Run automated validation:** run `php artisan app:lint-articles`, but treat lint as a structural check only. A passing linter does not establish technical accuracy or source fidelity.

Source-faithful porting does not mean copying pages verbatim. Articles should be rewritten for clarity and mobile readability while keeping the archived technical claims, limitations, and uncertainty intact.

## 5. Next Steps

1. **Source-fidelity review:** compare generated and lightly edited articles against their archived pages, prioritizing long technical references and procedures.
2. **Attachment audit:** reconcile archive attachment records with article bundles and verify every retained image and download URL.
3. **Stub decisions:** review the 20 short archived topics and either intentionally ignore, merge, or expand them.
4. **Presentation cleanup:** replace malformed legacy tables, link soup, raw HTML, and unsupported Markdown without changing technical meaning.
