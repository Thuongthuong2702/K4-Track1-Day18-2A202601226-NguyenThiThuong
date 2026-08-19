# Prototype Feedback Note 

## Tester 1: NGUYỄN VIỆT HẢI - 2A202601656

**Tester/context:** Đã có kinh nghiệm dùng VLearn — thao tác trên cả 3 prototype khá thuần thục, không hỏi lại cách dùng trong lúc test.

| Observation | Note |
|---|---|
| First action | Đọc slide bình thường → nhận ra chỗ có định nghĩa mới, câu chưa rõ nghĩa → chủ động bôi đen đúng đoạn đó rồi đặt câu hỏi cho AI (đúng luồng lối vào #1 của A: bôi đen → nút nổi "Tôi vẫn chưa hiểu"). |
| Chỗ dừng, do dự hoặc hiểu sai | Không do dự ở bước thao tác — điểm dừng duy nhất là dừng đọc khi gặp câu định nghĩa chưa rõ, đây là điểm dừng do nội dung chứ không phải do không hiểu UI. |
| Evidence được đọc hay bỏ qua | Không ghi nhận riêng |
| Cách tester sửa hoặc lấy lại control | Tự bôi đen đúng đoạn không hiểu để hỏi trực tiếp, thay vì chờ AI đoán hoặc lật giở danh sách khái niệm |
| Option được chọn | A |
| Lý do và trade-off | Thích A vì được chủ động tìm hiểu kiến thức — chỉ chọn đúng phần mình quan tâm, không muốn AI tự dự đoán thay mình (đề cao "control" cá nhân). Cho rằng việc dừng lâu ở một slide (dấu hiệu B/C dùng để trigger) chưa chắc là dấu hiệu "chưa hiểu" — có thể do đang bận việc khác — nên AI tự bật lên (B, C) là không cần thiết và khiến tester có xu hướng skip thông báo đó. |
| Evidence chống lại kỳ vọng của nhóm | Giả định nền của B/C — ">15 phút xem slide = tín hiệu đáng tin để AI chủ động can thiệp" — bị tester nghi ngờ là false positive phổ biến, không phải lỗi thao tác nhưng làm giảm giá trị của cơ chế proactive/collaborative. |

## Tester 2: HUỲNH THỊ HẢI CHÂU - 2A202601912

**Tester/context:** Đã có kinh nghiệm dùng VLearn — tương tự Tester 1, việc làm quen với luồng thao tác diễn ra nhanh.

| Observation | Note |
|---|---|
| First action | Đọc slide xem trên slide có gì |
| Chỗ dừng, do dự hoặc hiểu sai | Không đáng kể, nhờ đã quen giao diện dạng VLearn |
| Evidence được đọc hay bỏ qua | Không ghi nhận riêng |
| Cách tester sửa hoặc lấy lại control | Chọn thẳng phương án A để tự kiểm soát thay vì chờ AI |
| Option được chọn | A |
| Lý do và trade-off | Cùng lý do với Tester 1: thích được chủ động, chỉ muốn chọn đúng phần mình quan tâm, cá nhân ưu tiên cảm giác control hơn là để AI dự đoán hộ. Đồng tình rằng dừng lâu ở slide không nhất thiết là "chưa hiểu" — có thể do lý do khác (bận việc khác) — nên thông báo tự động của AI (B, C) là dư thừa và dễ bị bỏ qua/skip. **Thêm:** hoài nghi về độ chính xác của AI trong việc "bắt đúng tín hiệu" — lo ngại AI sẽ chủ động hỏi/gợi ý đúng vào chỗ mà bản thân không hề thắc mắc, tức là đoán sai trọng tâm chứ không chỉ sai thời điểm. |
| Evidence chống lại kỳ vọng của nhóm | Củng cố lại quan sát của Tester 1 — hai tester độc lập cùng nêu chung một lý do phản đối tín hiệu ">15 phút" của B/C, không phải trùng hợp cá nhân đơn lẻ. Ngoài ra Tester 2 chỉ ra thêm một lớp rủi ro khác của B/C: ngay cả khi AI đúng thời điểm can thiệp, nội dung AI đoán ra cũng có thể sai — đây là rủi ro ở tầng "AI hiểu đúng cái user cần" chứ không chỉ ở tầng "khi nào nên hỏi". |

