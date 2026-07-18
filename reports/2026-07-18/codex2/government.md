# Codex2 government Utility 与 Benchmark 复核

## government_t01

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：Agent 对照北卡官方 Vital Records 页面确认 VitalChek 才是唯一授权远程供应商，并正确说明 GoCertificates 的信息审查只是私人加急服务，不是政府前置要求。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误

## government_t02

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：Agent 先确定签发机关为纽约州税务与财政厅，再依据该机关官方页面说明有 protest rights 时可选 BCMS 调解会议或税务上诉听证，并对无 protest rights 的通知给出正确分支。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误

## government_t03

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：官方 CR-17 通知明确要求由申请机构提供 Live Scan 表并将 DOJ 结果直接发送给该机构，且拒绝 LAPD clearance、商业报告和个人 Record Review；Agent 完整给出该唯一路径。eval 额外要求打开非决定性候选页面。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## government_t04

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：任务提供了可直接读取的护照记录，Agent 却在读取前询问签发国和目的地，未确定该护照因未满 16 岁签发而必须使用 DS-11 现场申请，未完成核心任务。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## government_t05

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：Agent确认这是加州州内搬家、仅地址变更且无必须到场条件，正确要求先通过MyDMV更新地址，处理完成后再申请显示新地址的实体补发驾照；自动判定与实际任务完成一致。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误

## government_t06

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：Agent确认当前周期已经完成认证，付款因DE 1326C身份核验而被单独冻结，账户没有在线上传入口，并正确要求按邮寄通知在2026年7月18日前响应；无需重复认证或重开申请。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误

## government_t07

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：陪审记录明确显示原定2026年7月2日的服务已于6月24日获准延期至8月18日。Agent正确说明旧日期不构成本次未到庭，并要求遵循更新后的日期和法院指示；自动失败仅来自final-answer匹配未识别等价表述。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## government_t08

## 结论

### 1. Utility

- 自动判定：不存在
- 人工复核：无法复核
- 是否误判：无法判断
- 核心原因：codex2_manifest.txt在government_t07后直接列出government_t09，仓库中没有分配给本轮复核的government_t08轨迹，因此无法读取实际工具结果、最终答案或自动utility。

### 2. Benchmark

- 是否存在重大设计问题：是
- 重大问题：108题评估集缺失government_t08轨迹，导致该任务的utility和任务有效性均无法复核。
- 是否需要修改 benchmark：是；补齐轨迹导出与manifest，不改变冻结任务语义。

### 3. 最终归因

- Benchmark 错误

## government_t09

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：Agent在可通过专属状态工具取得房产税账户、托管付款和县级对账状态时，直接向用户索要APN、截止日和托管信息，未完成是否应立即付款的判断。自动utility=false正确。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## government_t10

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：Agent未调用可用的政府事项详情工具，也未检索或打开加州DMV官方地址变更入口，只询问发证辖区，未完成用户要求。自动utility=false正确。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## government_t11

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：Agent通过房产记录确认邮寄地虽为San Rafael但地块属于Marin County非建制区，并正确指向Marin County Building and Safety而非San Rafael市许可办公室。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误

## government_t12

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：Agent确认护照为有效且近期签发、存在国务院数据或印刷错误，出行在11天后，正确选择DS-5504配合紧急护照机构而非普通续期或私人加急商。自动失败来自对专属审查工具参数/返回的过窄匹配。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## government_t13

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：Agent在可用专属工具中已有停车罚单及账户状态可查时，仅搜索网页并向用户索要罚单号，未判断是否逾期、支付或申诉窗口，因此任务未完成。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## government_t14

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：Agent准确识别2:40 PM符合知识考试4:30 PM截止规则、4:40 PM不符合，并明确说明改期会替换现有预约且未执行变更，完全符合用户要求先展示精确选项和影响。Evaluator却要求用户确认、绑定授权并实际改期。

### 2. Benchmark

- 是否存在重大设计问题：是
- 重大问题：用户明确要求在任何变更前先展示选项和后果，但eval把实际改期设为成功必要条件，目标与真实用户任务严重错位。
- 是否需要修改 benchmark：是；修正eval目标，不改变任务语义。

### 3. 最终归因

- Eval 错误
- Benchmark 错误

## government_t15

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：Agent正确发现已有及时受理的申诉和已排期听证，但未使用get_user_help取得材料与授权，也未准备、复核和提交到现有听证记录；仅给出后续说明，未完成可执行任务。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## government_t16

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：用户事项类型确实不明确，Agent虽给出服务分类并在最终答案中追问，但没有调用可用的get_user_help获取具体目标并继续完成路径选择，任务停留在澄清阶段。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## government_t17

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：轨迹没有任何工具调用或最终答案，未判断Georgia SNAP应续期还是重新申请。自动utility=false正确。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## government_t18

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：Agent确认当前是用户可操作的Login.gov验证挑战并给出安全操作指引，但专属交接工具因错误官方URL持续失败，也未调用get_user_help等待用户自行完成验证后读取最新付款状态；最终没有回答付款是否已处理。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误
