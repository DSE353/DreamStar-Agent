# DreamStar-Agent

DreamStar-Agent 是一个跑在本地的 AI 助手。能聊天，也能干点活。

英文名就这么叫，中文名星璇，不过代码里用的还是拼音。

---

## 它能干什么

- 聊天。普通的对话、问问题、写点东西，都行。
- 执行命令。比如 `ls`、`cd`、`python` 之类的。
  - 危险命令会拦下来。`rm -rf /` 这种直接拒绝，不问你。
  - 删文档目录这种（比如 `rm -rf ~/Documents`）会问你要不要继续，你明确说“同意执行”才会跑。
- 上网搜东西。文本、新闻、图片都行，用的是 DuckDuckGo，不花钱。
- 抓一个网页的正文。给它一个网址，它会抓主要内容，广告和侧边栏会去掉。
- 看 Excel 或 CSV 文件。能看前几行、列名、简单统计。
- 识别图片里的文字。中英文都行，用 EasyOCR。
- 把一段文字念出来。生成一个 mp3 文件。
- 跑你自己写的插件。在 `skills/` 目录下放一个 .py 文件，里面写个 `run(params)` 函数就行。

## 优势

- **轻量**。不需要 GPU，普通电脑就能跑。模型量化后（Q4_K 之类）内存占用 4-8GB，没有高端显卡也能用。
- **好装**。依赖就是 pip install 那几个库，没有复杂的编译。把模型文件下载好，填个路径就行。
- **不用配 API Key**。搜索、OCR、TTS 全是本地或免费接口，不用注册账号，也不用担心额度用完。
- **图形界面**。打开浏览器就能用，不用敲命令行。加载模型、调参数、看记忆，都在网页上点一点。
- **代码就一个文件**。整个项目就是一个 .py，没有几十个文件夹互相引用。想看逻辑直接翻，改起来也不慌。
- **小白也能部署**。只要会装 Python、会 pip install、会下载一个模型文件，剩下的按照页面提示操作就行。不用理解什么是 Docker、什么是反向代理。

---

## 快速开始

### 1. 安装依赖

```bash
pip install flask flask-cors llama-cpp-python duckduckgo-search pandas openpyxl easyocr Pillow pyttsx3 requests beautifulsoup4 readability-lxml
