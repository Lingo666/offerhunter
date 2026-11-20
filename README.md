# OfferHunter · 项目走读教练

当一个功能已经跑通，你能从用户的一个动作开始，在代码中找到谁接收输入、谁改变数据、谁决定最终结果吗？把 `project-reading-coach` 装到 Codex 或 Claude Code，然后打开自己感兴趣的项目，就可以和 AI 一步一步读这条链路。

**每轮只学一个功能。** 教练先画一张简图，提出第一问，等你预测。你答完，它才带你看实际文件和关键几行，解释结果，再往下走。通常一轮 5–8 问，最多 10 问。最后换一个此前没讲过的条件，由你独立判断，再留下一张可以接着用的学习卡。

## 一键安装

**把下面这句话发给本机的 Codex 或 Claude Code 即可。** 装进个人目录后，换一个项目也能用。

```text
请按 https://github.com/Lingo666/offerhunter 的安装说明，为你当前所在的工具安装个人技能 project-reading-coach v1.0.0，装好后检查 SKILL.md 并告诉我怎么开始第一问。
```

### 在终端安装

选自己使用的工具，复制对应的一行。命令需要 Git 和带有 `npx` 的 Node.js 22.20 或更高版本。[安装工具说明](https://github.com/vercel-labs/skills)

**Codex**

```sh
npx -y skills@1.9.0 add Lingo666/offerhunter@v1.0.0 --skill project-reading-coach -a codex -g --copy -y
```

**Claude Code**

```sh
npx -y skills@1.9.0 add Lingo666/offerhunter@v1.0.0 --skill project-reading-coach -a claude-code -g --copy -y
```

| 工具 | 安装后可检查的文件 | 在新对话中调用 |
| --- | --- | --- |
| Codex | `~/.agents/skills/project-reading-coach/SKILL.md` | `$project-reading-coach` |
| Claude Code | `~/.claude/skills/project-reading-coach/SKILL.md` | `/project-reading-coach` |

如果电脑缺少 Git 或合适的 Node.js，agent 可以直接下载 [v1.0.0 安装包](https://github.com/Lingo666/offerhunter/releases/download/v1.0.0/project-reading-coach-v1.0.0.zip)，将解压后的整个 `project-reading-coach` 文件夹放到表中对应的位置。`~` 表示用户主目录。[Codex 技能目录](https://developers.openai.com/codex/skills/) · [Claude Code 技能目录](https://code.claude.com/docs/en/skills)

## 第一次怎么用

打开**你想学习的源码目录**，新开一个本地对话，输入上表中的调用名，再加上这句话。

> 带我读当前项目。我会读基本的代码，但第一次接触这个仓库，今天有 25 分钟。请挑一个我能观察到结果的功能，先画从输入到输出的简图，再只问第一题，等我回答。

也可以自己点题。例如，打开一个音乐播放器项目时，可以把上面的「挑一个功能」换成「我想弄清楚打开单曲循环后，点『下一首』会发生什么」。教练会先查找当前项目对应的实现，再决定怎么问。

| 你学到哪了 | 可以直接对教练说 |
| --- | --- |
| 看不懂一个参数 | 用这次输入演示一下这个参数的值怎么变，然后回到这一问。 |
| 觉得自己会了 | 换一个条件让我预测。我先指出代码依据，你再解释。 |
| 今天先到这里 | 把我独立答对的、靠提示答对的和下次要验证的，记在同一张学习卡上。 |
| 换对话继续 | 这是上次的学习卡。我已经打开同一个项目，从卡上未完成的那一问继续。 |

一轮结束后，合上笔记试三件事：画出这条链路，指出一个能验证结果的代码位置，再说出需求变化时你会先看哪里。学习卡会留下你已经能独立做到的部分。[查看学习卡样式](skills/project-reading-coach/references/learning-card.md)
