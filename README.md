# 电商竞品标签Skill_v2

这是一个用于电商竞品数据分析的Skill。

## 仓库结构

```text
.
├── README.md
├── LICENSE
├── .gitignore
└── skills/
    └── tagging-ecommerce-competitors/
        ├── SKILL.md
        └── agents/
            └── openai.yaml
```

## 安装方法

### 方法一：复制 Skill 文件夹

下载或克隆本仓库，然后将以下文件夹：

```text
skills/tagging-ecommerce-competitors
```

复制到本机的 Codex Skills 目录：

```text
~/.codex/skills/tagging-ecommerce-competitors
```

Windows 常见位置：

```text
C:\Users\你的用户名\.codex\skills\tagging-ecommerce-competitors
```

安装完成后，重新打开 Codex，或新建一个任务，使其重新识别 Skill。

### 方法二：让 Codex 帮助安装

将本仓库的 GitHub 地址发送给 Codex，并提出：

```text
请从这个 GitHub 仓库安装 tagging-ecommerce-competitors Skill：
https://github.com/你的用户名/你的仓库名
```

如果仓库中包含多个 Skill，请同时说明 Skill 的目录：

```text
skills/tagging-ecommerce-competitors
```

## 使用方法

在 Codex 中上传或指定竞品 Excel 文件，然后调用：

```text
$tagging-ecommerce-competitors 分析这个竞品表，为每个竞品生成核心标签。
```

也可以直接使用自然语言：

```text
请使用电商竞品标签 Skill 分析这个表格，在原表最后新增核心标签列。
```

## 推荐输入字段

Skill 会根据表头名称识别字段，不依赖固定列号。建议表格包含以下字段：

| 字段 | 用途 |
|---|---|
| 商品ID | 识别商品 |
| IPV／整体点击 | 判断整体流量规模 |
| 转化率 | 判断流量承接能力 |
| 成交笔数 | 判断整体成交规模 |
| 付费点击量 | 判断广告投放规模 |
| PPC | 判断单次付费点击成本 |
| ROI | 判断广告投入产出效率 |
| 付费成交笔数 | 判断广告归因成交规模 |

字段不完整时仍可分析，但可能被标记为“数据不足”或降低判断确定性。

## 使用注意事项

- 每个竞品只会获得一个核心标签。
- 标签按照规定顺序判断，命中后停止。
- 付费点击量高不代表投放效果一定好。
- PPC高不代表竞品一定更强。
- ROI反映广告投入产出，不等同于利润。
- 缺少毛利率、退款率等数据时，不应根据ROI直接判断盈利能力。

## 更新 Skill

核心规则统一维护在：

```text
skills/tagging-ecommerce-competitors/SKILL.md
```

更新规则后建议重点检查：

1. 新旧标签是否保持互斥
2. 是否存在永远无法命中的规则
3. 区间重叠时是否被错误判断为确定领先
4. 数据缺失时是否仍能稳定处理
5. 输出是否仍然只有一列“核心标签”

`README.md` 主要用于向使用者介绍安装和使用方法，不作为实际标签判定依据。

## License

本项目建议使用 [MIT License](LICENSE)。

在遵守许可证的前提下，可以自由使用、修改和分发本项目。
