# Zabbix 前端繁體中文翻譯

此 Repository 提供各版本的繁體中文翻譯檔、安裝說明，以及來源與授權資訊。

| Zabbix 系列 | 翻譯檔 |
| --- | --- |
| 6.0 | [frontend.po](6.0/frontend.po) |
| 6.4 | [frontend.po](6.4/frontend.po) |
| 7.0 | [frontend.po](7.0/frontend.po) |
| 7.2 | [frontend.po](7.2/frontend.po) |
| 7.4 | [frontend.po](7.4/frontend.po) |
| 8.0 | [frontend.po](8.0/frontend.po) |

來源與授權見 [SOURCES.md](SOURCES.md)。

## 下載與編譯

請選擇與 Zabbix **前端版本**相同的系列。前端版本可在其 `include/defines.inc.php` 的 `ZABBIX_VERSION` 查看。

```bash
# 選擇 6.0、6.4、7.0、7.2、7.4 或 8.0
VERSION=8.0
curl -fL -o frontend.po \
  "https://raw.githubusercontent.com/kuan909608/zabbix_frontend_zh-TW/main/${VERSION}/frontend.po"
msgfmt --check --statistics -o frontend.mo frontend.po
```

Repo 名稱使用 `zh-TW`，Zabbix 語系目錄使用 `zh_TW`。

也可從 [Releases](https://github.com/kuan909608/zabbix_frontend_zh-TW/releases) 選擇已發布的 `zabbix-<版本>-zh-TW.tar.gz`，取得 PO 與編譯完成的 MO，以及來源和授權資訊。

## 安裝（Linux）

在前端 Web 主機安裝 gettext 與繁中 locale。Debian／Ubuntu 範例：

```bash
sudo apt-get update
sudo apt-get install -y gettext locales
# 在 /etc/locale.gen 啟用 zh_TW.UTF-8 UTF-8 後執行
sudo locale-gen
locale -a
```

RHEL 系列可安裝 `gettext glibc-langpack-zh`。確認 `locale -a` 包含 `zh_TW.utf8`；參考 [Zabbix 官方語系說明](https://www.zabbix.com/documentation/7.4/en/manual/appendix/install/locales)。

將已編譯的 `frontend.mo` 安裝到實際前端目錄。常見位置包括 `/usr/share/zabbix`、`/usr/share/zabbix/ui` 和 `/usr/share/zabbix/www`，請依部署環境選擇：

```bash
FRONTEND_DIR=/usr/share/zabbix/ui  # 改成實際前端目錄
TARGET="$FRONTEND_DIR/locale/zh_TW/LC_MESSAGES/frontend.mo"

# 既有翻譯檔存在時先備份
if [ -f "$TARGET" ]; then
  sudo cp -p -- "$TARGET" "${TARGET}.bak.$(date +%Y%m%d%H%M%S)"
fi
sudo install -d -- "$(dirname -- "$TARGET")"
sudo install -m 0644 -- frontend.mo "$TARGET"
```

完成後重新載入實際使用的 PHP／Web 服務（如 PHP-FPM、Apache），在 Zabbix 個人設定選擇繁體中文，必要時按 Ctrl + F5。翻譯變更不需要重啟 Zabbix Server。若語言選項未啟用，檢查該版 `include/locales.inc.php` 的 `getLocales()`，修改前請備份。容器部署請將翻譯放入映像或持久化掛載。

還原時將來源換成實際備份路徑，然後重新載入 PHP／Web 服務：

```bash
# sudo cp -p -- /實際路徑/frontend.mo.bak.時間戳記 "$TARGET"
```

## 圖表中文字體（選用）

圖表若出現方框，可安裝支援繁中的字體，並將實際前端 `include/defines.inc.php` 中的 `ZBX_GRAPH_FONT_NAME` 設為字體檔名（不含 `.ttf`），修改前請備份。

以下以 Noto Sans TC 為例，須確認環境的 GD／FreeType 支援此字體：

```bash
FRONTEND_DIR=/usr/share/zabbix/ui  # 改成實際前端目錄
curl -fL -o NotoSansTC.ttf \
  'https://raw.githubusercontent.com/google/fonts/main/ofl/notosanstc/NotoSansTC%5Bwght%5D.ttf'
sudo install -m 0644 NotoSansTC.ttf "$FRONTEND_DIR/assets/fonts/NotoSansTC.ttf"
# 在 defines.inc.php 將 ZBX_GRAPH_FONT_NAME 設為 NotoSansTC
```

字體依其 [SIL Open Font License](https://github.com/google/fonts/blob/main/ofl/notosanstc/OFL.txt) 使用。

## 格式檢查

可使用 gettext 檢查指定版本：

```bash
msgfmt --check --statistics -o frontend.mo 8.0/frontend.po
```
