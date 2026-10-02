# Day 16 · Track 1 — Teardown sản phẩm AI

**Sản phẩm:** ChatGPT  
**Người thực hiện:** Đinh Trường An · **MSV:** 2A202602393  
**Ngày:** 02/10/2026  
**Phạm vi:** Các quyết định sản phẩm có nguồn công khai; trạng thái tính năng và kế hoạch tương lai có thể thay đổi theo thời gian.

**Vì sao chọn sản phẩm:** AI đề xuất ChatGPT vì AI là lõi trải nghiệm, có chuỗi quyết định sản phẩm công khai từ 2022 đến 2026, và use case từ hỏi đáp/học tập tới nghiên cứu và hoàn thành công việc đủ rõ để phân tích. Người nộp nên xác nhận lựa chọn này phù hợp với mình.

## Tóm tắt

ChatGPT bắt đầu như một giao diện hội thoại miễn phí để người dùng thử và phản hồi về mô hình ngôn ngữ. Qua các lần ra mắt, OpenAI mở rộng sản phẩm theo ba hướng liên kết: tăng năng lực lõi của mô hình, đưa AI vào nhiều phương thức và công việc cụ thể, rồi để AI tìm thông tin và hành động qua công cụ. Đây là teardown từ thông tin công khai, không phải khẳng định về ý định nội bộ của OpenAI.

Luận điểm của memo: lợi thế sản phẩm ngày càng ít nằm ở một ô chat đơn lẻ. Giá trị chuyển sang trải nghiệm kết hợp mô hình, ngữ cảnh hội thoại, tìm kiếm, tệp và ứng dụng kết nối. Những lớp giao diện có thể bị sao chép; chất lượng mô hình, phân phối, độ tin cậy, quyền truy cập dữ liệu và việc hoàn thành công việc đầu-cuối có khả năng tạo lợi thế bền hơn. Nhận định về “lợi thế” là phân tích của người viết, không phải dữ kiện do công ty xác nhận.

## §1 · Timeline các cập nhật lớn

| Thời điểm | Cập nhật | Context lúc đó | Revert về nguyên lý |
|---|---|---|---|
| **30/11/2022 — ChatGPT research preview** | Giới thiệu ChatGPT như mô hình hội thoại: trả lời tiếp nối, thừa nhận sai, phản biện tiền đề và từ chối yêu cầu không phù hợp. Bản preview miễn phí để nhận phản hồi. [Nguồn 1](https://openai.com/index/introducing-chatgpt/) | Chatbot nghiên cứu và mô hình ngôn ngữ vừa được mở tới công chúng; cách dùng AI phổ biến vẫn đòi hỏi công cụ/kỹ năng chuyên biệt. | **Định nghĩa “tốt” là người mới có thể thử năng lực mô hình ngay trong hội thoại quen thuộc.** Miễn phí giảm ma sát thử và tạo vòng phản hồi. |
| **14/03–25/09/2023 — GPT‑4, ảnh và giọng nói** | GPT‑4 được mở cho Plus và API, có khả năng nhận ảnh; sau đó ChatGPT bắt đầu nhận ảnh và trò chuyện bằng giọng nói cho Plus/Enterprise. [GPT‑4](https://openai.com/index/gpt-4/) · [Ảnh và giọng nói](https://openai.com/index/chatgpt-can-now-see-hear-and-speak/) | ChatGPT trả lời bằng chữ rất dễ thử, nhưng nhiều câu hỏi nảy sinh từ ảnh, tài liệu và tình huống không thuận tiện để gõ. Năng lực cao hơn cần được triển khai có kiểm soát. | **Phân tầng năng lực rồi mở thêm phương thức theo việc user cần làm.** Gói trả phí hỗ trợ tiếp cận năng lực mới; ảnh/giọng nói đưa AI vào nhiều ngữ cảnh và tạo vòng phản hồi đa phương thức. |
| **06/11/2023 — GPT tùy chỉnh và GPT Store** | GPTs cho phép tạo phiên bản ChatGPT chuyên biệt bằng chỉ dẫn, tri thức và công cụ; GPT Store được công bố để khám phá GPT cộng đồng. [Nguồn 4](https://openai.com/index/introducing-gpts/) | User muốn cá nhân hóa; người dùng thành thạo thường tự lưu prompt và hướng dẫn để tái sử dụng. | **Cho phép đóng gói hiểu biết miền và mở rộng nguồn cung qua cộng đồng.** Store chỉ bền nếu tìm kiếm, chất lượng, tin cậy và động lực nhà tạo tốt; danh mục tự nó chưa phải moat. |
| **13/05/2024 — GPT‑4o và mở rộng Free** | GPT‑4o xử lý văn bản, âm thanh, hình ảnh theo thời gian thực; văn bản và ảnh bắt đầu triển khai cho Free với giới hạn sử dụng khác nhau. [Nguồn 5](https://openai.com/index/hello-gpt-4o/) | Đa phương thức đã có tiền lệ, nhưng độ trễ và chi phí cản trở việc mở rộng trải nghiệm tới đông người. | **Hạ chi phí/độ trễ để đưa trải nghiệm mạnh tới nhiều người.** Miễn phí mở phân phối; phân tầng dần chuyển sang mức sử dụng và tiện ích nâng cao. |
| **31/10/2024 — ChatGPT Search** | ChatGPT bắt đầu tìm web và đưa link nguồn trong câu trả lời; OpenAI cho biết đã tích hợp trải nghiệm SearchGPT. [Nguồn 6](https://openai.com/index/introducing-chatgpt-search/) | Mô hình không tự cập nhật tin tức; người dùng phải rời chat, tìm link, đọc và tự tổng hợp. | **Đưa thông tin mới và nguồn kiểm chứng vào nơi user hỏi.** Đối thoại liên tục có thể thay một phần thao tác nhiều tab; nguồn giúp kiểm tra nhưng không đảm bảo câu trả lời đúng. |
| **02/02/2025 — Deep Research** | Nghiên cứu nhiều bước tìm, đọc và tổng hợp nguồn web thành báo cáo có dẫn nguồn cho câu hỏi cần đào sâu. [Nguồn 7](https://openai.com/index/introducing-deep-research/) | Search nhanh xử lý câu hỏi ngắn, nhưng tác vụ nhiều khía cạnh vẫn cần người dùng mở nguồn, so sánh và viết báo cáo. | **Tối ưu cho kết quả công việc hoàn chỉnh thay vì lượt chat đơn lẻ.** Cho AI tự lập kế hoạch, tìm thêm bằng chứng và tổng hợp; thời gian cao có thể chấp nhận nếu tiết kiệm nhiều công sức. |
| **17/07–07/08/2025 — Agent và GPT‑5** | Agent kết hợp nghiên cứu với trình duyệt/terminal để làm chuỗi thao tác; GPT‑5 trở thành mặc định, định tuyến giữa trả lời nhanh và suy luận sâu. [Agent](https://openai.com/index/introducing-chatgpt-agent/) · [GPT‑5](https://openai.com/index/introducing-gpt-5/) | Deep Research tổng hợp, Operator thao tác web; hai hướng tiến gần nhau trong tác vụ đầu-cuối. | **Tiến từ “nói cách làm” sang “làm từng bước có giám sát”, đồng thời giảm ma sát chọn model.** Quyền kiểm soát, xác nhận hành động quan trọng và khả năng dừng/sửa giúp tạo niềm tin. |
| **04/06–13/08/2026 — Memory và tệp kết nối** | Memory được nâng cấp để tự cập nhật sở thích/ngữ cảnh; Google Drive được tích hợp sâu hơn vào Library để tìm và dùng tài liệu trong hội thoại. [Memory](https://openai.com/index/chatgpt-memory-dreaming/) · [Release notes](https://help.openai.com/en/articles/6825453-chatgpt-release-notes) | Khi chat và agent được dùng qua nhiều phiên, người dùng phải lặp lại bối cảnh và tự mang tệp giữa các công cụ. | **Tích lũy ngữ cảnh hữu ích để giảm lặp lại, đồng thời đặt quyền xem/sửa/xóa memory và kết nối làm điều kiện tin cậy.** Lợi thế có thể đến từ sự phù hợp theo thời gian, nhưng lo ngại dữ liệu có thể làm user không bật tính năng. |

**Vì sao chọn các mốc này:** Đây là những lần thay đổi cách người dùng tiếp cận năng lực, đưa thông tin vào, tùy chỉnh sản phẩm, lấy dữ liệu mới, giao việc và duy trì ngữ cảnh. Tôi cân nhắc các lần tăng phiên bản model nhỏ và bản vá, nhưng loại vì không đổi rõ workflow hoặc phân khúc ở mức sản phẩm trong nguồn đã xem.

### Mẫu hình xuyên suốt

1. **Từ demo tới thói quen:** bản miễn phí giúp thử nhanh; tiện ích lặp lại và giới hạn theo gói tạo động lực nâng cấp.
2. **Từ wrapper tới nền tảng:** chat, GPT tùy chỉnh, Search và agent làm giao diện ngày càng dày. Phần dễ bắt chước nhất là cách trình bày; phần khó thay hơn có thể là chất lượng mô hình, tốc độ, dữ liệu/ứng dụng đã kết nối, niềm tin và mức độ hoàn thành công việc.
3. **Vòng lặp học:** triển khai theo giai đoạn, giới hạn gói và phản hồi sử dụng giúp quan sát hành vi, phát hiện lỗi/rủi ro rồi cải tiến. Đây là suy luận từ cách các lần ra mắt được mô tả, không phải xác nhận về toàn bộ quy trình nội bộ.

## §2 · Tệp user, JTBD và switching cost

| | **Early adopters (2022–23)** | **Tệp hiện tại (2025–26)** |
|---|---|---|
| **Đặc điểm** | Chân dung giả thuyết: một lập trình viên frontend ở startup nhỏ, đã dùng diễn đàn/dev tools và theo dõi AI, thử ChatGPT để giải thích code hoặc tạo bản nháp dù biết câu trả lời có thể lỗi. Hacker News thảo luận ngay ngày ra mắt có người kể đã dùng chatbot GPT trước đó để hoàn thành phần lớn một lớp code nhỏ cho công việc — một tín hiệu sớm, không đại diện toàn bộ cohort. [Thảo luận HN](https://news.ycombinator.com/item?id=33804874) | Chân dung giả thuyết: một product manager/analyst ở đội nhỏ cần tổng hợp tài liệu, tìm nguồn và viết brief có cấu trúc; bên cạnh đó là người dùng cá nhân dùng trợ lý cho nhiều việc thường ngày. Báo cáo OpenAI ghi nhận 800 triệu người dùng hàng tuần và mức sử dụng Enterprise tăng; đây là dữ liệu do công ty công bố. [Usage report](https://openai.com/index/the-state-of-enterprise-ai-2025-report/) |
| **JTBD chính** | “Khi muốn thử giải quyết một câu hỏi hay bản nháp bằng AI, giúp tôi có câu trả lời đối thoại để kiểm tra và tiếp tục.” | “Khi cần hoàn thành việc học/làm nhiều bước, giúp tôi tìm thông tin, xử lý tài liệu và tạo kết quả có thể kiểm tra trong một luồng.” |
| **Trước đó làm bằng cách nào** | Tìm kiếm web, diễn đàn, tài liệu hướng dẫn; tự thử prompt/model hoặc viết nháp thủ công. | Chuyển giữa công cụ tìm kiếm, tài liệu, trợ lý chuyên biệt và đồng nghiệp; tự ghép nguồn, kiểm tra và thực hiện thao tác. |
| **Mốc gắn với dịch chuyển** | ChatGPT preview miễn phí (11/2022) biến thử nghiệm mô hình thành sản phẩm hội thoại công khai. | GPT‑4o Free (05/2024) hạ rào cản đa phương thức; Search, Deep Research và Agent mở rộng từ hỏi đáp sang nghiên cứu/hành động. |

**Dịch chuyển tệp:** Nhận định của tôi là chuyển từ nhóm thử nghiệm sớm sang phổ rộng người dùng cá nhân, rồi tiến sâu vào workflow người làm tri thức/nhóm. Các mốc mở rộng Free, Search, Research và Agent giải thích hướng dịch chuyển; nguồn OpenAI xác nhận thay đổi sản phẩm và quy mô, còn chân dung cụ thể cần thêm review/phỏng vấn độc lập.

**JTBD của đội ngũ doanh nghiệp:** “Khi nhóm cần trả lời bằng tài liệu và công cụ được phép truy cập, giúp mọi người làm nhanh và nhất quán mà quản trị viên vẫn kiểm soát quyền.” Trước đó họ có thể dùng tìm kiếm nội bộ, mẫu tài liệu và nhân sự hỗ trợ; switching cost phát sinh từ cài quyền, đào tạo và workflow chung. Đây là giả thuyết cần phỏng vấn khách hàng xác thực.

### 4 lực chuyển đổi (Switching Forces)

- **Push — bất mãn với hiện trạng:** câu trả lời sai hoặc thiếu nguồn; phải tự kiểm tra nhiều bước; gói miễn phí có hạn mức; việc chuyển từ câu trả lời sang hành động còn cần tự thao tác. Với nhóm, thiếu ngữ cảnh doanh nghiệp hoặc kiểm soát có thể là lực đẩy.
- **Pull — sức hút của lựa chọn mới:** mô hình khác có thể mạnh hơn ở một tác vụ; công cụ chuyên ngành tích hợp sâu hơn; chi phí thấp hơn; hoặc nền tảng làm liền mạch một workflow cụ thể. ChatGPT cũng tự tạo lực hút qua Search, Deep Research, multimodal và agent.
- **Anxiety — nỗi lo khi đổi:** độ chính xác và quyền riêng tư; dữ liệu lịch sử có chuyển được không; gói giá/giới hạn sẽ thay đổi ra sao; hành động agent có thể gây lỗi; công cụ mới có bị khóa vào một nhà cung cấp không.
- **Habit — quán tính ở lại:** lịch sử chat, thói quen hỏi bằng ngôn ngữ tự nhiên, GPT/prompt đã cấu hình và đồng nghiệp cùng dùng. Với tổ chức, đào tạo, kiểm duyệt và tích hợp làm quán tính cao hơn.

**Đánh giá:** switching cost của người dùng cá nhân ở mức thấp đến trung bình; phần giữ chân chủ yếu là thói quen và chất lượng đủ tốt. Với người dùng chuyên sâu và doanh nghiệp, chi phí tăng khi ChatGPT gắn với tài liệu, tùy chỉnh và quy trình nhóm. Chưa có bằng chứng trong nguồn đã xem rằng người dùng khó xuất dữ liệu hoặc bị khóa chặt; vì vậy không nên gọi lock-in kỹ thuật là moat đã được chứng minh.

## §3 · Ba dự đoán trong 6–12 tháng tới

> Dự đoán dưới đây là phán đoán tại ngày 02/10/2026, không phải thông tin nội bộ hay lời hứa của OpenAI.

1. **Agent sẽ được đóng gói thành workflow có kiểm soát rõ hơn, theo từng nhóm công việc.** Cơ sở: Deep Research đã lập kế hoạch và tổng hợp; Agent đã chuyển sang thao tác trên web/công cụ; GPT‑5 hợp nhất chọn mức suy luận. §2 cho thấy nhóm chuyên sâu trả giá cao hơn cho kết quả hoàn chỉnh và khả năng nối với quy trình. Tôi dự đoán sẽ có thêm mẫu workflow, điểm dừng xác nhận và trạng thái thực hiện cho các tác vụ lặp lại. **Dấu hiệu kiểm chứng:** ra mắt workflow/agent theo ngành hoặc công việc; hiển thị quyền, bước đã làm, kết quả và chỗ cần người dùng duyệt. **Có thể sai nếu:** rủi ro thao tác, lỗi kéo dài hoặc chi phí inference khiến sản phẩm giữ agent ở chế độ hẹp.
2. **Ngữ cảnh cá nhân và kết nối ứng dụng sẽ trở thành trục giữ chân quan trọng hơn GPT Store.** Cơ sở: GPT tùy chỉnh đưa tri thức vào trải nghiệm; Search và Deep Research bổ sung nguồn; Agent và công bố connector mở đường cho hành động trong công cụ. Từ 4 forces, dữ liệu và thói quen quy trình tạo switching cost có ý nghĩa hơn một danh sách GPT. **Dấu hiệu kiểm chứng:** memory có kiểm soát tốt hơn; connector và dự án dùng lại được qua nhiều phiên; trải nghiệm cá nhân/team hiểu ngữ cảnh mà vẫn cho xem, sửa, xóa quyền. **Có thể sai nếu:** lo ngại riêng tư hoặc cấu hình phức tạp khiến user không bật kết nối.
3. **Phân tầng miễn phí/trả phí sẽ chuyển mạnh sang mức sử dụng, độ tin cậy và khả năng hành động.** Cơ sở: GPT‑4o đưa năng lực cao hơn xuống Free; GPT‑5 đặt model làm mặc định với routing; agent có chi phí và rủi ro cao hơn chat. §1 cho thấy giảm ma sát dùng thử nhưng vẫn giữ giới hạn cho năng lực tốn kém. **Dấu hiệu kiểm chứng:** Free tiếp tục có tính năng lõi nhưng giới hạn lượt/độ sâu; gói trả phí nhấn vào research/agent, dung lượng, kết nối và SLA/quản trị. **Có thể sai nếu:** cạnh tranh buộc mở rộng miễn phí hoặc chi phí mô hình giảm nhanh hơn dự kiến.

## §4 · AI Log

| Việc | AI làm hay bạn làm? | Bạn kiểm chứng/phán đoán lại thế nào? |
|---|---|---|
| Chọn sản phẩm, tìm nguồn và lập timeline | AI đề xuất ChatGPT, tìm/đọc thông báo sản phẩm và tự chọn 8 mốc cho bản nháp. | Đối chiếu ngày và mô tả với các trang OpenAI đã tra cứu. Các mốc/nhận định vẫn cần người nộp tự rà lại và quyết định giữ hay loại. |
| Revert về nguyên lý | AI đề xuất và viết các nguyên lý trong bản nháp. | Đây là diễn giải của AI từ dữ kiện công khai, không phải động cơ nội bộ đã xác nhận; người nộp cần xem lại và viết lại theo product sense của mình. |
| Xác định user/JTBD/4 forces | AI dựng chân dung giả thuyết, JTBD và phân tích 4 forces; chưa có dữ liệu phỏng vấn từ người viết. | Chân dung early adopter dựa một bình luận HN và định vị research preview, không đại diện cohort; switching forces là giả thuyết. Người nộp cần sửa theo trải nghiệm/dữ liệu mình thực sự có. |
| Dự đoán | AI soạn 3 dự đoán và dấu hiệu kiểm tra trong bản nháp. | Mỗi dự đoán nối với mốc §1 hoặc giả thuyết §2 và có điều kiện có thể làm sai; người nộp cần tự quyết định có đồng ý trước khi nộp. |
| Viết memo | AI soạn bản nháp bằng tiếng Việt và cấu trúc theo template. | Bản hiện tại chưa được cá nhân hóa bởi người nộp. Họ tên và MSV đã được điền theo thông tin người nộp cung cấp; người nộp vẫn cần tự rà, sửa và xác nhận nội dung trước khi nộp. Không dùng dữ liệu riêng tư hay API key. |

## Nguồn

1. OpenAI, [Introducing ChatGPT](https://openai.com/index/introducing-chatgpt/), 30/11/2022.
2. OpenAI, [GPT‑4](https://openai.com/index/gpt-4/), 14/03/2023.
3. OpenAI, [ChatGPT can now see, hear, and speak](https://openai.com/index/chatgpt-can-now-see-hear-and-speak/), 25/09/2023.
4. OpenAI, [Introducing GPTs](https://openai.com/index/introducing-gpts/), 06/11/2023.
5. OpenAI, [Hello GPT‑4o](https://openai.com/index/hello-gpt-4o/), 13/05/2024.
6. OpenAI, [Introducing ChatGPT search](https://openai.com/index/introducing-chatgpt-search/), 31/10/2024.
7. OpenAI, [Introducing deep research](https://openai.com/index/introducing-deep-research/), 02/02/2025.
8. OpenAI, [Introducing ChatGPT agent](https://openai.com/index/introducing-chatgpt-agent/), 17/07/2025.
9. OpenAI, [Introducing GPT‑5](https://openai.com/index/introducing-gpt-5/), 07/08/2025.
10. OpenAI, [The state of enterprise AI 2025](https://openai.com/index/the-state-of-enterprise-ai-2025-report/), 2025.
11. OpenAI, [Dreaming: Better memory for a more helpful ChatGPT](https://openai.com/index/chatgpt-memory-dreaming/), 04/06/2026.
12. OpenAI Help Center, [ChatGPT Release Notes](https://help.openai.com/en/articles/6825453-chatgpt-release-notes), cập nhật đến 13/08/2026.
13. Hacker News, [thảo luận về ChatGPT khi ra mắt](https://news.ycombinator.com/item?id=33804874), 30/11/2022; bình luận cá nhân, chỉ dùng như một ví dụ, không đại diện toàn bộ người dùng.

---

**Lưu ý trước khi nộp:** người nộp nên tự mở lại các nguồn và chỉnh nhận định JTBD theo hiểu biết/trải nghiệm của mình.
