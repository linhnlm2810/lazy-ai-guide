# Tổng hợp: Cách setup Đội AI Hermes trên máy tính cá nhân

## Bối cảnh
Người dùng (Linhnlm) đã setup một đội 7 bot AI hoạt động 24/7 trên Discord, chạy trên Mac Mini cá nhân — không cần thuê VPS hay server đắt tiền. Mỗi bot đảm nhận một vai trò chuyên biệt, phối hợp với nhau như một team thật.

## Đội hình "Sân 7"

| Vai trò | Model AI | Provider | Nền tảng |
|---------|----------|----------|----------|
| Coordinator (đội trưởng) | Claude Opus 4.6 | cliproxy | Discord + Telegram |
| Developer (lập trình) | GPT 5.5 | cliproxy | Discord |
| Researcher (nghiên cứu) | Gemini Pro Agent | cliproxy | Discord |
| Writer (viết bài) | Claude Sonnet 5 | cliproxy | Discord |
| Reviewer (kiểm duyệt) | Grok 4.6 | Kira API | Discord |
| Designer (thiết kế) | Kira 3.5 Flash | Kira API | Discord |
| QA (kiểm thử) | DeepSeek V4 Pro | Kira API | Discord |

## Cách hoạt động
- 1 bot Coordinator điều phối toàn bộ: nhận yêu cầu từ người dùng, phân việc cho bot chuyên môn, kiểm tra kết quả
- 6 bot con chạy chế độ "mention_only" — chỉ phản hồi khi được gọi tên, không tự ý nói
- Tất cả giao tiếp qua Discord server riêng (guild "Đội Hermes")
- Coordinator chạy cả Discord + Telegram (để người dùng nhắn từ điện thoại)

## Chuẩn bị cần thiết

### Phần cứng
- 1 máy tính chạy liên tục (Mac Mini, laptop cũ, PC để bàn đều được)
- Kết nối internet ổn định

### Tài khoản cần tạo
1. **Discord** — tạo server riêng, tạo bot application cho mỗi bot (Discord Developer Portal)
2. **API key AI** — đăng ký tài khoản lấy API key:
   - cliproxy (hoặc OpenRouter, Anthropic, OpenAI trực tiếp) cho 4 bot
   - Kira API (kiraai.vn) cho 3 bot — có model miễn phí
3. **Hermes Agent** — cài phần mềm Hermes (miễn phí, mã nguồn mở)
4. **Telegram Bot** (tuỳ chọn) — tạo bot qua BotFather để nhắn từ điện thoại

### Các bước setup
1. Cài Hermes Agent trên máy tính
2. Tạo Discord server + tạo 7 bot trên Discord Developer Portal
3. Cấu hình từng bot: gán model AI, provider, vai trò (system prompt)
4. Kết nối Telegram (tuỳ chọn)
5. Chạy gateway — tất cả bot lên mạng cùng lúc
6. Test: mention bot trên Discord, xem phản hồi

## So sánh với VPS

### Giống nhau
- Chạy 24/7, luôn sẵn sàng phục vụ
- Chạy nhiều "dịch vụ" cùng lúc (7 bot = 7 worker)
- Truy cập từ xa qua internet (Discord/Telegram)
- Tự động hoá công việc (cron job, script)

### Khác nhau
- **VPS**: Thuê máy ảo trên cloud, trả phí hàng tháng, cần kiến thức Linux/server
- **Setup này**: Dùng máy tính có sẵn tại nhà, không tốn phí thuê server, chỉ tốn phí API (có free tier)
- **VPS**: Cần SSH, command line, quản trị server
- **Setup này**: Cài 1 lần, quản lý qua Discord — giao diện quen thuộc

### Kết luận so sánh
Setup này thực chất biến máy tính cá nhân thành một "VPS tại nhà" chuyên chạy đội AI. Không cần thuê server, không cần biết Linux — chỉ cần 1 máy tính chạy liên tục và vài tài khoản API.

## Ưu điểm
1. **Tiết kiệm chi phí** — không thuê VPS (tiết kiệm $10-50/tháng), chỉ trả API theo dùng
2. **Dễ quản lý** — nói chuyện với bot qua Discord, không cần mở terminal
3. **Linh hoạt** — đổi model AI bất kỳ lúc nào, thêm/bớt bot tuỳ ý
4. **Chuyên môn hoá** — mỗi bot giỏi 1 việc, kết quả tốt hơn 1 bot làm tất cả
5. **Làm việc từ xa** — nhắn Discord/Telegram từ điện thoại, bot vẫn chạy ở nhà
6. **Mã nguồn mở** — Hermes miễn phí, cộng đồng hỗ trợ

## Nhược điểm & Lưu ý
1. **Máy phải chạy liên tục** — tắt máy = bot offline (giải pháp: Mac Mini tiết kiệm điện ~10W)
2. **Internet phải ổn** — mất mạng = bot mất kết nối
3. **Chi phí API** — model mạnh = tốn tiền (giải pháp: dùng model free cho bot ít quan trọng)
4. **Cần thời gian setup ban đầu** — lần đầu mất 1-2 tiếng cấu hình
5. **Cập nhật thủ công** — cần update Hermes khi có phiên bản mới
6. **Bảo mật** — API key lưu trên máy, cần giữ máy an toàn
