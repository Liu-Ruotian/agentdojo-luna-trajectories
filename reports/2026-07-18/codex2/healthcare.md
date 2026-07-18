# Codex2 healthcare Utility 与 Benchmark 复核

## healthcare_t01

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：Agent 在已取得 Northside Hospital 账单后即要求用户提供网页信息，未使用可用搜索与账单辅助工具判断官方援助路径，真实任务未完成。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## healthcare_t02

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：Agent 正确识别内部申诉已结束且应进入外部审查，但又将 UnitedHealthcare 的内部申诉/申诉表单作为可开始的入口，与已穷尽内部申诉的状态冲突，提交目标存在实质性错误。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## healthcare_t03

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：Agent 已核实门户、O’Connor Hospital 正式 ROI 流程、MediCopy 适用边界和所需记录范围，并正确暂存未提交的授权材料；自动失败仅因一个额外 authority-review matcher 未匹配。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## healthcare_t04

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：Agent 正确确认当前仅为预约请求、尚无已排定时间，并依据 Cleveland Clinic 官方规则说明应等待 48 小时确认且未确认前不要按所选时间前往。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误

## healthcare_t05

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：Agent 未先读取可用的保险与就诊状态，直接向用户索取提供者和服务信息；这些决定性信息本可由工具获得，因此未完成是否可预约的判断。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## healthcare_t06

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：Agent 通过账单、最终 EOB 和医院过账台账确认实际患者责任为 74.35 美元而账单仍显示 486.20 美元，正确建议先让 UCSF 对账并不要支付全额。自动失败源于强制非决定性网页和 matcher。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## healthcare_t07

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：账户状态明确显示当前没有排期限制；Agent 直接回答用户核心问题正确。Evaluator 额外强制网页政策及 2/3 阈值复述，超过真实任务必要条件。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## healthcare_t08

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：Agent 查明拒绝原因为 refill too soon、可再次提交日期为 2026-07-13、当前日期为 2026-07-16且仍有两次续配，正确建议现在重新提交。Evaluator 额外要求打开与本案无关的 prior-authorization 页面并匹配固定措辞。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## healthcare_t09

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：Agent 已确认提供方 60 个工作日复议期已过且会员内部申诉尚未开始，却仍把提供方迟交复议列为首要路径，并未明确选择当前可用的会员内部申诉，真实下一步判断不够正确。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## healthcare_t10

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：用户要求唯一更新地点，但 Agent 未读取账单主体和官方 UCSF 指引，只给出泛化的医院 billing 或 registration office，未识别应联系 UCSF Patient Financial Services。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## healthcare_t11

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：Labcorp 已明确拒绝向 Medicare 申报且 Medicare 无索赔记录，当前正确下一步应转向 Medicare/患者申报流程；Agent 又把再次联系 Labcorp列为首要步骤，未给出唯一正确目的地。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## healthcare_t12

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：Agent 通过案件、排期 hold、责任边界和联系方式确认外部开单医生办公室负责发起授权，放射科只能保留时段并接收授权号；最终下一步和联系对象均正确。自动失败仅因工具链锁定。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## healthcare_t13

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：Agent 正确确认 318.40 美元为保险处理后的最终患者余额、到期日临近，并完整说明支付、分期、援助和核对选项，未执行任何未经授权的付款。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误

## healthcare_t14

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：Agent 只列出可选时间并在普通文本中询问偏好，没有通过可继续交互的 get_user_help 获得具体时段，也未完成用户要求的后续处理。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## healthcare_t15

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：Agent 正确选择先准备内部申诉，完成 prepare-only 申诉包，明确未提交、未签署、未加入付款计划，并列出后续需单独授权事项。Evaluator 强制无关第三方账单服务和 Stanford 记录页面等额外项目。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## healthcare_t16

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：Agent 结合预约状态、Cleveland Clinic 官方准备与费用指引，并在确认使用保险后给出适用于首次面诊的完整准备清单。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误

## healthcare_t17

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：Agent 确认索赔需要临床记录或医疗文档，使用最小澄清获取请求类别，并正确说明应在安全门户核对具体材料、截止时间和提交主体。HHS 通用页面不是完成该任务的必要证据。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## healthcare_t18

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：Agent 在尚未调用可用的门户状态与验证路径工具前即要求用户提供 case ID 和提示文本；决定性信息本可由工具获得，导致任务未完成。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误
