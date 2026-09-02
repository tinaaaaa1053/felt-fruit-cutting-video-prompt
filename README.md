# Felt Fruit Cutting Video Prompt Skill

一个为任意微缩羊毛毡水果生成中英文双语 ASMR 切割视频提示词的 Codex Skill，适用于 Google Flow 及同类文生视频工具。

它不会简单替换水果名称，而会根据水果种类联动设计：

- 羊毛毡水果的外形、表皮与针毡纹理
- 对应水果的剖面、果核、籽、瓣膜、果皮和色彩层次
- 适合该水果结构的切割方向与切片形状
- 羊毛压缩、纤维分离和切片落下的干燥 ASMR 声音
- 固定微距镜头下可追踪的连续切割动作
- 语义严格一致、表达自然的中文和英文版本

## 安装

```bash
git clone https://github.com/tinaaaaa1053/felt-fruit-cutting-video-prompt.git ~/.codex/skills/felt-fruit-cutting-video-prompt
```

重新打开 Codex 后即可使用。

## 用法

只提供水果名称：

```text
使用 $felt-fruit-cutting-video-prompt，为羊毛毡猕猴桃生成中英文切割视频 Prompt。
```

指定更多画面要求：

```text
使用 $felt-fruit-cutting-video-prompt，为一颗拇指大小的羊毛毡水蜜桃生成中英文 Prompt。暖色窗光，木质砧板，从一侧连续切三片，最后露出完整的羊毛毡果核。
```

修复失败的生成结果：

```text
使用 $felt-fruit-cutting-video-prompt 改写这份 Prompt：上次生成出现真实果汁、金属刀，而且切片在刀落下前就出现了。
```

默认输出结构：

```text
🧶 中文版本
主题 / 声音风格 / 视觉效果 / 灯光与镜头 / 动作

✨ English Version
Theme / Sound Style / Visual Style / Lighting & Camera / Action
```

## 文件结构

```text
felt-fruit-cutting-video-prompt/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── fruit-anatomy.md
    └── original-prompts.md
```

三份用于归纳规则的原始双语 Prompt（羊毛毡草莓、香蕉、橘子）保存在 [`references/original-prompts.md`](references/original-prompts.md)，方便回溯和比较。

## 设计重点

Skill 会根据水果类别选择合理剖面与切法：柑橘保留放射状果瓣和内皮，苹果与梨显示中心果核，桃李类绕开羊毛毡果核，猕猴桃和火龙果使用嵌入羊毛中的籽点。所有可见结构始终保持羊毛毡材质，不生成真实果汁、湿润果肉、金属刀或塑料质感。

文生视频具有随机性，提示词能够强化材质与动作连续性，但不能保证模型每次完全服从。遇到具体失败时，可将失败现象和原 Prompt 一并交给 Skill 定向修复。
