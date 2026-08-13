# 工序 4 — 高级调色 (Color)

**目标**：给底图建立统一、有情绪的色调，服务明信片整体调性，与所选模板强绑定。

**输入**：retouch 底图 + 选定模板（读取 `templates/<name>.md` 的配色与情绪定义）。

**步骤**：

1. 读取模板规范中的「配色」与「情绪」，明确方向：
   - `classic`：明亮均衡、轻微暖调、干净
   - `minimal`：低饱和、留白感、柔和
   - `vintage`：暖黄 / 褪色、颗粒感、怀旧
   - `editorial`：高对比、冷调或电影感、高级
2. 用 ImageGen 图生图施加调色：统一白平衡、建立主色调、控制对比与饱和度。
3. 保护主体自然度：人像肤色不偏绿、食物不灰、天空不脏。
4. 输出调色后图像，进入 `postcard.md`。

**ImageGen 图生图提示参考**：

- 中文：「电影感调色，<模板情绪>，统一白平衡，胶片般色调，专业级」
- 英文：`cinematic color grade, <template mood>, consistent white balance, film-like tones, professional, <template-specific keywords>`

**质量门禁**：

- 色调统一，无脏色、无色块断层。
- 情绪明显符合所选模板。
- 主体材质 / 肤色自然。
- 不达标 → 重做本工序，回 retouch 只在前序有问题时才需要。
