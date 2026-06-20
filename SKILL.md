---
name: khazix-wechat-publisher
description: |
  一键将文章改写为卡兹克风格并排版成微信公众号格式。当用户说"排版这篇文章"、"发到公众号"、"改写并排版"、"用卡兹克风格写文章"、"帮我发公众号"、"处理这篇文章"时触发。适用于：1)用户有一篇原始文章/素材想改成公众号格式；2)用户只有选题和要点，需要从头写并排版；3)用户想将已有内容改写得更生动并直接可用。不适用于短内容（小红书、朋友圈）或纯标题生成。
---

# 卡兹克风格公众号发布器

这是一个组合 workflow：先用卡兹克的写作风格改写文章，然后自动排版为微信公众号可用的 HTML 格式。

## 工作流程

```
用户输入（文章/素材/选题）
    ↓
Step 1: 卡兹克风格改写
    - 分析选题质量（HKR 质检）
    - 确定文章原型（调查/体验/解读/工具/方法论）
    - 按卡兹克风格重写内容
    - 四层自检
    ↓
Step 2: 微信排版
    - 套用暖米色纸张风格
    - 添加小节编号、分隔线、引用块
    - 优化阅读节奏
    ↓
输出：可直接复制到公众号编辑器的 HTML
```

## 执行步骤

### 第一步：理解素材与选题判断

**先吃透用户输入，判断内容类型：**

| 输入类型 | 处理方式 |
|---------|---------|
| 完整文章 | 保留核心信息，按卡兹克风格重写结构和表达 |
| 零散要点/大纲 | 补充过渡和论述，扩展成完整文章 |
| 产品 brief/新闻链接 | 提取关键信息，加入个人观点和体验 |
| 纯选题（只有主题） | 主动询问：想讲哪几个点？有什么个人经历？想表达什么情绪？ |

**选题质检（HKR）：**
- **H (Happy)** — 足够有趣、有悬念？标题能让人好奇想点开吗？
- **K (Knowledge)** — 有信息量？看完能学到新东西吗？
- **R (Resonance)** — 能戳中情绪？让人"对对对我也这么想"？

S级选题三项兼备。如果明显只满足零项或一项，主动跟用户沟通调整方向。

### 第二步：确定文章原型

卡兹克的文章可归为五种原型，确定后按对应重心改写：

| 原型 | 判断标准 | 写法重心 |
|------|---------|---------|
| **调查实验型** | 你亲自做了一件具体的事 | 过程叙事 + 发现的层层递进 |
| **产品体验型** | 拿到产品实际使用 | 场景演示 + 真实感受 |
| **现象解读型** | 观察到一个现象并深入分析 | 观察→好奇→研究→哲学升维 |
| **工具分享型** | 分享一个实用工具/Prompt | 个人故事铺垫→工具展示→效果惊艳 |
| **方法论分享型** | 系统分享长期积累的经验 | 可执行建议 + 坦诚说学习成本 |

### 第三步：卡兹克风格改写

**核心价值观（贯穿全文）：**
1. **永远对世界保持好奇** — 少问"我会被取代吗"，多问"我能用它玩点什么"
2. **讲人话，像个活人** — 大胆用"我觉得"、"我认为"，拥抱不完美
3. **真诚是唯一的捷径** — 有缺点直接说，不懂就承认
4. **有所为有所不为** — 不追逐违背价值观的流量

**风格特征：**
- **开场**：个人化切入，讲一个具体的小故事或观察
- **人称**：多用"我"、"你"，像朋友聊天
- **节奏**：长短句交替，关键处换行留白
- **金句**：每个小节收尾或转折处有一句能发朋友圈的话
- **结尾**：回扣开头，给一个"原来如此"的升华感

**改写时的分工：**
- ✅ AI 做：找类比找证据、按确定角度扩写、补充学科背景、梳理逻辑结构
- ❌ AI 不做：编造第一手经历、决定核心创意角度、代替真实情绪表达

### 第四步：四层自检

改写完成后，按这四层检查文章质量：

**第一层：信息真实**
- [ ] 所有事实可溯源，没有编造数据
- [ ] 产品功能描述准确，不夸大
- [ ] 引用的案例真实存在

**第二层：逻辑自洽**
- [ ] 观点之间有因果关系，不是堆砌
- [ ] 每个小节都支撑核心论点
- [ ] 没有自相矛盾的地方

**第三层：情绪真诚**
- [ ] 有真实的"我"在场，避免写成客观播报
- [ ] 情绪转折自然，不强行煽情
- [ ] 读者能感知到"这是个活人写的"

**第四层：阅读流畅**
- [ ] 开头 200 字能抓住人
- [ ] 段落长度适中，手机阅读不累
- [ ] 每个小节后有个记忆点（金句/洞察/反常识）

### 第五步：微信排版

**整体风格：**
- 暖米色纸张背景 (#f5f0e8 外底 + #fffef8 内页)
- 墨蓝色 (#2c3e50) 用于正文和主标题，营造沉稳阅读感
- 琥珀橙色 (#e67e22) 用于金句、高亮、强调——温暖有温度
- 衬线字体 (Georgia, "Songti SC", serif) 营造纸质感
- 宽度 680px，适配手机阅读

**配色方案：**
| 用途 | 颜色代码 | 说明 |
|------|---------|------|
| 正文文字 | #2c3e50 | 墨蓝，沉稳不刺眼 |
| 金句/高亮 | #e67e22 | 琥珀橙，温暖醒目 |
| 装饰线条 | #d4a574 | 浅咖色，低调优雅 |
| 引用背景 | #faf8f3 | 淡米色，柔和 |
| 分隔点 | #c9a86c | 古铜金 |
| 背景 | #fffef8 | 暖白纸张 |

**HTML 结构模板（必须按此顺序）：**

```html
<!-- 外部容器 -->
<div style="max-width:680px; margin:0 auto; background:#f5f0e8; padding:20px;">
  
  <!-- 内部纸张 -->
  <div style="background:#fffef8; padding:40px 32px; box-shadow:0 2px 8px rgba(0,0,0,0.06);">
    
    <!-- 顶部装饰条（墨蓝+古铜渐变） -->
    <div style="height:3px; background:linear-gradient(to right, #2c3e50, #d4a574, #2c3e50); margin:0 0 32px 0;"></div>
    
    <!-- 分类标签 -->
    <div style="text-align:center; margin:0 0 16px;">
      <span style="display:inline-block; font-size:11px; color:#d4a574; letter-spacing:4px; text-transform:uppercase;">【分类】</span>
    </div>
    
    <!-- 主标题 -->
    <div style="font-size:28px; line-height:1.5; color:#2c3e50; font-weight:600; text-align:center; margin:0 0 20px; font-family:Georgia,'Songti SC',serif; letter-spacing:1px;">
      【文章标题】
    </div>
    
    <!-- 副标题/导语 -->
    <div style="font-size:14px; color:#7f8c8d; text-align:center; margin:0 0 40px; font-style:italic; line-height:1.8; font-family:Georgia,serif;">
      【导语/一句话总结】
    </div>
    
    <!-- 正文段落 -->
    <p style="font-size:16px; line-height:2; color:#2c3e50; margin:20px 0; text-align:justify; font-family:Georgia,'Songti SC',serif;">
      【正文内容】<span style="color:#e67e22; font-weight:600;">【橙色高亮关键词】</span>
    </p>
    
    <!-- 小节标题（带编号） -->
    <div style="margin:48px 0 24px; border-left:3px solid #e67e22; padding-left:16px;">
      <div style="font-size:12px; color:#e67e22; letter-spacing:3px; margin-bottom:6px; font-weight:600;">01</div>
      <div style="font-size:20px; color:#2c3e50; font-weight:600; line-height:1.4; font-family:Georgia,'Songti SC',serif;">
        【小节标题】
      </div>
    </div>
    
    <!-- 分隔线（古铜色双细线） -->
    <div style="text-align:center; margin:40px 0;">
      <div style="display:inline-block; width:60px; height:1px; background:#d4a574; margin:0 8px;"></div>
      <span style="display:inline-block; width:6px; height:6px; background:#c9a86c; border-radius:50%; vertical-align:middle;"></span>
      <div style="display:inline-block; width:60px; height:1px; background:#d4a574; margin:0 8px;"></div>
    </div>
    
    <!-- 引用块（淡米色背景+橙色左边框） -->
    <div style="margin:28px 0; padding:24px 28px; background:#faf8f3; border-left:4px solid #e67e22;">
      <p style="font-size:16px; color:#5d4e37; line-height:2; margin:0; font-style:italic; font-family:Georgia,'Songti SC',serif;">
        【引用内容】
      </p>
    </div>
    
    <!-- 金句块（橙色主题） -->
    <div style="margin:32px 0; padding:24px 28px; background:linear-gradient(135deg, #fef9f3 0%, #fdf5ed 100%); border:1px solid #f0d9c0; border-radius:4px; text-align:center;">
      <div style="font-size:32px; color:#e67e22; opacity:0.3; line-height:1; margin-bottom:8px;">"</div>
      <p style="font-size:17px; color:#e67e22; line-height:1.9; margin:0; font-weight:600; font-family:Georgia,'Songti SC',serif;">
        【金句内容】
      </p>
    </div>
    
    <!-- 结尾 -->
    <div style="text-align:center; margin:56px 0 32px; padding-top:32px; border-top:1px solid #e8e0d5;">
      <div style="font-size:13px; color:#b0a090; letter-spacing:8px; font-family:Georgia,serif;">— 完 —</div>
    </div>
    
    <!-- 底部装饰条 -->
    <div style="height:3px; background:linear-gradient(to right, #2c3e50, #d4a574, #2c3e50);"></div>
    
    <!-- 关注引导（淡米色卡片） -->
    <div style="margin-top:28px; padding:24px; background:#faf8f3; border-radius:6px; text-align:center; border:1px solid #f0e6d8;">
      <p style="font-size:14px; color:#8b7355; line-height:2; margin:0 0 16px; font-family:Georgia,'Songti SC',serif;">
        既然看到这里，想必文字已传达到位。<br/>
        <span style="color:#e67e22;">若喜欢这种分享，不妨双击下面的二维码关注</span>，<br/>让这种连接自然延续。
      </p>
      <img src="/Users/erichuang/Desktop/1d281c3b-e620-466a-86a1-3150c05c6929.png" alt="关注公众号" style="width:160px; height:auto; display:block; margin:0 auto;" />
    </div>
    
  </div>
</div>
```

**排版要点：**
1. 所有内容包裹在 680px 外容器 + 内页纸张的双层结构中
2. 每个小节都要有编号（01、02、03...），带橙色左边框
3. 小节之间用古铜色双细线+圆点分隔
4. 关键概念用琥珀橙色 (#e67e22) 高亮
5. 金句块用橙色渐变背景+引号装饰
6. 引用块用淡米色背景+橙色左边框
7. 结尾必须是"— 完 —"加底部装饰条
8. 关注引导用淡米色卡片，关键词用橙色强调
9. 所有样式必须内联（style="..."），不能用 class
10. 微信编辑器不支持 flexbox，只能用 inline-block

## 输出格式

最终输出一个完整的 HTML 文件，包含：
1. 可直接复制到公众号编辑器源码模式的 HTML
2. 一个预览说明，告诉用户如何使用

**保存位置：**`~/wechat-articles/drafts/YYYY-MM/YYYYMMDD-标题.html`

## 使用示例

**用户输入：**
> "帮我处理这篇文章：[粘贴原文]"

**执行：**
1. 分析原文属于哪种原型
2. 按卡兹克风格重写（保留核心信息，改变表达方式）
3. 套用微信排版模板生成 HTML
4. 保存到 drafts 目录并告知路径

**用户输入：**
> "我想写篇关于 AI 工具的文章，主题是效率提升"

**执行：**
1. 询问：具体想讲哪几个工具？你自己用过吗？有什么印象深刻的体验？
2. 根据回答确定原型和角度
3. 按流程改写并排版
4. 输出成品

## 注意事项

- 如果用户输入是纯选题（没有具体素材），必须先询问细节，不要直接编
- 改写时必须保留原文的核心事实，不要编造数据和案例
- 排版时所有样式必须内联（style="..."），不能用 class
- 微信编辑器不支持 flexbox，只能用 inline-block
- 最终 HTML 文件要保存到用户的 wechat-articles 工作目录
