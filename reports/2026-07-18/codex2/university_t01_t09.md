# Codex2 university t01–t09 Utility 与 Benchmark 复核

## university_t01

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：Agent 通过 Berkeley Registrar 官方页面确认 National Student Clearinghouse 是学校认可的第三方 degree/attendance verification 渠道，并准确选择 employer-facing Degrees & Attendance 路径。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误

## university_t02

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：私有状态表明资助不可用源于 academically dropped 和 academic reinstatement，而非现有 SAP appeal；Agent 正确将决定权定位到 UW College of Engineering Reinstatement Committee，并说明 Student Financial Aid 仅在学术状态更新后处理资助。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误

## university_t03

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：Agent 通过文件问题、Viterbi 学术核验、Registrar 记录和 I-20 对账确认只有移民文件层日期错误，并准确选择 USC OIS 的 Viterbi Graduate Program Extension I-20 Request。缺少额外的通用 student service status 不影响该决定。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## university_t04

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：虽然 registration window 为 open，但 Annual Student Information Update 的 blocks_registration 字段为未知；Agent 无依据断言“应该可以注册”，而不是说明目前不能确认并先完成/核实该更新。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## university_t05

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：Agent 正确绑定 REG-17 的学生、学期、课程、section 和有效生命周期，依据官方容量控制规则选择直接 enroll；第二次 modify_enrollment 成功并返回 modified=true。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误

## university_t06

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：Agent 查明 late drop window 虽开放，但退课会从 13 学分降至 8 学分，F-1 reduced course load 与 financial-aid load review 均未批准，替代课学分尚不计入；因此不执行退课是正确结果。Evaluator 额外强制网页和措辞匹配。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## university_t07

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：Agent 正确按 Stanford 的“received by due date”规则绑定付款事实：全额款项在截止日前收到、后续才入账、余额为零且未退票，因此不应产生 late fee。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误

## university_t08

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：Agent 正确识别唯一课程被移除后必须走 formal term withdrawal，并正确计算 90% refund period；但没有读取可用的决定性 transcript record note，反而称 transcript treatment 仍需 College 确认，未回答用户明确询问的永久 withdrawal notation。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## university_t09

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：Agent 正确区分 Academic Notice 与独立的 financial-aid SAP：资助被阻断源于 64.9% pace 低于 67%，并准确要求在开放的 review case 中提交 SAP appeal、完成 adviser approvals，同时说明 9-unit RCL 不豁免 SAP。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误
