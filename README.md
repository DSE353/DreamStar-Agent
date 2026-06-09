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

---

## 快速开始

```bash
pip install flask flask-cors llama-cpp-python duckduckgo-search pandas openpyxl easyocr Pillow pyttsx3 requests beautifulsoup4 readability-lxml
