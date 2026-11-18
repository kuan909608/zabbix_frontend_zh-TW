# 翻譯來源與授權

整理日期：2026-11-18。7.0、7.2、7.4、8.0 最初以官方繁中為基線，依原文、語境及複數原文完全比對後帶入 6.4 的翻譯；其後完成下述翻譯與校對。目前各版皆無空白譯文與 fuzzy，尚待實機畫面驗證。

8.0 於 2026-11-18 由 Codex 輔助依英文原文、簡中參考及本機用語表補齊原先 1,475 筆空白譯文與 27 筆 fuzzy，並修正部分既有用語與遺失參數。其後完成其餘 4,191 筆既有譯文的第一輪英文對照校對，其中修正 2,038 筆，保留 2,153 筆；修正包含語意錯誤、未翻譯內容、固定技術鍵名及用語一致性。目前 5,693 筆皆有譯文；已完成本機 PO 解析、參數／巨集／換行檢查與 MO 編譯回讀測試，尚待實際畫面的用語、排版及操作語境驗證。本機未執行 GNU msgfmt，該檢查由 GitHub Actions 在推送後執行。翻譯工具與逐筆校對進度僅留在本機，不隨 Repository 提供。

8.0 另完成一輪核心用語複查：將本機用語表由 88 項草案整理為 238 項採用用語，以全部 5,693 筆檢查核心名稱、衍生詞、單複數與已知異體，涵蓋 3,744 筆含核心用語的譯文，再修正 221 筆。用語表記錄語境差異，例如驗證／授權、使用者／用戶端、運算式／正規表示式、連線／連結，以及程式碼與固定參數的保留規則。此輪也修正維護期間誤譯為事件關聯的遺漏；檢查通過不代表所有畫面語意已完成實機驗證。用語表、檢查工具與修改明細仍僅存於本機，6.4／7.x 未同步套用這輪變更。

8.0 隨後完成全檔文法校對，逐筆檢視 5,693 筆，以固定 commit 的英文原文為準、簡中為參考，修順 518 筆並保留 5,175 筆。修改包含語序、否定與條件句、時間描述、相依關係及操作警告；有歧義的訊息另對照官方原始碼或文件確認。此輪保留既定核心用語，重新執行 238 項用語檢查，並通過全檔參數／巨集／換行與 MO 編譯回讀檢查；未修改其他版本與本機來源檔。各輪修改筆數可能重疊，不代表互不重複的譯文數量。仍待實機畫面驗證；本輪明細與工具亦僅留在本機。

6.4、7.0、7.2、7.4 隨後沿用已校對的 8.0 成果，以 `msgctxt`、`msgid`、`msgid_plural` 完全相符為條件，另檢查版本語境及參數：6.4 沿用 4,223 筆，7.0 沿用 4,756 筆，7.2 沿用 4,747 筆，7.4 沿用 5,156 筆。6.4 另有 498 筆專用字串逐筆依英文與可取得的簡中校對，統一核心用語並修順文法；簡中缺少對應時，以英文與語境判斷，不套用模糊比對結果。

6.4 的原專案檔案與固定官方模板比較後，補上原先缺少的 50 筆，並保留 104 筆未見於該模板的舊版字串，因此共 4,721 筆，涵蓋固定官方模板的全部 4,617 筆。原有訊息鍵與來源註記均保留。7.0／7.2／7.4 的訊息鍵集合各與固定官方英文模板相符。四版均重新執行 238 項核心用語規則、全檔參數／巨集／換行與 MO 編譯回讀檢查；6.4 舊格式的 VMware 角括號參數也另行核對。中文採單一複數形式，6.4 兩筆「每隔幾天／幾週」訊息保留複數原文的完整間隔參數。本機未執行 GNU msgfmt，仍由推送後的 GitHub Actions 檢查。已確認的 8.0 成果與 `src/` 原檔均未變更，工具、用語表、逐筆進度及修改明細仍只存於本機。

| 版本 | 來源 | 固定 commit |
| --- | --- | --- |
| 6.4 | [原始 Repo 的 frontend.po](https://github.com/kuan909608/zabbix_frontend_zh-TW/blob/620269d/frontend.po)；缺漏字串依下述固定官方英文模板補齊 | clone 時的 `main`：`620269d`；保留自訂來源，修正四行註解格式後進行校對 |
| 7.0 | [官方 release/7.0](https://git.zabbix.com/projects/ZBX/repos/zabbix/browse/ui/locale/zh_TW/LC_MESSAGES/frontend.po?at=e556a0076ff42fa566eb5acf4882cfbadd8b46cd) | `e556a0076ff42fa566eb5acf4882cfbadd8b46cd` |
| 7.2 | [官方 release/7.2](https://git.zabbix.com/projects/ZBX/repos/zabbix/browse/ui/locale/zh_TW/LC_MESSAGES/frontend.po?at=e8af8368d9b024900498f101c5a8927ac78746ab) | `e8af8368d9b024900498f101c5a8927ac78746ab` |
| 7.4 | [官方 release/7.4](https://git.zabbix.com/projects/ZBX/repos/zabbix/browse/ui/locale/zh_TW/LC_MESSAGES/frontend.po?at=a4c3a13d49ba159685452a7459ba17fccf36cd24) | `a4c3a13d49ba159685452a7459ba17fccf36cd24` |
| 8.0 | [官方 release/8.0](https://git.zabbix.com/projects/ZBX/repos/zabbix/browse/ui/locale/zh_TW/LC_MESSAGES/frontend.po?at=67679b38b5778b4159b198652853a912434d21fb) | `67679b38b5778b4159b198652853a912434d21fb` |

官方路徑為 `ui/locale/zh_TW/LC_MESSAGES/frontend.po`。官方檔案來源統一使用 Zabbix Git（`git.zabbix.com`），保留原先固定 commit；先前從 GitHub 鏡像取得的基線亦已重新下載核對。6.4 自訂翻譯的歷史來源仍保留原專案連結。本機 `src/` 保留官方翻譯者和原始 PO 中繼資料；原檔的舊 `Project-Id-Version: Zabbix 6.0` 標頭未改寫，版本依來源分支判斷。各版成果檔已更新專案版本、修訂日期及 Codex 輔助翻譯標記，並保留原始作者註記。

本機 `src/<版本>/frontend.po` 存放未修改的來源檔，整個 `src/` 已排除 Git。GitHub checkout 不含這些原文備份，需要時可依上表重新取得。

## 英文與簡中對照

英文與簡中原始檔保存在本機已排除 Git 的 `src/`，供維護翻譯時對照：

五個版本均直接下載自 Zabbix Git 的固定 commit，不使用 GitHub 鏡像。

- `src/<版本>/en_US/frontend.pot`：官方英文原文模板，原始路徑為 `ui/locale/en_US/LC_MESSAGES/frontend.pot`。
- `src/<版本>/zh_CN/frontend.po`：官方簡中翻譯，原始路徑為 `ui/locale/zh_CN/LC_MESSAGES/frontend.po`。
- `src/<版本>/references.json`：下載網址、完整 commit 和 SHA-256，方便核對來源。

7.0、7.2、7.4、8.0 對照檔與上表繁中基線使用相同 commit。6.4 對照檔取自官方 `release/6.4` 的固定 commit `d771ef9710e76a3458ec4d9f7df681744cacbfe1`；原專案自訂 6.4 翻譯沒有記錄對應官方 commit，因此字串集合可能不同，須依語境與原文比對，不能按行號對齊。

英文模板的 `msgstr` 留空，原文在 `msgid` 和 `msgid_plural`。簡中只作語意對照；未翻譯或 fuzzy 項目仍須人工核對英文原文。`src/` 保留原始檔，版本目錄保存繁中成果。

Zabbix 6.4 的官方 COPYING 為 GPL-2.0-or-later；7.x 和 8.0 為 AGPL-3.0。官方授權全文保存於 `LICENSES/`。原始自訂翻譯未另附專案授權聲明，本次保留其原有權利狀態，未替原作者新增授權。
