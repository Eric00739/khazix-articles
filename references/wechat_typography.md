# 卡兹克公众号排版规范（手机端优先 v3）

> 本规范来自 Eric00739/khazix-articles 的排版部分（v2），合并进 khazix-writer 时做了 v3 修订。
> 分工：本文件只管版式，不管文字。文字以四层自检通过的终稿为准，排版过程中不得改写。

## v3 修订记录（合并时的第一性原理裁决）

1. **去掉外层框线结构**：原版是"米色外底(#f5f0e8) + 白色内页"双层结构，手机端两侧各吃掉约20px的框线区，加上内页边距，横向空间损耗严重。改为**单层暖白纸底**，横向空间全部让给文字。
2. **去掉一切四周边框**：金句块、关注卡的1px四周边框全部移除。保留左缘细色条（不占横向宽度、不对称，属停顿信号，不是框）。
3. **装饰总量上限**：分隔线全文≤4条（只在结构板块边界）、金句块≤2个、引用块≤2个、橙色高亮每千字≤2处。超限时删装饰，不删文字。
4. **导航从标题移到分隔线**：流式文章不加小标题。编号节标题仅当正稿已有"1、短语"式分条或用户明确要求时启用。
5. **关注引导卡被固定尾部取代**：写作部分规定的固定尾部（三连+星标+作者+邮箱）本来就承担引导职能，样式化呈现即可，避免同一位置出现两段引导。
6. **衬线字体只留在展示层**：主标题、金句、引用用 Georgia/宋体 纸感；正文用系统默认字体（微信客户端常覆盖 font-family，且宋体长文阅读不如系统字体清晰）。
7. 以下兼容铁律是特定时间的实测结论，微信过滤规则会不定期变化。用户实测反馈与铁律冲突时，以用户反馈为准并更新本文件。
8. **v4 修订（安全与真实性加固）**：固定尾部移除「作者：卡兹克」署名与投稿邮箱，只保留三连/星标/致谢文案；作者、邮箱、公众号名、二维码等身份字段一律按 SKILL.md「身份字段规则」处理。

## 配色方案

| 用途 | 色值 | 说明 |
|------|---------|------|
| 正文文字 | #2c3e50 | 墨蓝，沉稳不刺眼 |
| 金句/高亮 | #e67e22 | 琥珀橙，温暖醒目 |
| 装饰条/线条 | #d4a574 | 浅咖色，低调优雅 |
| 引用块/占位块背景 | #faf8f3 | 淡米色，柔和 |
| 金句块背景 | #fdf5ed | 暖橙白，纯色 |
| 分隔点 | #c9a86c | 古铜金 |
| 页面背景（单层） | #fffef8 | 暖白纸张 |
| 次要文字 | #7f8c8d / #8b7355 / #b0a090 | 导语 / 尾部正文 / 装饰字 |

## 微信粘贴兼容性铁律（每次生成都要遵守）

1. **容器标签用 `<section>`，不用 `<div>`**——微信自己存内容用的就是 section，div 嵌套层级一深，背景色常在粘贴转换时被吞掉。
2. **背景色只写 `background-color:`，不写 `background:` 简写**——长写法更容易被保留。
3. **绝不用 `linear-gradient` 等渐变**——几乎100%会在粘贴时被整条丢弃，留下透明背景。需要渐变质感的地方统一用纯色兜底。
4. **不用 `box-shadow`**——粘贴后必丢，写了也是死代码。
5. `border`、`border-left`、`border-radius`、`padding`、`margin`、`color`、`font-*`、`line-height`、`text-align` 目前实测能稳定保留，正常用。
6. 微信编辑器不支持 flexbox，只能用 inline-block。
7. 所有样式必须内联（style="..."），不能用 class。

## HTML 结构模板（v3，按模块顺序，可选模块已标注）

```html
<!-- 单层容器：无外框、无两侧框线，暖白纸底 -->
<section style="max-width:680px; margin:0 auto; background-color:#fffef8; padding:28px 20px;">

  <!-- 顶部装饰条（横向纯色线，不占横向空间） -->
  <section style="height:3px; background-color:#d4a574; margin:0 0 28px 0;"></section>

  <!-- 分类标签（可选，填文章原型名或省略） -->
  <section style="text-align:center; margin:0 0 14px;">
    <span style="display:inline-block; font-size:11px; color:#d4a574; letter-spacing:4px;">【分类】</span>
  </section>

  <!-- 主标题（交付时提醒：公众号编辑器另有标题栏，本模块可按需删除避免标题重复） -->
  <section style="font-size:26px; line-height:1.5; color:#2c3e50; font-weight:600; text-align:center; margin:0 0 16px; letter-spacing:1px; font-family:Georgia,'Songti SC',serif;">
    【文章标题】
  </section>

  <!-- 导语（可选，从文中金句提取，禁止新写；没有合适的就删掉整个模块） -->
  <section style="font-size:14px; color:#7f8c8d; text-align:center; margin:0 0 32px; line-height:1.8;">
    【从文中提取的一句话】
  </section>

  <!-- 正文段落（橙色高亮：每千字≤2处） -->
  <p style="font-size:16px; line-height:2; color:#2c3e50; margin:20px 0; text-align:justify;">
    【正文内容】<span style="color:#e67e22; font-weight:600;">【关键词】</span>
  </p>

  <!-- [可选] 编号节标题：仅当正稿已有"1、短语"式分条或用户明确要求时使用，节标题文字必须是正稿既有短语 -->
  <section style="margin:40px 0 20px; border-left:3px solid #e67e22; padding-left:14px;">
    <section style="font-size:12px; color:#e67e22; letter-spacing:3px; margin-bottom:4px; font-weight:600;">01</section>
    <section style="font-size:19px; color:#2c3e50; font-weight:600; line-height:1.4; font-family:Georgia,'Songti SC',serif;">【正稿既有短语】</section>
  </section>

  <!-- 分隔线（全文≤4条，只在结构板块边界） -->
  <section style="text-align:center; margin:36px 0;">
    <section style="display:inline-block; width:48px; height:1px; background-color:#d4a574; margin:0 8px;"></section>
    <span style="display:inline-block; width:5px; height:5px; background-color:#c9a86c; border-radius:50%; vertical-align:middle;"></span>
    <section style="display:inline-block; width:48px; height:1px; background-color:#d4a574; margin:0 8px;"></section>
  </section>

  <!-- 引用块（左橙条+淡米底，无四周边框；全文≤2个） -->
  <section style="margin:26px 0; padding:20px 22px; background-color:#faf8f3; border-left:4px solid #e67e22;">
    <p style="font-size:16px; color:#5d4e37; line-height:2; margin:0; font-family:Georgia,'Songti SC',serif;">
      【引用内容】
    </p>
  </section>

  <!-- 金句块（纯色暖橙底，无边框；全文≤2个） -->
  <section style="margin:30px 0; padding:22px 24px; background-color:#fdf5ed; border-radius:4px; text-align:center;">
    <section style="font-size:30px; color:#e67e22; opacity:0.3; line-height:1; margin-bottom:6px;">"</section>
    <p style="font-size:17px; color:#e67e22; line-height:1.9; margin:0; font-weight:600; font-family:Georgia,'Songti SC',serif;">【文中金句】</p>
  </section>

  <!-- 图片占位块（由正稿「图片」标记转换而来；发布时在公众号编辑器手动插图，不编造图片路径） -->
  <section style="margin:24px 0; padding:28px 16px; background-color:#faf8f3; border-radius:4px; text-align:center;">
    <section style="font-size:13px; color:#b0a090; letter-spacing:2px;">[ 此处插图 ]</section>
  </section>

  <!-- 固定尾部（三连/星标/致谢文案照抄，不得改字；不含作者署名、邮箱等身份字段） -->
  <section style="margin:48px 0 0; padding-top:28px; border-top:1px solid #e8e0d5; text-align:center;">
    <p style="font-size:14px; color:#8b7355; line-height:2; margin:0;">
      以上，既然看到这里了，如果觉得不错，随手点个赞、在看、转发三连吧，如果想第一时间收到推送，也可以给我个星标⭐～<br/>
      谢谢你看我的文章，我们，下次再见。
    </p>
  </section>

  <!-- 结束装饰 -->
  <section style="text-align:center; margin:32px 0 24px;">
    <section style="font-size:13px; color:#b0a090; letter-spacing:8px;">— 完 —</section>
  </section>

  <!-- 底部装饰条 -->
  <section style="height:3px; background-color:#d4a574;"></section>

  <!-- [可选] 二维码卡：仅当用户提供图片时使用，无边框；没有就不编造路径，整个模块删除 -->
  <section style="margin-top:24px; padding:20px; background-color:#faf8f3; border-radius:6px; text-align:center;">
    <img src="【用户提供的二维码图片路径】" alt="关注公众号" style="width:150px; height:auto; display:block; margin:0 auto;" />
  </section>

</section>
```

## 模块使用规则

1. 单层容器 `max-width:680px` 居中，移动端自动占满屏宽，两侧无框线、无外底。
2. 分类标签可选，填文章原型名或省略。
3. 导语从文中金句提取；没有合适的就删掉整个模块，禁止新写。
4. 主标题模块默认保留，交付时提醒标题栏重复问题。
5. 编号节标题默认不用，启用条件见 SKILL.md 排版铁律2；节标题文字必须是正稿既有短语。
6. 分隔线只在结构板块边界（开头/铺垫/核心板块之间/升华/收尾）插，全文≤4条。
7. 引用块用于文中引用他人的话；金句块留给全文最重的1-2句。
8. 图片占位块由正稿「图片」标记转换而来。
9. 固定尾部文字逐字照抄模板，不得改字；模板不含作者署名、投稿邮箱等身份字段。用户明确要求署名时使用其明确提供的字段，不自动署名卡兹克。
10. 正文不加粗（高亮 span 的 font-weight 除外）、不使用任何小标题结构切分流式文章。

## 交付说明

1. 保存为工作目录下 `YYYYMMDD-标题.html`。
2. 使用方式（普通公众号账号没有源码粘贴入口）：浏览器打开该文件 → **全选（Ctrl/Cmd+A）→ 复制（Ctrl/Cmd+C）** → 切到公众号编辑器正文区域**直接粘贴（Ctrl/Cmd+V）**，不要用"粘贴为纯文本"。
3. 浏览器预览 ≠ 公众号最终效果，微信的过滤更狠。若粘贴后背景色/装饰条仍丢失，把 HTML 导入 **135编辑器** 或 **秀米**（有导入HTML/源代码入口），用它们自带的"一键复制到公众号"，兼容性更可靠。
4. 交付时必须附上述粘贴指引，并提醒公众号编辑器另有标题栏、正文大标题模块可按需删除。
