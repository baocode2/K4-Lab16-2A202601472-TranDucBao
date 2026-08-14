# Lab 16 — Product Teardown: Checkpoints & Cách làm việc nhóm

> **Sản phẩm đã chốt:** **Cursor** (AI code editor).
> **Nhóm B2** — Khóa 3 (K3) · Lab 16 · **Thành viên:** Lê Quang Huy (A) · Trần Đức Bảo (B) · Đàm Việt Cường (C) · Hoàng Minh Quân (D)
> File này là kế hoạch chung của buổi. Mỗi thành viên đọc trước khi bắt đầu. Deliverable cuối: `memo.md` + `slides.pdf`.

---

## ⏱ Dòng thời gian buổi (1h30)

| Bắt đầu | Step | Nội dung | Checkpoint |
|---|---|---|---|
| 0:00 | Step 0 | Chọn sản phẩm & khai phá nguồn | CP0 |
| 0:10 | Step 1 | Dựng timeline & revert nguyên lý | CP1 |
| 0:40 | Step 2 | Tệp user & JTBD | CP2 |
| 0:55 | Step 3 | Ba dự đoán hướng đi | CP3 |
| 1:15 | Step 4 | AI log & hoàn thiện memo | CP4 |
| 1:30 | Cuối | Slide, nộp bài & thuyết trình | HOÀN TẤT |

---

## Step 0 — Chọn sản phẩm & khai phá nguồn · (10') · 0:00
🎯 **Mục tiêu:** chốt 1 sản phẩm + đủ nguồn thô để dựng timeline.

**Việc cần làm:**
1. Chọn 1 sản phẩm thỏa 3 tiêu chí: (1) AI đóng vai trò đủ lớn trong trải nghiệm; (2) đủ dữ liệu công khai cho ≥6 mốc; (3) use case & JTBD rõ.
2. Chia nhau đào nguồn, mỗi người 1–2 nguồn.

💡 **Nguồn để đào:** changelog/blog công ty (đọc kỹ thông điệp trang chủ qua từng thời kỳ — chỗ lộ pivot rõ nhất), Product Hunt archive, tweet/podcast founder, thread HN/Reddit, version history App Store. Được dùng AI tổng hợp — **nhưng mọi mốc phải có link nguồn gốc đã tự mở kiểm chứng.**

👥 **Nhóm:** chia song song mỗi người 1–2 nguồn. **2 việc làm chung:** chốt sản phẩm (cả nhóm đồng ý) và gộp nguồn thô về một chỗ trước khi sang Step 1.

✅ **Kết quả:** 1 sản phẩm đã chốt + danh sách nguồn thô với vài chục mốc ứng viên.

### ✅ CHECKPOINT CP0
- **Nghiệm thu:** sản phẩm thỏa 3 tiêu chí; mở được ≥3 nguồn có dữ liệu timeline (changelog tồn tại, Product Hunt có trang launch, có bài/tweet founder về các lần ra mắt lớn).
- **Ghi nhận:** ghi tên sản phẩm vào đầu memo ngay từ bây giờ.

---

## Step 1 — Dựng timeline & revert nguyên lý · (30') · 0:10
🎯 **Mục tiêu:** đọc sản phẩm như một chuỗi quyết định, không phải đọc changelog.

**Việc cần làm:**
- Lọc còn **6–8 cột mốc lớn nhất**. Một cột mốc = một quyết định sản phẩm (tính năng lớn, pivot, đổi pricing, đổi segment) — **không phải bản vá lỗi**.
- Điền 3 cột đầu: **Thời điểm · Cập nhật · Context lúc đó** (đối thủ vừa ra gì, model nào mạnh lên, công ty đang ở giai đoạn nào).
- **Revert nguyên lý** (cột cuối): với mỗi mốc truy ngược "nước đi này chạy theo nguyên lý cốt lõi nào?" — map về khái niệm có tên: *x10 · wrapper/moat · Vertical AI · vòng lặp học · định nghĩa "tốt"…*
- Chuẩn bị 2–3 câu trả lời: "vì sao chọn những mốc này mà loại mốc kia?"

📋 **Ví dụ 1 hàng:**
| Thời điểm | Cập nhật | Context lúc đó | Nguyên lý |
|---|---|---|---|
| 11/2022 | Notion ra Notion AI (waitlist) | ChatGPT vừa ra, cả ngành docs hoang mang | Gắn AI vào đúng chỗ user đã có data sẵn → moat từ workflow hiện có |

👥 **Nhóm:** chia mốc — mỗi người phụ trách kỹ 2 cột mốc (tự đào context, tự revert nguyên lý). Sau đó cả nhóm đi qua **từng mốc**: người phụ trách trình bày, cả nhóm chất vấn "nguyên lý đúng chưa, context thiếu gì". Không ai bỏ qua mốc của người khác — chấm chéo là lúc kho kinh nghiệm hình thành.

✅ **Kết quả:** bảng 6–8 hàng, mỗi hàng có link nguồn + một nguyên lý có tên, đứng một mình đọc vẫn hiểu.

⚠️ **Dấu hiệu sai đường:** bảng 15+ hàng toàn cập nhật nhỏ (đó là liệt kê changelog); nhãn đại trà kiểu "cái này để tăng trưởng"/"để giữ chân user" (đó không phải nguyên lý).

### ✅ CHECKPOINT CP1
- **Nghiệm thu:** bảng 6–8 hàng, mỗi hàng đủ 4 cột + link nguồn gốc; mỗi nguyên lý là khái niệm có tên đã học.
- **Phản biện:** đâu là cột mốc nhóm đã cân nhắc rồi loại ra? Vì sao nó không đủ tư cách là "quyết định sản phẩm"?

---

## Step 2 — Tệp user & JTBD · (15') · 0:40
🎯 **Mục tiêu:** xác định ai thật sự dùng và họ "thuê" sản phẩm để làm việc gì — thay vì nói "cho mọi người".

**Việc cần làm:**
1. **Early adopters là ai?** Rất cụ thể (không phải "developer" mà "frontend dev ở startup nhỏ, đã dùng VS Code, theo dõi AI Twitter"). Tìm ở: Product Hunt comment, subreddit, review sớm.
2. **Tệp hiện tại là ai?** Khác early adopters ở điểm nào? Cột mốc nào ở Step 1 gây dịch chuyển đó?
3. **JTBD chính từng tệp:** viết theo việc cần làm, không theo tính năng ("trả lời email khách hàng nhanh hơn" — không phải "cần AI chatbot"). Trước đó họ làm việc đó bằng cách nào?
4. **Switching cost:** điều gì giữ user ở lại — thói quen, dữ liệu trong sản phẩm, cộng đồng, hay chưa có gì tốt hơn? Map vào **4 forces**.

💡 **Nguồn:** review G2/Capterra/App Store (đọc cả 1–2 sao — lộ JTBD chưa được đáp ứng), Discord/community, bài "why I switched from X to Y". Khuyến khích tự dùng free tier.

👥 **Nhóm:** chia song song phần đào (một người đọc review, một người đọc Product Hunt/community). **Chốt chung:** bảng so sánh 2 tệp + câu trả lời 4 forces — mỗi người viết nháp JTBD trước rồi đối chiếu.

✅ **Kết quả:** bảng so sánh early adopters vs tệp hiện tại (đặc điểm · JTBD · cách cũ · cột mốc gây dịch chuyển) + phân tích 4 forces.

### ✅ CHECKPOINT CP2
- **Nghiệm thu:** bảng so sánh 2 tệp hoàn chỉnh, tệp nào cũng đủ cụ thể để "gọi tên một người thật"; JTBD viết theo việc cần làm; segment-shift nối về ≥1 cột mốc ở Step 1.
- **Phản biện:** trong 4 forces, lực nào đang giữ user mạnh nhất — nếu lực đó biến mất thì chuyện gì xảy ra?

---

## Step 3 — Phán đoán: 3 dự đoán hướng đi · (20') · 0:55
🎯 **Mục tiêu:** luyện phán đoán — dùng kho kinh nghiệm Step 1–2 để dự đoán tương lai. Dự đoán buộc nhóm chịu trách nhiệm với nhận định của mình.

**Việc cần làm:** viết 3 dự đoán cho 6–12 tháng tới, mỗi cái thuộc một loại (chọn 3 cái lập luận chặt nhất):
- **Mở rộng tính năng** — build thêm gì?
- **Mở rộng segment** — nhắm sang tệp nào?
- **Thay đổi mô hình kiếm tiền** — pricing, gói, đối tượng trả tiền.
- **Đe dọa từ Big Tech** — có bị tích hợp luôn không, sản phẩm phản ứng thế nào?

Mỗi dự đoán đúng 2 dòng: **Dự đoán** (sẽ làm gì) · **Lập luận** (dẫn ngược về Step 1–2).

📋 **Ví dụ:**
> **Dự đoán 1** *(mở rộng segment)*
> - **Dự đoán:** Notion đẩy mạnh gói enterprise cho đội CSKH, tích hợp AI agent trả lời ticket.
> - **Lập luận:** các mốc 2024–2025 liên tục thêm tính năng cho team lớn (Step 1), tệp hiện tại đã dịch từ cá nhân sang doanh nghiệp (Step 2) → bước tiếp theo hợp lý là ăn sâu workflow doanh nghiệp.

💡 **Nguồn:** roadmap công khai, job posting (tuyển ai lộ đang build gì), phát biểu gần nhất của founder/CEO, động thái các lab (OpenAI, Anthropic, Google).

👥 **Nhóm:** bắt buộc cả nhóm cùng làm. Mỗi người viết ≥1 dự đoán nháp (kèm lập luận), cả nhóm chất vấn ("dựa vào mốc nào? tệp nào?"), rồi chọn & mài 3 dự đoán chung chặt nhất.

✅ **Kết quả:** 3 khối ngắn (~nửa trang), dự đoán nào cũng mọc từ dữ liệu đã phân tích.

⚠️ **Dấu hiệu sai đường:** dự đoán chung chung ("sẽ phát triển thêm nhiều tính năng AI"); lập luận đứng một mình không dẫn về Step 1–2.

### ✅ CHECKPOINT CP3
- **Nghiệm thu:** 3 dự đoán, mỗi cái đủ 2 dòng, lập luận trỏ về ≥1 cột mốc hoặc 1 nhận định về tệp user.
- **Phản biện:** dự đoán nào nhóm tự tin nhất — giả định nào nếu sai sẽ làm nó gãy?

---

## Step 4 — AI log & hoàn thiện memo · (15') · 1:15
🎯 **Mục tiêu:** ghép memo hoàn chỉnh + khai báo trung thực vai trò AI.

**Việc cần làm:**
- Ghép memo 3–5 trang theo template bên dưới.
- Điền bảng AI log 3 cột: **Việc · AI làm hay nhóm làm? · Nhóm kiểm chứng/phán đoán lại thế nào?**

📋 **Ví dụ AI log:**
| Việc | AI hay nhóm? | Kiểm chứng thế nào? |
|---|---|---|
| Tổng hợp timeline từ changelog | AI | Đối chiếu 3 link gốc, loại 1 mốc AI bịa |
| Chọn 7 cột mốc đưa vào memo | Nhóm | Tranh luận trong nhóm, loại 3 mốc chỉ là vá lời |

👥 **Nhóm:** AI log mỗi người tự khai phần việc của mình (không khai hộ). Một người ghép memo. Ghép memo + làm slide có thể chia nhau, nhưng **cả nhóm đọc lại memo một lượt trước khi nộp.**

✅ **Kết quả:** `memo.md` hoàn chỉnh 4 phần (timeline · tệp user & JTBD · 3 dự đoán · AI log).

⚠️ **Lưu ý:** không trừ điểm vì dùng AI nhiều — chỉ trừ khi **khai thiếu hoặc không kiểm chứng** output AI.

### ✅ CHECKPOINT CP4
- **Nghiệm thu:** `memo.md` đủ 4 phần theo template; AI log ≥3 hàng, hàng nào cũng có cột kiểm chứng.
- **Phản biện:** chỗ nào AI làm thay nhiều nhất? Nếu bỏ phần đó ra, nhóm còn tự giải thích được không?

---

## Cuối — Slide, nộp bài & thuyết trình · (30') · 1:30
1. Làm `slides.pdf` cho thuyết trình.
2. Nộp 2 file: **`memo.md`** (theo template, gồm AI log) + **`slides.pdf`**. Tên nhóm & thành viên ghi ở đầu memo.

**Checklist trước khi nộp:**
- [ ] Timeline 6–8 mốc, mỗi mốc là quyết định sản phẩm và có link nguồn?
- [ ] Mỗi mốc đã revert về một nguyên lý có tên?
- [ ] Tệp user đủ cụ thể? JTBD viết theo việc cần làm?
- [ ] 3 dự đoán đều có lập luận dẫn về timeline + tệp user?
- [ ] AI log khai đủ và trung thực?

### ✅ HOÀN TẤT
- **Nghiệm thu:** đủ 2 file `memo.md` + `slides.pdf`, checklist tick hết.
- **Thuyết trình:** trình bày nhanh luồng **timeline → nguyên lý → tệp user → 3 dự đoán**, sẵn sàng trả lời câu hỏi cả lớp.

---

## 🧮 Chấm điểm (100đ) — chấm chất lượng lập luận, không chấm đúng/sai

| Khối | Điểm | Tiêu chí | Không tính điểm nếu |
|---|---|---|---|
| **1 · Timeline** | 30 | Chọn mốc có chọn lọc + context đầy đủ (10) · chất lượng revert nguyên lý, map đúng framework (20) | Liệt kê changelog; nhãn "để tăng trưởng"; mốc không link nguồn |
| **2 · Tệp user & JTBD** | 20 | Tệp cụ thể + JTBD đúng chất, viết theo việc cần làm (10) · 4 forces + nối segment-shift với §1 (10) | Tệp chung chung ("giới trẻ"); JTBD theo tính năng ("cần AI chatbot") |
| **3 · Ba dự đoán** | 30 | Mỗi dự đoán 10 = cụ thể (5) + lập luận dẫn từ timeline & tệp user (5) | Dự đoán chung chung; lập luận không dẫn về §1–§2 |
| **4 · AI log** | 10 | Khai đầy đủ, trung thực (5) · ranh giới rõ "AI tổng hợp" vs "nhóm phán đoán", có kiểm chứng (5) | — |
| **5 · Thuyết trình** | 10 | Trình bày rõ, đúng giờ (5) · đối đáp tốt khi thảo luận (5) | — |

---

## 📄 Template `memo.md`
```markdown
# Memo Teardown — [TÊN SẢN PHẨM]
**Nhóm:** … · **Thành viên:** …
**Vì sao chọn sản phẩm này:** (1–2 câu)

## §1. Timeline các cập nhật lớn
| Thời điểm | Cập nhật | Context lúc đó | Nguyên lý |
|---|---|---|---|
| | | | |
*(6–8 hàng, mỗi hàng kèm link nguồn gốc)*
**Vì sao chọn những mốc này:** (2–3 câu — mốc nào đã loại và vì sao)

## §2. Tệp user & JTBD
| | Early adopters | Tệp hiện tại |
|---|---|---|
| Đặc điểm | | |
| JTBD chính | | |
| Trước đó họ làm bằng cách nào | | |
**Dịch chuyển tệp:** cột mốc nào ở §1 gây ra dịch chuyển? Tại sao?
**Switching cost (4 forces):** điều gì giữ user? Lực nào kéo đi / giữ lại?

## §3. Ba dự đoán (6–12 tháng tới)
**Dự đoán 1** *(loại: …)*
- **Dự đoán:** …
- **Lập luận:** … *(dẫn ngược về §1–§2)*
**Dự đoán 2** *(loại: …)* …
**Dự đoán 3** *(loại: …)* …

## §4. AI Log
| Việc | AI làm hay nhóm làm? | Nhóm kiểm chứng/phán đoán lại thế nào? |
|---|---|---|
| | | |
```

---
## 📁 Phân công nhóm (Step 0–1)
| Vai | Thành viên | Mã số | Nhiệm vụ | Nguồn đào | File |
|---|---|---|---|---|---|
| **A** | **Lê Quang Huy** | 2A202601821 | Blog & Changelog chính thức | cursor.com/changelog, docs "Updates" — lọc tính năng lớn (Tab, Composer, Agent), bỏ bản vá | `CP1-Timeline-Nguyen-Ly-Cursor.md` ✅ |
| **B** | **Trần Đức Bảo** | 2A202601472 | Product Hunt & Hacker News | Trang PH của Cursor, thread HN "Cursor IDE" — phản hồi early adopters, mốc thảo luận sôi nổi | *(chưa nộp)* |
| **C** | **Đàm Việt Cường** | 2A202601566 | Tweet & phát biểu Founder | X của Michael Truell / @cursor_ai, podcast (Lex Fridman, a16z) — định hướng & pivot | *(chưa nộp)* |
| **D** | **Hoàng Minh Quân** | 2A202601574 | Báo chí & Reddit | TechCrunch, The Verge, r/cursor, r/vscode — "why I switched", review 1 sao (feed Step 2) | `HoàngMinhQuân.md` ✅ |

> **Quy ước file:** mỗi người một file riêng đặt theo tên mình, header ghi rõ vai (`# Thành viên X — <nhiệm vụ>`). Sau khi đủ 4 phần, cả nhóm ghép vào `memo.md` chung.

*Cập nhật: 2026-08-14.*
