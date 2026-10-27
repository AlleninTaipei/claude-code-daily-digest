# D:\daily-task 工作目錄

此目錄下有兩個獨立專案, 各自有自己的 git repo 與 CLAUDE.md:

- `bnext-ai-news\` — bnext AI 新聞摘要專案
- `one_day_one_ai\` — 一天一AI 文章摘要專案

## Auto Mode 更新指令

當使用者在此目錄層級以 "Auto Mode" 說「請更新」時, 依序對兩個專案分別執行各自 CLAUDE.md 內定義的完整更新流程(抓取新文章, 更新 MD/HTML, commit, push), 不需逐一詢問確認:

1. 進入 `bnext-ai-news\`, 依該專案 CLAUDE.md 的更新指令執行, 完成後 commit 並 push 到 `origin master`
2. 進入 `one_day_one_ai\`, 依該專案 CLAUDE.md 的更新指令執行, 完成後 commit 並 push 到 `origin main`

兩個專案彼此獨立, 一個失敗(例如抓取失敗或無新文章)不影響另一個繼續執行. 全部完成後, 向使用者回報兩個專案各自的更新結果(新增篇數, commit hash 是否成功 push).
