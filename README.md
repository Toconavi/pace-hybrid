# PACE / HYBRID

German local-first HYROX training PWA. Static HTML, CSS and JavaScript; serve `dist/` over HTTPS. No build dependencies.

## Version 0.4
- Dashboard prioritizes the next incomplete task, a recent measured fitness picture and weekly completion. The race goal is a small editable note.
- FIT/ZIP import decodes sessions, timestamped records, laps and timer events; analysis uses full-resolution data before chart thinning.
- Feedback covers pace, heart rate, round variation, Garmin aerobic Training Effect, cadence/power where present, and cautious comparisons with similar solo runs.
- Heart-rate change is compared after the initial 10 minutes only when speed and elevation permit; weather and measurement limitations remain explicit. No diagnostic or VO2max claim.
- Same-day runs/HIIT sessions match compatible planned tasks, preserve notes and link IDs. Short sessions remain partial; explicit confirmation can complete them. Reimports enrich old summaries without duplicate credit.
- Per-activity context can exclude accompanied/easy runs from performance comparisons. Known five-station sequences can be reconstructed from user-entered timing; they are not automatically recognized.
- Import and task completion produce a celebration; reduced-motion preference is respected.
- Imported high aerobic TE (>=4.5, >=40 min) can make the next two days easier while recovery feedback is missing. Positive recovery overrides this precaution. This is a transparent app rule, not a validated readiness model.

## Privacy and persistence
Profile, logs, analysis samples and summaries remain in browser localStorage. Original uploads are archived separately in local IndexedDB when available. Keep the downloaded originals; JSON backup contains application data but does not include original file blobs. No cloud synchronization and no AI service receives activity data. Public repository contains synthetic test data only, never user Garmin files.

Pre-0.4 imports retained only summaries; reimport the same FIT/ZIP once for detailed analysis. Existing logs/settings are retained. A full localStorage raises a visible save error; imports roll back instead of reporting false success.

## Boundaries
No overall HYROX fitness percentage is estimated. The displayed percentage means weekly plan completion only. Wrist measurements do not establish station loads, repetitions, technique, individual HRmax or assured finish time. Supported analyses cover common FIT fields, not every vendor extension. Original uploads are retained locally for future processing. Interval/station verification is limited to recorded/user-described data.

## Validation
Run `node tests/coach.test.cjs`. Tests cover synthetic FIT records, missing values, detail metrics, import-to-task completion, duplicates, unlinking, partial completion, explicit confirmation, load rules and recovery overrides. Four real user-provided recordings were checked privately against expected session values; those fixtures are excluded. Browser checked real ZIP import, analysis/graphs, task linking, next task and celebration. Physical-device installation and offline data recovery were not re-tested.
