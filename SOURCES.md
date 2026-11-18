# 翻譯來源與授權

繁體中文翻譯維護：[kuan909608](https://github.com/kuan909608)。

## 官方來源

英文原文與簡中對照統一取自 [Zabbix Git](https://git.zabbix.com/projects/ZBX/repos/zabbix/browse)，各版本使用以下固定 commit。

| Zabbix 系列 | 來源分支 | 固定 commit |
| --- | --- | --- |
| 6.0 | [release/6.0](https://git.zabbix.com/projects/ZBX/repos/zabbix/browse/ui/locale?at=fb00b18353a1211dac3b47d4644d21e962a17e67) | `fb00b18353a1211dac3b47d4644d21e962a17e67` |
| 6.4 | [release/6.4](https://git.zabbix.com/projects/ZBX/repos/zabbix/browse/ui/locale?at=d771ef9710e76a3458ec4d9f7df681744cacbfe1) | `d771ef9710e76a3458ec4d9f7df681744cacbfe1` |
| 7.0 | [release/7.0](https://git.zabbix.com/projects/ZBX/repos/zabbix/browse/ui/locale?at=e556a0076ff42fa566eb5acf4882cfbadd8b46cd) | `e556a0076ff42fa566eb5acf4882cfbadd8b46cd` |
| 7.2 | [release/7.2](https://git.zabbix.com/projects/ZBX/repos/zabbix/browse/ui/locale?at=e8af8368d9b024900498f101c5a8927ac78746ab) | `e8af8368d9b024900498f101c5a8927ac78746ab` |
| 7.4 | [release/7.4](https://git.zabbix.com/projects/ZBX/repos/zabbix/browse/ui/locale?at=a4c3a13d49ba159685452a7459ba17fccf36cd24) | `a4c3a13d49ba159685452a7459ba17fccf36cd24` |
| 8.0 | [release/8.0](https://git.zabbix.com/projects/ZBX/repos/zabbix/browse/ui/locale?at=67679b38b5778b4159b198652853a912434d21fb) | `67679b38b5778b4159b198652853a912434d21fb` |

官方檔案路徑：

| 語系 | 路徑 |
| --- | --- |
| 英文 | `ui/locale/en_US/LC_MESSAGES/frontend.pot` |
| 簡體中文 | `ui/locale/zh_CN/LC_MESSAGES/frontend.po` |
| 繁體中文 | `ui/locale/zh_TW/LC_MESSAGES/frontend.po` |

6.0、7.0、7.2、7.4、8.0 的繁中基線亦取自表中對應 commit。6.4 保留[本專案原始翻譯](https://github.com/kuan909608/zabbix_frontend_zh-TW/blob/620269d4ef8d8cf57bb8d938d43c6e0672cf1af7/frontend.po)，並依官方原文補齊；原始翻譯未記錄對應的官方 commit，因此保留部分舊版字串。

翻譯以英文原意為準，簡中作為參考；沿用其他版本譯文時，依原文、複數原文及語境精確比對。原有作者註記保留於翻譯檔中。

## 檔案範圍

`<版本>/frontend.po` 為本專案提供的繁中翻譯檔。原文與對照檔存放於本機 `src/`，來源網址及 SHA-256 記錄於 `references.json`；原文、翻譯工具、用語表、校對進度與修改明細均排除 Git，不隨 Repository 提供。

## 授權

| Zabbix 系列 | 上游授權 | 授權全文 |
| --- | --- | --- |
| 6.0 | GPL-2.0-or-later | [COPYING](LICENSES/Zabbix-6.0-COPYING) |
| 6.4 | GPL-2.0-or-later | [COPYING](LICENSES/Zabbix-6.4-COPYING) |
| 7.0、7.2、7.4、8.0 | AGPL-3.0 | [COPYING](LICENSES/Zabbix-7.x-COPYING) |

原始自訂 6.4 翻譯未另附專案授權聲明，本專案保留其原有權利狀態，不替原作者新增授權。
