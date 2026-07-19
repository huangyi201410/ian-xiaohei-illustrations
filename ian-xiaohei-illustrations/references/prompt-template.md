# 生图提示词模板

每张图单独生成。根据正文内容替换变量，不要把多张图拼在一起。

## 生成前的角色参考步骤

1. 打开 `assets/aiko-character-sheet.png`。
2. 将它作为生成调用的唯一 `strict character reference` 附带；若工具只支持对话图片，先查看该文件再引用它。
3. 在提示词中说明：只参考 Aiko 的角色外形，忽略三视图版式、题字、姿势和背景。

```text
Generate one standalone 16:9 horizontal Chinese article illustration.

Character reference image:
Attach `assets/aiko-character-sheet.png` as the one strict identity reference. Preserve only Aiko’s character design from that reference; do not reproduce its three-view layout, handwritten “Aiko” title, pose sheet, or labels.

Visual DNA:
Pure white background. Minimalist black hand-drawn line art with slightly wobbly pencil/crayon texture. Lots of empty white space. Sparse red/orange/blue handwritten Chinese annotations. Clean absurd product-sketch feeling. No gradients, no shadows, no paper texture, no complex background, no commercial vector style, no PPT infographic look, no realistic UI.

Recurring IP character required — Aiko, “蓝白机器人”:
Use the cartoon/chibi Aiko from the character reference: large rounded head, short small body, big black round eyes, long straight near-black hair, white short-sleeve T-shirt with a blue {heart} mark and robot sleeve patch, sky-blue drawstring shorts/skort, tiny robot waist charm, white socks with blue hearts, and white-blue sneakers. Do not invent an alternative hairstyle, outfit, or art style. Aiko is a small active operator, not the picture’s protagonist.

Theme:
{正文配图主题}

Structure type:
{结构类型：Workflow / 系统局部 / 前后对比 / 角色状态 / 概念隐喻 / 方法分层 / 地图路线 / 小漫画分镜}

Core idea:
{这张图要表达的核心意思}

Main visual metaphor:
{先写主物件、结构或状态变化；它必须是画面第一视觉中心}

Aiko’s key action and scale:
{Aiko 完成一个推动因果的动作，例如：修补、递交、连接、记录、开门、分拣。Aiko 高度约为她正在操作的局部关键物件的 0.8–1.2 倍}

Composition:
{主物件占画面约 45%-60%；Aiko 放在边缘、路径旁或物件内部，约占画面 15%-22%，并与局部关键物件同尺度；信息如何流动}

Suggested elements:
{元素1} / {元素2} / {元素3} / {元素4}

Chinese handwritten labels:
{标注词1} / {标注词2} / {标注词3} / {可选标注词4}

Color use:
Black for main line art and structure. Keep Aiko's signature clothing and robot details in light sky blue. Orange for main flow/path/arrows. Red only for key warnings/problems/results. Blue only for Aiko's signature details and secondary notes or feedback/system state.

Constraints:
One image explains only one core structure. Preserve at least 35% blank white space. Aiko must be visible and perform the key causal action. Size her to match the local key object she operates: her height should be about 0.8–1.2x that object’s height, usually 15%-22% of the canvas and never more than 25%. Make the metaphor or system structure the largest and first-read element. No Aiko close-up, portrait, centered full-body pose, character-poster composition, title in the top-left corner, or structure-type label. Use at most 4 short handwritten Chinese labels. Do not make a formal diagram, course slide, or dense explainer. Invent a fresh visual metaphor for this article. Do not use a monster mascot, school-uniform styling, hooded outerwear, cyberpunk neon, dark backgrounds, 3D rendering, or unreadable pseudo-text.
```

## 图像编辑提示

去掉左上角标题：

```text
Edit the provided image. Remove only the handwritten title "{要删除的文字}" and its underline from the top-left corner. Fill that area with the same clean white background, matching the surrounding blank paper. Preserve everything else exactly: the small Aiko character, her dark long hair, white T-shirt, sky-blue skort, robot details, the main metaphor, labels, paths, line style, composition, aspect ratio, and image quality. Do not add any new text or objects.
```

缩小 Aiko、强化观点：

```text
Regenerate this illustration with the same core idea and main metaphor. Keep Aiko consistent with the attached Aiko character sheet. Size Aiko to match the local key object she operates—about 0.8–1.2x its height and usually 15%-22% of the canvas—while keeping the main metaphor as the first thing a reader sees. Do not use an Aiko close-up, character-poster composition, or centered full-body pose.
```
