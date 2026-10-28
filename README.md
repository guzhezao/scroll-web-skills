# Scroll Web Skills

**人人都能学会的炫酷网页制作教程**

顾着造的两份可复用提示词规范：**先生成产品动画，再把动画做成随滚动展开的完整网页。**

来自跑鞋与冰淇淋网站的制作经验，整理了主体连续性、拆解分镜、品牌加载、滚动暂停与回看、后续介绍和款式选择。适合想做产品展示、独立站或交互实验的人。

## 先选一种使用方式

| 你想怎么用 | 从哪里开始 |
|---|---|
| 直接复制提示词，不安装任何Skill | [动画模板](product-motion-prompts/references/prompt-template.md) → [网页模板](scroll-product-website/references/prompt-template.md) |
| 先看具体例子 | [跑鞋与冰淇淋动画](product-motion-prompts/references/examples.md) · [不同产品的网页表达](scroll-product-website/references/examples.md) |
| 让Agent按规范帮你做 | [产品动画Skill](product-motion-prompts/SKILL.md) · [滚动网页Skill](scroll-product-website/SKILL.md) |

## 两步怎么接

### 1. 生成动画

准备一张清楚的产品参考图，把产品外观、可动部件、主要动作填入[动画模板](product-motion-prompts/references/prompt-template.md)，再交给你正在使用的视频生成工具。MiniMax Design或其他支持相应能力的工具都可以；本仓库不绑定具体模型，也不提供模型调用接口。

优先获得一段连续、主体稳定、能停住看清的产品运动。生成结果需要检查，短片是否足够取决于内容；有跳切、部件增生或融化就针对问题修正，不能靠网页代码弥补所有画面缺陷。

### 2. 做成网页

把真实视频、海报、产品介绍和款式素材交给编码Agent，使用[网页模板](scroll-product-website/references/prompt-template.md)。其中约定加载入场、滚动推进/暂停/反向、连续章节、后续介绍、选择区与设备适配。

先本地运行，按[验收清单](scroll-product-website/references/acceptance.md)实际下滚、停住和上滚。完成的不只是一个视频播放器，也要有可阅读的产品内容与有效操作。

## 为什么做成Skill

提示词是交给模型执行的一次需求；Skill还规定输入怎么检查、怎样拆分任务、如何交接素材和怎样判断完成。这里两种形式一起提供：你可以复制模板，也可以安装后让Agent按这些规则整理具体需求。

它不是视频生成器、网站源码模板或“一句话必成”的承诺。现有示例不包含视频素材、录音、第三方参考原片和字体；文件名与规格示例不能当成已生成结果。

## 安装到支持Skill的工具

两个目录各自完整，可单独复制到工具的技能目录。保持整个目录结构，不只复制SKILL.md。目录已存在时先查看现有内容，不覆盖自己的版本。

以Codex本地技能目录为例（macOS / Linux）：

~~~bash
git clone https://github.com/guzhezao/scroll-web-skills.git
mkdir -p ~/.codex/skills
cp -R -n scroll-web-skills/product-motion-prompts ~/.codex/skills/
cp -R -n scroll-web-skills/scroll-product-website ~/.codex/skills/
~~~

其他Agent使用其对应的Skills目录；未识别技能时按该工具的加载方式刷新会话。没有Skill功能也能直接复制上面的提示词。

调用示例：

~~~text
使用 $product-motion-prompts。根据这张跑鞋图，为滚动网站写连续拆解动画提示词；先写提示词，不生成视频。
~~~

~~~text
使用 $scroll-product-website。已有产品视频和三种配色图，请在当前项目做一个带品牌加载、连续介绍和配色选择的网站；先本地运行，不部署。
~~~

## 目录

~~~text
product-motion-prompts/   动画提示词、示例、素材交接
scroll-product-website/  网页提示词、案例表达、交互验收
README.md                使用入口
LICENSE                  MIT
~~~

规范整理自实际制作与返修过程；本次整理已检查技能格式、示例与文件引用，不代表使用任意模型都会得到相同结果，也不把示例记为新生成的成片。

**不只想，顾着造。**
