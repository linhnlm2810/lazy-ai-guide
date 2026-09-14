# Biến Máy Tính Thành Đội AI — Hướng Dẫn Setup Hermes Team

## Overview
Hướng dẫn từng bước cách biến 1 máy tính cá nhân thành trung tâm điều hành đội 7 bot AI chuyên biệt trên Discord. So sánh với VPS truyền thống.

## Learning Objectives
The viewer will understand:
1. Cần chuẩn bị gì để bắt đầu (phần cứng + tài khoản)
2. Các bước setup từ A đến Z
3. Đội bot hoạt động như thế nào
4. So sánh với VPS — giống/khác gì
5. Ưu điểm và lưu ý khi dùng

---

## Section 1: Ý tưởng — Máy tính của bạn = "Văn phòng AI"

**Key Concept**: Thay vì thuê server đắt tiền, bạn dùng chính máy tính ở nhà làm nơi chạy đội AI.

**Content**:
- 1 máy tính cá nhân (Mac Mini, laptop, PC) chạy liên tục
- 7 bot AI, mỗi bot 1 chuyên môn: lập trình, nghiên cứu, viết bài, thiết kế, kiểm duyệt, kiểm thử
- 1 bot "đội trưởng" (Coordinator) điều phối tất cả
- Giao tiếp qua Discord — app chat quen thuộc
- Nhắn từ điện thoại qua Telegram cũng được

**Visual Element**:
- Type: illustration
- Subject: Hình ngôi nhà/phòng làm việc với 1 máy tính ở giữa, xung quanh có 7 nhân vật nhỏ (stick figure) đại diện 7 bot, mỗi người cầm 1 công cụ khác nhau
- Treatment: IKEA line art, minimal

**Text Labels**:
- Headline: "💡 Ý TƯỞNG"
- Subhead: "Máy tính của bạn = Văn phòng AI"
- Labels: "Coordinator", "Developer", "Researcher", "Writer", "Reviewer", "Designer", "QA"

---

## Section 2: Chuẩn bị — 3 thứ cần có

**Key Concept**: Chỉ cần 3 thứ: 1 máy tính, tài khoản Discord, và API key AI.

**Content**:
- 🖥️ MÁY TÍNH: Bất kỳ máy nào chạy được liên tục. Mac Mini là lý tưởng (nhỏ, tiết kiệm điện ~10W). Laptop cũ, PC đều OK.
- 💬 DISCORD: Tạo 1 server riêng (miễn phí) + tạo bot trên Discord Developer Portal
- 🔑 API KEY: Đăng ký tài khoản AI provider để lấy "chìa khoá" truy cập AI:
  - cliproxy / OpenRouter — nhiều model, 1 key dùng được nhiều AI
  - Kira API (kiraai.vn) — có model miễn phí

**Visual Element**:
- Type: 3 icons with labels
- Subject: Computer icon, Discord logo icon, Key icon — arranged vertically
- Treatment: Simple line art, numbered 1-2-3

**Text Labels**:
- Headline: "🛒 CHUẨN BỊ"
- Labels: "1. Máy tính chạy liên tục", "2. Tài khoản Discord + Bot", "3. API Key (chìa khoá AI)"

---

## Section 3: Bước 1 — Cài Hermes Agent

**Key Concept**: Hermes là phần mềm miễn phí biến máy tính thành trung tâm quản lý AI.

**Content**:
- Hermes Agent = phần mềm mã nguồn mở (miễn phí)
- Cài bằng 1 dòng lệnh duy nhất
- Hỗ trợ Mac, Windows, Linux
- Sau khi cài, chạy "hermes setup" để cấu hình lần đầu

**Visual Element**:
- Type: step illustration
- Subject: Terminal window with command line, arrow pointing to Hermes logo
- Treatment: Line art terminal icon

**Text Labels**:
- Headline: "BƯỚC 1"
- Subhead: "Cài Hermes Agent"
- Label: "curl ... | bash → hermes setup"

---

## Section 4: Bước 2 — Tạo đội bot trên Discord

**Key Concept**: Tạo 7 bot application trên Discord, mỗi bot một tên và vai trò riêng.

**Content**:
- Vào Discord Developer Portal (discord.com/developers)
- Tạo 7 Application → mỗi cái = 1 bot
- Đặt tên theo vai trò: Coordinator, Developer, Researcher, Writer, Reviewer, Designer, QA
- Copy token (mật khẩu) của mỗi bot
- Invite tất cả vào server Discord riêng của bạn

**Visual Element**:
- Type: diagram
- Subject: Discord developer portal → 7 bot icons flowing into 1 server
- Treatment: Line art with arrows

**Text Labels**:
- Headline: "BƯỚC 2"
- Subhead: "Tạo 7 Bot trên Discord"
- Labels: "Developer Portal → 7 Bot → 1 Server"

---

## Section 5: Bước 3 — Gán "não" AI cho mỗi bot

**Key Concept**: Mỗi bot được gán 1 model AI khác nhau tuỳ theo công việc.

**Content**:
- Coordinator (đội trưởng): Claude Opus — thông minh nhất, biết điều phối
- Developer: GPT 5.5 — giỏi code
- Researcher: Gemini Pro — giỏi tìm kiếm, tổng hợp
- Writer: Claude Sonnet — viết hay
- Reviewer: Grok — kiểm duyệt chất lượng
- Designer: Kira Flash — thiết kế nhanh
- QA: DeepSeek — kiểm thử kỹ lưỡng

**Visual Element**:
- Type: matching diagram
- Subject: 7 bot icons, each with an arrow pointing to their AI model brain icon
- Treatment: Two columns connected by arrows

**Text Labels**:
- Headline: "BƯỚC 3"
- Subhead: "Gán 'Não' AI Cho Mỗi Bot"
- Labels: Bot names on left, Model names on right

---

## Section 6: Bước 4 — Bật đội lên!

**Key Concept**: Chạy 1 lệnh duy nhất, tất cả 7 bot online cùng lúc trên Discord.

**Content**:
- Chạy Hermes gateway → tất cả bot lên mạng
- Test: mention @Coordinator trên Discord
- Bot phản hồi = thành công!
- Coordinator tự phân việc cho bot khác khi cần

**Visual Element**:
- Type: illustration
- Subject: Power button being pressed → 7 bot icons light up → Discord chat bubble showing "Xin chào!"
- Treatment: Sequence with arrows

**Text Labels**:
- Headline: "BƯỚC 4"
- Subhead: "Bật đội & Test"
- Label: "hermes gateway → 7 bot online → ✅ Xong!"

---

## Section 7: Cách đội hoạt động

**Key Concept**: Coordinator nhận lệnh từ bạn, tự phân việc cho bot chuyên môn, kiểm tra kết quả rồi trả về.

**Content**:
- Bạn nhắn tin cho Coordinator trên Discord (hoặc Telegram)
- Coordinator phân tích yêu cầu → gọi đúng bot chuyên gia
- Bot chuyên gia làm việc → trả kết quả
- Reviewer kiểm duyệt chất lượng
- Coordinator tổng hợp → gửi lại cho bạn
- Bạn không cần biết bot nào đang làm gì — chỉ cần nói với đội trưởng

**Visual Element**:
- Type: flow diagram
- Subject: User → Coordinator → [Developer/Researcher/Writer/Designer] → Reviewer → User
- Treatment: Hub-spoke with directional arrows

**Text Labels**:
- Headline: "⚙️ CÁCH HOẠT ĐỘNG"
- Labels: "Bạn → Đội trưởng → Chuyên gia → Kiểm duyệt → Bạn"

---

## Section 8: So sánh với VPS

**Key Concept**: Setup này giống VPS ở chỗ chạy 24/7 và truy cập từ xa, nhưng đơn giản và rẻ hơn nhiều.

**Content**:
GIỐNG:
- Chạy 24/7, luôn sẵn sàng
- Chạy nhiều "dịch vụ" cùng lúc
- Truy cập từ xa qua internet
- Tự động hoá công việc

KHÁC:
- VPS: Thuê máy trên cloud, $10-50/tháng, cần biết Linux
- Setup này: Dùng máy có sẵn, $0 tiền server, quản lý qua Discord

**Visual Element**:
- Type: split comparison
- Subject: Left side "VPS" with cloud server icon, Right side "Hermes" with home computer icon
- Treatment: Two columns, checkmarks and X marks

**Text Labels**:
- Headline: "🔄 SO SÁNH VỚI VPS"
- Left: "VPS truyền thống"
- Right: "Setup tại nhà"

---

## Section 9: Ưu điểm & Lưu ý

**Key Concept**: Tiết kiệm, linh hoạt, dễ quản lý — nhưng cần máy chạy liên tục và internet ổn.

**Content**:
ƯU ĐIỂM:
- ✅ Tiết kiệm — không thuê VPS, chỉ trả API theo dùng
- ✅ Dễ quản lý — nói chuyện với bot qua Discord
- ✅ Linh hoạt — đổi model AI bất kỳ lúc nào
- ✅ Chuyên môn hoá — mỗi bot giỏi 1 việc
- ✅ Làm việc từ xa — nhắn từ điện thoại

LƯU Ý:
- ⚠️ Máy phải chạy liên tục — tắt = bot offline
- ⚠️ Internet phải ổn — mất mạng = mất kết nối
- ⚠️ Model mạnh = tốn tiền API (dùng model free cho bot phụ)
- ⚠️ Lần đầu setup mất 1-2 tiếng

**Visual Element**:
- Type: two lists with icons
- Subject: Green checkmarks for pros, yellow warning triangles for cons
- Treatment: Clean list format

**Text Labels**:
- Headline: "📊 ƯU ĐIỂM & LƯU Ý"
- Left: "Ưu điểm"
- Right: "Lưu ý"

---

## Data Points (Verbatim)
- "7 bot AI, 1 coordinator + 6 chuyên gia"
- "Mac Mini tiết kiệm điện ~10W"
- "Tiết kiệm $10-50/tháng so với thuê VPS"
- "Lần đầu mất 1-2 tiếng cấu hình"
- "4 bot qua cliproxy, 3 bot qua Kira API"
- "Hermes Agent — mã nguồn mở, miễn phí"

---

## Design Instructions

### Style Preferences
- IKEA manual style: clean black line art on white/cream background
- Red accents for warnings/important notes
- Blue accents for highlights/links
- Stick figures for human elements
- Minimal text, mostly icons and labels

### Layout Preferences
- Vertical linear progression (portrait 9:16)
- Numbered steps flowing top to bottom
- Clear connectors/arrows between steps
- Comparison section uses split layout
- Final section uses two-column pros/cons

### Other Requirements
- Vietnamese language throughout
- No jargon — simple everyday words
- Visual metaphors (office, team, brain) over technical diagrams
- Target: Facebook/Instagram sharing
