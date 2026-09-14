# Setup Flow — Hermes AI Team
## Dùng để tạo prompt tự động

### Prerequisites (môi trường cần có trước)
1. macOS / Linux / Windows (WSL)
2. Terminal access
3. Ít nhất 1 AI subscription: Claude Max/Pro, ChatGPT Plus/Pro, Gemini, hoặc Grok
4. Tài khoản Discord (miễn phí)

### Flow chính (thứ tự bắt buộc)

```
PHASE 1: PROXY LAYER (CLIProxyAPI)
├── 1.1 Kiểm tra OS → chọn lệnh cài phù hợp
├── 1.2 Cài CLIProxyAPI
│   ├── macOS: brew tap router-for-me/tap && brew install cliproxyapi
│   ├── Linux/WSL: curl -fsSL https://cli-proxy.dev/install.sh | sh
│   └── Windows: tải .exe từ GitHub Releases
├── 1.3 Đăng nhập AI provider (tuỳ user có gì)
│   ├── cliproxyapi --claude-login
│   ├── cliproxyapi --openai-login
│   ├── cliproxyapi --gemini-login
│   └── cliproxyapi --grok-login
├── 1.4 Khởi động CLIProxy
│   ├── macOS: brew services start cliproxyapi
│   ├── Linux: systemctl --user enable --now cliproxyapi.service
│   └── Windows: cli-proxy-api.exe --config config.yaml
└── 1.5 Verify: curl http://localhost:8317/v1/models → phải trả về danh sách model

PHASE 2: HERMES AGENT
├── 2.1 Cài Hermes Agent
│   └── curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash
├── 2.2 Setup wizard
│   ├── hermes setup
│   ├── Provider: custom / OpenAI-compatible
│   ├── Base URL: http://localhost:8317/v1
│   ├── API Key: not-needed
│   └── Model: (tuỳ user đăng nhập provider nào ở 1.3)
├── 2.3 Verify: hermes chat -q "Xin chào" → phải nhận được phản hồi
└── 2.4 (Tuỳ chọn) Kết nối Telegram: hermes gateway setup → chọn Telegram

PHASE 3: DISCORD
├── 3.1 Tạo Discord Server (nếu chưa có)
├── 3.2 Tạo Bot trên Discord Developer Portal
│   ├── discord.com/developers/applications → New Application
│   ├── Bot tab → Reset Token → COPY NGAY
│   ├── Bật 3 Privileged Gateway Intents:
│   │   ├── Presence Intent
│   │   ├── Server Members Intent
│   │   └── Message Content Intent
│   ├── OAuth2 → scope: bot → permissions:
│   │   ├── Send Messages, Read Message History
│   │   ├── Embed Links, Attach Files
│   │   ├── Use Slash Commands, Add Reactions
│   │   ├── Manage Messages, Create Public Threads
│   │   └── Send Messages in Threads, Manage Threads
│   └── Copy invite URL → mời bot vào server
├── 3.3 Lấy User ID (Developer Mode → Copy User ID)
├── 3.4 Cấu hình Hermes + Discord
│   ├── hermes gateway setup → chọn Discord → paste token + user ID
│   └── Hoặc thủ công: thêm vào ~/.hermes/.env
│       ├── DISCORD_BOT_TOKEN=...
│       ├── DISCORD_ALLOWED_USERS=...
│       └── DISCORD_HOME_CHANNEL=...
├── 3.5 Khởi động: hermes gateway start
└── 3.6 Verify: mention @bot trên Discord → phải nhận phản hồi

PHASE 4: MỞ RỘNG ĐỘI (tuỳ chọn)
├── 4.1 Tạo profile mới: hermes profile create <tên>
├── 4.2 Cấu hình: hermes -p <tên> setup
├── 4.3 Thêm Discord bot token vào profile .env
└── 4.4 Chạy tất cả: hermes gateway start --all
```

### Điểm cần hỏi người dùng (interactive)
- Đang dùng AI nào? (Claude/GPT/Gemini/Grok)
- Đã có Discord server chưa?
- Muốn bao nhiêu bot?
- Muốn kết nối Telegram không?

### Điểm cần check (preconditions)
- brew installed? (macOS)
- curl available?
- Node.js / Python available? (Hermes cần Python)
- Có quyền admin trên máy?
- Port 8317 có bị chiếm không?

### Lưu ý bảo mật
- Token AI lưu trong ~/.cli-proxy-api/ → KHÔNG share
- Discord bot token lưu trong ~/.hermes/.env → KHÔNG share
- localhost:8317 là địa chỉ mặc định, chỉ truy cập nội bộ
