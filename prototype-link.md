# Prototype Link
## Option A — User-led

- File: [prototype-user-led.html](prototype-user-led.html)
- Cơ chế: **user-led với 2 input**, cả hai đều do user chủ động khởi tạo, AI không đoán trước:
  1. **Select-to-ask** — user tự bôi đen (select) đúng đoạn/cụm từ trên slide → nút nổi "Tôi vẫn chưa hiểu" hiện cạnh vùng chọn → bấm vào, một khối hội thoại mới xuất hiện trong panel bên phải để xác nhận đoạn đã chọn.
  2. **Browse khái niệm** — user bấm nút cố định "Tôi vẫn chưa hiểu" dưới slide → một khối hội thoại mới xuất hiện bên phải, hiện danh sách khái niệm quan trọng trong slide để chọn, hoặc mô tả tiếp bằng ô text.
- Có thể lặp lại nhiều lần (bôi đen nhiều đoạn khác nhau) — mỗi lần tạo thêm một khối hội thoại mới trong panel bên phải, các khối trước vẫn hiển thị và cuộn được.

## Option B — Collaborative

- File: [prototype-collaborative.html](prototype-collaborative.html)
- Trigger: giả lập ở topbar (⏱ Giả lập: đã xem slide >15 phút), mô phỏng cho việc AI phát hiện dấu hiệu mà không cần chờ thật.
- Cơ chế: AI **hỏi xác nhận trước khi làm** — "Bạn đang gặp vấn đề gì không?"
  - Chọn **Không** → AI phản hồi ngắn và dừng lại, không có gì xảy ra thêm.
  - Chọn **Có** → AI hiện danh sách khái niệm có thể bị miss (kèm "Khác" để tự mô tả/chat) → user chọn/gõ → AI tổng hợp một đoạn kiến thức liên quan → AI đưa nhận xét, cho user chọn **"đã học"** (AI tự gửi kèm nguồn ngay trong bài giảng) hoặc **"chưa học"** (AI hỏi tiếp có muốn research ngoài bài giảng không → Có: tổng hợp + nguồn ngoài; Không: kết thúc luồng).
- Toàn bộ chuỗi hỏi–đáp này hiện dần thành các khối hội thoại nối tiếp nhau trong panel bên phải, slide bên trái không bị che hay đổi màn hình.

## Option C — Proactive

- File: [prototype-proactive.html](prototype-proactive.html)
- Trigger: chỉ có nút giả lập ở topbar (⏱ Giả lập: đã xem slide >15 phút).
- Cơ chế: AI **tự tổng hợp và gửi luôn** một đoạn kiến thức liên quan mà AI đoán user có thể đang thiếu, kèm câu hỏi xác nhận ngay trong cùng một khối hội thoại (không hỏi trước khi hành động như Option B) → user xác nhận **"Đúng"** hoặc **"Khác"** (kèm chat mô tả thêm nếu muốn) → AI đưa nhận xét, cùng hai lựa chọn **"đã học"/"chưa học"** và nhánh research ngoài bài giảng giống Option B.
- Control/recovery: có nút "Đóng, mình tự đọc lại" ngay trong khối tin nhắn đầu tiên để dismiss sớm.

## So sánh nhanh 3 option khi test

| | A — User-led | B — Collaborative | C — Proactive |
|---|---|---|---|
| Ai khởi động | User (bôi đen / bấm nút) | AI (sau khi phát hiện dấu hiệu) | AI (sau khi phát hiện dấu hiệu) |
| AI hỏi trước khi đưa nội dung? | Không cần hỏi — user đã tự chỉ rõ | Có — hỏi "gặp vấn đề gì không?" trước, rồi mới hỏi chọn khái niệm | Không — AI đưa nội dung ngay trong tin nhắn đầu tiên, hỏi xác nhận sau |
| Điểm dismiss sớm nhất | Bất kỳ lúc nào (không hành động gì) | Ngay bước thông báo đầu tiên ("Không") | Sau khi đã thấy nội dung AI gửi ("Đóng, mình tự đọc lại") |
