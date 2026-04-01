# 勞動部就業資訊查詢系統

## 📖 Overview

A frontend web application that integrates with Taiwan's Ministry of Labor (勞動部) Open Data APIs to provide a comprehensive employment information portal. The system enables job seekers, students, and researchers to query real-time employment data — including job listings, salary statistics, training courses, and labor survey results — through a clean, user-friendly interface.

本專案是一個前端網頁應用程式，串接台灣勞動部開放資料 API，建立完整的就業資訊查詢入口網站。系統整合職缺清單、薪資統計、職業訓練課程及勞動調查等多元資料，提供求職者、學生與研究人員一站式查詢服務。

👉 **Live Demo:** https://cat0428mew.github.io/employment_api_testing/

---

## 🚀 Features

- **Job Market & Vacancy Info** — Browse job listings from Taiwan's official employment platform (台灣就業通) and explore occupational classification data
- **Salary & Insurance Data** — Query starting salary benchmarks (113年初任人員薪資), labor insurance premium tables, and historical minimum wage adjustments (1930–2023)
- **Employment Statistics** — Access monthly employment service statistics and youth labor surveys (15–29 years old)
- **Training Course Search** — Find available vocational training programs
- **Private Employment Agency Records** — View evaluation results of private job placement agencies (108–112年)
- **Sortable & Exportable Tables** — Data tables support column sorting and local save functionality
- **Consultation / Feedback Form** — Built-in inquiry form with backend data collection

- **就業市場與職缺資訊** — 瀏覽台灣就業通最新職缺，並查詢通俗職業分類資料
- **薪資與保險資訊** — 查詢 113 年初任人員薪資、勞保投保薪資分級表，以及 1930–2023 年基本工資調整歷程
- **就業統計資料** — 瀏覽逐月就業服務人數及 15–29 歲青年勞工就業狀況調查
- **職業訓練課程查詢** — 搜尋勞動力發展署提供之訓練課程資訊
- **私立就服機構評鑑資料** — 查閱 108–112 年私立就業服務機構基本資料及評鑑結果
- **表格排序與儲存功能** — 各資料表格支援欄位排序與本地儲存
- **諮詢 / 意見箱** — 內建意見回饋表單，並串接後台資料收集

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML / CSS / JavaScript |
| Data Source | 勞動部 Open Data API |
| API Communication | AJAX (Fetch / XMLHttpRequest) |
| Data Format | JSON |
| Deployment | GitHub Pages |

| 層級 | 技術 |
|---|---|
| 前端 | HTML / CSS / JavaScript |
| 資料來源 | 勞動部開放資料 API |
| API 通訊 | AJAX（Fetch / XMLHttpRequest）|
| 資料格式 | JSON |
| 部署方式 | GitHub Pages |

---

## 📡 Data Sources (APIs Used)

All data is retrieved from Taiwan's official open government data platforms:

| Module | Data Source |
|---|---|
| 台灣就業通職缺清單 | 勞動部就業服務開放資料 |
| 114年就業服務人數 | 勞動部統計資料 |
| 113年初任人員薪資 | 勞動部薪資調查 |
| 職業訓練課程 | 勞動力發展署訓練資訊 |
| 青年就業狀況調查 | 勞動部青年調查報告 |
| 通俗職業分類 | 勞動部職業分類資料 |
| 勞保投保薪資分級表 | 勞工保險局 |
| 勞就保費分擔金額表 | 勞工保險局 |
| 基本工資調整經過 (1930–2023) | 勞動部歷史資料 |
| 私立就服機構評鑑結果 (108–112年) | 勞動部評鑑資料 |

---

## 📂 Project Structure

```
employment_api_testing/
│── index.html       # 首頁 / Landing page
│── app01.html       # 台灣就業通職缺清單
│── app02.html       # 114年就業服務人數
│── app03.html       # 113年初任人員薪資
│── app04.html       # 職業訓練課程
│── app05_1.html     # 青年調查：初次尋職遭遇困難
│── app05_2.html     # 青年調查：初次尋職所需時間
│── app05_3.html     # 青年換工作情形
│── app06.html       # 通俗職業分類
│── app07.html       # 私立就服機構評鑑
│── app08.html       # 勞保投保薪資分級表
│── app09.html       # 勞就保費分擔金額表
│── app10.html       # 基本工資歷史調整
└── static/          # CSS / JS assets
```

---

## ⚙️ System Architecture

```
User Browser
    │
    ▼ HTTP Request
GitHub Pages (Static Frontend)
    │
    ▼ AJAX (async fetch per module)
勞動部 Open Data API  ──→  JSON Response
    │
    ▼
Data Normalization (JavaScript)
    │
    ▼
Dynamic UI Rendering (Tables / Charts)

使用者瀏覽器
    │
    ▼ HTTP 請求
GitHub Pages（靜態前端）
    │
    ▼ AJAX（各模組非同步請求）
勞動部開放資料 API  ──→  JSON 回應
    │
    ▼
資料標準化處理（JavaScript）
    │
    ▼
動態 UI 渲染（表格 / 圖表）
```

---

## 🧪 Testing Scope

This project validates real government API responses across 10+ endpoints:

| Test Type | Description |
|---|---|
| Response status | Confirm 200 OK; handle 400 / 404 / 500 gracefully |
| Data structure | Verify JSON fields match expected schema per module |
| Field-level checks | Validate data types, required fields, and value ranges |
| Edge cases | Empty datasets, API timeouts, malformed or missing fields |
| UI data binding | Confirm data renders correctly in tables and sorted views |

本專案針對 10+ 個政府 API 端點進行回應驗證：

| 測試類型 | 說明 |
|---|---|
| 回應狀態驗證 | 確認 200 OK；妥善處理 400 / 404 / 500 錯誤 |
| 資料結構驗證 | 確認 JSON 欄位符合各模組預期 Schema |
| 欄位層級檢查 | 驗證資料型別、必填欄位與數值範圍 |
| 邊界條件測試 | 空資料集、API 逾時、欄位缺漏或格式錯誤 |
| UI 資料綁定 | 確認資料能正確渲染至表格與排序視圖 |

---

## 🧠 Challenges & Solutions

### 🔸 CORS & API Access Restrictions
**Issue:** Some government open data endpoints restrict cross-origin browser requests, causing fetch failures on the client side.  
**Solution:** Inspected response headers and adjusted fetch options (e.g., `mode`, `credentials`); where CORS was fully blocked, proxied requests or switched to JSONP-compatible endpoints provided by the data platform.

### 🔸 Inconsistent API Response Formats
**Issue:** Different government datasets return data in varying JSON structures, key naming conventions, and character encodings (UTF-8 vs Big5).  
**Solution:** Wrote a per-module normalization layer in JavaScript to map raw API fields to a consistent internal schema before passing data to the render functions.

### 🔸 Asynchronous Data Loading UX
**Issue:** Slow or unpredictable API response times left users with a blank or broken interface.  
**Solution:** Added per-module loading spinners and implemented progressive rendering — table headers and skeleton rows appear immediately while data loads in the background.

### 🔸 Large Dataset Display Performance
**Issue:** Some datasets (e.g., wage tables, job listings) contain hundreds of rows, causing noticeable lag on initial render.  
**Solution:** Applied client-side pagination and deferred sorting — only the current page is rendered to the DOM, reducing layout thrashing on large datasets.

### 🔸 CORS 跨域存取限制
**問題：** 部分政府開放資料端點限制瀏覽器端的跨域請求，導致 fetch 失敗。  
**解決方式：** 檢查回應標頭並調整 fetch 參數（如 `mode`、`credentials`）；遇到完全封鎖 CORS 的情況，改用該資料平台提供的 JSONP 相容端點或透過代理請求處理。

### 🔸 API 回應格式不一致
**問題：** 不同政府資料集的 JSON 結構、欄位命名慣例與字元編碼（UTF-8 vs Big5）差異大。  
**解決方式：** 為各模組撰寫獨立的資料標準化層，將原始 API 欄位對應至統一的內部 Schema，再傳入渲染函式處理。

### 🔸 非同步載入的使用者體驗
**問題：** API 回應速度慢或不穩定，導致畫面空白或顯示異常。  
**解決方式：** 為各模組加入載入動畫，並實作漸進式渲染——表格標頭與骨架列先行顯示，資料在背景載入完成後再填入。

### 🔸 大量資料的顯示效能
**問題：** 部分資料集（如薪資表、職缺清單）包含數百筆資料，初始渲染有明顯延遲。  
**解決方式：** 實作前端分頁與延遲排序，每次僅渲染當前頁面的資料至 DOM，避免大量資料造成版面重排的效能問題。

---

## 📈 What This Project Demonstrates

- Consuming real-world government Open Data APIs (not mock data)
- Handling async data flows and cross-origin constraints in a pure frontend environment
- Data parsing, normalization, and validation across 10+ structurally different JSON APIs
- Building a scalable multi-page portal with modular, maintainable JavaScript
- Static site deployment and hosting via GitHub Pages

- 串接真實政府開放資料 API（非模擬資料）
- 在純前端環境中處理非同步資料流與跨域限制
- 針對 10+ 個結構各異的 JSON API 進行資料解析、標準化與驗證
- 建構可擴展的多頁式入口網站，採模組化、易維護的 JavaScript 架構
- 使用 GitHub Pages 進行靜態網站部署與上線

---

## 🎯 Future Improvements

- [ ] Keyword search and advanced filtering across datasets
- [ ] Data visualization (trend charts for salary and employment statistics)
- [ ] localStorage caching to reduce redundant API calls
- [ ] Mobile-responsive layout improvements
- [ ] Automated API health checks and regression test reports
- [ ] English language support

- [ ] 新增關鍵字搜尋與進階篩選功能
- [ ] 實作資料視覺化（薪資趨勢、就業統計圖表）
- [ ] 整合 localStorage 快取，減少重複 API 請求
- [ ] 改善行動裝置響應式排版
- [ ] 建立自動化 API 健康檢查與回歸測試報告
- [ ] 新增英文版介面

---

## 👨‍💻 Author

**Kanyun Lee**

---

## ⭐ Notes for Recruiters

This project focuses on **real API integration and frontend data engineering**, not UI aesthetics. Key highlights:

- **Real data, real constraints** — all 10 modules pull from live government APIs with varying formats and reliability
- **Async handling** — each page manages its own fetch lifecycle, error state, and rendering pipeline independently
- **Data validation mindset** — response integrity is verified before any data reaches the UI layer
- **Modular design** — each `app0X.html` is a self-contained module that can be extended or replaced without affecting others

- 本專案核心重點在於 **真實 API 串接與前端資料工程**，而非單純的 UI 設計。主要亮點如下：

- **真實資料，真實限制** — 10 個模組均串接政府正式 API，各自面對不同的格式與穩定性挑戰
- **非同步處理能力** — 每個頁面獨立管理自身的 fetch 生命週期、錯誤狀態與渲染流程
- **資料驗證思維** — 所有資料在進入 UI 渲染層之前，皆經過回應完整性驗證
- **模組化設計** — 每個 `app0X.html` 為獨立模組，可單獨擴充或替換，不影響其他頁面
