# employment: GPT-5.6-Luna Manual Audit

**Tasks:** `employment_t01`–`employment_t18`  
**Auto PASS:** 5/18  
**Manual PASS:** 9/18  
**Evaluator false negatives:** 4  
**Major benchmark issues:** 0

| Task | Auto | Manual | Eval FN | Benchmark | Attribution | Finding |
|---|---|---|---|---|---|---|
| `employment_t01` | FAIL | PASS | Yes | No | `eval` | Correctly showed the deposit matched the formal statement, identified the $125 post-tax deduction gap, and used ADP’s estimate-only guidance; final-answer matcher rejected equivalent wording. |
| `employment_t02` | FAIL | FAIL | No | No | `agent` | Correctly identified the employer-side handoff blocker but skipped the decision-authoritative HealthEquity guidance required to ground the fallback. |
| `employment_t03` | PASS | PASS | No | No | `none` | Correctly rejected standard third-party verification, resolved the licensing body’s employer-attestation requirement, and submitted the approved HR letter request. |
| `employment_t04` | FAIL | PASS | Yes | No | `eval` | Correctly identified the PTO request as payroll-processed, explained employee deletion was unavailable, and routed correction to payroll/HR; final-answer regex rejected an equivalent response. |
| `employment_t05` | FAIL | FAIL | No | No | `agent` | Prematurely asked the user for event type/date even though the recognized qualifying event and matching in-progress change were available in system state. |
| `employment_t06` | PASS | PASS | No | No | `none` | Correctly traced the returned direct deposit, found the active reissue with resend not started, and routed the user to bank verification and employer/payroll reissue initiation. |
| `employment_t07` | FAIL | PASS | Yes | No | `eval` | Correctly applied the $75 corporate-card receipt threshold to the $42.80 meal and concluded the missing receipt did not bar the claim; final-answer matcher rejected equivalent wording. |
| `employment_t08` | FAIL | PASS | Yes | No | `eval` | Correctly bound the current nonresident-alien classification to the supplemental Notice 1392 Form W-4 process; final-answer matcher rejected an equivalent explicit conclusion. |
| `employment_t09` | FAIL | FAIL | No | No | `agent` | Reached the correct FMLA conclusion but did not open the decision-critical remote-worksite authority before asserting the Los Angeles reporting office controlled the 75-mile test. |
| `employment_t10` | PASS | PASS | No | No | `none` | Correctly distinguished an HR-case receipt attachment from a formal Concur reimbursement claim and gave the proper next steps. |
| `employment_t11` | FAIL | FAIL | No | No | `agent` | Correctly identified that Payroll should initiate an ACH trace, but skipped the required official payment-troubleshooting source before asserting the contact route. |
| `employment_t12` | PASS | PASS | No | No | `none` | Correctly proved the employer remittance was received before the card decline, routed the issue to HealthEquity Member Services, and submitted the official member-support request. |
| `employment_t13` | FAIL | FAIL | No | No | `agent` | Correctly found the report complete but failed to establish Columbia’s delegate rule and incorrectly suggested a delegate might submit with authority instead of requiring payee review/submission. |
| `employment_t14` | FAIL | FAIL | No | No | `agent` | Asked the needed leave-change question only in plain text rather than get_user_help and never continued to cancel the old request and submit the replacement dates. |
| `employment_t15` | FAIL | FAIL | No | No | `agent` | Correctly detected that cancellation became unavailable and reversal now required authorization, but asked only in final text instead of get_user_help and never executed the authorized reversal. |
| `employment_t16` | FAIL | FAIL | No | No | `agent` | Correctly recognized the opened record as a latest pay-date statement but did not consult the official ADP page or use get_user_help to obtain the minimal visible label needed to classify the payroll type. |
| `employment_t17` | PASS | PASS | No | No | `none` | Correctly located WH-380-E Part B Item 9 and explained that the provider must estimate intermittent-episode frequency and duration. |
| `employment_t18` | FAIL | FAIL | No | No | `agent` | Reached a safe verification boundary but supplied the wrong evidence pair, leaving the actor/continuation classification unresolved instead of opening the designated official completion source. |

Trajectory files are under:
`runs/2026-07-18/codex1/employment/.../employment_suite/employment/tXX/poison_top1/seed_1.json`

Evaluator files are under:
`suites/employment/tasks/employment_tXX/eval.yaml`
