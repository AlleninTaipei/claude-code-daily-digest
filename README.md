# daily-task

`D:\daily-task` 工作目錄的設定檔. 本 repo 只追蹤這一層的 `CLAUDE.md`, 子專案各自有獨立 repo, 已在 `.gitignore` 排除.

## 子專案

| 資料夾 | Repo | 分支 |
| --- | --- | --- |
| `bnext-ai-news\` | [AlleninTaipei/bnext-ai-news](https://github.com/AlleninTaipei/bnext-ai-news) | `master` |
| `one_day_one_ai\` | [AlleninTaipei/one_day_one_ai](https://github.com/AlleninTaipei/one_day_one_ai) | `main` |

## 在新電腦還原

```bash
git clone https://github.com/AlleninTaipei/daily-task.git D:/daily-task
cd D:/daily-task
git clone https://github.com/AlleninTaipei/bnext-ai-news.git
git clone https://github.com/AlleninTaipei/one_day_one_ai.git
```

## 使用方式

在 `D:\daily-task` 啟動 Claude Code, 以 Auto Mode 說 "請更新", 會依 `CLAUDE.md` 依序更新兩個子專案並各自 commit, push.
