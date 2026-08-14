# Memo Teardown — Cursor

**Nhóm B2** — Khóa 3 (K3) · Lab 16
**Thành viên:** Lê Quang Huy (2A202601821 — A) · Trần Đức Bảo (2A202601472 — B) · Đàm Việt Cường (2A202601566 — C) · Hoàng Minh Quân (2A202601574 — D)
**Vì sao chọn sản phẩm này:** Cursor là sản phẩm AI-native nơi AI đóng vai trò trung tâm của trải nghiệm (autocomplete dự đoán → agent tự code), có changelog + Wikipedia + phỏng vấn founder đủ dày để dựng >6 mốc, và use case/JTBD rất rõ ("để AI viết & sửa code nhanh hơn ngay trong editor").

---

## §0. Kiểm tra 3 tiêu chí chọn sản phẩm (CP0)

| Tiêu chí | Đạt? | Bằng chứng |
|---|---|---|
| (1) AI đóng vai trò đủ lớn | ✅ | Toàn bộ giá trị lõi là lớp AI (Tab, Composer, Agent, model Composer riêng) trên nền VS Code fork. |
| (2) Đủ dữ liệu cho 6+ mốc | ✅ | [Changelog chính thức](https://cursor.com/changelog) (phân trang lùi), [Wikipedia](https://en.wikipedia.org/wiki/Cursor_(code_editor)), transcript Lex Fridman #447, phỏng vấn founder. |
| (3) Use case & JTBD rõ | ✅ | "Viết/sửa code nhanh hơn ngay trong IDE"; early adopters & tệp enterprise xác định được qua HN, G2, Reddit. |

**≥3 nguồn có dữ liệu timeline đã mở & kiểm chứng:** Changelog (tồn tại, có ngày + version), Wikipedia (mốc công ty + sự cố), Hacker News (thread ra mắt 2023).

---

## §1. Timeline các cập nhật lớn

| Thời điểm | Cập nhật | Context lúc đó | Nguyên lý |
|---|---|---|---|
| **03/2023** | **Ra mắt Cursor** — editor "AI-first", fork VS Code. Lõi ban đầu: **Cursor Tab** đoán trước *cả một thay đổi mạch lạc*, không chỉ vài ký tự. [(HN)](https://news.ycombinator.com/item?id=37888477) | ChatGPT vừa ra (11/2022), Copilot đang thống trị autocomplete; nhóm bạn MIT vừa pivot từ dự án AI cơ khí thất bại. | **wrapper/moat + định nghĩa "tốt"**: fork VS Code để mượn ngay distribution + ecosystem, dồn lực vào lớp AI; định nghĩa lại "gợi ý tốt". |
| **13/07/2024** | **v0.37 — Composer**: chỉnh **nhiều file cùng lúc**. [(Changelog 0.37.x)](https://cursor.com/changelog/0-37-x) | GPT-4/Claude 3 đủ mạnh suy luận đa file; Cursor vừa gọi Series A ($60M), tăng tốc sản phẩm. | **Vertical AI + định nghĩa "tốt"**: nâng đơn vị công việc từ "dòng" → "nhiều file". |
| **24/11/2024** | **v0.43 — Agent mode**: tự đọc codebase, sửa nhiều file, chạy terminal. [(Changelog)](https://cursor.com/changelog) | Định giá ~$2.5B; mua lại Supermaven; Devin tạo cơn sốt "AI kỹ sư". | **vòng lặp học + x10**: từ "gợi ý cho người gõ" → "tự thực thi". |
| **15/05/2025** | **v0.50 — Background Agent** (chạy nền/song song) + gộp **pricing theo request** + Max Mode. [(Changelog 0.50)](https://cursor.com/changelog/0-50) | Vượt $100M ARR; đua "agent nền" (Codex, Claude Code); vừa qua sự cố bot "Sam" bịa chính sách (04/2025). | **vòng lặp học**: tách agent khỏi vòng lặp gõ phím của con người. |
| **04/06/2025** | **v1.0** — **Bugbot** (auto-review PR), **Background Agent cho mọi user**, **MCP 1-click**. [(Changelog 1.0)](https://cursor.com/changelog/1-0) | Vượt $500M ARR; gọi **Series C $900M** (định giá $9.9B). | **wrapper/moat (nền tảng)**: mở agent cho tất cả + MCP = moat hệ sinh thái tích hợp. |
| **07/2025** | **Đổi pricing Pro** (bỏ 500 request → **usage-metered**) → **backlash** → **rollback** + hoàn tiền. [(Wikipedia)](https://en.wikipedia.org/wiki/Cursor_(code_editor)) · [(FinTech Weekly)](https://www.fintechweekly.com/magazine/articles/cursor-pricing-change-user-backlash-refund) | Chi phí model tăng, ép biên lợi nhuận; forum/Reddit phản ứng vì hoá đơn bất ngờ. | **định nghĩa "tốt" + vòng lặp học**: "tốt" với công ty ≠ với user → thị trường phản hồi → học & rollback. |
| **29/10/2025** | **Cursor 2.0** — model coding riêng **Composer** ("4x nhanh") + **8 agent song song** + giao diện xoay quanh agent. [(Changelog 2.0)](https://cursor.com/changelog/2-0) | Chuẩn bị **Series D $2.3B** (định giá $29.3B); đồng sáng lập Arvid Lunnemark rời đi. | **Vertical AI + x10**: tự làm model dọc thay vì chỉ wrap API; đổi định vị "editor có AI" → "nền tảng điều phối agent". |

**Vì sao chọn những mốc này:** Mỗi mốc **đổi workflow hoặc mô hình kinh doanh** (gõ phím → đa file → tự thực thi → chạy nền → nền tảng → tự làm model), không phải bản vá. Các mốc chỉ *cải thiện tuyến tính cùng một nguyên lý* (nâng chất lượng Tab, Composer 2.5) được gộp vào mốc gốc. Đã **cố ý giữ 1 mốc "thất bại"** (pricing 07/2025) vì nó lộ nguyên lý rõ hơn nhiều mốc suôn sẻ. **Mốc đã loại:** sự cố bot "Sam" (sự cố PR, không phải quyết định sản phẩm → dùng làm context), các bản vá hiệu năng ("mốc rác"), các vòng gọi vốn & thương vụ SpaceX (sự kiện tài chính → context), tính năng khu vực (Cursor Start ₹649, iPad — nhỏ hơn về mức đổi định vị).

---

## §2. Tệp user & JTBD

| | **Early adopters (2023–2024)** | **Tệp hiện tại (2025–2026)** |
|---|---|---|
| **Đặc điểm** | Solo dev / indie hacker, frontend & full-stack ở startup nhỏ, đã quen VS Code, theo dõi "AI Twitter", thích thử tool mới, tự trả tiền gói cá nhân. | Kỹ sư trong **đội & doanh nghiệp**: **64% Fortune 500**, 50k+ tổ chức mua theo seat; tech lead/eng manager duyệt ngân sách; enterprise chiếm ~45–60% doanh thu. [(getpanto)](https://www.getpanto.ai/blog/cursor-ai-statistics) |
| **JTBD chính** | "Giúp tôi **viết & sửa code nhanh hơn ngay trong editor** mà không rời workflow VS Code." | "Giúp **cả đội giao tính năng nhanh hơn**, giữ chất lượng & chuẩn code chung, và **quản trị chi phí/bảo mật** khi AI viết code ở quy mô lớn." |
| **Trước đó họ làm bằng cách nào** | GitHub Copilot (gợi ý từng dòng) + copy-paste qua ChatGPT ở tab riêng. | Copilot Enterprise / thuê thêm người / review thủ công; 67% enterprise **chuyển từ Copilot sang Cursor trong 90 ngày**. [(bonjoy)](https://bonjoy.com/articles/claude-code-cursor-enterprise-guide-2025/) |

**Dịch chuyển tệp:** Từ **cá nhân → đội/doanh nghiệp**, kích hoạt bởi cụm mốc **v0.43 Agent (11/2024)** và **v1.0 + Background Agent cho mọi user (06/2025)**: khi AI chuyển từ "gợi ý" sang "tự thực thi ở quy mô nhiều file/nền", giá trị đủ lớn để tổ chức mua theo seat, kéo theo nhu cầu **admin control, chi phí, bảo mật** — chính là thứ **Cursor 2.0 (Team Commands, Router)** phục vụ.

**Switching cost (map 4 forces):**
- **Push (đẩy khỏi hiện trạng):** Copilot chỉ gợi ý từng dòng, chậm khi codebase lớn → không đủ cho công việc đa file.
- **Pull (kéo sang Cursor):** trải nghiệm AI-native, ngữ cảnh toàn dự án, agent tự thực thi → giao việc nhanh hơn (Stripe báo +38%).
- **Anxiety (lo ngại):** **hoá đơn usage khó đoán** sau đổi pricing (Trustpilot 1.6/268 review), lo chất lượng code AI, lo khoá vào một vendor. [(G2)](https://www.g2.com/products/cursor/reviews)
- **Habit (thói quen giữ lại):** Cursor **là fork VS Code** → giữ nguyên phím tắt/extension → gần như **không có anxiety khi chuyển vào**; đây là lực giữ chân mạnh nhất cùng với dữ liệu/ngữ cảnh dự án đã nằm trong công cụ.

---

## §3. Ba dự đoán hướng đi (6–12 tháng tới)

**Dự đoán 1** *(loại: đe dọa Big Tech)*
- **Dự đoán:** Cursor tiếp tục **đầu tư model coding riêng** (dòng Composer, sau bản 2.5) để giảm phụ thuộc API Anthropic/OpenAI, phòng khi chính các lab tích hợp thẳng agent vào IDE của họ (Claude Code, Copilot Agent).
- **Lập luận:** Mốc **Cursor 2.0** (§1) đã bật sang **Vertical AI** (tự làm model dọc); founder tuyên bố chiến lược cạnh tranh bằng **model chuyên biệt + UX + enterprise**, không đấu trực diện foundation model. [(YC Library)](https://www.ycombinator.com/library/MU-cursor-ceo-going-beyond-code-superintelligent-ai-agents-and-why-taste-still-matters)

**Dự đoán 2** *(loại: mở rộng segment)*
- **Dự đoán:** Cursor sẽ **đào sâu enterprise**: thêm admin/governance, phân quyền, kiểm soát chi phí và bảo mật cấp tổ chức, bán mạnh theo seat.
- **Lập luận:** Tệp đã dịch từ cá nhân sang **64% Fortune 500** (§2); cụm mốc **v1.0 + 2.0** (Team Commands, Router, admin control) cho thấy hướng đi này — bước hợp lý tiếp theo là ăn sâu workflow doanh nghiệp.

**Dự đoán 3** *(loại: thay đổi mô hình kiếm tiền)*
- **Dự đoán:** Cursor sẽ chốt hẳn mô hình **usage/credit-based cho power-user** + **seat cố định cho enterprise**, nhưng bọc thêm **công cụ kiểm soát chi phí** (định tuyến model theo Cost/Balance/Intelligence, spending cap) để dập lại anxiety về hoá đơn.
- **Lập luận:** Mốc **pricing 07/2025** (§1) cho thấy usage-metered là hướng bắt buộc vì chi phí model, nhưng backlash (§2, force *Anxiety*) buộc phải thêm lớp kiểm soát — đúng thứ **Cursor Router** (2026) đang làm.

---

## §4. AI Log

| Việc | AI làm hay nhóm làm? | Nhóm kiểm chứng/phán đoán lại thế nào? |
|---|---|---|
| Tổng hợp các mốc từ changelog & Wikipedia | AI (web research) | Đối chiếu lại link gốc chính thức; đã **loại URL bịa** (bản 0.43 trả 404 → không dẫn link sai, gắn cờ chờ nhóm chốt anchor). |
| Chọn 7 cột mốc đưa vào §1 | Nhóm | Tranh luận, loại 4 nhóm mốc (bản vá, gọi vốn, sự cố PR, tính năng khu vực) vì không đổi workflow/segment. |
| Gán "nguyên lý" cho mỗi mốc | Nhóm (dựa gợi ý AI) | Bắt buộc mỗi nhãn là **khái niệm có tên đã học** (x10, wrapper/moat, Vertical AI, vòng lặp học, định nghĩa "tốt"), loại nhãn đại trà kiểu "để tăng trưởng". |
| Xác định JTBD & 4 forces (§2) | AI gợi ý + Nhóm chốt | Đọc review 1–2 sao thật (G2, Trustpilot 1.6) để xác nhận force *Anxiety*; mỗi người viết nháp JTBD rồi đối chiếu. |
| Viết 3 dự đoán (§3) | Nhóm | Mỗi dự đoán buộc trỏ ngược về ≥1 mốc §1 hoặc nhận định §2; loại các dự đoán chung chung không có neo. |

**Chỗ AI làm thay nhiều nhất:** tổng hợp timeline thô ở §1. **Nếu bỏ ra, nhóm còn tự giải thích được không?** Có — vì phần *chọn mốc*, *gán nguyên lý* và *revert lập luận* đều do nhóm quyết và kiểm chứng qua link gốc; AI chỉ rút gọn bước tra cứu.

---

### Nguồn gốc đã mở & kiểm chứng
Changelog: [0.37.x](https://cursor.com/changelog/0-37-x) · [0.50](https://cursor.com/changelog/0-50) · [1.0](https://cursor.com/changelog/1-0) · [2.0](https://cursor.com/changelog/2-0) · [gốc](https://cursor.com/changelog) — [Wikipedia](https://en.wikipedia.org/wiki/Cursor_(code_editor)) — [HN ra mắt](https://news.ycombinator.com/item?id=37888477) — [G2 reviews](https://www.g2.com/products/cursor/reviews) — [FinTech Weekly (pricing backlash)](https://www.fintechweekly.com/magazine/articles/cursor-pricing-change-user-backlash-refund) — [YC Library (Truell)](https://www.ycombinator.com/library/MU-cursor-ceo-going-beyond-code-superintelligent-ai-agents-and-why-taste-still-matters)

*Cập nhật: 2026-08-14. Nguồn thứ ba (releasebot, PromptLayer) chỉ dùng để phát hiện mốc, không dẫn trong memo — đúng quy tắc CP.*
