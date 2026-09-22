# 低频分轨器

可直接部署到 GitHub Pages 的纯静态音乐分轨工具。使用 WebAssembly + WebGPU 在浏览器本地运行 HTDemucs，不上传歌曲。

## 最简单的部署方法

1. 在 GitHub 新建一个空仓库，例如 `bass-stem-splitter`。
2. 解压本 ZIP，把里面的所有文件上传到仓库根目录，隐藏目录 `.github` 也要保留。
3. 确保默认分支名为 `main`。
4. 打开仓库 `Settings` → `Pages`。
5. 在 `Build and deployment` 的 `Source` 中选择 `GitHub Actions`。
6. 打开仓库的 `Actions` 页面，等待 `Deploy static site to GitHub Pages` 变成绿色。
7. 回到 `Settings` → `Pages` 查看公开网址，通常是：

   `https://你的用户名.github.io/仓库名/`

以后只要更新 `main` 分支，网站会自动重新发布。

## 使用方式

1. 用最新版桌面 Chrome 或 Edge 打开网站。
2. 上传 MP3、WAV、M4A、AAC、FLAC 或 OGG。
3. 推荐选择“六轨分离”。
4. 首次使用下载约 84 MB 模型，随后缓存在浏览器中。
5. 完成后可分别试听并下载鼓、贝斯、其他、人声、吉他、键盘 WAV。

## 注意事项

- GitHub Pages 必须通过 HTTPS 访问，不能双击 `index.html` 使用。
- 长歌曲需要较多内存和处理时间，建议先用短片段测试。
- 模型下载来自 Hugging Face；某些网络环境可能需要确保该站点可访问。
- 请只处理你有权使用的音频。

## 文件说明

- `index.html`：网站入口。
- `assets/`：页面脚本和样式。
- `engine/`：本地分轨 Worker 与 WebAssembly 引擎。
- `.github/workflows/pages.yml`：GitHub Pages 自动部署工作流。
- `.nojekyll`：避免 GitHub Pages 对静态文件进行 Jekyll 处理。

## 第三方许可

推理引擎基于 `nikhilunni/demucs-rs`，遵循 Apache License 2.0。详情见 `LICENSE` 和 `NOTICE`。
