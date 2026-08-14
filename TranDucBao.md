# TranDucBao — Thành viên B: Product Hunt & Hacker News

**Nhóm:** B2 — Lab 16 · **Thành viên:** Trần Đức Bảo (2A202601472 — **B**)
**Vai trò được phân công (CHECKPOINTS.md):** Product Hunt & Hacker News — tìm trang Product Hunt của Cursor (ngày ra mắt), thread HN từ khóa "Cursor IDE", phản hồi early adopters và mốc cộng đồng thảo luận sôi nổi. Kết quả nuôi §1 (context các mốc) và §2 (JTBD/4 forces) của `memo.md`.

---

## 1. Product Hunt

| Mục | Kết quả |
|---|---|
| Trang sản phẩm | [producthunt.com/products/cursor](https://www.producthunt.com/products/cursor) |
| Đánh giá hiện tại | 4.7–5.0★ tuỳ thời điểm truy cập, 68–925 review (số liệu PH đổi liên tục) |
| Giải thưởng sớm nhất xác nhận được | **Golden Kitty Awards 2024** — "Product of the Year", "AI Copilot", "Developer Tools" |
| **Ngày launch gốc (2023)** | ⚠️ **Chưa xác minh được**, dù đã thử: mở trực tiếp trang sản phẩm (chỉ lazy-load các đợt launch tính năng 2025–2026), tìm URL kiểu cũ `producthunt.com/posts/cursor`, search chéo nhiều cách. **Việc còn thiếu:** tự mở trình duyệt, đăng nhập PH, kéo hết lịch sử launch xuống dưới cùng để lấy đúng ngày + link. |

## 2. Hacker News — nguồn đã tự mở & xác minh

| # | Thread | Ngày | Điểm / Cmt | Dùng cho |
|---|--------|------|-----------|----------|
| 1 | [Show HN: Cursor – IDE built for coding with GPT-4](https://news.ycombinator.com/item?id=35267741) | 22/03/2023 | 9đ | Ứng viên mốc ra mắt sớm nhất tìm được trên HN — phản ứng nhạt, nghi ngờ giá trị so với Copilot/TabNine |
| 2 | [Cursor – The AI-First Code Editor](https://news.ycombinator.com/item?id=37888477) | 15/10/2023 | 40đ | **Nguồn cho Mốc 1** — CP1-Timeline & §1 memo.md (ra mắt/Cursor Tab) |
| 3 | [Cursor IDE support hallucinates lockout policy, causes user cancellations](https://news.ycombinator.com/item?id=43683012) | 26/04/2025 | — | Khả năng là nguồn gốc sự cố bot "Sam" mà Wikipedia + §1 nhắc gián tiếp — **nguồn cho Mốc 4** |
| 4 | [Cursor IDE Problems Mount with Each Update](https://news.ycombinator.com/item?id=43340172) | 03/2025 | — | Tín hiệu bất mãn cộng đồng tích tụ trước đợt pricing 07/2025 |
| 5 | [Clarifying our pricing](https://news.ycombinator.com/item?id=44470148) (Cursor tự đăng blog phản hồi) | 05/07/2025 | **84đ, 89 cmt** | **Thread sôi nổi nhất tìm được** — **nguồn cho Mốc 6** (đổi pricing → backlash → rollback) |
| 6 | [The Void IDE, Open-Source Alternative to Cursor](https://news.ycombinator.com/item?id=44350367) | 06/2025 | — | Cộng đồng phản ứng khi có đối thủ mã nguồn mở, ngay sau vụ pricing |

## 3. Phản biện của cộng đồng (early adopters) — đối trọng với narrative marketing

Đây là phần cốt lõi của vai B: soi những gì cộng đồng **phản đối/nghi ngờ**, không chỉ khen — đúng tinh thần CHECKPOINTS.md Step 2 ("đọc cả 1–2 sao — lộ JTBD chưa được đáp ứng").

**Từ thread #5 (89 comment, sôi nổi nhất):**
- *"Did they really drop this news at Friday night, on a holiday?"* — nghi ngờ ý định che giấu qua thời điểm công bố.
- *"Feeling like someone is trying to pull a fast one"* — nghi ngờ độ thành thật của lời xin lỗi chính thức.
- *"Cursor is about to go the way of Sublime Text"* — dự đoán bi quan: mất thị phần vào đối thủ mã nguồn mở.
- *"They've done nothing but fork VS code and add a chat window"* — phản biện thẳng vào giá trị cốt lõi ("wrapper/moat" trong §1 chỉ là vỏ bọc, không phải hào sâu).
- *"I've deleted all these wrappers after discovering Claude Code on pro"* — bằng chứng **switching cost thấp hơn kỳ vọng**: rời đi ngay khi có biến, phản biện trực tiếp mục "Habit" trong 4 forces ở §2 memo.md.

**Từ thread #2 (ra mắt 10/2023):** tranh cãi giá ($20/tháng 500 lượt "nhanh" vs Copilot $10 không giới hạn), lo ngại code vẫn gửi server dù bật "privacy mode", so sánh Command-K với Copilot — cho thấy JTBD ban đầu **chưa rõ ràng ngay từ lúc ra mắt**, không phải chuyện mới phát sinh năm 2025.

**Đối chiếu với §2 memo.md:** phản biện "chỉ fork VS Code, không có gì riêng" (2023 lẫn 2025) mâu thuẫn trực tiếp với nguyên lý "wrapper/moat" mà §1 gán cho Mốc 1 — đáng đưa vào câu trả lời phản biện CP1 ("nguyên lý nào nhóm tự tin nhất, giả định nào nếu sai sẽ gãy?"): nếu fork VS Code không tạo đủ khác biệt lâu dài, cả chuỗi nguyên lý "sở hữu tầng sản phẩm" ở Mốc 1 & 7 sẽ lung lay.

## 4. Đóng góp vào các file chung

- **CP1-Timeline-Nguyen-Ly-Cursor.md** — Mốc 4: thêm nguồn #3 (sự cố bot CSKH) vào cột Nguồn gốc. Mốc 6: thêm nguồn #5 + TechCrunch, cụ thể hoá mốc thời gian (đổi giá 16/06/2025 → blog phản hồi 05/07/2025 → hoàn tiền tới 4/7).
- `memo.md` §2 (JTBD/4 forces): 5 quote ở mục 3 trên dùng trực tiếp được, đặc biệt cho lực **Anxiety** và **Habit**.

## 5. Giới hạn cần khai thật trong AI log

- Không xác minh được ngày launch Product Hunt gốc (2023) — mục 1 đánh dấu ⚠️, cần tự kiểm tra lại bằng tay.
- Phần tra cứu & mở link do AI hỗ trợ (search + fetch); phần **chọn quote nào đủ mạnh, nối phản biện nào vào nguyên lý nào ở §1/§2** là phán đoán cần Trần Đức Bảo tự đọc lại và xác nhận trước khi đưa vào memo chính thức.

---
### Nguồn gốc đã mở & kiểm chứng
[Product Hunt](https://www.producthunt.com/products/cursor) · [HN #35267741](https://news.ycombinator.com/item?id=35267741) · [HN #37888477](https://news.ycombinator.com/item?id=37888477) · [HN #43683012](https://news.ycombinator.com/item?id=43683012) · [HN #43340172](https://news.ycombinator.com/item?id=43340172) · [HN #44470148](https://news.ycombinator.com/item?id=44470148) · [HN #44350367](https://news.ycombinator.com/item?id=44350367) · [TechCrunch (pricing apology)](https://techcrunch.com/2025/07/07/cursor-apologizes-for-unclear-pricing-changes-that-upset-users/)

*Cập nhật: 2026-08-14 — CP1 / Step 1, thành viên B (Trần Đức Bảo).*
