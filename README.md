## 🚀 Installation Guide

### 🧬 Clone with Submodules

    git clone --recurse-submodules git@github.com:MiipisSus/MiGoJob.git
    cd MiGoJob

## 🐳 Setup with Docker (Recommended)

1. 複製 `.env.example` 為 `.env`：

   ```
   cp .env.example .env
   ```

2. 可選：根據需求自定義 .env 設定。

3. 建立並啟動專案：

   ```
   docker-compose up --build
   ```

   預設服務包含：Frontend + Backend (Django) + PostgreSQL

4. 建立初始資料（Optional）

   ```
   docker compose exec backend /bin/bash
   python3 manage.py seed_data
   ```

## 🛠 Manual Setup

### 📦 Backend

    ⚠️ 請先手動安裝 PostgreSQL 並啟動資料庫服務。

1. 進入 backend 資料夾：

   ```
   cd backend
   ```

2. 複製 .env.example 為 .env 並根據需求修改。

3. 安裝依賴：

   ```
   pip install -r requirements.txt
   ```

4. 手動在 PostgreSQL 建立資料庫與使用者，對應 .env 內的 DB_NAME 和 DB_USERNAME。

5. 遷移資料庫：

   ```
   python3 manage.py migrate
   ```

6. 啟動後端伺服器：

   ```
   uvicorn MiGoJob.asgi:application --host 0.0.0.0 --port 8000
   ```

🌐 Frontend

1. 進入 frontend 資料夾：

   ```
   cd frontend
   ```

2. 安裝依賴並啟動本地開發伺服器：

   ```
   npm install
   npm run dev
   ```
