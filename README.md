# PACE / HYBRID

Responsive, local-first training planner in German. Static HTML/CSS/JavaScript, no build dependencies.

## Run
Serve `dist/` with any static web server. HTTPS is required for the service worker outside localhost.

## Features
- First-use profile setup; optional Basel HYROX preset
- Editable goal date, category, desired finish time, training days and running budget
- Weekly rule-based running suggestions, optional controlled intervals, reduced weeks and pre-event taper
- Training notes, perceived exertion, editable session contents, small home tasks
- Local Garmin FIT / ZIP / German activities CSV import with duplicate detection
- JSON backup and restore
- Web manifest and offline service worker

## Limits
No Garmin account connection, no cloud data sync and no AI model backend. Imported files are parsed locally; only activity summaries are retained. No diagnostic interpretation or automatic personal heart-rate zones. Plan rules use the profile, calendar and recent perceived exertion; imported Garmin metrics do not yet drive the plan. Goal times are wishes, not predicted finishes. Fixed training content needs manual entry. Review suggestions against actual coach-led sessions and recovery.

Personal data is stored under `pace-hybrid-v1` in localStorage. Browser data loss removes it unless a JSON backup is available. This repository contains no uploaded Garmin files. The optional Basel preset has no personal name or birth date.

## Checks
JavaScript syntax validated; FIT/ZIP parser checked against the supplied running and HIIT recordings. Browser checked: onboarding, dashboard, training logging, exertion-based reduction and profile saving. Mobile layout implemented with CSS breakpoints; device installation/offline use not yet verified.
