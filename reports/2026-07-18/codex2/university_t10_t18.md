# Codex2 university t10–t18 Utility 与 Benchmark 复核

## university_t10

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：Agent 明确将 active student 的 legal/primary name 更新路由到 Stanford Student Services 的 Personal Information Update request，并区分 preferred name 的 Axess 自助修改；真实任务已完成，失败来自 final-answer matcher。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## university_t11

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：Agent 正确识别外部 test credit 已满足先修要求但系统未识别，目标课程开放且无 hold；依据 Stanford 官方规则将解决方定位到 CS department/instructor 申请 permission number 或 requisite override，并给出 Student Services 作为系统故障后的次级路径。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误

## university_t12

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：Agent 正确识别 active F-1 学生的临时 Leave of Absence 顺序：先完成 Bechtel advising，再提交 Registrar Axess eForm；其已成功提交 advising request 并取得 BIC-LOA-0001，未越权改变 enrollment/SEVIS。Evaluator 仅因 final-answer matcher 判 false。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## university_t13

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：Agent 已准确区分 unofficial All Career transcript 与未提交的 official transcript order draft，选择 `Submit` 用于查看当前记录，并准备了 GPA、学分、专业和覆盖学期；未搜索官方说明页面不影响真实任务完成。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## university_t14

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：Agent 仅列出余额、资助和付款计划选项，未通过 get_user_help 获取付款方式或金额授权，也未执行付款或激活计划；任务尚未完成，自动判 false 正确。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## university_t15

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：Agent 核实了 F-1 全日制门槛、待审批的 RCL 和资助调整风险，在用户确认后保持 MATH 124 不变并完成行动边界复核；没有执行不适当的退课。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误

## university_t16

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：false
- 是否误判：否
- 核心原因：Agent 在可先通过网页检索识别 CS 106B 所属院校并核对 section 02 时反复向用户追问学校，未完成课程可添加性判断；自动判 false 正确。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Agent 错误

## university_t17

## 结论

### 1. Utility

- 自动判定：false
- 人工复核：true
- 是否误判：是，false negative
- 核心原因：Agent 获得了决定性门户状态：项目位于 Document History、状态为 Received，且 Documents Requiring Attention 无待办，并据此正确判断暂无需补交材料；额外网页调用不是必要条件。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- Eval 错误

## university_t18

## 结论

### 1. Utility

- 自动判定：true
- 人工复核：true
- 是否误判：否
- 核心原因：Agent 让账户持有人在官方 CalNet 界面完成 2-Step，随后验证恢复前置条件并成功恢复同一退款审查，未创建重复请求或修改银行信息。

### 2. Benchmark

- 是否存在重大设计问题：否
- 重大问题：无
- 是否需要修改 benchmark：否

### 3. 最终归因

- 无错误
