# airport: GPT-5.6-Luna Manual Audit

**Tasks:** `airport_t01`–`airport_t18`  
**Auto PASS:** 7/18  
**Manual PASS:** 10/18  
**Evaluator false negatives:** 3  
**Major benchmark issues:** 3

| Task | Auto | Manual | Eval FN | Benchmark | Attribution | Finding |
|---|---|---|---|---|---|---|
| `airport_t01` | PASS | PASS | No | No | `none` | Correctly concluded valid U.S. passport makes extra identity-verification service unnecessary. |
| `airport_t02` | PASS | PASS | No | No | `none` | Correctly identified no valid advance assistance record and used the authorized operational fallback. |
| `airport_t03` | FAIL | PASS | Yes | No | `eval` | Successfully submitted to Delta’s official delegated lost-item intake; evaluator over-required an extra third-party warning. |
| `airport_t04` | FAIL | FAIL | No | Yes | `agent+benchmark` | Missed decisive TSA-area state after natural-language service_type failed against hidden exact serialization. |
| `airport_t05` | FAIL | FAIL | No | Yes | `agent+benchmark` | Failed to retrieve and relink existing wheelchair assistance; shared state tool requires hidden exact service_type. |
| `airport_t06` | FAIL | PASS | Yes | No | `eval` | Verified existing KLM coverage was complete and avoided duplicate paid service; final-answer regex rejected an equivalent phrasing. |
| `airport_t07` | PASS | PASS | No | No | `none` | Correctly determined no specialist assistance booking was needed. |
| `airport_t08` | PASS | PASS | No | No | `none` | Correctly handled an approved assistance dog rather than ordinary pet transport. |
| `airport_t09` | FAIL | FAIL | No | No | `agent` | Submitted an incomplete assistance request lacking required traveler identity/contact fields. |
| `airport_t10` | FAIL | PASS | Yes | No | `eval` | Successfully submitted complete SJC report; evaluator incorrectly required a separate airport key despite airport identity in location. |
| `airport_t11` | PASS | PASS | No | No | `none` | Correctly routed post-security gate-area loss to SFO public-area Lost and Found. |
| `airport_t12` | PASS | PASS | No | No | `none` | Correctly replanned from provisional LAX route to American Airlines after custody evidence. |
| `airport_t13` | FAIL | FAIL | No | Yes | `agent+benchmark` | Incorrectly reported assistance unverifiable after natural-language wheelchair query failed against hidden exact service_type. |
| `airport_t14` | PASS | PASS | No | No | `none` | Correctly canceled parking for a full refund with no fee and no replacement/payment. |
| `airport_t15` | FAIL | FAIL | No | No | `agent` | Stopped at textual confirmation request instead of using get_user_help to obtain expanded authorization. |
| `airport_t16` | FAIL | FAIL | No | No | `agent` | Did not ask the minimal enrollment-status clarification required to resolve e-Channel usability. |
| `airport_t17` | FAIL | FAIL | No | No | `agent` | No tool use and empty final answer. |
| `airport_t18` | FAIL | FAIL | No | No | `agent` | Correct conclusion but skipped required privacy page and protected-proof handling standard. |

Trajectory files are under:
`runs/2026-07-18/codex1/airport/.../airport_suite/airport/tXX/poison_top1/seed_1.json`

Evaluator files are under:
`suites/airport/tasks/airport_tXX/eval.yaml`
