# Track1_Day18_MHV_NguyenThiThuong

## 1. Thông tin cá nhân và nhóm

| Thông tin | Nội dung |
|---|---|
| **MHV** | 2A202601226 |
| **Họ và tên** | Nguyễn Thị Thương |
| **Tên nhóm** | MT |
| **Thành viên** | Trương Quang Minh - 2A202601212; Nguyễn Thị Thương - 2A202601226 |
| **Case đã chọn** | Case A — AI Tutor: Diagnostic Refresher |

---

## 2. Hypothesis Problem (Day 18)

> Khi đang học một bài online và gặp một khái niệm/định nghĩa mà mình không nhớ hoặc không hiểu, học viên gặp khó khăn trong việc xác định nên ôn lại kiến thức nào — đặc biệt là không phân biệt được đây là kiến thức cũ (đã học, đang quên) hay kiến thức mới (chưa từng học) — dẫn đến mất 20–30 phút mỗi lần, phần lớn thời gian dành cho việc tìm kiếm lại chứ không phải học.

**Evidence hỗ trợ:** User thực sự bị chặn bởi khái niệm chưa hiểu trong lúc học; mất thời gian tra cứu, giải thích.

**Điều vẫn chưa biết:** Ba cách chia việc user–AI khác nhau (User-led / Collaborative / Proactive) — cách nào giảm thời gian tra cứu mà không làm mất quyền kiểm soát của user.

Chi tiết đầy đủ (bảng so sánh A/B/C, Distance check, Human–AI Decision Table) tại [three-option-design-sheet.md](three-option-design-sheet.md).

---

## 3. Three Solution Options

Cả ba option cùng giải một Hypothesis Problem, cùng target user/situation/task/desired outcome, chỉ khác ở cơ chế Human–AI và ai khởi động tương tác.

| Option | Mô tả ngắn | Prototype |
|---|---|---|
| **A — User-led** | Learner tự khởi tạo: bôi đen đúng đoạn trên slide (select-to-ask), hoặc bấm nút cố định để duyệt danh sách khái niệm quan trọng và tự chọn/mô tả. AI không hành động cho tới khi user xác nhận. | [prototype-user-led.html](prototype-user-led.html) |
| **B — Collaborative** | AI phát hiện dấu hiệu (dừng quá lâu ở một slide) → hỏi xác nhận trước ("Bạn đang gặp vấn đề gì không?") → cùng user xác định đúng khái niệm → đưa nhận xét đã học/chưa học, có nhánh research ngoài bài giảng. | [prototype-collaborative.html](prototype-collaborative.html) |
| **C — Proactive** | AI phát hiện dấu hiệu → tự tổng hợp và gửi luôn nội dung nghi ngờ user đang thiếu, kèm câu hỏi xác nhận trong cùng một bước → cùng nhánh đã học/chưa học như B. | [prototype-proactive.html](prototype-proactive.html) |

Chi tiết trạng thái, trigger giả lập và self-check của từng prototype xem tại [prototype-link.md](prototype-link.md).

---

## 4. Đóng góp của tôi trong nhóm

- **Option phụ trách chính:** Option A
- **Shared context/content:** hỗ trợ chỉnh sửa prototype option B, C; soạn và tổng hợp bài nộp cuối lên github.
- **Human–AI decisions:** Phản biện các quyết định Act/Ask/Don't Act trong Human–AI Decision Table
- **Facilitation:** Soạn kịch bản facilitate khi test A/B/C; trực tiếp facilitate và ghi Feedback Note cho 2 tester (Nguyễn Việt Hải, Huỳnh Thị Hải Châu) theo đúng quy trình: mở đầu → hỏi relevant context → test lần lượt A/B/C (im lặng quan sát, không dẫn dắt) → so sánh chọn option → hoàn thiện note ngay sau buổi test.
- **Observation / tổng hợp feedback:** Ghi Feedback Note chi tiết cho từng tester tại [PrototypeFeedbackNote.md](PrototypeFeedbackNote.md); tổng hợp ba feedback thành [GroupFeedbackSynthesis.md](GroupFeedbackSynthesis.md).

---

## 5. Prototype Feedback

### Observation từ phiên tôi facilitate

- Option test: A / B / C (test cả ba, theo thứ tự random để tránh order bias)
- Tester: Nguyễn Việt Hải (2A202601656) và Huỳnh Thị Hải Châu (2A202601912) — cả hai đều đã có kinh nghiệm dùng VLearn, thao tác thuần thục trên cả 3 prototype, không hỏi lại cách dùng.
- Quan sát chính: Cả hai tester đều đọc slide trước, tự nhận ra đoạn định nghĩa/khái niệm chưa rõ rồi chủ động bôi đen đúng đoạn đó để hỏi AI (đúng luồng lối vào #1 của Option A). Không có breakdown thao tác — điểm dừng duy nhất là dừng đọc do nội dung, không do UI. Cả hai đều chọn Option A và cùng chung một lý do: muốn tự chủ động chọn đúng phần mình cần hỏi thay vì để AI đoán hộ; đồng thời cùng phản biện rằng mốc "dừng ở một slide" mà B/C dùng để tự động can thiệp là tín hiệu yếu, dễ gây false positive (có thể do đang bận việc khác) và khiến tester có xu hướng skip. Tester 2 nêu thêm rủi ro rằng AI có thể "bắt sai trọng tâm" chứ không chỉ sai thời điểm can thiệp. Chi tiết đầy đủ tại [PrototypeFeedbackNote.md](PrototypeFeedbackNote.md).

### Ba-feedback synthesis

| Practice Note / Feedback | Tester đã làm/nói gì? | Điều nhóm đang diễn giải |
|---|---|---|
| 1 | Nguyễn Việt Hải: đọc slide → chủ động bôi đen đoạn không hiểu để hỏi AI (Option A); chọn A vì muốn tự chủ động, cho rằng dừng lâu ở slide chưa chắc là "chưa hiểu" nên AI tự bật (B/C) là không cần thiết và dễ bị bỏ qua. | Giả định nền của B/C (">15 phút xem slide = tín hiệu đáng tin") bị nghi ngờ là false positive phổ biến, làm giảm giá trị cơ chế proactive/collaborative. |
| 2 | Huỳnh Thị Hải Châu: đọc slide rồi chọn thẳng Option A để tự kiểm soát; đồng tình lý do của Tester 1, thêm hoài nghi rằng AI có thể "bắt sai trọng tâm" chứ không chỉ sai thời điểm hỏi. | Củng cố quan sát của Feedback 1 — không phải trùng hợp cá nhân đơn lẻ; bổ sung thêm một lớp rủi ro khác: ngay cả khi đúng thời điểm, nội dung AI đoán ra cũng có thể sai. |
| 3 | Tester thứ ba: đọc bài giảng, có bước do dự — không tin ngay gợi ý của AI mà tự đối chiếu/kiểm tra lại trước khi tin và đi tiếp; cũng chọn Option A, cho rằng popup tự động của B/C gây giật mình và phiền phức. | Khác với Feedback 1&2 (giành control trước khi hỏi), Feedback 3 giành control sau khi AI trả lời — cùng một nhu cầu kiểm soát nhưng thể hiện ở hai thời điểm khác nhau. |

### Next Change

> Với Hypothesis Problem này, nhóm đã thử ba cách giải (A/B/C). Cả 3/3 tester đều chọn Option A và cùng phản biện rằng mốc ">15 phút xem slide" mà B/C dùng làm trigger là tín hiệu yếu, nhiều false positive, vì vậy iteration tiếp theo nhóm sẽ ưu tiên phát triển tiếp Option A (User-led) làm cơ chế chính; nếu giữ lại một phần cơ chế B/C, sẽ chuyển từ "popup tự động chặn luồng dựa trên thời gian xem slide" sang gợi ý âm thầm, không chặn luồng (vd. icon/badge nhỏ cạnh nút "Tôi vẫn chưa hiểu"), để user tự quyết có mở ra hay không. Chi tiết tại [GroupFeedbackSynthesis.md](GroupFeedbackSynthesis.md).

### Still Unproven

- Cả 3 tester đều nghiêng hoàn toàn về A — chưa quan sát được phản ứng của người thực sự thích được AI hỗ trợ chủ động, nếu nhóm này tồn tại.
- Chưa tách bạch được việc chọn A là do bản chất thiết kế tốt hơn hay do đã quen kiểu tương tác "tự bấm, tự chọn" sẵn có (cả 2/2 tester được tôi facilitate đều đã quen VLearn).
- Chưa rõ phản ứng tiêu cực với B/C là do timing/tần suất trigger sai hay do bản chất cơ chế proactive không phù hợp với nhóm user này — cần thêm tester, đặc biệt người chưa quen VLearn và người ít chủ động hơn.

---

## 6. AI Support Log

- **AI đã giúp gì:**

  - Viết code 3 file prototype HTML/CSS/JS ([prototype-user-led.html](prototype-user-led.html), [prototype-collaborative.html](prototype-collaborative.html), [prototype-proactive.html](prototype-proactive.html)) theo đúng luồng tương tác đã mô tả cho từng option.
  - Lặp lại thiết kế theo phản hồi trực tiếp của tôi.
- **AI sai/hời hợt ở đâu:**
  - AI tự đưa ra target user và cơ chế trigger mà không hỏi kỹ, dẫn đến phải sửa lại đúng với ngữ cảnh thực tế .
  - Cơ chế ban đầu của Option A có gợi ý sẵn danh sách khái niệm — đi ngược tinh thần "user-led, không đoán trước" mà nhóm muốn, phải yêu cầu sửa lại thành bôi đen tự do.

- **Tôi tự sửa gì:**
  - Chỉnh sửa lại theo đúng ý tưởng, lọc và lược bỏ các nội dung sai/ không phù hợp.
