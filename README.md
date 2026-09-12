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


### V3 更新
- 全車鍍膜：交車日前 2 個工作日排程。
- 洗車打蠟：交車日前 1 個工作日排程。
- 已排程／施工中／QC檢查／已完工四格分色。
- 標題更新為「大桐桃園-新車美容鍍膜預約」。
- 排程跳過週六、週日及 2026 年政府行政機關辦公日曆表所列假日/補假日。
