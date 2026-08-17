# Track1_Day17_2A202601840_PhamTuanAnh

Bài nộp Track 1 · Day 17 — Problem Hypothesis & User Interview · **Case C — AI Support Radar**

---

## 1. Thông tin cá nhân và nhóm

| Mục | Nội dung |
| --- | --- |
| MHV | 2A202601840 |
| Họ tên | Phạm Tuấn Anh |
| Tên nhóm | *(điền)* |
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

> ⚠️ Vòng này chỉ có learner-side evidence; instructor-side job chưa được kiểm chứng.

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

Toàn bộ phần trên là suy luận **trước** khi phỏng vấn, giữ nguyên để đối chiếu.

Hai interview thật — [interview/notes.md](interview/notes.md) (lượt mình làm interviewer) và một interview learner thứ hai do thành viên khác trong nhóm thực hiện — **đều bác cả Pain A lẫn Pain B**. Learner không im lặng và không ngại hỏi: họ "la lên", nhắn Discord, gọi thẳng Lab Coach, và nói rõ được mình vướng phần nào.

Ba cơ chế hỏng thật, đều nằm ở phía người hỗ trợ:

1. **Capacity** — Lab Coach ít so với số học viên; có lần yêu cầu bị quên.
2. **Ownership / routing** — người tiếp nhận không phụ trách phần nội dung được hỏi, nên "chưa trả lời thỏa đáng".
3. **Context transfer** — người hỗ trợ chưa nắm bối cảnh bài/dự án, learner phải giải thích lại từ đầu.

**Pain Hypothesis C — thay cho A:**

> Khi learner vướng một phần nội dung trong hoặc sau buổi học và **đã chủ động nêu qua kênh hỗ trợ**, họ vẫn không gỡ được vì người tiếp nhận không phụ trách đúng phần đó và không có sẵn bối cảnh bài/dự án, dẫn đến câu trả lời không thỏa đáng, phải giải thích lại từ đầu, hoặc yêu cầu bị quên.

**Điều gì sẽ bác Pain C:** learner nói lần nào raise lên cũng được giải đáp trong buổi; hoặc việc chờ và giải thích lại không dẫn tới hậu quả nào đo được.

**Hệ quả cho solution directive:** Support Queue được thiết kế để *phát hiện ai có thể đang cần hỗ trợ*, nhưng evidence nói phát hiện không phải chỗ tắc — learner tự lộ diện. Nếu giữ hướng này, giá trị phải dịch sang thành phần (3) của directive — *gói tín hiệu và bối cảnh cho người hỗ trợ* — chứ không phải thành phần (1) *danh sách ai cần hỗ trợ*.

**Còn chưa kiểm chứng:** consequence (cả hai interview dừng ở "chưa được giải thích" / "cảm thấy nản"), pattern lặp, và toàn bộ phía instructor/coach — nơi cả ba cơ chế trên thực sự diễn ra.

---

## 3. Conversation Guide — phiên bản cuối

*Bản đã sửa sau khi phỏng vấn thật ở Chặng 3.*

**Tiêu chí tuyển người:** Chúng tôi cần nói chuyện với người đã **nêu một vấn đề học tập qua kênh hỗ trợ (Discord, nhắn trực tiếp, gọi Lab Coach)**, trong vòng **7** ngày gần đây — bất kể sau đó có được giải quyết hay không. Mục tiêu bao phủ **2 learner + 1 instructor/coach**.

**Recruitment check:** "Trong 7 ngày gần đây, bạn có thể kể tên một buổi cụ thể mà bạn phải nhờ hỗ trợ hoặc tự xoay xở với một phần bài không?"

**Lời mở đầu:**

"Bọn mình đang tìm hiểu cách mọi người xử lý những tình huống khó khăn trong quá trình học và hỗ trợ học. Mình muốn nghe về một lần xảy ra gần đây, các bước bạn đã làm và điều xảy ra sau đó. Không có câu trả lời đúng hay sai; bọn mình không đánh giá bạn và cũng chưa giới thiệu giải pháp nào. Mình sẽ hỏi chủ yếu về việc đã xảy ra, không phải điều bạn nghĩ có thể xảy ra trong tương lai."

**Story opener:** "Kể mình nghe về lần gần nhất trong 7 ngày qua bạn bị mắc ở một phần bài và phải nhờ tới ai đó. Hôm đó là buổi nào, bạn đang làm phần gì?"

**Big 3 Questions — learner:**

| # | Điều cần học | Câu hỏi sẽ dùng |
| --- | --- | --- |
| 1 *(đáng sợ)* | Sau khi learner **đã nêu** vấn đề, cái gì làm lần hỗ trợ đó thất bại — sai người phụ trách, thiếu bối cảnh, hay chỉ là chờ lâu? | "Sau khi bạn nêu vấn đề, chuyện gì xảy ra tiếp theo? Ai là người đến hỗ trợ bạn, bạn phải giải thích lại những gì, và họ trả lời thế nào?" |
| 2 | Hậu quả thật sau một lần hỗ trợ không thỏa đáng | "Sau lần đó bạn làm gì với phần chưa gỡ được? Nó ảnh hưởng thế nào tới bài hoặc buổi học sau?" |
| 3 | Tần suất và pattern | "Trong tuần vừa rồi chuyện tương tự xảy ra mấy lần? Lần gần nhất trước đó là khi nào và kết thúc ra sao?" |

**Big 3 Questions — instructor/coach:**

| # | Câu hỏi sẽ dùng |
| --- | --- |
| 1 | "Khi nhận yêu cầu đó, bạn cần biết những gì trước khi trả lời được? Bạn lấy thông tin đó bằng cách nào và mất bao lâu?" |
| 2 | "Lần đó kết thúc thế nào? Có yêu cầu nào bạn không xử lý được hoặc bị rơi không?" |
| 3 | "Trong tuần vừa rồi có bao nhiêu yêu cầu rơi vào phần bạn không phụ trách? Bạn xử lý thế nào?" |

**Probe bank — chỉ dùng khi cần đào sâu:**

- "Lúc đó chuyện gì xảy ra tiếp theo?"
- "Bạn đã làm gì cụ thể?"
- "Vì sao bạn chọn cách đó?"
- "Phần nào khó nhất hoặc tốn thời gian nhất?"
- "Bạn đã thử cách nào khác chưa?"
- "Việc đó kéo theo hậu quả gì?"
- "Lần gần nhất trước đó là khi nào?"
- "Người đến hỗ trợ bạn có nắm được bài/dự án bạn đang làm không? Bạn phải kể lại từ đâu?"
- "Có lần nào bạn nêu rồi mà không ai quay lại không? Lúc đó bạn làm gì?"
- "Bạn chờ khoảng bao lâu? Trong lúc chờ bạn làm gì?"

**Ba phản xạ khi data lệch:**

| User đưa ra | Phản xạ | Cách quay lại evidence |
| --- | --- | --- |
| Lời khen | Deflect | "Cảm ơn bạn. Mình muốn quay lại lần gần nhất: lúc đó bạn đã làm gì cụ thể?" |
| Câu chung chung hoặc lời hứa tương lai | Anchor | "Lần gần nhất chuyện đó thực sự xảy ra là khi nào? Bạn đã xử lý thế nào lúc đó?" |
| Ý tưởng hoặc feature request | Dig | "Điều đó giúp bạn làm được gì? Trước đây, ở lần gần nhất, bạn đã xử lý việc đó ra sao?" |

**Đã sửa gì so với bản trước khi luyện:**

| Câu cũ | Vấn đề gặp phải khi hỏi thật | Câu mới |
| --- | --- | --- |
| "Gần đây nhất, bạn có gặp khó khăn trong quá trình học mà bạn không được hỗ trợ kịp thời không?" | Câu đóng, lại cài sẵn kết luận "không được hỗ trợ kịp thời"; 25 giây đầu chỉ thu được "có" | "Kể mình nghe về lần gần nhất trong 7 ngày qua bạn bị mắc ở một phần bài và phải nhờ tới ai đó. Hôm đó là buổi nào?" |
| "Tức là bạn chủ động liên hệ trực tiếp với Lab Coach?" | Tóm tắt hộ interviewee; họ chỉ đáp "cũng tương tự vậy" nên không rõ hành vi thật khớp tới đâu | "Rồi sau đó thế nào?" |
| *(không có câu nào đào phía người hỗ trợ)* | Tín hiệu mạnh nhất — người đến hỗ trợ không phụ trách phần đó — xuất hiện ở 1:18 rồi bị bỏ trôi | "Ai là người đến hỗ trợ bạn? Bạn phải giải thích lại những gì, và họ trả lời thế nào?" |
| Câu hỏi ảnh hưởng gộp chung chung | Cả hai interview đều dừng ở "chưa được giải thích" / "cảm thấy nản", không có hậu quả đo được | "Sau lần đó bạn làm gì với phần chưa gỡ được?" |

Ngoài bốn câu trên, **trọng tâm Big 3 cũng đổi**: guide cũ xây trên giả định learner không nêu được vấn đề; cả hai learner đều nêu ngay, nên câu hỏi có giá trị bây giờ nằm ở *sau khi đã hỏi*.

---

## 4. Practice Reflection

1. **Câu hỏi nào đã giúp user kể một tình huống cụ thể?**

   *"Lúc mà bạn gặp tình huống đấy, bạn có làm gì tiếp theo không? Kiểu để được hỗ trợ ấy."* Câu này hỏi vào **hành động đã làm** chứ không hỏi trạng thái, nên interviewee chuyển từ trả lời có/không sang kể việc mình đã làm: "mình sẽ la lên", "lên Discord, hay là nhắn các anh".

2. **Chỗ nào mình cần làm tốt hơn ở lần phỏng vấn thật?**

   Ba điều cụ thể: (a) không mở bằng câu có/không, nhất là câu đã cài sẵn kết luận mình muốn nghe — *"bạn có gặp khó khăn... mà không được hỗ trợ kịp thời không?"* làm mất 25 giây đầu; (b) không tóm tắt hộ interviewee như *"Tức là bạn chủ động liên hệ trực tiếp với Lab Coach?"*; (c) khi nghe thấy tín hiệu trái giả thuyết thì đào ngay tại chỗ. Buổi này chỉ dài 1 phút 41 giây và mình đóng lại đúng lúc đáng ra phải bắt đầu — tín hiệu quan trọng nhất xuất hiện ở giây 1:18.

3. **Sau khi luyện, nhóm đã sửa Conversation Guide ở đâu và vì sao?**

   Bốn câu ở bảng cuối phần 3, và quan trọng hơn là đổi cả trọng tâm Big 3. Guide cũ xây trên giả định learner không nêu được vấn đề (không định vị được chỗ hổng, hoặc ngại hỏi). Cả hai learner được phỏng vấn đều nêu ngay và nêu to, nên hai nhánh đó hết giá trị phân biệt. Big 3 mới hỏi vào chỗ thật sự hỏng: sau khi learner đã nêu, cái gì làm lần hỗ trợ đó thất bại.

---

## 5. AI Support Log

**Cách mình dùng AI:**

Mình chọn Case C, chốt hướng đi, quyết định cấu trúc bài và duyệt từng phần trước khi đưa vào. AI đóng vai công cụ: dựng khung bốn chặng theo cấu trúc BTC, soạn bản nháp cho capability trung tính, chuỗi Change, hai nhánh Pain và Evidence Map ở Chặng 1; sau khi có transcript thì tổng hợp evidence từ hai interview thành Conversation Guide phiên bản cuối.

**Điểm nào AI làm sai hoặc hời hợt:**

Trước khi có dữ liệu thật, AI dựng một Interview Record mô phỏng — đó là kịch bản, không phải evidence, và đã bị thay hoàn toàn bằng transcript thật. Ở Chặng 1, cả hai nhánh Pain mà AI soạn (không định vị được chỗ hổng / ngại hỏi) đều bị phỏng vấn thật bác bỏ — suy luận trên bàn giấy không thay được việc đi hỏi người thật.

**Mình đã tự sửa thế nào:**

*(Phần này viết bằng chữ của mình — sửa diễn đạt nào, bỏ ý nào của AI, và tự rút ra điều gì sau khi phỏng vấn.)*

................................................................................

---

## Ghi chú về bản ghi phỏng vấn

[interview/notes.md](interview/notes.md) chứa Interview Record của chính lượt mình làm interviewer, kèm transcript đầy đủ ở cuối file.

- Người được phỏng vấn đã đồng ý cho ghi lại: **Có** — đã xin phép trước khi bắt đầu ghi.
- Bản ghi: `interview/recording.m4a` (~1 phút 41 giây), chỉ dùng để xem lại, bóc transcript và phục vụ bài học; không chia sẻ công khai.

---

## Cấu trúc repo

```
Track1_Day17_2A202601840_PhamTuanAnh/
├── README.md
└── interview/
    ├── notes.md
    └── recording.m4a
```

---

## Kiểm tra trước khi nộp

- [X] Repo đúng tên `Track1_Day17_MHV_HoVaTen`
- [X] `README.md` đủ năm phần
- [X] `interview/notes.md` là notes của chính lượt bạn làm interviewer
- [X] Bản ghi hoặc recording link mở được với giảng viên/TA
- [X] Người được phỏng vấn đã đồng ý cho ghi lại
- [X] Conversation Guide không làm lộ solution và đã được sửa sau khi luyện
