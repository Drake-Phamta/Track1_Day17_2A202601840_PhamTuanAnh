# Track1_Day17_2A202601840_PhamTuanAnh

Bài nộp Track 1 · Day 17 — Problem Hypothesis & User Interview · **Case C — AI Support Radar**

---

## 1. Thông tin cá nhân và nhóm

| Mục | Nội dung |
| --- | --- |
| MHV | 2A202601840 |
| Họ tên | Phạm Tuấn Anh |
| Tên nhóm | Nhóm không đặt tên riêng |
| Thành viên | Nguyễn Ngọc Chi<br>Nguyễn Minh Hiếu<br>Phạm Tuấn Anh |
| Case đã chọn | **Case C — AI Support Radar** |

---

## 2. Problem Hypothesis Brief

### 2.1. Solution — gỡ khỏi hình thức cụ thể

**Solution directive (nguyên văn):**

Sau mỗi phiên học, hệ thống phân tích các tín hiệu như di chuyển giữa slide, dừng lâu hoặc xem lại, highlight và ghi chú, đánh dấu "Chưa hiểu", thay đổi câu trả lời, và nội dung trao đổi với AI Chat. AI tạo một Support Queue cho giảng viên, gồm: (1) những học viên có thể cần hỗ trợ, (2) phần nội dung mà họ có thể đang gặp khó khăn, (3) các tín hiệu dẫn đến nhận định đó, (4) một hành động hỗ trợ được đề xuất. Giảng viên xem lại và quyết định có liên hệ với học viên hay không.

**Capability trung tính:**

> Sau mỗi phiên học, biến những dấu hiệu vướng mắc rải rác của người học thành một danh sách ưu tiên có thể hành động — ai nên được hỏi thăm, về phần nội dung nào, dựa trên căn cứ gì.

### 2.2. Change — chuỗi thay đổi được kỳ vọng

```
Solution → Người phụ trách lớp nhìn thấy dấu hiệu vướng mắc mà trước đây không thấy
        → Họ chủ động liên hệ đúng người, đúng phần nội dung; học viên phản hồi và được gỡ vướng
        → Outcome
```

1. Người phụ trách lớp biết ai đang vướng ở phần nào mà không phải chờ học viên tự lên tiếng.
2. Việc hỗ trợ chuyển từ "ai hỏi thì trả lời" sang chủ động, có thứ tự ưu tiên.
3. Học viên vướng nhưng im lặng được tiếp cận trong vài ngày, thay vì tự xoay xở hoặc bỏ qua.

Output team tạo ra là **danh sách ưu tiên**; outcome team chỉ có thể ảnh hưởng là **học viên thực sự gỡ được chỗ vướng**. Giữa hai cái có hai hành vi người khác phải làm: người phụ trách lớp phải mở danh sách và liên hệ, học viên phải phản hồi. Nếu hai hành vi đó không xảy ra, danh sách vẫn được sinh ra nhưng không tạo được outcome nào.

### 2.3. Actor

| Actor | Họ đang làm gì? | Pain hoặc hậu quả có thể có | Họ hưởng lợi thế nào? |
| --- | --- | --- | --- |
| Learner | Sau buổi học ngồi làm bài tập, xem lại slide, hỏi AI Chat | Vướng nhưng không gọi tên được chỗ vướng; tự xoay xở rồi làm qua loa, lỗ hổng trôi sang buổi sau | Được hỏi thăm đúng lúc, đúng phần nội dung |
| Instructor | Chấm bài, soạn buổi sau, trả lời tin nhắn rải rác | Không biết ai đang đuối cho tới khi có người nộp trễ hoặc vắng học | Có danh sách ưu tiên thay vì phán đoán cảm tính |
| Coach / TA | Hỗ trợ 1-1 theo người chủ động nhắn tin | Thời gian bị phân bổ theo người lên tiếng to nhất; người im lặng bị bỏ sót | Biết nên chủ động tìm ai trước |

**Actor chọn để điều tra trước: Learner.** Người *nhận* feature là instructor, nhưng người *sở hữu pain gốc* là learner. Toàn bộ chuỗi thay đổi sụp nếu learner thực ra tự gỡ được, hoặc không phản hồi khi được liên hệ — đây là mắt xích rủi ro cao nhất và cũng là chỗ giả thuyết dễ bị bác bỏ nhất.

> ⚠️ Ghi nhận tại thời điểm Chặng 1: vòng này chỉ có learner-side evidence; instructor-side job chưa được kiểm chứng. *(Đã được lấp ở vòng sau bằng interview Lab Coach LC-01 — xem mục 2.8.)*

### 2.4. Situation & Job

> Khi **vừa kết thúc một buổi học và ngồi làm bài tập vào buổi tối**, **learner** đang cố **hiểu lại phần nội dung mình không theo kịp** bằng cách **tự xem lại slide, tua recording và hỏi AI Chat**.

**JTBD Hypothesis:**

> Khi **tôi phát hiện mình không theo kịp một phần nội dung sau buổi học**, tôi muốn **gỡ được chỗ hổng đó trước buổi kế tiếp**, để có thể **làm được bài tập và không bị trôi xa hơn**.

### 2.5. Pain — hai cách giải thích cạnh tranh

**Pain Hypothesis A** *(nhóm chọn điều tra trước)*:

> Khi ngồi làm bài tập sau buổi học, learner gặp khó khăn trong việc gỡ phần nội dung mình không theo kịp vì **không định vị được chính xác mình hổng ở đâu để đặt câu hỏi**, dẫn đến tua lại slide và hỏi AI Chat nhiều lượt vẫn không trúng, cuối cùng làm qua loa phần đó hoặc bỏ trống.

**Pain Hypothesis B** *(cạnh tranh)*:

> Khi ngồi làm bài tập sau buổi học, learner gặp khó khăn trong việc gỡ phần nội dung mình không theo kịp vì **hỏi người khác tốn chi phí xã hội và thời gian chờ** (ngại làm phiền, sợ bị đánh giá, không biết hỏi lúc nào), dẫn đến họ chọn tự xoay xở hoặc chấp nhận hiểu lơ mơ rồi đi tiếp.

**Lý do chọn A:** A là giả định nền mà directive đang đứng lên — danh sách ưu tiên chỉ có giá trị nếu chỗ vướng *phải* được người ngoài chỉ ra. Nếu B mới đúng thì chỉ đúng chỗ vướng cũng không đổi được gì. A cũng dễ bị bác bỏ hơn chỉ bằng một câu chuyện cụ thể.

### 2.6. Evidence Map

| Cần kiểm tra | Evidence làm nhóm tin hơn | Evidence làm nhóm nghi ngờ hoặc bác bỏ |
| --- | --- | --- |
| Situation có thật | Kể được một buổi cụ thể trong 7 ngày gần đây: hôm nào, nội dung gì, ngồi làm lúc mấy giờ | Chỉ nói "thỉnh thoảng cũng có", không nhớ nổi lần nào |
| Pain có ý nghĩa | Bỏ ra trên 30 phút mà vẫn không gỡ được, phải hoãn hoặc bỏ dở | Vài phút là qua; "buổi sau tự khắc hiểu" |
| Workaround tồn tại | Kể được chuỗi: mở lại slide → tua recording → hỏi AI Chat → nhắn bạn | Không làm gì cả, chờ tới buổi sau |
| Consequence tồn tại | Nộp trễ, bỏ trống một phần, làm theo mẫu mà không hiểu, ảnh hưởng buổi sau | Vẫn nộp bài bình thường, không kể được hậu quả nào |
| Pattern có lặp | Kể được lần trước đó và khoảng cách thời gian giữa hai lần | Chỉ đúng một lần, do lý do bất thường |

**Điều gì phải đúng để giả thuyết đứng vững:** (1) learner có vướng mắc mà tự họ không nêu ra được thành câu hỏi; (2) chỗ vướng nhận ra được từ bên ngoài; (3) được chỉ đúng chỗ vướng sẽ làm learner hành động khác đi.

**Điều gì có thể khiến sửa hoặc bác bỏ:** learner tự gỡ trong dưới 10 phút; hoặc họ biết rõ mình hổng chỗ nào nhưng vẫn không hỏi; hoặc không kể được hậu quả nào.

### 2.7. Solution Parking Lot

| # | Hướng giải quyết có thể có | AI / Không sử dụng AI |
| --- | --- | --- |
| 1 | Danh sách ưu tiên tự sinh sau mỗi buổi từ tín hiệu học tập (chính directive) | AI |
| 2 | Ô "chỗ mình chưa chắc" cuối mỗi buổi, learner tự đánh dấu, tổng hợp thành danh sách | Không sử dụng AI |
| 3 | 10 phút mở đầu buổi sau đi qua 3 chỗ được đánh dấu nhiều nhất, không nêu tên ai | Không sử dụng AI |
| 4 | Cặp bạn học check-in nhau sau mỗi buổi theo một checklist cố định 3 câu | Không sử dụng AI |
| 5 | Tóm tắt hội thoại AI Chat của learner thành "câu hỏi thật sự bạn muốn hỏi" để họ tự gửi đi | AI |

### 2.8. Cập nhật sau phỏng vấn — giả thuyết đã bị evidence bác

Toàn bộ phần trên là suy luận **trước** khi phỏng vấn, giữ nguyên để đối chiếu. Nhóm đã thực hiện **ba interview: 2 Learner + 1 Lab Coach**, và kết quả bác giả thuyết gốc ở cả hai phía.

| Đối tượng | Hành vi thật | Điểm gãy / Pain thật |
| --- | --- | --- |
| **Learner 1** *(lượt mình phỏng vấn)* | "Mình sẽ la lên" — lên Discord, nhắn thẳng Lab Coach: *"Anh ơi, em bị vướng phần này, phần này"* | Người tiếp nhận **không phụ trách đúng phần đó** → *"chưa trả lời cho mình thỏa đáng"* |
| **Learner 2** | Nhắn qua Discord, gọi Lab Coach ngay khi gặp lỗi code | Lab Coach bận hoặc quên yêu cầu; phải **load lại bối cảnh** dự án/bài học nên khó hiểu ngay |
| **Lab Coach (LC-01)** | Không có cảnh báo tự động; phải **đi bộ dò từng bàn, nhìn lướt terminal**; dùng mic xử lý lỗi chung; hỏi follow-up nhiều bước | Mù thông tin về tiến độ của nhóm im lặng; câu hỏi gửi đến quá dài lan man ("đại hải") khiến Coach tốn thời gian giải mã |

**Ba cơ chế hỏng thực tế trong quy trình hỗ trợ:**

1. **Detection & Visibility Gap** — Coach không có công cụ phát hiện tự động, phải đi dò thủ công quanh lớp; học viên không hiểu bài và không được can thiệp kịp thời dẫn đến hành vi tiêu cực (thả bot vào phá hệ thống).
2. **Context Gap & Routing** — Người hỗ trợ vào cuộc mà không có sẵn bối cảnh (slide nào, terminal lỗi gì, repo nào); học viên diễn đạt câu hỏi dài dòng làm Coach mất nhiều lượt follow-up để hiểu đúng vấn đề.
3. **Capacity & Ownership** — Số lượng Coach ít; phân công hỗ trợ chưa đúng chuyên môn từng phần bài học dẫn đến yêu cầu bị trôi hoặc trả lời không thỏa đáng.

**Điểm mình rút ra thêm khi ghép ba interview: có hai phân khúc learner, hỏng ở hai chỗ khác nhau.**

| Phân khúc | Hành vi | Chỗ hỏng | Support Queue có giúp được không? |
| --- | --- | --- | --- |
| Learner lên tiếng (cả hai learner được phỏng vấn) | Raise ngay qua Discord hoặc gọi trực tiếp | Routing và context — đã hỏi rồi mà vẫn không gỡ được | **Không** — họ đã tự lộ diện, việc phát hiện không thêm giá trị |
| Learner im lặng (Coach mô tả) | Không giơ tay; Coach phải đi dò từng bàn mới thấy | Detection — không ai biết họ đang kẹt | **Có** — đây đúng là phân khúc mà việc phát hiện tạo ra giá trị |

Đây là lý do không thể kết luận gọn "phát hiện không phải nút thắt": với người đã lên tiếng thì đúng, nhưng Coach vẫn đang mù với phần còn lại của lớp.

**Pain Hypothesis C — bản nhóm đã thống nhất:**

> Khi học viên gặp khó khăn trong buổi học (hoặc qua Discord), quy trình hỗ trợ bị tắc nghẽn vì Coach không có tín hiệu nhận diện sớm (phải đi dò từng bàn) và câu hỏi của học viên bị thiếu bối cảnh kỹ thuật (context gap), dẫn đến việc Coach mất nhiều thời gian làm rõ câu hỏi, hỗ trợ sai chuyên môn, hoặc học viên nản lòng sinh ra hành vi phá rối/bỏ dở bài học.

**Điều gì sẽ bác Pain C:** Learner và Coach khẳng định các buổi học đều nắm bắt bối cảnh của nhau ngay lập tức; không có câu hỏi nào bị hiểu sai ngữ cảnh; và Coach không tốn thời gian cho việc đi dò tìm người kẹt bài.

**Hệ quả cho solution directive:** directive ban đầu tập trung vào thành phần *(1) danh sách xếp hàng ai cần hỗ trợ*. Evidence cho thấy giá trị cốt lõi nằm ở thành phần *(2) và (3)*: **tự động trích xuất ngữ cảnh** và **định vị chính xác điểm nghẽn** — để giảm công đi dò bàn của Coach và xoá khoảng cách diễn đạt của Learner. Danh sách xếp hàng chỉ có giá trị với phân khúc im lặng.

**Vòng phỏng vấn tiếp theo nên đo:** số lượt follow-up và số phút Coach cần để làm rõ một câu hỏi trước khi vào fix thật; tần suất yêu cầu rơi vào phần Coach không phụ trách trong một tuần; và độ trễ từ lúc learner kẹt tới lúc Coach phát hiện, với nhóm không giơ tay.

---

## 3. Conversation Guide — phiên bản cuối

*Bản v2 nhóm thống nhất sau ba interview, đã bổ sung nhánh câu hỏi cho Lab Coach.*

**Tiêu chí tuyển người:** người đã **trực tiếp tham gia học/làm bài thực hành, hoặc trực tiếp làm Lab Coach hỗ trợ**, trong vòng **7** ngày gần đây. Mục tiêu bao phủ: **2 Learner + 1 Lab Coach**.

**Recruitment check:**

- **Với Learner:** "Trong 7 ngày gần đây, bạn có thể kể tên một buổi lab cụ thể mà bạn gặp lỗi kỹ thuật hoặc phải nhờ Coach trợ giúp không?"
- **Với Coach:** "Trong các buổi học tuần vừa rồi, anh/chị có trực tiếp đứng lớp hướng dẫn thực hành và giải đáp thắc mắc trên Discord không?"

**Lời mở đầu:**

"Bọn mình đang tìm hiểu về trải nghiệm thực tế trong quá trình học thực hành và hỗ trợ giải đáp thắc mắc giữa học viên và đội ngũ Coach. Cuộc trò chuyện này hoàn toàn nhằm mục đích học hỏi quy trình thực tế, không có câu trả lời đúng hay sai và tụi em không đánh giá bất kỳ ai. Bọn mình sẽ chỉ hỏi về những sự kiện cụ thể đã diễn ra trong các buổi học vừa qua."

**Story opener:**

- **Learner:** "Kể mình nghe về lần gần nhất trong 7 ngày qua bạn bị mắc ở một đoạn code/slide và phải tìm sự trợ giúp. Hôm đó là bài nào và bạn đã xử lý thế nào?"
- **Coach:** "Kể em nghe về lần gần nhất trong tuần qua anh/chị trực tiếp đứng lớp hỗ trợ bài lab và phát hiện học viên đang gặp sự cố?"

**Big 3 Questions — Learner:**

| # | Điều cần học | Câu hỏi sẽ dùng |
| --- | --- | --- |
| 1 | Ngữ cảnh & tiếp nhận hỗ trợ | "Sau khi bạn nhắn hỏi hoặc gọi Coach, bạn đã phải giải thích những gì để Coach hiểu được phần bạn đang làm? Coach có nắm được ngay bài bạn đang làm không?" |
| 2 | Hậu quả thật | "Sau lần hỗ trợ chưa thỏa đáng (hoặc phải chờ lâu) đó, bạn đã làm gì tiếp theo? Việc đó ảnh hưởng thế nào đến việc hoàn thành bài tập hôm đó?" |
| 3 | Pattern & workaround | "Trong tuần qua, trước khi gọi Coach thì bạn đã thử những cách nào khác (hỏi bạn bên cạnh, hỏi AI ngoài)? Tỷ lệ tự gỡ được là bao nhiêu?" |

**Big 3 Questions — Lab Coach:**

| # | Điều cần học | Câu hỏi sẽ dùng |
| --- | --- | --- |
| 1 | Cách phát hiện & độ trễ nhận biết | "Trong buổi học gần nhất, từ lúc học viên gặp sự cố (terminal lỗi, đứng hình) đến khi anh/chị phát hiện ra là mất bao lâu? Anh/chị nhận biết bằng cách nào khi bạn ấy không giơ tay?" |
| 2 | Xử lý context gap | "Lần gần nhất nhận một câu hỏi dài dòng hoặc thiếu thông tin, anh/chị đã mất bao nhiêu thời gian và làm những bước nào để làm rõ bối cảnh câu hỏi trước khi trả lời?" |
| 3 | Hành vi khắc phục & xử lý lỗi chung | "Kể lại lần gần nhất có nhiều bạn cùng vướng một lỗi: anh/chị đã làm gì để giải quyết dứt điểm cho cả lớp mà không phải đi đến từng bàn?" |

**Probe bank — chỉ dùng khi cần đào sâu:**

- "Lúc đó chuyện gì xảy ra tiếp theo?"
- "Bạn đã làm gì cụ thể?"
- "Vì sao bạn chọn cách đó?"
- "Phần nào khó nhất hoặc tốn thời gian nhất?"
- "Bạn đã thử cách nào khác chưa?"
- "Việc đó kéo theo hậu quả gì?"
- "Lần gần nhất trước đó là khi nào?"
- "Lúc học viên không hiểu bài và bắt đầu có hành vi thả bot phá hệ thống, anh/chị đã xử lý tình huống đó thế nào?"
- "Khi học viên hỏi câu hỏi 'đại hải', anh/chị phải hỏi follow-up bao nhiêu câu thì mới chốt được vấn đề?"
- "Có bao giờ anh/chị đến hỗ trợ nhưng nhận ra nội dung bài đó không thuộc phần chuyên môn chính của mình không? Lúc đó anh/chị xử lý ra sao?"

**Ba phản xạ khi data lệch:**

| User đưa ra | Phản xạ | Cách quay lại evidence |
| --- | --- | --- |
| Lời khen | Deflect | "Dạ vâng, vậy trong buổi học gần nhất chuyện đó diễn ra cụ thể thế nào ạ?" |
| Câu chung chung hoặc lời hứa tương lai | Anchor | "Lần gần nhất chuyện đó xảy ra là khi nào ạ? Lúc đó anh/chị đã xử lý ra sao?" |
| Ý tưởng hoặc feature request | Dig | "Điều đó giúp anh/chị giải quyết được khó khăn gì cụ thể? Hiện tại khi chưa có nó thì anh/chị đang xử lý bằng cách nào?" |

**Đã sửa gì so với bản trước khi luyện** *(trích nguyên câu cũ từ buổi phỏng vấn của mình)*:

| Câu cũ | Vấn đề gặp phải khi hỏi thật | Câu mới |
| --- | --- | --- |
| "Gần đây nhất, bạn có gặp khó khăn trong quá trình học mà bạn không được hỗ trợ kịp thời không?" | Câu đóng, lại cài sẵn kết luận "không được hỗ trợ kịp thời"; 25 giây đầu chỉ thu được "có" | "Kể mình nghe về lần gần nhất trong 7 ngày qua bạn bị mắc ở một đoạn code/slide và phải tìm sự trợ giúp. Hôm đó là bài nào?" |
| "Tức là bạn chủ động liên hệ trực tiếp với Lab Coach?" | Tóm tắt hộ interviewee; họ chỉ đáp "cũng tương tự vậy" nên không rõ hành vi thật khớp tới đâu | "Rồi sau đó thế nào?" |
| *(không có câu nào đào phía người hỗ trợ)* | Tín hiệu mạnh nhất — người đến hỗ trợ không phụ trách phần đó — xuất hiện ở 1:18 rồi bị bỏ trôi | "Bạn đã phải giải thích những gì để Coach hiểu được phần bạn đang làm? Coach có nắm được ngay không?" |
| Câu hỏi ảnh hưởng gộp chung chung | Cả ba interview ban đầu đều dừng ở "chưa được giải thích" / "cảm thấy nản" | "Sau lần đó bạn đã làm gì tiếp theo? Việc đó ảnh hưởng thế nào đến việc hoàn thành bài tập hôm đó?" |

Ngoài bốn câu trên, **trọng tâm Big 3 đổi hẳn** và guide có thêm nhánh riêng cho Lab Coach — vì evidence cho thấy phần lớn nút thắt nằm ở phía người hỗ trợ, chỗ mà guide bản đầu không hề chạm tới.

---

## 4. Practice Reflection

1. **Câu hỏi nào đã giúp user kể một tình huống cụ thể?**

   *"Lúc mà bạn gặp tình huống đấy, bạn có làm gì tiếp theo không? Kiểu để được hỗ trợ ấy."* Câu này hỏi vào **hành động đã làm** chứ không hỏi trạng thái, nên interviewee chuyển từ trả lời có/không sang kể việc mình đã làm: "mình sẽ la lên", "lên Discord, hay là nhắn các anh".

2. **Chỗ nào mình cần làm tốt hơn ở lần phỏng vấn thật?**

   Ba điều cụ thể: (a) không mở bằng câu có/không, nhất là câu đã cài sẵn kết luận mình muốn nghe — *"bạn có gặp khó khăn... mà không được hỗ trợ kịp thời không?"* làm mất 25 giây đầu; (b) không tóm tắt hộ interviewee như *"Tức là bạn chủ động liên hệ trực tiếp với Lab Coach?"*; (c) khi nghe thấy tín hiệu trái giả thuyết thì đào ngay tại chỗ. Buổi này chỉ dài 1 phút 41 giây và mình đóng lại đúng lúc đáng ra phải bắt đầu — tín hiệu quan trọng nhất xuất hiện ở giây 1:18.

3. **Sau khi luyện, nhóm đã sửa Conversation Guide ở đâu và vì sao?**

   Bốn câu ở bảng cuối phần 3, và hai thay đổi lớn hơn. Thứ nhất, **trọng tâm Big 3 đổi**: guide cũ xây trên giả định learner không nêu được vấn đề, nhưng cả hai learner đều nêu ngay và nêu to, nên nhánh đó hết giá trị phân biệt. Thứ hai, sau interview Lab Coach, nhóm **thêm hẳn một bộ câu hỏi cho phía người hỗ trợ** — hỏi về độ trễ phát hiện, số lượt follow-up để làm rõ câu hỏi, và cách xử lý lỗi chung mà không phải đi từng bàn. Đây là phần guide bản đầu không có, mà lại là nơi chứa nút thắt thật.

---

## 5. AI Support Log

**Cách mình dùng AI:**

Mình chọn Case C, chốt hướng đi, quyết định cấu trúc bài và duyệt từng phần trước khi đưa vào. AI đóng vai công cụ: dựng khung bốn chặng theo cấu trúc BTC, soạn bản nháp cho capability trung tính, chuỗi Change, hai nhánh Pain và Evidence Map ở Chặng 1; sau khi có transcript thì tổng hợp evidence và đối chiếu bài của mình với bản tổng hợp của nhóm.

**Điểm nào AI làm sai hoặc hời hợt:**

Ba lần AI đi sai và mình phải sửa lại:

1. Trước khi có dữ liệu thật, AI dựng một Interview Record mô phỏng — đó là kịch bản, không phải evidence, và đã bị thay hoàn toàn bằng transcript thật.
2. Ở Chặng 1, cả hai nhánh Pain AI soạn (không định vị được chỗ hổng / ngại hỏi) đều bị phỏng vấn thật bác bỏ. Suy luận trên bàn giấy không thay được việc đi hỏi người thật.
3. Sau hai interview learner, AI kết luận gọn "phát hiện không phải nút thắt vì learner tự lộ diện". Interview Lab Coach của nhóm bác lại kết luận đó: Coach vẫn mù với nhóm im lặng và phải đi dò từng bàn. Kết luận đúng phải tách thành hai phân khúc learner, và đó là phần mình sửa khi ghép bài của mình với bản nhóm trưởng.

**Mình đã tự sửa thế nào:**

Bốn chỗ mình can thiệp và bác lại output của AI:

1. **Bỏ toàn bộ Interview Record do AI dựng.** AI đề nghị một buổi phỏng vấn mô phỏng với số liệu tự nghĩ ra để bài trông đầy đủ. Mình không dùng, và thay bằng transcript buổi phỏng vấn thật mình tự thực hiện — kể cả khi buổi đó chỉ dài 1 phút 41 giây và lộ rõ lỗi hỏi của mình.

2. **Không chấp nhận kết luận "phát hiện không phải nút thắt".** Sau hai interview learner, AI chốt gọn như vậy. Khi bản tổng hợp của nhóm trưởng có thêm interview Lab Coach, mình yêu cầu đối chiếu lại và sửa thành hai phân khúc learner — nhóm lên tiếng hỏng ở routing, nhóm im lặng hỏng ở detection. Đây là phần mình thấy bản nhóm cũng chưa tách rõ, nên giữ lại như đóng góp riêng.

3. **Cắt bài từ sáu file xuống đúng cấu trúc BTC.** Bản đầu có `worksheets/` và `group/` với nhiều phiên bản trùng nhau. Mình yêu cầu rút về một phiên bản mới nhất duy nhất, và kéo bảng Actor cùng Evidence Map vào README để không mất mắt xích nào trong chuỗi Solution → Evidence.

4. **Giữ lại phần chỉ ra lỗi của chính mình** trong `interview/notes.md`, dù nó làm bài nhìn kém hoàn hảo hơn. Ba lỗi hỏi — câu mở đóng cài sẵn kết luận, tóm tắt hộ interviewee, và dừng phỏng vấn ngay khi tín hiệu quan trọng nhất vừa xuất hiện — đều là quan sát từ chính transcript của mình, và chính chúng dẫn tới bốn câu sửa trong guide.

**Điều mình rút ra:** giả thuyết viết trên bàn nghe rất hợp lý mà sai hoàn toàn. Cả Pain A lẫn Pain B nhóm dựng đều đổ chỉ sau một câu của người thật: "mình sẽ la lên". Một phút 41 giây phỏng vấn thật có giá trị hơn cả buổi ngồi suy luận.

---

## Ghi chú về bản ghi phỏng vấn

[interview/notes.md](interview/notes.md) chứa Interview Record của chính lượt mình làm interviewer, kèm transcript đầy đủ ở phụ lục cuối file.

- Người được phỏng vấn đã đồng ý cho ghi lại: **Có** — đã xin phép trước khi bắt đầu ghi.
- Bản ghi (~1 phút 41 giây) lưu trên Drive của nhóm: [interview/recording-link.md](interview/recording-link.md).
- Bản ghi được dùng để xem lại, bóc transcript và phục vụ bài học — đúng mục đích đã nói khi xin phép.

---

## Cấu trúc repo

```
Track1_Day17_2A202601840_PhamTuanAnh/
├── README.md
└── interview/
    ├── notes.md
    └── recording-link.md
```

---

## Kiểm tra trước khi nộp

- [X] Repo đúng tên `Track1_Day17_MHV_HoVaTen`
- [X] `README.md` đủ năm phần
- [X] `interview/notes.md` là notes của chính lượt bạn làm interviewer
- [X] Bản ghi hoặc recording link mở được với giảng viên/TA
- [X] Người được phỏng vấn đã đồng ý cho ghi lại
- [X] Conversation Guide không làm lộ solution và đã được sửa sau khi luyện
