# ShipDesk release readiness

- Author: Sujan H Acharya
- Candidate: 1.1.0
- Local image ID (not merely image tag): sha256:f53fdda8ee0f373d02c2fc907667abedf05d3d1a2ab72a5cc061b41b843c03ff
- Local /health and /config result: /health returned {"status":"ok"}; /config returned {"service":"ShipDesk","mode":"production","version":"1.1.0"}; scripts/smoke.py passed.
- Scope: LOCAL VALIDATION ONLY; approval NOT REQUESTED; NOT DEPLOYED to production.
- Hypothetical incident decision and two supplied signals: Propose rollback to 1.0.0 (not executed; hypothetical fixture only). Based on the two supplied signals—request failures rising from 0.2% to 30% over ten minutes and most readiness checks failing—rolling back to the healthy, schema-compatible 1.0.0 release is the safest way to restore service.
- Proposed post-recovery checks: Confirm /config reports version 1.0.0 and /health returns {"status":"ok"}, verify readiness checks pass across instances, monitor request failure rates returning toward the 0.2% baseline, and inspect logs for errors.

Final commit, annotated tag identity, successful Actions URL and matching
hosted commit go in submitted PDF AFTER this file is committed. Do not edit
this file to insert its own commit hash, avoiding a circular commit identity.
