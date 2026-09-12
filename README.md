# GitHub Pages + Supabase 共用版

## 為什麼之前不同人看到不同資料？
舊版在沒有設定 Supabase 時會自動使用瀏覽器 localStorage，所以每台裝置各自一份資料。

本版已修正：
**沒有設定 Supabase 時不再儲存本機預約資料，而是直接提示尚未設定。**
所有預約正式寫入同一個 Supabase 資料庫。

## 安裝
1. 建立 Supabase Project。
2. SQL Editor 執行 `supabase_schema.sql`。
3. 複製 `config.js`。
4. 填入 Supabase Project URL 和公開 anon/publishable key。
5. 將 `index.html`、`config.js`、`supabase_schema.sql`、README 上傳 GitHub。
6. GitHub Settings → Pages → main / root。
7. 所有人使用同一個 GitHub Pages 網址。

## 注意
不要把 Supabase `service_role` key 放到 GitHub。前端只能使用公開 anon/publishable key。

目前 SQL 為測試用公開 RLS；正式公司環境應加入 Supabase Auth 與角色權限。


## 行事曆版修改
- 新增月曆行事曆，可查看每日施工排程。
- 週日固定休息，行事曆標示「週日休息」，不安排施工。
- 洗車打蠟施工日：交車日前 1 個工作日。
- 全車鍍膜施工日：交車日前 2 個工作日。
- 週六可排程；2026 年政府公告假日/補假日會跳過。
- 延續 V2 的 Supabase 共用資料庫架構，不需重新建立資料表。
