Eliza là gì?
Eliza là một framework (khung phát triển) giúp bạn dễ dàng xây dựng, triển khai và quản lý các hệ thống “multi-agent” (nhiều tác nhân AI) trên nhiều nền tảng, như Discord, Telegram, v.v. Dự án này giúp bạn tạo ra chatbot, trợ lý tự động, NPC game, hệ thống xử lý nghiệp vụ doanh nghiệp, v.v. chỉ với một vài thao tác.

Tính năng nổi bật
Kết nối đa nền tảng: Dễ dàng kết nối với Discord, Telegram, Farcaster,… và còn nhiều nền tảng khác.

Hỗ trợ mọi mô hình AI: Dùng được các mô hình như Llama, Grok, OpenAI, Anthropic, Gemini,…

Giao diện quản lý hiện đại: Có dashboard trực quan để quản lý agent và nhóm agent.

Giao tiếp thời gian thực: Nhắn tin với các agent, quản lý kênh, tin nhắn,… rất mượt.

Nhóm agent & quản lý linh hoạt: Tạo, quản lý nhiều agent và nhóm agent dễ dàng.

Tương tác tài liệu: Nạp và trao đổi với tài liệu của bạn.

Bộ nhớ lưu trữ mạnh: Lưu trữ dữ liệu, tài liệu, và trí nhớ của agent để truy xuất lại bất kỳ lúc nào.

Dễ mở rộng: Có thể tự viết plugin, hành động, client riêng.

Dễ sử dụng: Thiết lập và chạy rất nhanh.

Eliza dùng để làm gì?
Chatbot: Tạo ra bot trò chuyện trên nhiều nền tảng.

Tác nhân tự động: Dùng agent để tự động hóa quy trình.

Xử lý nghiệp vụ doanh nghiệp: Tự động xử lý quy trình kinh doanh.

NPC Game: Tạo NPC có AI cho game.

Trading AI: Làm trợ lý/agent giao dịch.

Cách bắt đầu nhanh với Eliza
1. Cài đặt các phần mềm cần thiết
Node.js (bản 23 trở lên)

bun (trình quản lý package, siêu nhanh)

(Nếu dùng Windows): Cần cài WSL 2

2. Cài ElizaOS CLI
bash
Sao chép
Chỉnh sửa
bun install -g @elizaos/cli
elizaos --version         # Kiểm tra cài đặt
elizaos --help            # Xem các lệnh CLI
3. Tạo Project Đầu Tiên
bash
Sao chép
Chỉnh sửa
elizaos create my-agent   # Tạo project mới, sẽ có giao diện hỏi thông tin
Gợi ý cho người mới:

Database: Chọn pglite (gọn nhẹ, không phải setup nhiều)

Model provider: Chọn openai (ổn định, dễ dùng nhất)

Project type: Chọn project

4. Cấu hình agent
Vào thư mục project vừa tạo, chỉnh sửa file môi trường:

bash
Sao chép
Chỉnh sửa
cd my-agent
elizaos env edit-local   # Sửa file .env nhanh
# hoặc tự sửa file .env
nano .env
Biến môi trường quan trọng:

bash
Sao chép
Chỉnh sửa
OPENAI_API_KEY=your_api_key_here
LOG_LEVEL=info
DISCORD_APPLICATION_ID=your_discord_app_id
DISCORD_API_TOKEN=your_discord_bot_token
Chỉ cần nhập key OpenAI là đủ chạy agent, các dòng khác chỉ cần khi kết nối Discord, debug,…

5. Khởi động agent
bash
Sao chép
Chỉnh sửa
elizaos start           # Chạy agent lên
# Hoặc chạy ở chế độ debug
LOG_LEVEL=debug elizaos start
Sau khi chạy, bạn vào giao diện web: http://localhost:3000 để quản lý, chat, cấu hình agent.

6. Quy trình phát triển
Chỉnh sửa code: Xong thì build lại và chạy lại:

bash
Sao chép
Chỉnh sửa
bun run build
elizaos start
Chạy test:

bash
Sao chép
Chỉnh sửa
elizaos test
7. Một số lệnh nâng cao
Tạo plugin mới:
elizaos create my-plugin --type plugin

Quản lý agent:
elizaos agent list, elizaos agent start --name "TênAgent"

Xem biến môi trường:
elizaos env list

8. Debug và logging
Điều chỉnh mức độ log:

LOG_LEVEL=error elizaos start (chỉ hiện lỗi)

LOG_LEVEL=info elizaos start (mặc định)

LOG_LEVEL=debug elizaos start (debug chi tiết)

LOG_LEVEL=verbose elizaos start (rất chi tiết)

9. Giao diện Web Quản Lý
Khi đã chạy agent, bạn sẽ có một dashboard rất xịn ở http://localhost:3000:

Quản lý agent và nhóm agent

Thêm, sửa, xóa agent

Chat trực tiếp với agent

Quản lý plugins, bộ nhớ, lịch sử hội thoại,…

Kiến trúc & Thư mục của dự án
Dự án được tổ chức dạng monorepo (nhiều package trong 1 repo) giúp quản lý code hiệu quả:

packages/: chứa code các thành phần chính

app/: UI, app desktop/mobile

core/: Xử lý PDF, logging, xử lý lỗi

plugin-bootstrap/: Xử lý giao tiếp chính giữa agent và user

plugin-sql/: Tích hợp database

cli/: Command-line interface

docs/: Tài liệu chính thức

project-starter/: Template tạo project nhanh

...v.v.

Lưu ý khi phát triển
Thường xuyên chạy test (elizaos test) để đảm bảo code ổn định

Không chia sẻ file .env lên GitHub hoặc chỗ công khai!

Đọc thêm tài liệu trong thư mục docs/ và file AGENTS.md trong repo để hiểu sâu hơn

Tóm tắt cho người mới
Eliza là công cụ giúp bạn làm AI agent (chatbot, trợ lý, NPC,…) một cách nhanh, dễ, chuyên nghiệp, giao diện đẹp, dễ mở rộng, chạy được trên nhiều nền tảng. Không cần giỏi code, chỉ cần cài đúng và làm theo hướng dẫn là có thể thử nghiệm ngay.

Bạn có thể bắt đầu thử ngay bằng các bước:

Cài Node + bun

Cài ElizaOS CLI

Tạo project mới

Thêm OpenAI key

Chạy thử, vào web UI, bắt đầu khám phá!
