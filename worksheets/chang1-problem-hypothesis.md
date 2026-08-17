# Chặng 1 — Đặt giả thuyết · 60 phút

**Mục tiêu:** mở lại toàn bộ logic đang bị nén trong solution directive và biến nó thành một giả thuyết đủ cụ thể để evidence có thể làm thay đổi.

```
Solution → Change → Actor → Situation & Job → Pain → Evidence
```

> **Luật chặng:** 15 phút đầu mỗi thành viên tự suy luận, **chưa dùng AI**. Sau đó nhóm so các nhánh, giữ lại những cách giải thích khác nhau và cùng đi tiếp.
> Mọi nội dung trong chặng này đều là **hypothesis**, chưa phải fact về user.

---

## 1. Solution — Gỡ solution khỏi hình thức cụ thể

**Case đã chọn:** Case C — AI Support Radar (VLearn)

<details>
<summary>Bảng directive gốc của case</summary>

| Thành phần | Solution đã mô tả |
| --- | --- |
| Trigger | Kết thúc một phiên học |
| Input | Slide navigation, notes, answers và AI Chat |
| AI action | Suy đoán nhu cầu hỗ trợ và xếp mức ưu tiên |
| Output | Support Queue cho giảng viên |
| Human control | Giảng viên quyết định có can thiệp hay không |

</details>

> **Câu hỏi dẫn dắt**
> - Câu nào trong directive đang mô tả giao diện, tên feature hoặc công nghệ?
> - Nếu bỏ tên nút, màn hình và AI action, khả năng cần tạo ra là gì?
> - Nhóm có đang mặc định cách triển khai được giao là cách duy nhất không?
> - Capability có thể được mô tả mà không dùng tên feature không?

**Solution directive** *(nguyên văn)*:

Sau mỗi phiên học, hệ thống phân tích các tín hiệu như di chuyển giữa slide, dừng lâu hoặc xem lại, highlight và ghi chú, đánh dấu "Chưa hiểu", thay đổi câu trả lời, và nội dung trao đổi với AI Chat. AI tạo một Support Queue cho giảng viên, gồm: (1) những học viên có thể cần hỗ trợ, (2) phần nội dung mà họ có thể đang gặp khó khăn, (3) các tín hiệu dẫn đến nhận định đó, (4) một hành động hỗ trợ được đề xuất. Giảng viên xem lại và quyết định có liên hệ với học viên hay không.

**Những chỗ đang mô tả hình thức, không phải khả năng:** "Support Queue", "AI phân tích tín hiệu", "danh sách cho giảng viên", "hành động hỗ trợ được đề xuất" — đều là tên feature hoặc mô tả output.

**Capability trung tính:**

Sau mỗi phiên học, biến những dấu hiệu vướng mắc rải rác của người học thành một danh sách ưu tiên có thể hành động — ai nên được hỏi thăm, về phần nội dung nào, dựa trên căn cứ gì.

---

## 2. Change — Làm lộ chuỗi thay đổi được kỳ vọng

> **Câu hỏi dẫn dắt**
> - User sẽ biết hoặc làm được điều gì khác?
> - Hành vi nào phải thay đổi để outcome xảy ra?
> - Trạng thái hoặc kết quả nào được kỳ vọng thay đổi?
> - Đâu là output team tạo ra, đâu là outcome team chỉ có thể ảnh hưởng?
> - Nếu user không thay đổi hành vi, solution còn tạo được outcome không?

```
Solution → Người phụ trách lớp nhìn thấy dấu hiệu vướng mắc mà trước đây không thấy
        → Họ chủ động liên hệ đúng người, đúng phần nội dung; học viên phản hồi và được gỡ vướng
        → Outcome
```

**Các thay đổi được kỳ vọng:**

1. Người phụ trách lớp biết ai đang vướng ở phần nào mà không phải chờ học viên tự lên tiếng.
2. Việc hỗ trợ chuyển từ "ai hỏi thì trả lời" sang chủ động, có thứ tự ưu tiên.
3. Học viên vướng nhưng im lặng được tiếp cận trong vài ngày, thay vì tự xoay xở hoặc bỏ qua luôn.

**Output vs outcome:** output team tạo ra là *danh sách ưu tiên được sinh ra sau mỗi buổi*. Outcome team chỉ có thể ảnh hưởng là *học viên thực sự gỡ được chỗ vướng*. Giữa hai cái có ít nhất hai hành vi người khác phải làm: người phụ trách lớp phải mở danh sách và liên hệ, học viên phải phản hồi.

**Nếu user không đổi hành vi:** danh sách vẫn được sinh ra nhưng không có outcome nào. Toàn bộ giá trị nằm ở hai mắt xích hành vi, không nằm ở chỗ sinh ra danh sách.

---

## 3. Actor — Xác định các nhóm người có liên quan

> **Câu hỏi dẫn dắt**
> - Ai trực tiếp sử dụng solution? Ai trực tiếp trải nghiệm pain?
> - Ai phải thay đổi hành vi để outcome xảy ra?
> - Ai chịu hậu quả nếu problem không được giải quyết? Ai hưởng lợi gián tiếp?
> - Người nhận feature có chắc là người sở hữu pain chính không?

| Actor | Họ đang làm gì? | Pain hoặc hậu quả có thể có | Họ hưởng lợi thế nào? |
| --- | --- | --- | --- |
| Learner | Sau buổi học ngồi làm bài tập, xem lại slide, hỏi AI Chat | Vướng nhưng không gọi tên được chỗ vướng; tự xoay xở rồi làm qua loa, lỗ hổng trôi sang buổi sau | Được hỏi thăm đúng lúc, đúng phần nội dung |
| Instructor | Chấm bài, soạn buổi sau, trả lời tin nhắn rải rác | Không biết ai đang đuối cho tới khi có người nộp trễ hoặc vắng học | Có danh sách ưu tiên thay vì phán đoán cảm tính |
| Coach / TA | Hỗ trợ 1-1 theo người chủ động nhắn tin | Thời gian bị phân bổ theo người lên tiếng to nhất; người im lặng bị bỏ sót | Biết nên chủ động tìm ai trước |

**Actor nhóm chọn để điều tra trước:** Learner

**Vì sao chọn nhánh này thay vì actor khác:**

Người *nhận* feature là instructor, nhưng người *sở hữu pain gốc* là learner. Toàn bộ chuỗi thay đổi sụp nếu learner thực ra tự gỡ được trong vài phút, hoặc không phản hồi khi được liên hệ — nên learner là mắt xích rủi ro cao nhất và cũng là chỗ giả thuyết dễ bị bác bỏ nhất. Ngoài ra, trong giờ lab nhóm chỉ tiếp cận được learner.

> ⚠️ **Vòng này chỉ có learner-side evidence; instructor-side job chưa được kiểm chứng.**

---

## 4. Situation & Job — User đang cố làm gì trong tình huống nào?

> **Câu hỏi dẫn dắt**
> - Tình huống bắt đầu khi chuyện gì xảy ra? Lúc đó user đang cố hoàn thành việc gì?
> - Vì sao việc đó quan trọng với họ? Hiện tại họ đang làm thế nào?
> - Họ bắt đầu gặp vướng mắc ở điểm nào?

| Bước | Nội dung |
| --- | --- |
| Tình huống bắt đầu | Buổi học kết thúc; tối hôm đó learner mở lại slide để làm bài tập và nhận ra có một phần mình không theo kịp |
| User muốn hoàn thành việc gì | Hiểu lại phần bị hổng đủ để làm tiếp bài tập và không bị đuối ở buổi sau |
| Hiện tại họ làm như thế nào | Xem lại slide từ đầu, tua recording, hỏi AI Chat, nhắn bạn cùng nhóm, tìm Google |
| Điểm bắt đầu gặp vướng mắc | Không diễn đạt được chính xác mình không hiểu chỗ nào, nên hỏi gì cũng nhận về câu trả lời chung chung, không trúng chỗ đang kẹt |

**Mô tả Situation & Job:**

> Khi **vừa kết thúc một buổi học và ngồi làm bài tập vào buổi tối**, **learner** đang cố **hiểu lại phần nội dung mình không theo kịp** bằng cách **tự xem lại slide, tua recording và hỏi AI Chat**.

**JTBD Hypothesis:**

> Khi **tôi phát hiện mình không theo kịp một phần nội dung sau buổi học**, tôi muốn **gỡ được chỗ hổng đó trước buổi kế tiếp**, để có thể **làm được bài tập và không bị trôi xa hơn**.

*Job này vẫn tồn tại nếu bỏ hết AI và feature khỏi bối cảnh: người học vẫn phải tự gỡ chỗ hổng trước buổi sau.*

---

## 5. Pain — Viết các cách giải thích cạnh tranh

> **Câu hỏi dẫn dắt**
> - Barrier cụ thể nào đang cản actor hoàn thành job? Họ thiếu thông tin, kỹ năng, thời gian hay sự hỗ trợ?
> - Họ có nhận ra mình đang gặp pain không? Nếu không xử lý, hậu quả thực tế là gì?
> - Có cách giải thích nào khác cho cùng hành vi?
> - Pain có còn tồn tại nếu solution directive biến mất khỏi đầu nhóm không?

**Pain Hypothesis A:**

> Khi **ngồi làm bài tập sau buổi học**, **learner** gặp khó khăn trong việc **gỡ phần nội dung mình không theo kịp** vì **không định vị được chính xác mình hổng ở đâu để đặt câu hỏi**, dẫn đến **tua lại slide và hỏi AI Chat nhiều lượt vẫn không trúng, cuối cùng làm qua loa phần đó hoặc bỏ trống**.

**Pain Hypothesis B — cách giải thích cạnh tranh:**

> Khi **ngồi làm bài tập sau buổi học**, **learner** gặp khó khăn trong việc **gỡ phần nội dung mình không theo kịp** vì **hỏi người khác tốn chi phí xã hội và thời gian chờ (ngại làm phiền, sợ bị đánh giá, không biết hỏi lúc nào)**, dẫn đến **họ chọn tự xoay xở hoặc chấp nhận hiểu lơ mơ rồi đi tiếp**.

*Cùng một hành vi quan sát được — tua đi tua lại, hỏi AI Chat, không nhắn giảng viên — nhưng hai barrier khác hẳn nhau: A là "không biết hỏi gì", B là "biết nhưng không dám/không tiện hỏi".*

**Giả thuyết nhóm chọn để điều tra trước:**  **A**  /  B

**Lý do chọn:** A chính là giả định nền mà directive đang đứng lên — Support Queue chỉ có giá trị nếu chỗ vướng *phải* được người ngoài chỉ ra. Nếu B mới đúng, việc chỉ đúng chỗ vướng không đổi được gì và solution phải khác hẳn. A cũng là giả thuyết dễ bị bác bỏ hơn chỉ bằng một câu chuyện cụ thể.

**Pain có còn nếu bỏ solution directive không?** Có. Việc "biết mình hổng nhưng không gọi tên được chỗ hổng" tồn tại độc lập với bất kỳ tính năng nào.

---

## 6. Evidence — Xác định điều cần tìm trước khi viết câu hỏi

> **Câu hỏi dẫn dắt**
> - User có kể được một sự kiện gần đây với trình tự cụ thể không? Trong sự kiện đó họ thực sự đã làm gì?
> - Họ đã dùng workaround nào và bỏ ra bao nhiêu công sức? Tình huống có lặp lại không?
> - Hậu quả quan sát được là gì? Điều gì cho thấy pain không đủ quan trọng?
> - Evidence nào sẽ khiến nhóm sửa hoặc bác bỏ hypothesis?

| Cần kiểm tra | Evidence làm nhóm tin hơn | Evidence làm nhóm nghi ngờ hoặc bác bỏ |
| --- | --- | --- |
| Situation có thật | Kể được một buổi cụ thể trong 2 tuần gần đây: hôm nào, nội dung gì, ngồi làm lúc mấy giờ | Chỉ nói "thỉnh thoảng cũng có", không nhớ nổi lần nào |
| Pain có ý nghĩa | Bỏ ra trên 30 phút mà vẫn không gỡ được, phải hoãn hoặc bỏ dở | Vài phút là qua; "buổi sau tự khắc hiểu" |
| Workaround tồn tại | Kể được chuỗi: mở lại slide → tua recording → hỏi AI Chat nhiều lượt → nhắn bạn | Không làm gì cả, chờ tới buổi sau |
| Consequence tồn tại | Nộp trễ, bỏ trống một phần, làm theo mẫu mà không hiểu, ảnh hưởng buổi sau | Vẫn nộp bài bình thường, không kể được hậu quả nào |
| Pattern có lặp | Kể được lần trước đó và khoảng cách thời gian giữa hai lần | Chỉ đúng một lần, do hôm đó nghỉ học hoặc lý do bất thường |

---

## Chốt Problem Hypothesis và park solution

**Problem Hypothesis nhóm mang sang Chặng 2:**

Learner trong khoá học lịch dày, sau buổi học khi ngồi làm bài tập thường phát hiện mình hổng một phần nội dung nhưng không gọi tên được chính xác chỗ hổng để hỏi đúng câu; họ tua lại slide và hỏi AI Chat nhiều lượt, tốn thời gian mà vẫn không gỡ được, dẫn tới làm qua loa phần đó và bước vào buổi sau với lỗ hổng chưa xử lý.

**Điều gì phải đúng để giả thuyết đứng vững:**

1. Learner thực sự có vướng mắc mà tự họ không nêu ra được thành câu hỏi.
2. Chỗ vướng đó nhận ra được từ bên ngoài, không chỉ nằm trong đầu learner.
3. Được chỉ đúng chỗ vướng sẽ làm learner hành động khác đi, chứ không chỉ "biết thêm".

**Điều gì có thể khiến nhóm sửa hoặc bác bỏ giả thuyết:**

Learner tự gỡ được trong dưới 10 phút bằng AI Chat hoặc bạn học; hoặc họ biết rõ mình hổng chỗ nào nhưng vẫn không hỏi (→ nghiêng về Pain B); hoặc không kể được hậu quả nào và tình huống không lặp lại.

**Solution Parking Lot:**

| # | Hướng giải quyết có thể có | AI / Không sử dụng AI |
| --- | --- | --- |
| 1 | Danh sách ưu tiên tự sinh sau mỗi buổi từ tín hiệu học tập (chính directive) | AI |
| 2 | Ô "chỗ mình chưa chắc" cuối mỗi buổi, learner tự đánh dấu, tổng hợp lại thành danh sách | Không sử dụng AI |
| 3 | 10 phút mở đầu buổi sau đi qua 3 chỗ được đánh dấu nhiều nhất, không nêu tên ai | Không sử dụng AI |
| 4 | Cặp bạn học check-in nhau sau mỗi buổi theo một checklist cố định 3 câu | Không sử dụng AI |
| 5 | Tóm tắt hội thoại AI Chat của learner thành "câu hỏi thật sự bạn đang muốn hỏi" để họ tự gửi đi | AI |

---

## ✅ Tự kiểm · CHECKPOINT 1 — Problem Hypothesis

- [x] Lần theo được đủ chuỗi 6 lớp, không nhảy cóc
- [x] Capability trung tính không chứa tên feature / tên màn hình / chữ "AI"
- [x] Có **hai** cách giải thích cạnh tranh (Pain A và Pain B), đã chọn A để điều tra trước
- [x] Nói rõ được điều gì có thể làm giả thuyết được chọn trở nên sai
- [x] Pain không được viết dưới dạng "thiếu feature X"
- [x] Parking Lot đủ 5 hướng, có 3 hướng không dùng AI

---

## 📌 Cập nhật sau Chặng 3 — giả thuyết đã bị evidence bác

> Phần trên giữ nguyên là suy luận **trước** khi phỏng vấn. Mục này ghi lại điều đã thay đổi sau khi có evidence, không sửa ngược lên trên.

**Cả Pain A lẫn Pain B đều không đứng vững.** Hai learner được phỏng vấn ([../interview/notes.md](../interview/notes.md) và [../group/interview-learner-2.md](../group/interview-learner-2.md)) đều **chủ động nêu vấn đề ngay** — "la lên", nhắn Discord, gọi Lab Coach. Họ không thiếu khả năng định vị chỗ vướng (A) và không ngại hỏi (B).

**Ba cơ chế hỏng thật, đều nằm ở phía người hỗ trợ:**

1. **Capacity** — Lab Coach ít so với số học viên; có lần yêu cầu bị quên.
2. **Ownership / routing** — người tiếp nhận không phụ trách phần nội dung được hỏi, nên "chưa trả lời thỏa đáng".
3. **Context transfer** — người hỗ trợ chưa nắm bối cảnh bài/dự án, learner phải giải thích lại từ đầu.

**Pain Hypothesis C — thay cho A:**

> Khi learner vướng một phần nội dung trong hoặc sau buổi học và **đã chủ động nêu qua kênh hỗ trợ**, họ vẫn không gỡ được vì người tiếp nhận không phụ trách đúng phần đó và không có sẵn bối cảnh bài/dự án, dẫn đến câu trả lời không thỏa đáng, phải giải thích lại từ đầu, hoặc yêu cầu bị quên.

**Điều gì sẽ bác Pain C:** learner nói lần nào raise lên cũng được giải đáp trong buổi; hoặc việc chờ và giải thích lại không dẫn tới hậu quả nào đo được.

**Hệ quả cho solution directive:** Support Queue được thiết kế để *phát hiện ai có thể đang cần hỗ trợ*. Evidence nói phát hiện không phải chỗ tắc — learner tự lộ diện. Nếu giữ hướng này, giá trị phải dịch sang thành phần (3) của directive — *gói tín hiệu và bối cảnh cho người hỗ trợ* — chứ không phải thành phần (1) *danh sách ai cần hỗ trợ*.

**Vẫn chưa kiểm chứng được:** consequence (cả hai interview đều dừng ở "chưa được giải thích" / "cảm thấy nản"), pattern lặp, và toàn bộ phía instructor/coach — nơi cả ba cơ chế trên thực sự diễn ra.
