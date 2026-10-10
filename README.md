# DSH Antigravity Plus (增强版) 🚀

> **专为 DeepSeek Harness（DSH）打造的 Google Antigravity 插件增强版**  
> 彻底解除限制，让通过 Antigravity 接入的 Gemini 也能像 DeepSeek 一样主动干活、深度思考、积极调用工具！

---

## ❓ 为什么需要这个增强版？

如果你在 DSH 里用过原版的 `dsh-antigravity` 插件，你很可能遇到过这些情况：

1. **Gemini 像个"陪聊"，很不爱动手**：遇到排查或编写任务，它更倾向于直接用嘴回答，而不是主动去读文件、查代码、跑终端命令。
2. **思考时间很短，甚至几乎不思考**：明明开了思考模型，它却经常只思考几秒甚至敷衍两句就结束。
3. **切模型报错**：切换模型或打开历史会话时，经常莫名其妙弹 `no adapter registered for provider "antigravity"`。

**这不是 Gemini 模型本身不行，而是原版插件的配置在"拖后腿"！**  
原版插件在后台悄悄加了一句「你只是个结对编程陪聊，回答要简短，绝对不要输出检查清单」，而且默认只给它分了极少的思考额度。

---

## 🛠️ 这个增强版做了什么？

我们把原版插件的"封印"全部解除了：

1. **从"陪聊"变回"全自动干活 Agent"**
   - 彻底移除了结对陪聊设定与禁止清单输出的禁令；
   - 让 DSH 自带的专业 Agent 指令排在最前面生效！现在它知道自己是来干活的，会主动去查文件、跑命令。
2. **思考预算彻底放宽**
   - 默认思考档位直接上调为 `High`；
   - Gemini 3.8 / 3.7 直接给动态无上限思考额度；Gemini 3.1 Pro 思考预算放宽到 32,768（原版只有 10,001）！
3. **原生支持 Gemini 3.8 全系**
   - 完美内置 `gemini-3.8-flash` 与 `gemini-3.8-flash-tiered`，路由、配额进度条全部齐备。
4. **无缝双别名（告别报错）**
   - 原生同时支持 `agy` 和 `antigravity` 两个渠道名称，不管你怎么切会话，再也不会出现 `no adapter` 报错。
5. **完全兼容现有配置（免重新登录）**
   - 直接复用你现有的 Google 账号与代理设置，换上后连登录都不用重新登！

---

## ⚡ 怎么安装？（超简单两步）

### 方式一：终端一键安装（推荐）

打开 PowerShell，直接执行：

```powershell
dsh plugin add https://github.com/BigFier/dsh-antigravity-plus/releases/download/v1.0.0/dsh-antigravity-plus-1.0.0.tgz
```

### 方式二：手动安装

1. 前往 [Releases](https://github.com/BigFier/dsh-antigravity-plus/releases) 下载最新的 `dsh-antigravity-plus-1.0.0.tgz`；
2. 在你的 DSH desktop profile 目录下运行：
```powershell
pnpm add ./dsh-antigravity-plus-1.0.0.tgz --save-exact
```
3. 在 `package.json` 的 `dsh.profile.bundles` 中将 `dsh-antigravity` 改为 `dsh-antigravity-plus` 即可。

安装后完全退出并重启 DeepSeek Harness 即可生效！

---

## 📜 开源协议

MIT License
