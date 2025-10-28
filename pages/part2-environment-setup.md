---
theme: default
title: 第二部分：環境準備與安裝
info: |
  ## 第二部分：環境準備與安裝
  Docker Desktop 安裝與專案資料夾設置
---

# 第二部分：環境準備與安裝

- 安裝 Docker Desktop
- 驗證安裝環境
- Docker Desktop 介面導覽
- 建立專案資料夾結構

---

# 4. 安裝 Docker Desktop

## 開始前準備

- 確認您的作業系統 (Windows / Mac / Linux)
- 準備約 3-4 GB 的磁碟空間
- 確保網路連線穩定

<!--
這個投影片設定課程的期望和基本要求
-->

---

## Windows 安裝步驟

1. 訪問 [Docker 官方網站](https://www.docker.com/products/docker-desktop)
2. 點擊「Download for Windows」
3. 執行安裝檔 (`Docker Desktop Installer.exe`)

<v-click>

**安裝選項設定：**
- ✅ Install required Windows components for WSL 2
- ✅ Add Docker Desktop to the PATH
- ✅ Use WSL 2 (推薦)

</v-click>

<v-click>

4. 完成安裝後重新啟動電腦
5. 首次啟動可能需要 2-3 分鐘初始化

</v-click>

---

## macOS 安裝步驟

1. 訪問 [Docker 官方網站](https://www.docker.com/products/docker-desktop)
2. 選擇適合您的版本：
   - **Apple Silicon (M1/M2/M3)**: `Docker.dmg` for Apple Silicon
   - **Intel**: `Docker.dmg` for Intel Chip

<v-click>

3. 拖曳 Docker 應用程式到 Applications 資料夾
4. 從 Applications 中啟動 Docker.app

</v-click>

<v-click>

5. 輸入管理員密碼以完成特權安裝
6. 等待 Docker 啟動（約 1-2 分鐘）

</v-click>

---
layout: center
---

# 驗證安裝

## 確認 Docker 已正確安裝

---

## 驗證指令

**檢查 Docker 版本：**

```bash
docker --version
```

預期輸出：`Docker version 24.x.x, build xxxxxxx`

<v-click>

**檢查 Docker Compose 版本：**

```bash
docker compose version
```

預期輸出：`Docker Compose version 2.x.x, build xxxxxxx`

</v-click>

<v-click>

**執行簡單測試：**

```bash
docker run hello-world
```

</v-click>

<v-click>

✅ 若能成功顯示 "Hello from Docker!"，代表安裝成功

</v-click>

---

## Docker Desktop 介面導覽

<div class="grid grid-cols-2 gap-8">
<div>

### 主功能區

- **Containers/Apps**: 管理執行中的容器
- **Images**: 瀏覽已下載的映像檔
- **Volumes**: 管理資料卷
- **Networks**: 檢視網路設定

</div>
<div>

### 右上角功能

- ⚙️ **Settings**: 系統設定
- 📊 **Docker Stats**: 資源使用情況
- 📋 **Dashboard**: 整體概覽
- 🔔 **Notifications**: 系統通知

</div>
</div>

<!--
說明 Docker Desktop 的主要介面元素，幫助使用者熟悉工具
-->

---

## Docker Desktop 基本設定

**推薦設定調整：**

<v-clicks>
- **Resources** → 配置 CPU 和記憶體（視電腦硬體調整）
- **Docker Engine** → 確認使用最新版本
- **File Sharing** → 確認專案資料夾的存取權限
- **Network** → 預設設定即可
</v-clicks>

---
layout: center
---

# 5. 建立專案資料夾

## 組織與結構規劃

---

## 專案結構示意圖

```
my-n8n-project/
├── docker-compose.yml      # Docker Compose 設定檔
├── n8n_data/               # n8n 資料存放目錄
├── .env                    # 環境變數檔案
├── .gitignore             # Git 忽略清單
└── README.md              # 專案文檔
```

**優勢：** 使用 docker-compose.yml 簡化容器管理，資料存放在本地

---

## 資料夾用途說明

<div class="grid grid-cols-2 gap-6">
<div>

### docker-compose.yml 檔案
- Docker 容器設定檔
- 定義 n8n 服務和配置
- 環境變數和掛載設定

### .env 檔案
- 儲存環境變數
- 時區設定（GENERIC_TIMEZONE、TZ）
- 不應提交至 Git

</div>
<div>

### n8n_data/ 目錄
- 儲存 n8n 持久化資料
- 資料卷掛載位置
- 容器停止後資料保留

### .gitignore 檔案
- 列出 Git 忽略的檔案
- 排除 .env 和 n8n_data/
- 避免提交敏感資料

</div>
</div>

---

## 實際操作步驟

按照以下 4 個步驟設置您的 n8n 專案

---

## 步驟 1: 建立專案資料夾

**建立一個新的專案目錄並進入：**

```bash
# macOS / Linux
mkdir my-n8n-project
cd my-n8n-project

# Windows (PowerShell)
mkdir my-n8n-project
cd my-n8n-project
```

<v-click>

**驗證：** 您應該現在位於 `my-n8n-project/` 目錄中

</v-click>

---

## 步驟 2: 建立 n8n_data 資料夾

**建立用於儲存 n8n 資料的目錄：**

```bash
# 建立資料存放目錄
mkdir n8n_data
```

<v-click>

**用途：**
- 儲存 n8n 資料庫
- 儲存工作流設定
- 儲存使用者設定

</v-click>

---

## 步驟 3: 建立 .gitignore 檔案

**建立 Git 忽略清單（如使用版本控制）：**

```bash
# 建立 .gitignore
echo ".env" > .gitignore
echo "n8n_data/" >> .gitignore
echo ".DS_Store" >> .gitignore
```

<v-click>

**為什麼要忽略這些檔案？**
- `.env`: 包含敏感的環境變數
- `n8n_data/`: 容器資料，無需版本控制
- `.DS_Store`: macOS 系統檔案

</v-click>

---

## 步驟 4: 建立 .env 檔案

**建立環境變數設定檔案：**

```bash
# 建立環境變數檔案
echo "GENERIC_TIMEZONE=Asia/Taipei" > .env
echo "TZ=Asia/Taipei" >> .env
```

<v-click>

**環境變數說明：**
- `GENERIC_TIMEZONE`: n8n 時區設定
- `TZ`: 系統時區設定
- 根據您的位置修改時區設定

</v-click>

---

## 步驟 5: 建立 docker-compose.yml 檔案

**執行以下指令建立 Docker Compose 設定檔：**

```bash
cat > docker-compose.yml << 'EOF'
services:
  n8n:
    image: docker.n8n.io/n8nio/n8n
    container_name: n8n
    ports:
      - "5678:5678"
    environment:
      - GENERIC_TIMEZONE=Asia/Taipei
      - TZ=Asia/Taipei
      - N8N_ENFORCE_SETTINGS_FILE_PERMISSIONS=true
      - N8N_RUNNERS_ENABLED=true
    volumes:
      - ./n8n_data:/home/node/.n8n
    restart: always
EOF
```

---

## Docker-Compose 配置詳解

| 配置項目 | 值 | 說明 |
|---------|-----|------|
| **服務名稱** | `n8n` | 定義服務名稱 |
| **映像檔** | `docker.n8n.io/n8nio/n8n` | 使用官方 n8n 映像 |
| **容器名稱** | `n8n` | 容器識別名稱 |
| **埠號映射** | `5678:5678` | 主機埠:容器埠 |
| **時區設定** | `Asia/Taipei` | n8n 和系統時區 |
| **檔案權限** | `FILE_PERMISSIONS=true` | 強制檔案權限設定 |
| **執行器** | `RUNNERS_ENABLED=true` | 啟用 n8n 執行器 |
| **資料掛載** | `./n8n_data:/home/node/.n8n` | 本地路徑:容器路徑 |
| **重啟策略** | `always` | 異常停止時自動重啟 |

---
layout: center
---

# Docker Compose 啟動

## 使用 docker-compose.yml 運行 n8n

---

## 啟動 n8n 容器

**在專案目錄執行以下指令：**

```bash
docker compose up
```

<v-click>

**選項說明：**
- `docker compose up`: 啟動容器（前台運行）
- `docker compose up -d`: 背景運行
- `docker compose down`: 停止並刪除容器

</v-click>

<v-click>

**預期看到的輸出：**
```
n8n ready on 0.0.0.0, port 5678
```

</v-click>

---

## 本地資料夾掛載說明

### 使用 `./n8n_data` 方式的優勢：

<v-clicks>

- 📁 將 `n8n_data` 資料夾掛載到容器
- 🔄 資料自動同步到本地檔案系統
- 🔍 可直接在編輯器檢視與編輯
- 💾 便於版本控制與備份
- ✅ 簡單易懂的檔案結構
</v-clicks>

---

## 設置檢查清單

確認您的專案資料夾結構：

```bash
# 檢視目錄結構
ls -la my-n8n-project/
```

<v-click>

**應該看到：**
- ✅ docker-compose.yml 檔案
- ✅ n8n_data/ 資料夾
- ✅ .gitignore 檔案（Git 忽略清單）

</v-click>

<v-click>

**驗證資料夾結構：**
```bash
tree n8n_data/
# 或使用：
ls -la n8n_data/
```

</v-click>

---
layout: center
---

# 環境準備完成！

## 準備啟動 n8n 容器

**您已經準備好啟動第一個 n8n 容器！**

<v-click>

**快速啟動步驟：**
1. 在 `my-n8n-project/` 目錄開啟終端
2. 執行 `docker compose up`
3. 訪問 http://localhost:5678
4. 完成 n8n 初始設定

</v-click>

<v-click>

**資料儲存位置：**
- 所有 n8n 資料將儲存在本地 `./n8n_data/` 資料夾
- 容器停止時，資料會被保留

</v-click>

<!--
結束環境準備部分，進入下一部分
-->
