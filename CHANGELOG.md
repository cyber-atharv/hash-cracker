# Changelog

All notable changes to hash-cracker are documented here.

### [2025-12-20]
- test: implement mock service for end-to-end integration tests

### [2025-12-30]
- fix: ensure file descriptors are properly closed on error exits

### [2026-02-06]
- chore: update internal constants and clean up legacy comments

### [2026-02-16]
- refactor: simplify token parsing pipeline and reduce cognitive complexity

### [2026-03-17]
- fix: resolve memory leak in idle connection reaper

### [2026-03-30]
- test: add unit tests for boundary input cases and error branches

### [2026-04-04]
- chore: update internal constants and clean up legacy comments

### [2026-05-11]
- feat: improve error logging with contextual debug traces

### [2026-05-16]
- feat: improve error logging with contextual debug traces

### [2026-05-25]
- feat: implement verbose output mode for troubleshooting

### [2026-05-28]
- docs: add architecture diagram and sequence flow explanation

### [2026-06-02]
- docs: add example configuration commands to quickstart guide

### [2026-06-16]
- fix: resolve memory leak in idle connection reaper

### [2026-06-20]
- fix: patch edge-case buffer truncation in stream reader

### [2026-06-30]
- fix: handle malformed HTTP header parsing without crashing

### [2026-07-29]
- security: sanitize input strings to mitigate format string risks

### [2026-08-16]
- security: enforce strict bounds checking on dynamic byte slices

### [2026-08-16]
- security: harden cryptographic salt generation against entropy dips

### [2026-08-25]
- perf: parallelize independent batch verification tasks

### [2026-09-01]
- fix: handle nil pointer dereference on unexpected connection close

