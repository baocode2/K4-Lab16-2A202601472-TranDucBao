# Memo Teardown — Cursor

**Nhóm B2** — Khóa 3 (K3) · Lab 16
**Thành viên:** Lê Quang Huy (2A202601821 — A) · Trần Đức Bảo (2A202601472 — B) · Đàm Việt Cường (2A202601566 — C) · Hoàng Minh Quân (2A202601574 — D)

**Vì sao chọn sản phẩm này:** Cursor là sản phẩm AI-native nơi AI là lõi chứ không phải lớp phủ — toàn bộ giá trị nằm ở tầng AI dựng trên bản fork VS Code. Dữ liệu công khai đủ dày (changelog có ngày và số hiệu bản, Wikipedia, transcript founder, thread Hacker News) để dựng hơn 6 mốc, và tách được rõ hai tệp user với JTBD khác hẳn nhau.

> **Quy tắc nguồn nhóm tự đặt:** mỗi mốc phải có **link nguồn gốc đã tự mở**. Nguồn tổng hợp bên thứ ba (releasebot, PromptLayer, dataconomy, marktechpost) chỉ dùng để **phát hiện** mốc, **không được dẫn** trong memo. Nhóm đã loại 2 mốc thật vì vi phạm quy tắc này (xem §1).

---

## §1. Timeline các cập nhật lớn

| Thời điểm | Cập nhật | Context lúc đó | Nguyên lý |
|---|---|---|---|
| **03/2023** | **Ra mắt Cursor** — editor "AI-first", **fork từ VS Code**. Lõi ban đầu: **Cursor Tab** đoán trước *cả một thay đổi mạch lạc* trong code, không chỉ vài ký tự tiếp theo. [(Show HN 22/03/2023)](https://news.ycombinator.com/item?id=35267741) · [(HN "AI-First" 15/10/2023)](https://news.ycombinator.com/item?id=37888477) | ChatGPT vừa ra (11/2022); GitHub Copilot thống trị autocomplete; cả ngành dev tool hoang mang vì LLM. Nhóm bạn MIT vừa pivot khỏi một dự án AI cơ khí thất bại. | **wrapper/moat + định nghĩa "tốt"** — không dựng editor từ đầu mà fork VS Code để mượn ngay distribution và hệ sinh thái extension, dồn toàn lực vào lớp AI. Đồng thời **định nghĩa lại "gợi ý tốt"**. |
| **13/07 → 24/11/2024** | **Cung Composer** — hai bước của cùng một quyết định: **v0.37** mở Composer sửa **nhiều file cùng lúc**, rồi **v0.43** đưa Composer vào sidebar và cấy **mầm agent** *"tự chọn ngữ cảnh và dùng terminal"*. [(Changelog 0.37.x)](https://cursor.com/changelog/0-37-x) · [(Changelog 0.43.x)](https://cursor.com/changelog/0-43-x) | GPT-4/Claude 3 đủ mạnh suy luận đa file trong khi Copilot vẫn gợi ý từng dòng. Series A $60M (a16z, định giá $400M) công bố 08/2024. Tới 11/2024 định giá ~$2.5B, vừa mua Supermaven; Devin tạo cơn sốt "AI kỹ sư". | **Vertical AI → vòng lặp học + x10** — nâng **đơn vị công việc** hai nấc liên tiếp: "dòng" → "nhiều file" → "agent tự chọn ngữ cảnh + chạy lệnh". Nấc hai khép vòng lặp làm-kiểm-sửa. |
| **15/05/2025** | **v0.50 — Background Agent** (agent chạy **nền/song song** ở môi trường remote) + gộp pricing về request thống nhất + Max Mode. [(Changelog 0.50)](https://cursor.com/changelog/0-50) · [(HN — sự cố bot CSKH)](https://news.ycombinator.com/item?id=43683012) | Đầu 2025 vượt $100M ARR. Đua "agent nền" nóng lên (OpenAI Codex, Claude Code). Sự cố 26/04/2025 — bot CSKH "Sam" bịa chính sách giới hạn thiết bị — vừa gây khủng hoảng niềm tin. | **vòng lặp học** — tách agent khỏi **vòng lặp gõ phím của con người**; chạy nền/song song = mở rộng vòng lặp học ra ngoài phiên làm việc trực tiếp. |
| **04/06/2025** | **v1.0** — **Bugbot** (tự review PR), **Background Agent mở cho mọi user**, **cài MCP 1-click** + OAuth. [(Changelog 1.0)](https://cursor.com/changelog/1-0) | 05–06/2025: vượt $500M ARR, gọi Series C $900M (Thrive, định giá $9.9B). Chuyển mình từ "công cụ" sang "nền tảng". | **wrapper/moat (nền tảng)** — mở agent cho tất cả + biến MCP thành 1-click = dựng **moat hệ sinh thái tích hợp**: càng nhiều công cụ cắm vào, càng khó rời bỏ. |
| **16/06 → 07/2025** | **Đổi pricing Pro** — 16/06 bỏ hạn mức 500 request → **usage-metered ($20 credit)** → phản ứng dữ dội → blog "Clarifying our pricing" (05/07) → **rollback** + hoàn tiền khoản phát sinh 16/6–4/7. [(TechCrunch)](https://techcrunch.com/2025/07/07/cursor-apologizes-for-unclear-pricing-changes-that-upset-users/) · [(HN 84đ/89 cmt)](https://news.ycombinator.com/item?id=44470148) | Chi phí model (Claude/GPT) tăng, ép biên lợi nhuận. Thread HN phản hồi bài blog đạt **84 điểm/89 comment — mức tranh cãi cao nhất toàn timeline**; một bộ phận rời hẳn sang Claude Code ngay trong lúc tranh cãi. | **định nghĩa "tốt" + vòng lặp học** — thử khớp giá với chi phí thực, nhưng "tốt" với công ty ≠ "tốt" với user → thị trường phản hồi → **rollback = học từ vòng lặp**. |
| **29/10/2025** | **Cursor 2.0** — model coding riêng **Composer** (tự huấn luyện, "4x nhanh hơn model cùng tầm") + chạy tới **8 agent song song** + giao diện xoay quanh agent. [(Changelog 2.0)](https://cursor.com/changelog/2-0) · [(a16z podcast)](https://a16z.com/podcast/michael-truell-how-cursor-builds-at-the-speed-of-ai/) | Chuẩn bị Series D $2.3B (định giá $29.3B). Đồng sáng lập Arvid Lunnemark rời đi. Cạnh tranh model coding gay gắt. | **Vertical AI + x10** — tự làm model dọc thay vì chỉ "wrap" API người khác → kiểm soát chất lượng và chi phí; **đổi định vị** từ "editor có AI" sang "nền tảng điều phối nhiều agent". |
| **02/04/2026** | **Cursor 3.0 — Agents Window**: giao diện **agent-first** đứng riêng, chạy nhiều agent song song across repo và môi trường (local, worktree, cloud, remote SSH) + Design Mode + `/worktree`, `/best-of-n`. **IDE bị hạ xuống thành một pane.** [(Changelog 3.0)](https://cursor.com/changelog/3-0) | ~$3B ARR, 64% Fortune 500 dùng. Cùng tháng SpaceX chào mua $60B. Cộng đồng phản ứng **rất tiêu cực** trên Reddit/HN — "Cursor is dead", tố rời bỏ bản sắc IDE. | **định nghĩa "tốt" (tự đảo lại) + x10** — khi user không còn *gõ* code mà *duyệt* output agent, surface tối ưu cho việc gõ trở thành sai → **tự tay gỡ chính lực Habit mình đã dựng ở mốc 1**. |
| **16/06/2026** | **Origin** — công bố tại hội nghị Compile, một **git forge cho kỷ nguyên agent** (*"a git forge for the agentic era"*), dựng trên công nghệ từ thương vụ Graphite. Không còn là tính năng trong editor — là **thay thế cho chính GitHub**. [(Trang Origin chính thức)](https://cursor.com/origin) | GitHub vốn thiết kế cho người, không cho hàng nghìn agent clone/push/merge đồng thời. Cùng ngày, SpaceX mua lại $60B — đổi lại quyền truy cập cụm Colossus để train model từ đầu. | **wrapper/moat (đào xuống) + x10** — hết chỗ mở rộng theo chiều ngang thì **đi xuống tầng dưới**: từ editor xuống **nơi code được lưu và hợp nhất**. Nếu phần lớn code do agent sinh, moat thật không còn ở chỗ *viết* code. |

**Vì sao chọn những mốc này:** Tiêu chí lọc là *"có làm đổi workflow, segment hay mô hình kinh doanh không?"* — cả 8 mốc đều đổi cách user làm việc hoặc cách công ty kiếm tiền, tạo thành một chuỗi quyết định chứ không phải danh sách tính năng. Nhóm ưu tiên mốc **chuyển pha**, không tính cải thiện tuyến tính: v0.37 và v0.43 được **gộp làm một** vì cùng cung "Composer", làm nổi bước chuyển *đơn vị công việc* thay vì chẻ nhỏ theo số hiệu bản phát hành. Nhóm cũng **cố ý giữ một mốc thất bại** (pricing 07/2025) vì một quyết định bị rollback lộ nguyên lý rõ hơn nhiều mốc suôn sẻ.

**Các mốc đã cân nhắc rồi loại:**

| Mốc bị loại | Vì sao không đủ tư cách |
|---|---|
| **Automations (03/2026)** và **Cursor SDK (04/2026)** | Là quyết định sản phẩm thật, **cùng nguyên lý "đào xuống hạ tầng" với mốc 8** — nhưng chỉ tìm được nguồn thứ ba (dataconomy, marktechpost). Quy tắc nhóm cấm dẫn nguồn thứ ba, nên loại thay vì dẫn liều, để mốc 8 đứng vững bằng một nguồn chính thức duy nhất. |
| Các vòng gọi vốn Seed → Series D, thương vụ SpaceX $60B | **Sự kiện tài chính** — tiền không tự nó đổi workflow của user. Xếp vào cột *Context*, không phải cột mốc. |
| Sự cố bot CSKH "Sam" (26/04/2025) | **Sự cố vận hành**, không phải quyết định sản phẩm. Dùng làm context cho mốc Background Agent. |
| Bản vá và tối ưu hiệu năng (fix Python, LSP, drag-drop ảnh…) | **Bản vá** — không đổi workflow, đúng định nghĩa "mốc rác". |
| Composer 2.5, các bản Tab model mới | **Cải thiện tuyến tính** cùng một nguyên lý, không chuyển pha → gộp vào mốc gốc. |
| Tính năng khu vực và kênh mới (Cursor Start ₹649, iPad app, Google Workspace plugins) | **Mở rộng phân phối** — cùng giá trị lõi đưa tới kênh mới, không đổi định vị. |

---

## §2. Tệp user & JTBD

| | **Early adopters (2023–2024)** | **Tệp hiện tại (2025–2026)** |
|---|---|---|
| **Đặc điểm** | Indie hacker, senior engineer, power user MIT/Hacker News. Đã dùng VS Code, tự trả $20/tháng, một dev một repo, thích thử tool mới. | Team enterprise Fortune 500 (Nvidia, Uber, Adobe), Eng Manager, Platform/DevOps. Đội 10–100 dev, **30% PR do agent tạo**; mua theo gói Team/Business. |
| **JTBD chính** | "Giúp tôi **viết code nhanh hơn trong codebase lớn**, autocomplete đa file chính xác, đỡ gõ boilerplate." | "Giúp **đội tôi quản lý một đàn agent chạy song song**, tự review PR, và **giữ quyền kiểm soát logic** dù code do AI viết." |
| **Trước đó họ làm bằng cách nào** | GitHub Copilot + extension VS Code, copy-paste qua ChatGPT ở tab riêng, review thủ công. | Vẫn Copilot + review PR thủ công; đã thử Devin/Windsurf nhưng thiếu parallel worktrees và browser tích hợp để agent tự kiểm. |

**Dịch chuyển tệp:** **v1.0 (04/06/2025)** là điểm bẻ — Bugbot cộng Background Agent mở cho mọi user biến Cursor từ tool cá nhân thành workflow của cả đội, đủ giá trị để tổ chức mua theo seat. **Cursor 2.0** và **3.0** đẩy tiếp: khi agent chiếm phần lớn usage, người mua dịch từ lập trình viên sang **Eng Manager và CTO**, kéo theo nhu cầu quản trị chi phí, phân quyền và bảo mật — chính là thứ Team Commands và Router phục vụ.

**Switching cost (map 4 forces):**

- **Push (đẩy khỏi hiện trạng):** Copilot chậm và thiếu ngữ cảnh repo lớn; review PR thủ công quá tải; agent rời rạc không có harness chung.
- **Pull (kéo sang Cursor):** Tab phản hồi dưới 300ms, Composer dưới 30 giây một lượt, agent song song trên git worktree, Bugbot sửa lỗi một click.
- **Anxiety (lo ngại khi đổi):** hoá đơn usage khó đoán sau vụ pricing; sợ lock-in vào model riêng; lo privacy vì Background Agent yêu cầu tắt privacy mode.
- **Habit (quán tính giữ lại):** phím tắt VS Code quen tay, team đã set rules, Memories và codebase index đã "học" xong — bỏ đi là mất ngữ cảnh.

**Trả lời phản biện — lực nào mạnh nhất, và nếu mất thì sao?** Habit là lực mạnh nhất trên lý thuyết, nhưng nhóm tìm được **bằng chứng nó mỏng hơn tưởng**: ngay trong thread HN về pricing, một người viết *"I've deleted all these wrappers after discovering Claude Code on pro"* — rời đi lập tức khi có biến. Một bình luận khác phản biện thẳng vào giá trị cốt lõi: *"They've done nothing but fork VS Code and add a chat window."* Quan trọng hơn, **chính Cursor tự tay gỡ lực này ở mốc 3.0** khi hạ IDE xuống một pane. Kết luận: moat thật không nằm ở thói quen người dùng, nên Cursor buộc phải đi tìm moat mới ở tầng hạ tầng — đó chính là Origin (mốc 8).

---

## §3. Ba dự đoán hướng đi (6–12 tháng tới)

**Dự đoán 1** *(loại: mở rộng tính năng — từ editor xuống hạ tầng)*
- **Dự đoán:** Cursor đưa **Origin ra bản chính thức** vào mùa thu 2026, kèm CI và merge queue agent-native — agent tự sửa CI fail và giải quyết merge conflict.
- **Lập luận:** §1 mốc 8 đã công bố Origin xử lý conflict ở quy mô agent, mốc 2.0 đã có browser tích hợp để agent tự kiểm; §2 cho thấy tệp hiện tại là enterprise chạy nhiều agent nên cần hạ tầng chứ không chỉ editor.

**Dự đoán 2** *(loại: mở rộng segment — sang Platform/DevOps và người không viết code)*
- **Dự đoán:** Cursor đẩy gói cho **Platform team và PM** qua SDK cùng bản mobile, cho phép mô tả logic bằng ngôn ngữ tự nhiên mà không cần mở IDE desktop.
- **Lập luận:** §1 mốc 3.0 đã hạ IDE xuống một pane trong giao diện agent-first; §2 cho thấy người mua đã dịch từ lập trình viên sang Eng Manager — bước tiếp hợp lý là người **định nghĩa sản phẩm nhưng không gõ code**.

**Dự đoán 3** *(loại: thay đổi mô hình kiếm tiền + đe dọa Big Tech)*
- **Dự đoán:** Cursor chuyển sang **pricing lai theo compute** (token/compute cho Composer, lưu trữ cho Origin) kèm gói enterprise, thay vì thuần per-seat.
- **Lập luận:** §1 mốc 2.0 tự train model rất tốn compute và mốc 8 đổi cả công ty lấy quyền dùng cụm GPU — buộc phải thu theo compute. Khi Claude Code và Codex tích hợp miễn phí vào VS Code/GitHub, Cursor giữ chân bằng Origin và Memories làm tăng switching cost (§2 Habit/Anxiety) thay vì đấu giá theo seat.

**Tự tin nhất:** Dự đoán 1 — Origin đã có waitlist, có keynote công bố và có tuyển người làm hạ tầng Git. **Giả định gãy nếu:** GitHub ra merge queue cho agent trước, và doanh nghiệp không dám rời GitHub vì lý do tuân thủ — khi đó Origin chỉ còn là tính năng phụ chứ không thành moat.

---

## §4. AI Log

| Việc | AI làm hay nhóm làm? | Nhóm kiểm chứng/phán đoán lại thế nào? |
|---|---|---|
| Tổng hợp mốc từ changelog, blog, báo chí | AI tổng hợp, nhóm chọn lọc | Mở lại từng link gốc. **Bắt được 1 URL hỏng** (changelog `0-43` trả 404 → tìm ra đúng bản `0-43-x`) và **1 lỗi lệch ngày** (mốc 1 dẫn thread đăng 15/10/2023 cho sự kiện 03/2023 → thay bằng đúng Show HN 22/03/2023). |
| Chọn 8 cột mốc đưa vào §1 | **Nhóm** | Loại 6 nhóm mốc. Tranh luận và thống nhất tiêu chí "một cột mốc = một quyết định sản phẩm" khi hai thành viên xếp các vòng gọi vốn khác nhau. |
| Gán "nguyên lý" cho mỗi mốc | **Nhóm** (AI gợi ý khung) | Bắt buộc mỗi nhãn là **khái niệm có tên đã học** (x10, wrapper/moat, Vertical AI, vòng lặp học, định nghĩa "tốt"); loại nhãn đại trà kiểu "để tăng trưởng". |
| Đào nguồn cộng đồng và phát biểu founder | AI tìm, nhóm tự đọc và chọn | Tự mở từng thread Hacker News. **Khai thật hai giới hạn:** chưa lấy được transcript đầy đủ podcast a16z nên không trích nguyên văn; chưa xác minh được ngày launch gốc trên Product Hunt. |
| Loại 2 mốc vì nguồn không đạt | **Nhóm** | Automations và SDK có thật nhưng chỉ có nguồn thứ ba → quyết định loại thay vì dẫn liều, ghi rõ lý do trong bảng loại trừ. |
| Phân tích tệp user, JTBD và 4 forces | Nhóm làm, AI gợi ý khung | Mỗi người viết nháp JTBD rồi đối chiếu. Tranh luận "early adopter là indie hay team nhỏ?" → chốt là power user cá nhân vì Tab là magic moment đầu tiên. Dùng quote thật từ review và thread HN để xác nhận lực Anxiety. |
| Viết 3 dự đoán | **Nhóm** | Mỗi người viết ít nhất 1 nháp, cả nhóm chất vấn "dựa vào mốc nào, tệp nào?"; loại các dự đoán chung chung không có neo về §1–§2. |

**Chỗ AI làm thay nhiều nhất:** bước tra cứu và tổng hợp thô ở §1. **Nếu bỏ phần đó ra, nhóm còn tự giải thích được không?** Còn — vì việc *chọn mốc*, *gán nguyên lý* và *dựng lập luận* đều do nhóm quyết, và mọi mốc đều đã được mở lại link gốc để kiểm; chính quá trình kiểm đó bắt được hai lỗi mà AI tạo ra.

---

### Nguồn gốc đã mở và kiểm chứng

**Changelog chính thức:** [0.37.x](https://cursor.com/changelog/0-37-x) · [0.43.x](https://cursor.com/changelog/0-43-x) · [0.50](https://cursor.com/changelog/0-50) · [1.0](https://cursor.com/changelog/1-0) · [2.0](https://cursor.com/changelog/2-0) · [3.0](https://cursor.com/changelog/3-0)
**Trang sản phẩm chính thức:** [Origin](https://cursor.com/origin)
**Hacker News:** [Show HN 22/03/2023](https://news.ycombinator.com/item?id=35267741) · [AI-First 15/10/2023](https://news.ycombinator.com/item?id=37888477) · [Sự cố bot CSKH 26/04/2025](https://news.ycombinator.com/item?id=43683012) · [Clarifying our pricing 05/07/2025](https://news.ycombinator.com/item?id=44470148)
**Khác:** [Wikipedia — Cursor](https://en.wikipedia.org/wiki/Cursor_(code_editor)) · [TechCrunch — pricing apology](https://techcrunch.com/2025/07/07/cursor-apologizes-for-unclear-pricing-changes-that-upset-users/) · [Lex Fridman #447](https://lexfridman.com/cursor-team-transcript) · [a16z — Michael Truell](https://a16z.com/podcast/michael-truell-how-cursor-builds-at-the-speed-of-ai/) · [Product Hunt](https://www.producthunt.com/products/cursor)

**Bài làm chi tiết từng thành viên:** [Lê Quang Huy (A)](CP1-Timeline-Nguyen-Ly-Cursor.md) · [Trần Đức Bảo (B)](TranDucBao.md) · [Đàm Việt Cường (C)](DamVietCuong.md) · [Hoàng Minh Quân (D)](HoàngMinhQuân.md)

*Cập nhật: 2026-08-14. Memo đồng bộ với `slides.pdf`.*
