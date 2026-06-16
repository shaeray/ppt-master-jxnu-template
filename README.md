# 江西师范大学 PPT Master Deck 模板

这是一个用于 [hugohe3/ppt-master](https://github.com/hugohe3/ppt-master) 的非官方 `deck` 模板。

你有两种使用方式：

| 方式 | 适合谁 | 你需要做什么 |
|---|---|---|
| 只下载本仓库里的 `江西师范大学/` deck 模板 | 已经安装了原版 `ppt-master` 的用户 | 把 `江西师范大学/` 文件夹复制到原版 `ppt-master/templates/decks/` |
| 下载 Release 里的完整压缩包 | 想直接使用我魔改后的完整 `ppt-master` skill 的用户 | 解压完整 `ppt-master/`，安装依赖，然后放到 Codex skills 目录 |

## 方式一：只安装这个 Deck 模板

仓库里真正需要放进原版 `ppt-master` 的内容只有这个文件夹：

```text
江西师范大学/
```

请不要把整个仓库目录放进 `ppt-master`，只需要把 `江西师范大学` 文件夹移动或复制到原版 `ppt-master` 的 deck 模板目录。

### 1. 下载本仓库

使用 GitHub：

```bash
git clone https://github.com/shaeray/ppt-master-jxnu-template.git
```

或者使用 Gitee：

```bash
git clone https://gitee.com/shaeray/ppt-master-jxnu-template.git
```

也可以直接在网页上点击 `Code -> Download ZIP`，下载后解压。

### 2. 复制模板文件夹

把 `江西师范大学` 文件夹复制到原版 `ppt-master` 的 deck 模板目录：

```bash
cp -R ppt-master-jxnu-template/江西师范大学 /path/to/ppt-master/templates/decks/
```

如果你的 `ppt-master` 是作为 Codex skill 安装的，常见路径是：

```bash
cp -R ppt-master-jxnu-template/江西师范大学 ~/.codex/skills/ppt-master/templates/decks/
```

最终位置应该是：

```text
/path/to/ppt-master/templates/decks/江西师范大学/design_spec.md
```

而不是：

```text
/path/to/ppt-master/templates/decks/ppt-master-jxnu-template/江西师范大学/design_spec.md
```

### 3. 注册模板

进入原版 `ppt-master` 根目录后运行：

```bash
cd /path/to/ppt-master
python3 scripts/register_template.py 江西师范大学 --kind deck
```

如果你使用的是 Codex skill 路径，可以运行：

```bash
cd ~/.codex/skills/ppt-master
python3 scripts/register_template.py 江西师范大学 --kind deck
```

注册后，`templates/decks/decks_index.json` 会出现 `江西师范大学`，方便查询模板列表。

### 4. 使用模板

原版 `ppt-master` 默认通过显式模板路径触发 deck 模板。推荐提示词：

```text
请使用 ppt-master，根据以下内容制作 PPT，并使用模板路径 templates/decks/江西师范大学/。
```

如果你的 `ppt-master` 已经修改过 Step 3，支持注册 deck 名称精确匹配，也可以写：

```text
请使用 ppt-master，套用「江西师范大学」deck 模板，根据以下内容生成 PPT。
```

## 方式二：使用 Release 完整压缩包

如果你下载的是 Release 里的完整魔改版压缩包，例如：

```text
ppt-master-jxnu-edition-v0.1.0.zip
```

它不是单独的 deck 模板，而是一个完整的 `ppt-master` skill 目录，里面已经包含江西师范大学模板、更新后的 deck 索引、README、LICENSE 和 NOTICE。

### 1. 解压

```bash
unzip ppt-master-jxnu-edition-v0.1.0.zip
```

解压后应该得到：

```text
ppt-master/
```

### 2. 安装 Python 依赖

进入解压后的目录，安装依赖：

```bash
cd ppt-master
python3 -m pip install -r requirements.txt
```

如果你的系统没有 `python3` 命令，可以改用：

```bash
python -m pip install -r requirements.txt
```

### 3. 安装到 Codex skills 目录

如果你已经安装过原版 `ppt-master`，建议先备份：

```bash
mkdir -p ~/.codex/skills
mv ~/.codex/skills/ppt-master ~/.codex/skills/ppt-master.backup-$(date +%Y%m%d-%H%M%S)
```

然后回到解压目录的上一级，把完整 `ppt-master/` 放进 Codex skills 目录：

```bash
cd ..
cp -R ppt-master ~/.codex/skills/
```

最终路径应该是：

```text
~/.codex/skills/ppt-master/SKILL.md
```

而不是：

```text
~/.codex/skills/ppt-master-jxnu-edition-v0.1.0/ppt-master/SKILL.md
```

### 4. 使用完整魔改版

安装完成后，可以直接在 Codex 中使用 `ppt-master`：

```text
请使用 ppt-master，根据以下内容制作 PPT，并使用模板路径 templates/decks/江西师范大学/。
```

如果你的魔改版支持注册 deck 名称精确匹配，也可以写：

```text
请使用 ppt-master，套用「江西师范大学」deck 模板，根据以下内容生成 PPT。
```

## 仓库目录结构

```text
ppt-master-jxnu-template/
├── README.md
└── 江西师范大学/
    ├── design_spec.md
    ├── 01_cover.svg
    ├── 02_toc.svg
    ├── 02_chapter.svg
    ├── 03_content.svg
    ├── 03a_content_two_col.svg
    ├── 03b_content_image_text.svg
    ├── 03c_content_chart.svg
    ├── 03d_content_timeline.svg
    ├── 04_ending.svg
    ├── brand_wordmark.png
    ├── motto.png
    ├── motto_white.png
    ├── seal_white.png
    ├── cover_bg.jpeg
    ├── cover_bg_aligned.jpeg
    ├── chapter_bg.jpeg
    ├── toc_photo.jpeg
    ├── maple_motif.png
    └── assets/
```

## 模板说明

这个模板适用于：

- 毕业答辩
- 开题报告
- 中期汇报
- 科研汇报
- 课程教学
- 学术交流

模板风格为正式、学术、清爽。它包含封面、目录、章节页、多种正文页和结束页，并带有江西师范大学校名、校训、校徽和校园影像等视觉资产。

## 原版预览兼容

原版 `ppt-master` 的网页实时预览服务通常只稳定映射项目级 `images/` 与 `assets/`，不会自动映射项目里的 `templates/` 目录。

因此本模板的 `design_spec.md` 已经说明：最终生成到 `svg_output/` 的页面不要引用 `templates/` 或模板 SVG 同目录图片，而应先把模板图片部署到项目 `images/` 目录，并使用类似下面的路径：

```xml
<image href="../images/tmpl_brand_wordmark.png" ... />
<image href="../images/tmpl_cover_bg_aligned.jpeg" ... />
<image href="../images/tmpl_motto.png" ... />
```

这样可以让原版 live preview 正常显示背景图、校名和校训等模板资产。

## 校验模板

在原版 `ppt-master` 根目录下运行：

```bash
python3 scripts/svg_quality_checker.py templates/decks/江西师范大学 --template-mode --format ppt169
```

当前模板包含 9 个 SVG 页面，目标画布为 `ppt169`，即 16:9、`1280 x 720`。

## 许可证与声明

`ppt-master` 原项目由 [hugohe3/ppt-master](https://github.com/hugohe3/ppt-master) 提供，原项目使用 MIT License。

本仓库的模板结构、说明文档和与 `ppt-master` 适配相关的文件按 [MIT License](LICENSE) 发布，并在 [NOTICE.md](NOTICE.md) 中保留上游来源和修改说明。

本仓库是面向 `ppt-master` 的非官方 deck 模板，不代表江西师范大学官方发布或授权。

模板中的学校标识、校名、校训、校园图片等资产可能受单独的商标、品牌或版权限制，不因本仓库的 MIT License 自动获得自由商用授权。请仅用于学习、内部汇报或合规授权范围内的演示场景；公开传播、商业使用或正式对外发布前，请自行确认相关标识和图片资产的使用权限。
