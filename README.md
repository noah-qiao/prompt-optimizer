# prompt-optimizer

## 作用

你手里有一份写得潦草的草稿、拿不准模型能不能直接照着开工时，它交出三样东西：

1. 七段结构：节名与顺序固定，模型读完就能动手。
2. 可判断的要求：每条落到数量、格式、有无或可复现步骤。
3. 缺口清单：会改变目标或交付物的信息，先用弹窗问清，最多 2 轮。

## 优势

1. 草稿里的寒暄、重复强调、催促句得手工挑出来：它按 skeleton.md 逐句归类，只留删掉会让结果变差的元素，拼完再过 13 条自检。
2. 每条要求是否可执行要自己回头验一遍：它把要求改写成数量、格式、有无或可复现步骤，并按 vague-words.md 的 20 条词表清零模糊词。
3. 改完还得赌模型不会漏问关键信息：它只在会改变目标或交付物的缺口上弹窗，第 1 轮 ≤5 问、第 2 轮 ≤3 问，其余填默认值并标注。

## 用法

- 触发：输入 `/prompt-optimizer` 并附上草稿，或直接说“帮我优化这段提示词”。
- 输入：每轮只带 1 份草稿，质量、长度、语言不限；除触发语外不识别其他参数。
- 输出：1 个四反引号代码块，块外 0 字符；首行是 ≤30 字符的英文标题，其余是从 [Identity] 起的七段。
- 追问：第 1 轮 ≤5 问，第 2 轮 ≤3 问，最多 2 轮；被跳过的问题按推荐值填。
- 边界：只读草稿和工作区，不写文件、不装依赖、不改配置。

改前（1 行草稿）：

> 帮我写个周报，写得专业点

改后（节选，同一份草稿的产出）：

````text
[Goal]
周报在周五 18:00 前发出，含 3 条进展和 1 条风险。
[Hard Constraints]
- MUST: 正文 200±20 字。 Check: 字符数统计。
````


One-click install for codeagent
```powershell
$s = "$env:USERPROFILE\.cac\skills"
Rename-Item "$s\prompt-optimizer" ("prompt-optimizer.bak-" + (Get-Date -Format 'yyyyMMdd-HHmm'))
git clone https://github.com/shiho-qiao/prompt-optimizer.git "$s\prompt-optimizer"
```
The optimized prompt body is written in English, and the output language is locked to the language used to invoke the skill.
