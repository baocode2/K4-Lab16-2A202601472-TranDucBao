# Memo Teardown — Cursor (Anysphere)

**Nhóm:** B2 · **Thành viên:** Đàm Việt Cường

**Vì sao chọn sản phẩm này:** Cursor là IDE AI tăng trưởng nhanh nhất lịch sử ($300M ARR trong 2 năm, >$2B ARR đầu 2026), lộ rõ quỹ đạo từ autocomplete sang agent-first platform và vừa pivot sang infra với Origin + SDK + model tự train – case lý tưởng để phân tích product-led pivot và moat trong cuộc đua với Big Tech.

## §1. Timeline các cập nhật lớn

| Thời điểm | Cập nhật | Context lúc đó | Nguyên lý |
|---|---|---|---|
| 2022 - 2023 | Pivot từ CAD 3D autocomplete sang AI code editor | Team MIT thử CAD nhưng thiếu domain expertise và data, trong khi Copilot chứng minh nhu cầu code, team có thể dogfood. Nhận backing OpenAI Startup Fund | Build where you have unfair advantage; "wandering the desert" phải cắt sớm |
| 2024-02 | Cursor Tab – custom model multi-file <300ms | Copilot chậm, thiếu context repo lớn. Cursor tự train Tab trên open-source base để tạo magic moment | Every magic moment involves a custom model – không phải GPT wrapper |
| 2025-06-04 | Cursor 1.0 – BugBot, Background Agent GA, Memories beta, Jupyter, MCP one-click | Chuyển từ tab sang agent: PR review thủ công quá tải, cần remote agent. Link: https://cursor.com/en-US/changelog/1-0 | Own the editor to own full UX – plugin bị giới hạn |
| 2025-10-29 | Cursor 2.0 + Composer – first in-house frontier model 4x faster (<30s/turn), multi-agent parallel qua git worktrees + native browser | Phụ thuộc Claude/ GPT đắt, latency cao, cần model low-latency cho agentic loop. Raise $2.3B để đầu tư Composer. Link: https://cursor.com/blog/2-0 | Platform > tool; speed = retention cho interactive agent |
| 2026-03-05 | Automations – always-on agents trigger bởi Slack/Linear/GitHub/PagerDuty | 30% PR tại Cursor do agent tạo, track dozens agents thủ công không nổi. Tweet: "We're introducing Cursor Automations to build always-on agents." Link: https://dataconomy.com/2026/03/06/cursors-new-automations-launch-reimagines-agentic-coding/ | Conveyor belt – human in loop at right points, không phải prompt-and-monitor |
| 2026-04-29 | Cursor SDK – TypeScript SDK public beta, runtime/harness/models embeddable | Enterprise muốn nhúng agent vào CI/CD, backend service, không chỉ mở IDE. Truell retweet SDK. Link: https://www.marktechpost.com/2026/04/29/cursor-introduces-a-typescript-sdk-for-building-programmatic-coding-agents-with-sandboxed-cloud-vms-subagents-hooks-and-token-based-pricing/ | From tool to embeddable engine – mở rộng từ editor sang platform |
| 2026-06-16 | Compile 26 – Origin (agent-native Git), Cursor Mobile, model trained from scratch 10-20x compute | GitHub không thiết kế cho hàng nghìn agents commit đồng thời; 95% usage Cursor là agents. Link keynote: https://www.youtube.com/watch?v=fWa7uxyhVDE | Downward expansion: editor → infra; compute là bottleneck frontier |
| 2026-06-16 | SpaceX acquisition $60B all-stock + access Colossus 200k GPUs | Cần scale Composer, cạnh tranh Claude Code/Codex. Truell tweet: "Excited to be joining forces with @SpaceX to build useful AI." Link: https://www.ndtv.com/feature/meet-michael-truell-the-25-year-old-ceo-whose-ai-startup-was-acquired-by-spacex-for-60-billion-11647188 | Moat bằng capital + compute, không chỉ product |

**Vì sao chọn những mốc này:** Nhóm chọn 7 mốc làm thay đổi hành vi user hoặc kiến trúc (pivot, Tab, 1.0, 2.0, Automations, SDK, Origin+SpaceX). Đã loại 4 mốc nhỏ: Plan Mode, Mermaid diagram, Jupyter support, Java LSP improvement – vì chỉ là polish, không đổi JTBD hay tệp user, và không xuất hiện trong tweet của founder.

## §2. Tệp user & JTBD

|  | Early adopters (2023-2024) | Tệp hiện tại (2025-2026) |
|---|---|---|
| Đặc điểm | Indie hackers, senior engineers, MIT/HN power users, dùng VS Code, trả $20/mo, thích thử nghiệm, 1 dev 1 repo | Team enterprise Fortune 500 (Nvidia, Uber, Adobe per NDTV), Eng Manager, Platform/DevOps, 10-100 devs + 30% PR do agent tạo, dùng Cursor Team/Business |
| JTBD chính | Viết code nhanh hơn trong codebase lớn, autocomplete đa file chính xác, giảm gõ boilerplate | Quản lý fleet agents chạy song song, auto review PR (BugBot), chạy background tasks, trigger agent từ Slack/Linear, giữ control logic dù code do AI viết |
| Trước đó họ làm bằng cách nào | GitHub Copilot + VS Code extension, manual review, chạy script local, copy-paste từ ChatGPT | Vẫn Copilot + thủ công review PR, dùng Devin/Windsurf thử, nhưng thiếu parallel worktrees và native browser test |

**Dịch chuyển tệp:** Cột mốc 1.0 (BugBot/Background Agent GA) là điểm bẻ – biến Cursor từ tool cá nhân sang team workflow. Cột mốc 2.0 (Composer + multi-agent) và Automations (03/2026) đẩy mạnh: khi agent chiếm 95% usage (Compile 26), EM phải quản lý fleet thay vì 1 dev 1 chat. SDK và Origin (04-06/2026) củng cố dịch chuyển sang buyer là CTO/Platform.

**Switching cost (map 4 forces):**
- **Push (khó chịu với giải pháp cũ):** Copilot chậm, thiếu context repo, review PR thủ công mệt, agent rời rạc không có harness.
- **Pull (hút sang Cursor):** Tab nhanh <300ms, Composer <30s, parallel agents trên worktrees, BugBot fix-in-one-click, Memories nhớ facts per project.
- **Anxiety (lo ngại khi đổi):** Sợ lock-in model custom, sợ "vibe coding" tạo nền móng lung lay, lo privacy khi Background Agent cần tắt privacy mode.
- **Habit (quán tính giữ lại):** VS Code keybindings quen, team đã setup rules, Memories và codebase index đã train – bỏ đi mất context. Origin càng tăng habit khi repo đã host trên infra mới.

## §3. Ba dự đoán hướng đi (6–12 tháng tới)

**Dự đoán 1** *(loại: mở rộng tính năng – từ editor xuống infra)*
- **Dự đoán:** Cursor sẽ GA Origin vào Fall 2026 kèm Agent-native CI/Merge Queue – tự động fix CI fail, giải quyết merge conflict, và chạy BugBot security audit sâu bằng Automations.
- **Lập luận:** §1 mốc 2.0 đã có native browser để agent tự test, mốc Automations đã trigger sau PagerDuty, và Compile 26 công bố Origin xử lý conflict/CI – hợp logic downward expansion. Tệp hiện tại (§2) đã là enterprise chạy nhiều agents nên cần infra, không chỉ editor.

**Dự đoán 2** *(loại: mở rộng segment – sang Platform/DevOps và non-coder)*
- **Dự đoán:** Cursor sẽ đẩy mạnh gói cho Platform teams và PM/Design qua SDK + Cursor Mobile – cho phép tạo "logic spec bằng English-like" mà Truell gọi là what comes after code, không cần mở IDE desktop.
- **Lập luận:** §1 mốc SDK cho phép nhúng harness vào CI/CD/backend, mốc Mobile cho on-the-go agent, và Truell nói 95% usage là agents + tương lai là mô tả intent bằng pseudocode (§2 dịch từ coder thuần sang người định nghĩa logic) – bước tiếp hợp lý là mở sang người không code nhưng định nghĩa sản phẩm.

**Dự đoán 3** *(loại: thay đổi mô hình kiếm tiền + đe dọa Big Tech)*
- **Dự đoán:** Cursor sẽ chuyển pricing từ per-seat cố định sang hybrid usage-based (tokens/compute cho Composer + Origin storage) + Enterprise bundle, để chống lại Claude Code và OpenAI Codex tích hợp free vào VS Code/GitHub.
- **Lập luận:** §1 mốc 2.0 và model train từ scratch tốn 10-20x compute, raise $2.3B để phát triển Composer và SpaceX deal cho Colossus 200k GPU – buộc phải thu theo compute. Khi Big Tech tích hợp coding agent miễn phí, Cursor giữ moat bằng Origin + Memories + Automations làm tăng switching cost (§2 Habit/Anxiety) thay vì đấu giá seat.

**Tự tin nhất:** Dự đoán 1 (Origin GA + CI) – vì đã có waitlist, demo tại Compile 26 và job posting tuyển infra/Git. Giả định gãy nếu: GitHub ra agent-native merge queue trước và enterprise không muốn rời GitHub do compliance – Origin sẽ chỉ là feature phụ.

## §4. AI Log

| Việc | AI làm hay nhóm làm? | Nhóm kiểm chứng/phán đoán lại thế nào? |
|---|---|---|
| Tổng hợp timeline từ changelog/blog/X | AI (deep research) tổng hợp 15 nguồn, nhóm chọn 7 mốc | Đối chiếu lại 3 link gốc cursor.com/changelog/1-0, cursor.com/blog/2-0, youtube Compile 26; loại 2 mốc AI bịa (Cursor 2.1 Plan Mode) vì không có trong blog chính thức |
| Săn tweet & phát biểu founder (Step 1-2) | AI tìm @mntruell và @cursor_ai, tóm tắt Lex Fridman #447, Lenny, a16z | Mở lại x.com/mntruell/status/2028903020847841336 về recursive planning và check transcript EducationNext để xác minh "what comes after code" – không dùng quote không có nguồn |
| Phân tích tệp user & JTBD, 4 forces | Nhóm làm, AI gợi ý khung | Tranh luận: early là indie hay team nhỏ? Quyết định early = power user cá nhân vì Tab là magic moment đầu; hiện tại = enterprise vì NDTV báo >50% Fortune 500 dùng |
| Viết 3 dự đoán | Mỗi người viết 1 nháp, AI mài lại thành 2 dòng | Chất vấn lẫn nhau: dự đoán nào dẫn ngược được về §1? Loại dự đoán chung chung "sẽ thêm nhiều AI features"; giữ lại dự đoán có anchor vào Origin/SDK/SpaceX compute |
| Ghép memo theo template | Nhóm ghép, AI format bảng | Cả nhóm đọc lại memo một lượt, kiểm tra mỗi hàng timeline có link nguồn, mỗi dự đoán có lập luận trỏ về §1-§2 |
