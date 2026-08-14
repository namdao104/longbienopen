# Long Biên Tournament — Webapp thống kê

Webapp thống kê giải cầu lông Long Biên Tournament (LBO). Đọc dữ liệu trực tiếp từ Supabase mỗi lần mở trang — không cần deploy lại khi có trận đấu mới.

## Cấu trúc
- `index.html` — toàn bộ app (React đã bundle sẵn qua esbuild, single-file, không cần build step).

## Deploy

### Vercel (khuyến nghị)
1. Import repo này vào [vercel.com](https://vercel.com) → New Project.
2. Framework Preset: **Other**.
3. Build Command: để trống.
4. Output Directory: để trống (mặc định gốc repo).
5. Deploy.

### Netlify
Kéo thả `index.html` vào [app.netlify.com/drop](https://app.netlify.com/drop), hoặc connect repo tương tự như Vercel.

## Backend
- Database: Supabase (project id `yjhasbklswwzuyruwxwd`)
- Bảng chính: `matches`, `ga_contributions`, `ga_expenses`, `gold_member_balance`, `gold_member_deductions`
- Webapp gọi thẳng Supabase REST endpoint bằng `fetch()` + apikey header (không dùng SDK `supabase-js` — gây lỗi trong một số sandbox preview).

## Cập nhật dữ liệu
Trận đấu mới được ghi trực tiếp vào Supabase (qua Claude + MCP connector, hoặc SQL Editor thủ công) — không cần sửa hay deploy lại file này.
