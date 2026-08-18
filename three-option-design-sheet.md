# Three Solution Options — Design Sheet (Day 18)

**Case:** A — AI Tutor: Diagnostic Refresher
**MHV:** 2A202601226 — Nguyễn Thị Thương

---

## 1. Hypothesis Problem (tiếp tục từ Day 17)

> Khi đang học một bài online và gặp một khái niệm/định nghĩa mà mình không nhớ hoặc không hiểu, học viên gặp khó khăn trong việc xác định nên ôn lại kiến thức nào — đặc biệt là không phân biệt được đây là kiến thức **cũ** (đã học, đang quên) hay kiến thức **mới** (chưa từng học) — dẫn đến mất 20–30 phút mỗi lần, phần lớn thời gian dành cho việc tìm kiếm lại chứ không phải học.

**Evidence hỗ trợ:** User thực sự bị chặn bởi khái niệm chưa hiểu trong lúc học; mất thời gian tra cứu, giải thích.

**Điều vẫn chưa biết:** Ba cách chia việc user–AI khác nhau (tự chọn / cùng xác nhận / AI chủ động) — cách nào giảm đúng chi phí classification mà không làm mất quyền kiểm soát của user.

---

## 2. Ba Solution Options

TÌNH HUỐNG chung: *Học viên vừa trả lời sai một câu hỏi kiểm tra lần thứ hai trong bài và không biết tiếp tục thế nào.*

| Thành phần | Quyết định chung cho A/B/C |
|---|---|
| Target user | Learner đang học một bài online, cụ thể là đang xem slide, gặp một khái niệm chặn tiến độ |
| Situation | Đang học, dừng ở một slide quá lâu |
| Task | Xác định đúng kiến thức nền cần ôn và hiểu lại nó |
| Desired outcome | Quay lại bài học đang dang dở, không bị mất mạch |
| Content/data fixture | 1 bài học mock + 1 khái niệm nền giả định (dùng chung cho cả 3 option) |

| Thành phần | **A — User-led** | **B — Collaborative** | **C — Proactive** |
|---|---|---|---|
| Solution mechanism | Learner tự khởi tạo qua 2 cách: (1) bôi đen đúng đoạn trên slide, hoặc (2) bấm nút cố định để duyệt danh sách khái niệm quan trọng trong slide và tự chọn/tự mô tả tiếp — cả hai đều không có AI đoán trước | AI phát hiện dấu hiệu (dừng quá lâu ở một slide), hỏi xác nhận chẩn đoán trước khi hành động | AI tự phát hiện và tự mở gợi ý ôn tập ngay khi phát hiện dấu hiệu |
| User làm gì? | Tự xác định và bôi đen vùng không hiểu, hoặc tự chọn khái niệm từ danh sách/tự mô tả, rồi xác nhận | Xác nhận hoặc sửa lại chẩn đoán AI đưa ra | Duyệt, bỏ qua hoặc sửa gợi ý AI đã tự đưa ra |
| AI làm gì? | Chỉ generate giải thích sau khi user xác nhận lựa chọn | Đặt câu hỏi chẩn đoán, chờ user xác nhận/sửa trước khi generate | Tự chẩn đoán và tự generate trước, hiển thị luôn cho user |
| Trigger | Learner bôi đen đoạn trên slide → nút nổi "Tôi vẫn chưa hiểu" xuất hiện cạnh vùng chọn | AI hỏi khi thấy dấu hiệu (dừng quá lâu ở một slide) | AI tự phát hiện, tự mở, không chờ hỏi |
| Trade-off chính | Phải tự nhận diện đúng vùng chữ đang chặn mình → có thể bôi đen sai chỗ (quá rộng/quá hẹp) nếu không tự nhận ra được classification cũ/mới | Thêm một bước hỏi–đáp trước khi được giúp → chậm hơn A nhưng giảm rủi ro chọn sai | Dễ gây gián đoạn, dễ bị nghi ngờ (over-triggering) nếu chẩn đoán sai |

### Distance check

- **A khác B vì** A không có bước AI hỏi xác nhận — quyết định chẩn đoán hoàn toàn nằm ở user từ đầu đến cuối; B luôn có một vòng hỏi–đáp giữa AI và user trước khi hành động.
- **B khác C vì** B luôn dừng lại chờ user xác nhận trước khi tạo nội dung; C tạo nội dung trước và đưa ra sẵn, user chỉ duyệt/bỏ qua sau khi việc đã xảy ra.
- **A khác C vì** A đòi hỏi user tự khởi động toàn bộ tương tác và tự chịu trách nhiệm chẩn đoán; C đảo ngược hoàn toàn — AI khởi động và tự chẩn đoán, user ở vai trò review bị động.

```
A: USER CREATES / INITIATES
→ B: USER + AI CO-CREATE
→ C: AI CREATES / INITIATES, USER REVIEWS
```

---

## 3. Human–AI Decision Table

| Human–AI decision | A — User-led | B — Collaborative | C — Proactive |
|---|---|---|---|
| User làm gì? AI làm gì? | User tự bôi đen đúng đoạn trên slide mình không hiểu; AI chỉ generate giải thích cho đúng đoạn đó sau khi user xác nhận | User xác nhận/sửa chẩn đoán; AI đặt câu hỏi + generate sau khi được đồng ý | AI tự chẩn đoán + tự generate trước; user chỉ duyệt/bỏ qua |
| AI Act / Ask / Don't Act? Vì sao? | **Don't Act** cho tới khi user tự bôi đen và xác nhận — vì sai ở bước này (bôi đen nhầm vùng) chỉ tốn thời gian chọn lại, không ảnh hưởng nội dung khác | **Ask** trước khi Act — vì chẩn đoán có thể sai, cần user xác nhận để giảm rủi ro lệch hướng | **Act** trước, hỏi sau (qua duyệt) — chấp nhận rủi ro gián đoạn để tối ưu tốc độ |
| User hiểu capability/limit bằng gì? | Hint "Bôi đen phần bạn không hiểu → nút sẽ hiện lên cạnh đó" hiện sẵn dưới slide; không có gợi ý/khái niệm nào được đánh dấu trước | Câu hỏi AI nêu rõ tín hiệu dùng để chẩn đoán ("Bạn đang lẫn hai công thức?") | Banner nêu rõ đây là gợi ý tự động dựa trên số lần trả sai |
| Evidence/uncertainty được thể hiện thế nào? | Không cần — user tự cung cấp evidence bằng chính đoạn văn bản họ bôi đen; panel xác nhận hiển thị lại nguyên văn đoạn đó trước khi generate | AI nêu tín hiệu cụ thể đã dùng (vd: "sai câu X và Y") kèm mức độ chắc chắn ngầm qua câu hỏi Đúng/Không | AI hiển thị lý do trigger ngay trên banner ("Sai 2 lần → ôn lại phần này?") |
| User kiểm soát và recovery thế nào? | Có thể đóng panel bất kỳ lúc nào, bôi đen lại đoạn khác không giới hạn số lần; nút "Quay lại slide" luôn hiện | Có thể chọn "Không" để huỷ chẩn đoán và tự chọn lại theo cách khác | Có nút "Bỏ qua" ngay trên banner, không hành động gì thì banner tự đóng, không chặn luồng học |

**GATE 3 check:** Mỗi option nêu rõ ai làm gì, agency tương xứng với hậu quả sai (A/B thấp rủi ro vì user luôn xác nhận; C rủi ro gián đoạn cao hơn nhưng có "Bỏ qua" ngay lập tức), và đều có đường control/recovery.

---

## 4. Phạm vi build

Cả 3 option đều đã có micro-prototype chạy được (HTML/CSS/JS), dùng chung một slide "Đường thẳng và hệ số góc" làm common context để test A/B/C:

- **A — User-led:** [prototype-user-led.html](prototype-user-led.html) — user tự bôi đen hoặc bấm nút để chọn khái niệm, AI không hành động cho tới khi được xác nhận.
- **B — Collaborative:** [prototype-collaborative.html](prototype-collaborative.html) — AI phát hiện dấu hiệu, hỏi xác nhận trước ("Bạn đang gặp vấn đề gì không?"), rồi mới cùng user xác định đúng khái niệm.
- **C — Proactive:** [prototype-proactive.html](prototype-proactive.html) — AI phát hiện dấu hiệu, tự tổng hợp và gửi luôn nội dung kèm câu hỏi xác nhận trong cùng một bước.

Chi tiết trạng thái, trigger giả lập và self-check xem tại [prototype-link.md](prototype-link.md).
