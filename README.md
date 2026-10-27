# claude-code-daily-digest

一份 `CLAUDE.md`, 一句 "請更新", 讓 Claude Code 自動完成每日 AI 新聞整理.

這個 repo 示範如何把重複的日常工作交給 Claude Code: 不寫爬蟲程式, 不寫排程腳本, 只用自然語言在 `CLAUDE.md` 描述流程, Claude Code 就會依序抓取網頁, 比對新文章, 分類, 更新 Markdown 與 HTML, 最後 commit 並 push 到各自的 repo.

## 它做了什麼

在 `D:\daily-task` 啟動 Claude Code, 以 Auto Mode 說 "請更新":

1. 進入 `bnext-ai-news\`, 抓取數位時代「AI 與大數據」分類最新 20 頁, 找出新文章.
2. 進入 `one_day_one_ai\`, 抓取數位時代「一天一AI」專欄全部頁面, 找出新文章.
3. 每個專案各自將新文章分類, 同步更新 MD 與 HTML, commit 並 push.
4. 回報兩個專案的新增篇數與 commit 結果.

兩個專案彼此獨立, 一個失敗不影響另一個.

## 結構

```
D:\daily-task\                本 repo, 只追蹤這一層
├── CLAUDE.md                 總指揮: 定義 "請更新" 要依序做哪些事
├── README.md
├── bnext-ai-news\            子專案 (獨立 repo, 已排除)
│   └── CLAUDE.md             該專案的抓取, 比對, 更新規則
└── one_day_one_ai\           子專案 (獨立 repo, 已排除)
    └── CLAUDE.md
```

重點在分層: 根目錄的 `CLAUDE.md` 只負責調度, 每個子專案的 `CLAUDE.md` 各自定義細節. 要新增一個整理主題, 只要建一個新子專案, 寫好它的 `CLAUDE.md`, 再在根目錄加一行.

## 子專案

| 資料夾 | Repo | 分支 |
| --- | --- | --- |
| `bnext-ai-news\` | [AlleninTaipei/bnext-ai-news](https://github.com/AlleninTaipei/bnext-ai-news) | `master` |
| `one_day_one_ai\` | [AlleninTaipei/one_day_one_ai](https://github.com/AlleninTaipei/one_day_one_ai) | `main` |

## 自己試試看

```bash
git clone https://github.com/AlleninTaipei/claude-code-daily-digest.git D:/daily-task
cd D:/daily-task
git clone https://github.com/AlleninTaipei/bnext-ai-news.git
git clone https://github.com/AlleninTaipei/one_day_one_ai.git
```

接著在 `D:\daily-task` 執行 `claude`, 說 "請更新".

想做自己的版本, 可以把子專案換成你關注的網站或主題, 照著現有的 `CLAUDE.md` 改寫規則即可.

## 相關

- [my-claude-code-skills](https://github.com/AlleninTaipei/my-claude-code-skills): 個人的 Claude Code Skills 與 Slash Commands 集合.
