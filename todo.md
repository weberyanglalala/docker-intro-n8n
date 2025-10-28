# Slidev 投影片製作進度追蹤

## 課程: Docker Compose + n8n 部署 (2.5 小時)

---

## 第一部分: 基礎概念介紹 (30 分鐘)

### 1. 什麼是容器化技術? (10 分鐘)
- [x] Cover slide - 課程標題與簡介
- [x] 傳統部署 vs 容器化部署對比圖
- [x] Docker 解決的問題 (環境一致性)
- [x] Docker 解決的問題 (隔離性與資源管理)
- [x] Docker 解決的問題 (快速部署與移植)

### 2. Docker 核心概念 (15 分鐘)
- [x] Image (映像檔) 概念說明
- [x] Container (容器) 概念說明
- [x] Registry (倉庫) 概念說明
- [x] 三者關係圖解
- [x] 比喻說明 slide (Image=食譜, Container=菜)

### 3. 什麼是 n8n? (5 分鐘)
- [x] n8n 平台介紹
- [x] n8n 使用場景範例

---

## 第二部分: 環境準備與安裝 (20 分鐘)

### 4. 安裝 Docker Desktop (10 分鐘)
- [x] 安裝步驟 slide (Windows/Mac/Linux)
- [x] 驗證指令 slide (`docker --version`, `docker compose version`)
- [x] Docker Desktop 介面導覽

### 5. 建立專案資料夾 (10 分鐘)
- [x] 專案結構圖示 slide
- [x] 資料夾用途說明 slide
- [x] 實際操作步驟 slide

---

## 第三部分: Docker Compose 檔案詳解 (40 分鐘)

### 6. docker-compose.yml 逐行解析 (35 分鐘)
- [ ] docker-compose.yml 完整範例 slide
- [ ] `services:` 區塊說明 (3 分鐘)
- [ ] `n8n:` 服務名稱說明 (2 分鐘)
- [ ] `image:` 映像檔設定說明 (8 分鐘)
  - [ ] 映像檔名稱拆解圖解
  - [ ] Registry/組織/版本說明
  - [ ] 版本指定重要性
- [ ] `container_name:` 容器名稱說明 (3 分鐘)
- [ ] `restart:` 重啟策略說明 (4 分鐘)
  - [ ] always 策略說明
  - [ ] 其他選項對比表
- [ ] `environment:` 環境變數說明 (7 分鐘)
  - [ ] NODE_ENV 說明
  - [ ] GENERIC_TIMEZONE 說明
  - [ ] ${...} 語法說明
- [ ] `volumes:` 資料掛載說明 (10 分鐘)
  - [ ] 資料持久化概念圖解
  - [ ] n8n_storage 掛載說明
  - [ ] local-files 掛載說明
  - [ ] 實際應用案例
- [ ] `env_file:` 環境變數檔案說明 (3 分鐘)

### 7. 建立 .env 檔案 (5 分鐘)
- [ ] .env 檔案範例 slide
- [ ] 常用 n8n 環境變數說明

---

## 第四部分: 實際部署操作 (35 分鐘)

### 8. 啟動服務 (15 分鐘)
- [ ] 啟動指令 slide (`docker compose up`)
- [ ] 前台 vs 背景運行對比
- [ ] 啟動過程說明
- [ ] 常見錯誤處理 slide

### 9. 驗證與訪問 (5 分鐘)
- [ ] 訪問 n8n 介面 slide
- [ ] 初次設定步驟

### 10. 常用 Docker Compose 指令 (15 分鐘)
- [ ] 指令速查表 slide
- [ ] docker compose ps 說明
- [ ] docker compose logs 說明
- [ ] docker compose stop/down 說明
- [ ] docker compose restart 說明
- [ ] docker stats 說明

---

## 第五部分: 進階概念與疑難排解 (20 分鐘)

### 11. 資料持久化驗證 (5 分鐘)
- [ ] 資料持久化測試步驟 slide
- [ ] volumes 作用展示

### 12. 常見問題與解決方法 (10 分鐘)
- [ ] 容器無法啟動排查 slide
- [ ] docker exec 指令說明
- [ ] 更新版本方法 slide
- [ ] 備份資料方法 slide

### 13. 擴展說明 (5 分鐘)
- [ ] 加入資料庫服務範例 (PostgreSQL)
- [ ] 多容器協作概念
- [ ] 網路與連接埠映射

---

## 第六部分: Q&A 與實作練習 (25 分鐘)

### 14. 綜合練習 (15 分鐘)
- [ ] 練習題目 slide
- [ ] 練習步驟指引

### 15. 開放問答 (10 分鐘)
- [ ] Q&A slide
- [ ] 學習資源推薦 slide
- [ ] Thank you / 結束 slide

---

## 其他資源

### 支援檔案
- [ ] 準備完整的 docker-compose.yml 範例檔案
- [ ] 準備 .env 範例檔案
- [ ] 準備常見錯誤截圖
- [ ] 準備 n8n 工作流範例

---
