# 家庭医生 Skills

[English](README.md) | [信任与安全](TRUST.zh-CN.md) | [贡献指南](CONTRIBUTING.zh-CN.md)

面向中文和英文用户的健康分流指令集，支持 Codex Skills，也适合 Claude Code、Cursor、Windsurf、Cline、Roo Code 等 vibe coding / agent app 读取使用。它用于在家中遇到常见疾病、外伤或不适时，帮助用户先做安全分流、基础急救/居家处理，并判断什么时候需要门诊、急诊、急救电话或医生评估。

> 医疗安全提醒：这些 skills 不能替代医生诊断、处方、急救服务或线下就医。出现危及生命的症状时，请立即拨打当地急救电话；在中国大陆请拨打 `120`。

## 版本

| Skill | 语言 | 适合场景 |
| --- | --- | --- |
| `family-doctor-zh` | 简体中文 | 中国用户、中国大陆就医路径、`120`、社区/门诊/急诊分流、中文家庭场景 |
| `family-doctor-en` | English | 英语用户、911/999/112/000、urgent care、ER/ED、primary care/GP、Poison Control |

## 能做什么

- 判断症状或外伤是否有危险信号
- 给出居家观察和基础处理建议
- 提醒哪些事情不要做，例如滥用抗生素、普通感冒随意输液、烫伤抹牙膏/酱油、儿童酒精擦浴
- 帮助判断去哪里就医：居家观察、社区卫生服务中心、当天门诊/儿科、急诊、`120`
- 针对特殊人群降低风险阈值：儿童、老人、孕妇/产后、易过敏人群、慢病患者、免疫低下者、抗凝药使用者、多药联用者
- 帮助准备就医信息：症状时间线、体温记录、用药清单、过敏史、伤口/皮疹照片、药瓶或化学品包装

## 适合场景

- 发烧、咳嗽、喉咙痛、流鼻涕、类似感冒或流感的症状
- 呕吐、腹泻、肚子痛、疑似食物中毒
- 切伤、擦伤、出血、烫伤、扭伤、摔倒、头部撞击
- 过敏、皮疹、虫咬、疑似严重过敏反应
- 小孩发热、老人突然虚弱/糊涂、孕妇不适、慢病患者症状加重
- 误服药物、药物吃重了、儿童误食、接触化学品
- 不确定该居家观察、去门诊、去急诊，还是打 `120`

## 不适合

- 医生面诊、检查、诊断和治疗方案
- 处方药开具或处方药剂量调整
- 急救服务
- 长期慢病管理方案
- 精神危机干预

如果出现严重呼吸困难、胸痛、疑似中风、意识不清、抽搐、严重过敏、无法止住的大出血、严重外伤、严重烧烫伤、疑似中毒并有症状等情况，应立即拨打急救电话。

## 安装

克隆仓库后，把需要的 skill 目录复制到 Codex skills 目录。

```bash
cp -R family-doctor-zh ~/.codex/skills/
cp -R family-doctor-en ~/.codex/skills/
```

然后重启 Codex，或让 Codex 重新加载 skills。

## 其他 Vibe Coding 和 Agent App

这个仓库不只适合 Codex。两个 skill 目录本质上是 Markdown 指令集，所以即使某些工具不能原生识别 Codex Skills，也可以读取并使用这些内容。

- `CLAUDE.md`：供 Claude Code 使用
- `AGENTS.md`：供会读取仓库级指令的通用 agent 工具使用
- `family-doctor-en/SKILL.md` 和 `family-doctor-zh/SKILL.md`：主要指令本体
- `references/`：按场景拆分的医疗安全和分流参考

Claude Code、Cursor、Windsurf、Cline、Roo Code 以及类似的 vibe coding app 可以通过读取对应语言的 `SKILL.md` 和相关 `references/` 文件来使用这套指令。

## 如何使用

### 在 Codex 中使用

把 skill 目录复制到 `~/.codex/skills/` 后，重启 Codex 或重新加载 skills。然后直接要求 Codex 使用对应语言版本：

```text
请使用 family-doctor-zh，帮我判断这个症状是否危险，应该居家观察、去门诊、去急诊，还是拨打 120。
```

```text
Use family-doctor-en to help me assess whether these symptoms are dangerous and whether I should use home care, urgent care, the ER, or emergency services.
```

### 在 Claude Code 中使用

用 Claude Code 打开这个仓库。Claude Code 通常会读取 `CLAUDE.md` 作为项目级说明。然后你可以这样问：

```text
请根据这个仓库里的中文家庭医生指令，帮我判断这个症状是否危险：……
```

```text
Use the English Family Doctor instructions in this repository to triage this situation: ...
```

### 在 Cursor、Windsurf、Cline、Roo Code 等工具中使用

用对应 app 打开这个仓库，然后让 agent 读取：

- `AGENTS.md`：通用仓库级说明
- `family-doctor-zh/SKILL.md`：中文版本体
- `family-doctor-en/SKILL.md`：英文版本体
- `references/` 下相关文件：具体场景参考

示例：

```text
请先读取 AGENTS.md，然后使用 family-doctor-zh/SKILL.md 和相关 references 文件，帮我做居家健康分流：……
```

英文示例：

```text
Read AGENTS.md, then use family-doctor-en/SKILL.md and relevant reference files to help triage this home-health question: ...
```

## 提问时建议提供

- 年龄和性别
- 是否怀孕/产后
- 主要症状或受伤原因
- 什么时候开始的，持续多久
- 体温、血压、血糖、血氧等可用数据
- 呼吸、精神状态、喝水和尿量
- 基础疾病和正在吃的药
- 过敏史
- 是否为儿童、老人、免疫低下、易过敏、抗凝药使用者

## 示例

```text
请用 family-doctor-zh 帮我判断：3 岁孩子发烧 39 度，咳嗽一天，能喝水但精神一般，没有喘，今晚应该怎么处理？什么时候要去急诊？
```

```text
我爸 78 岁，有高血压和糖尿病，今天突然很虚弱，有点糊涂，没胃口。请帮我判断是不是需要急诊。
```

```text
孕 30 周，今天肚子一阵阵发紧，还有点头痛。请帮我判断需要观察还是去医院。
```

```text
我吃完虾以后全身起疹子，嘴唇有点肿，但还能说话呼吸。现在应该怎么办？
```

## 输出风格

两个版本都会优先输出可执行建议：

1. 先判断危险程度
2. 现在立刻做什么
3. 在家可以怎么处理
4. 不要做什么
5. 观察哪些红旗信号
6. 什么时候去门诊、急诊或拨打 `120`
7. 就医时带什么信息

## 可靠性与安全性

建议这样描述：这些 skills 是**以安全为核心、参考权威来源设计的居家分流工具**，而不是医生替代品。

它们的可靠性来自流程设计，而不是承诺“AI 一定正确”：

- 保守分流：先检查急症红旗信号，再给居家处理建议。
- 明确升级路径：危险情况会引导用户去急诊、拨打急救电话，或当天联系医生。
- 特殊人群更谨慎：儿童、老人、孕妇/产后、易过敏人群、慢病患者、免疫低下者、抗凝药使用者都会降低就医阈值。
- 明确边界：不做最终诊断，不开处方，不建议自行调整处方药。
- 内容可审查：知识被拆分到清晰的 reference 文件，方便逐条 review、修正和贡献。
- 参考权威来源：安全分流模式参考 CDC、American Red Cross、Poison Control、ACOG 以及本地急救/公共卫生资源。
- 要求更新核查：涉及药物剂量、疫苗、传染病政策、召回、本地急救路径等可能变化的信息时，skill 会要求 Codex 查阅最新权威来源。

可参考的来源示例：

- [CDC 流感症状与警示信号](https://www.cdc.gov/flu/signs-symptoms/index.html)
- [American Red Cross 急救资源](https://www.redcross.org/take-a-class/resources/learn-first-aid)
- [Poison Control](https://www.poison.org/)
- [ACOG 孕产妇紧急警示信号](https://www.acog.org/womens-health/infographics/urgent-maternal-warning-signs)

## 目录结构

```text
.
├── family-doctor-zh/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/
│       ├── china-localization.md
│       ├── children.md
│       ├── fever-respiratory.md
│       ├── first-aid-injuries.md
│       ├── gastro-poisoning.md
│       ├── medication-safety.md
│       ├── older-adults.md
│       ├── output-patterns.md
│       ├── pregnancy-allergy-high-risk.md
│       └── red-flags.md
└── family-doctor-en/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/
        ├── english-localization.md
        ├── children.md
        ├── fever-respiratory.md
        ├── first-aid-injuries.md
        ├── gastro-poisoning.md
        ├── medication-safety.md
        ├── older-adults.md
        ├── output-patterns.md
        ├── pregnancy-allergy-high-risk.md
        └── red-flags.md
```

## 安全原则

这些 skills 的设计原则是保守分流：帮助用户决定下一步，而不是做最终诊断。如果回答建议急诊、急救或当天就医，请优先执行现实世界的医疗行动。

更多说明见：[信任与安全](TRUST.zh-CN.md)。

## 贡献

欢迎提交 issue 或 pull request，尤其是：

- 更清晰的中文或英文问答模板
- 更完整的特殊人群分流规则
- 不同国家和地区的急救电话、就医路径补充
- 权威医学来源更新
- 更好的安全边界和误区提醒

涉及医学建议的修改请尽量附带权威来源，并保持保守分流原则。

贡献规则见：[贡献指南](CONTRIBUTING.zh-CN.md)。
