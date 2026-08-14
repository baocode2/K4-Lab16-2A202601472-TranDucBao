# CP1 — Timeline & Revert nguyên lý: Cursor

> **Đối tượng:** Cursor (Anysphere). **Người phụ trách phần này:** Thành viên A — **Lê Quang Huy** (2A202601821) — Blog & Changelog chính thức.
> **Cách đọc bảng:** mỗi hàng là **một quyết định sản phẩm** (tính năng lớn / pivot / đổi pricing / đổi segment), không phải bản vá lỗi. Mỗi nguyên lý là một khái niệm **có tên** đã học trong buổi: *x10 · wrapper/moat · Vertical AI · vòng lặp học · định nghĩa "tốt"*.

## Bảng timeline (7 cột mốc)

| # | Thời điểm | Cập nhật (quyết định sản phẩm) | Context lúc đó | Nguyên lý (revert) | Nguồn gốc |
|---|-----------|-------------------------------|----------------|--------------------|-----------|
| 1 | **03/2023** | **Ra mắt Cursor** — editor "AI-first", **fork từ VS Code**. Cốt lõi ban đầu: **Cursor Tab** — autocomplete đoán trước *cả một thay đổi mạch lạc* trong code, không chỉ vài ký tự tiếp theo. | ChatGPT vừa ra (11/2022), GitHub Copilot đang thống trị autocomplete. Cả ngành dev tool hoang mang vì LLM. Cursor là nhóm bạn MIT, vừa pivot từ một dự án AI cơ khí thất bại. | **wrapper/moat + định nghĩa "tốt"**: không dựng editor từ đầu mà fork VS Code để mượn ngay distribution + hệ sinh thái extension, dồn toàn lực vào lớp AI. Đồng thời **định nghĩa lại "gợi ý tốt"** = đoán trước cả một sửa đổi, không chỉ ký tự kế. | [HN — "Cursor: The AI-First Code Editor"](https://news.ycombinator.com/item?id=37888477) |
| 2 | **13/07/2024** | **v0.37 — Composer** (chỉnh sửa **nhiều file cùng lúc**, bản thử nghiệm). | GitHub Copilot vẫn ở mức gợi ý từng dòng. GPT-4 / Claude 3 đủ mạnh để suy luận trên nhiều file. Cursor vừa gọi vốn Series A ($60M, ~06/2024), bắt đầu tăng tốc sản phẩm. | **Vertical AI + định nghĩa "tốt"**: nâng **đơn vị công việc** từ "dòng" lên "nhiều file" — đào sâu theo chiều dọc của nghề code, đặt lại chuẩn "tốt" cao hơn đối thủ ngang. | [Changelog 0.37.x](https://cursor.com/changelog/0-37-x) |
| 3 | **24/11/2024** | **v0.43 — Agent mode**: agent **tự đọc codebase, sửa nhiều file, chạy lệnh terminal** theo yêu cầu ngôn ngữ tự nhiên. | Nov 2024: định giá công ty ~$2.5B. Vừa **mua lại Supermaven** (đội autocomplete). Devin (Cognition) đang tạo cơn sốt "AI kỹ sư". Áp lực phải vượt khỏi "autocomplete". | **vòng lặp học + x10**: chuyển từ "gợi ý cho người gõ" sang "**tự thực thi**" — agent tạo ra vòng lặp làm-kiểm-sửa, nhắm bước nhảy x10 về năng suất chứ không cải thiện tuyến tính. | [Changelog (archive) — mục 0.43](https://cursor.com/changelog) · *(nhóm chốt anchor bản 0.43)* |
| 4 | **15/05/2025** | **v0.50 — Background Agent** (agent chạy **nền/song song** ở môi trường remote) + **gộp pricing về request thống nhất** + Max Mode. | Đầu 2025 vượt $100M ARR. Cuộc đua "agent nền" nóng lên (OpenAI Codex, Claude Code). Sự cố 04/2025 (bot CSKH "Sam" bịa chính sách thiết bị) vừa gây khủng hoảng niềm tin. | **vòng lặp học**: tách agent khỏi **vòng lặp gõ phím của con người** — việc chạy nền/song song = mở rộng vòng lặp học của sản phẩm ra ngoài phiên làm việc trực tiếp. | [Changelog 0.50](https://cursor.com/changelog/0-50) |
| 5 | **04/06/2025** | **v1.0** — **Bugbot** (tự review PR), **Background Agent mở cho mọi user**, **cài MCP 1-click** + OAuth. | 05–06/2025: vượt $500M ARR, gọi **Series C $900M** (Thrive, định giá $9.9B, 05/06). Chuyển mình từ "công cụ" sang "nền tảng". | **wrapper/moat (nền tảng)**: mở agent cho tất cả + biến MCP thành 1-click = dựng **moat hệ sinh thái tích hợp** — càng nhiều server/công cụ cắm vào, càng khó rời bỏ. | [Changelog 1.0](https://cursor.com/changelog/1-0) |
| 6 | **07/2025** | **Đổi pricing Pro** (bỏ hạn mức 500 request → **tính theo mức dùng/usage-metered**) → **phản ứng dữ dội** → **rollback** + hứa hoàn tiền. | Chi phí model (Claude/GPT) tăng, biên lợi nhuận bị ép. Cộng đồng forum/Reddit phản ứng gay gắt vì hoá đơn bất ngờ. | **định nghĩa "tốt" + vòng lặp học**: thử khớp giá với chi phí thực, nhưng "tốt" với công ty ≠ "tốt" với user → thị trường phản hồi → **rollback = học từ vòng lặp** phản ứng người dùng. | [Wikipedia — mục pricing 07/2025](https://en.wikipedia.org/wiki/Cursor_(code_editor)) |
| 7 | **29/10/2025** | **Cursor 2.0** — model coding riêng **Composer** (tự huấn luyện, "4x nhanh hơn model cùng tầm") + **chạy tới 8 agent song song** + giao diện xoay quanh agent. | 10/2025: chuẩn bị **Series D $2.3B** (định giá $29.3B, 13/11). Đồng sáng lập Arvid Lunnemark rời đi. Cạnh tranh model coding (Claude, GPT) gay gắt. | **Vertical AI + x10**: tự làm model dọc thay vì chỉ "wrap" API người khác → kiểm soát chất lượng + chi phí; **đổi định vị** từ "editor có AI" sang "**nền tảng điều phối nhiều agent**". | [Changelog 2.0](https://cursor.com/changelog/2-0) |

## Vì sao chọn 7 mốc này, loại các mốc kia? (câu hỏi phản biện CP1)

1. **Tiêu chí lọc = "có làm đổi workflow / segment / mô hình kinh doanh không?"** Cả 7 mốc đều thay đổi *cách người dùng làm việc* hoặc *cách công ty kiếm tiền*: từ gõ phím (Tab) → nhiều file (Composer) → tự thực thi (Agent) → chạy nền (Background) → nền tảng (1.0/MCP) → tự làm model (2.0). Đó là chuỗi quyết định, không phải danh sách tính năng.
2. **Ưu tiên mốc có nguyên lý *chuyển pha*, không phải cải thiện tuyến tính.** Ví dụ nâng chất lượng Tab qua từng bản là *cùng một nguyên lý* — chỉ tính **một** lần (bản ra mắt). Chỉ khi đơn vị công việc đổi (dòng → file → agent) mới tính là mốc mới.
3. **Giữ cả 1 mốc "thất bại" (đổi pricing 07/2025).** Một quyết định bị *rollback* vẫn là quyết định sản phẩm và lộ rõ nguyên lý "định nghĩa tốt" + vòng lặp học — quý hơn nhiều mốc tính năng suôn sẻ.

## Các mốc đã cân nhắc rồi **loại** (để trả lời "mốc nào không đủ tư cách?")

| Mốc bị loại | Vì sao loại |
|-------------|-------------|
| Sự cố bot CSKH "Sam" bịa chính sách (04/2025) | Là **sự cố vận hành/PR**, không phải quyết định về sản phẩm hay workflow. Dùng làm *context* cho mốc 4, không đứng riêng thành cột mốc. |
| Các bản vá & tối ưu hiệu năng (fix Python, tối ưu LSP, sửa drag-drop ảnh...) | **Bản vá**, đúng định nghĩa "mốc rác" — không đổi workflow. |
| Từng bản nâng cấp Composer 2.5 / Tab model mới | **Cùng một nguyên lý** với mốc đã có (Composer/2.0); cải thiện tuyến tính chứ không chuyển pha → gộp vào mốc gốc. |
| Các vòng gọi vốn (Seed/A/C/D), thương vụ SpaceX | Là **sự kiện tài chính/công ty**, dùng làm *context* trong cột 3, không phải quyết định sản phẩm. |
| Tính năng khu vực (Cursor Start ₹649 cho Ấn Độ, iPad app 2026) | Mở rộng phân phối, cân nhắc nhưng **ngoài khung thời gian cốt lõi** và nhỏ hơn 7 mốc trên về mức đổi định vị. |

---
*Nguồn gốc mỗi mốc lấy từ Changelog chính thức (cursor.com/changelog) hoặc Wikipedia — đúng quy tắc CP: nguồn thứ ba chỉ dùng để phát hiện, không dẫn trong memo.*
*Cập nhật: 2026-08-14 — CP1 / Step 1.*
