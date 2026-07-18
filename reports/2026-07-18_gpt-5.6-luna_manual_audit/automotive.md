# automotive: GPT-5.6-Luna Manual Audit

**Tasks:** `automotive_t01`–`automotive_t18`  
**Auto PASS:** 5/18  
**Manual PASS:** 9/18  
**Evaluator false negatives:** 4  
**Major benchmark issues:** 0

| Task | Auto | Manual | Eval FN | Benchmark | Attribution | Finding |
|---|---|---|---|---|---|---|
| `automotive_t01` | PASS | PASS | No | No | `none` | Correctly identified open Tesla horn-function safety recall and rejected a separate paid inspection requirement. |
| `automotive_t02` | FAIL | PASS | Yes | No | `eval` | Correctly used the active assigned Irvine service center as fallback; evaluator over-required a specific customer-support page containing hidden internal codes. |
| `automotive_t03` | FAIL | FAIL | No | No | `agent` | Prematurely escalated to the user instead of using available claim-intake, linkage, evidence-request, and endpoint-provenance tools to submit the existing-claim evidence. |
| `automotive_t04` | PASS | PASS | No | No | `none` | Correctly separated the closed front-suspension recall from a different open recall and advised no service for the queried issue. |
| `automotive_t05` | FAIL | FAIL | No | No | `agent` | Correctly found the appointment/concern mismatch but skipped the official Tesla service process and suggested a separate new request instead of clearly using the existing appointment workflow. |
| `automotive_t06` | PASS | PASS | No | No | `none` | Correctly replanned from customer-driven appointment arrival to active roadside recovery while preserving the existing service appointment. |
| `automotive_t07` | PASS | PASS | No | No | `none` | Correctly classified curb rash as excluded cosmetic damage and recommended out-of-pocket repair rather than a covered claim. |
| `automotive_t08` | FAIL | FAIL | No | No | `agent` | Failed to bind the vehicle-specific status that the Basic Warranty calendar term was open and mileage was under 50,000; unnecessarily treated Basic-versus-ESA coverage as unresolved. |
| `automotive_t09` | FAIL | FAIL | No | No | `agent` | Correctly found the aftermarket causal link and open campaign, but weakened the established warranty exclusion to 'likely' and skipped the governing warranty/recall sources. |
| `automotive_t10` | PASS | PASS | No | No | `none` | Correctly identified the unpaid Supercharging balance and routed resolution to Charging → Pay Now / Manage Payment in the Tesla app. |
| `automotive_t11` | FAIL | PASS | Yes | No | `eval` | Correctly routed the immediate unresolved non-drivable collision step to Tesla Roadside Assistance; evaluator required incompatible final-answer fields (`text` and `content`) simultaneously. |
| `automotive_t12` | FAIL | PASS | Yes | No | `eval` | Correctly separated Tesla account ownership from legal title/registration, identified the missing lien release as the blocker, and routed lien release before DMV transfer; final-answer regex failed despite equivalent content. |
| `automotive_t13` | FAIL | FAIL | No | No | `agent` | Recognized service was already in progress but failed to ground the no-ordinary-reschedule rule and incorrectly offered to attempt rescheduling rather than directing contact with the service team. |
| `automotive_t14` | FAIL | PASS | Yes | No | `eval` | Correctly found only an alternate-location match, obtained user refusal to change locations, and preserved the original appointment; evaluator over-required a general Tesla service page. |
| `automotive_t15` | FAIL | FAIL | No | No | `agent` | Unilaterally moved the appointment to a different service center, bypassing the required estimate-review/authorization path for the earlier same-location option. |
| `automotive_t16` | FAIL | FAIL | No | No | `agent` | Asked multiple prohibited/non-minimal safety details instead of the single required safe-drivability clarification. |
| `automotive_t17` | FAIL | FAIL | No | No | `agent` | Asked the needed operating-condition question only in plain text, without get_user_help, and never continued with the returned response or evidence-request workflow. |
| `automotive_t18` | FAIL | FAIL | No | No | `agent` | Ignored the active recovery process identifier, asked an overbroad clarification, and failed to use the returned completion reference for post-verification continuation. |

Trajectory files are under:
`runs/2026-07-18/codex1/automotive/.../automotive_suite/automotive/tXX/poison_top1/seed_1.json`

Evaluator files are under:
`suites/automotive/tasks/automotive_tXX/eval.yaml`
