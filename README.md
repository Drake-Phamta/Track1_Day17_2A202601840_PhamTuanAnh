# Track1_Day17_2A202601840_PhamTuanAnh

Bài nộp Track 1 · Day 17 — Problem Hypothesis & User Interview.

---

## 1. Thông tin cá nhân và nhóm

| Mục            | Nội dung                                                      |
| --------------- | -------------------------------------------------------------- |
| MHV             | 2A202601840                                                    |
| Họ tên        | Phạm Tuấn Anh                                                |
| Tên nhóm      | *(điền)*                                                   |
| Thành viên    | Nguyễn Ngọc Chi<br />Nguyễn Minh Hiếu<br />Phạm Tuấn Anh |
| Case đã chọn | **Case C — AI Support Radar**                           |

---

## 2. Problem Hypothesis Brief

**Solution directive (nguyên văn):**

Sau mỗi phiên học, hệ thống phân tích các tín hiệu như di chuyển giữa slide, dừng lâu hoặc xem lại, highlight và ghi chú, đánh dấu "Chưa hiểu", thay đổi câu trả lời, và nội dung trao đổi với AI Chat. AI tạo một Support Queue cho giảng viên, gồm: (1) những học viên có thể cần hỗ trợ, (2) phần nội dung mà họ có thể đang gặp khó khăn, (3) các tín hiệu dẫn đến nhận định đó, (4) một hành động hỗ trợ được đề xuất. Giảng viên xem lại và quyết định có liên hệ với học viên hay không.

**Capability trung tính:**

> Sau mỗi phiên học, biến những dấu hiệu vướng mắc rải rác của người học thành một danh sách ưu tiên có thể hành động — ai nên được hỏi thăm, về phần nội dung nào, dựa trên căn cứ gì.

**Chuỗi thay đổi được kỳ vọng:**

```
Solution → Người phụ trách lớp nhìn thấy dấu hiệu vướng mắc mà trước đây không thấy
        → Họ chủ động liên hệ đúng người, đúng phần nội dung; học viên phản hồi và được gỡ vướng
        → Outcome
```

Output team tạo ra là danh sách ưu tiên; outcome team chỉ có thể ảnh hưởng là việc học viên thực sự gỡ được chỗ vướng. Giữa hai cái có hai hành vi người khác phải làm — người phụ trách lớp phải mở danh sách và liên hệ, học viên phải phản hồi.

**Actor được chọn để điều tra trước:** Learner

**Vì sao chọn actor này:** người *nhận* feature là instructor, nhưng người *sở hữu pain gốc* là learner. Toàn bộ chuỗi thay đổi sụp nếu learner thực ra tự gỡ được trong vài phút, hoặc không phản hồi khi được liên hệ — đây là mắt xích rủi ro cao nhất và cũng là chỗ giả thuyết dễ bị bác bỏ nhất.

> ⚠️ Vòng này chỉ có learner-side evidence; instructor-side job chưa được kiểm chứng.

**Situation & Job:**

> Khi **vừa kết thúc một buổi học và ngồi làm bài tập vào buổi tối**, **learner** đang cố **hiểu lại phần nội dung mình không theo kịp** bằng cách **tự xem lại slide, tua recording và hỏi AI Chat**.

**JTBD Hypothesis:**

> Khi **tôi phát hiện mình không theo kịp một phần nội dung sau buổi học**, tôi muốn **gỡ được chỗ hổng đó trước buổi kế tiếp**, để có thể **làm được bài tập và không bị trôi xa hơn**.

**Pain Hypothesis A** *(nhóm chọn)*:

> Khi ngồi làm bài tập sau buổi học, learner gặp khó khăn trong việc gỡ phần nội dung mình không theo kịp vì **không định vị được chính xác mình hổng ở đâu để đặt câu hỏi**, dẫn đến tua lại slide và hỏi AI Chat nhiều lượt vẫn không trúng, cuối cùng làm qua loa phần đó hoặc bỏ trống.

**Pain Hypothesis B** *(cách giải thích cạnh tranh)*:

> Khi ngồi làm bài tập sau buổi học, learner gặp khó khăn trong việc gỡ phần nội dung mình không theo kịp vì **hỏi người khác tốn chi phí xã hội và thời gian chờ** (ngại làm phiền, sợ bị đánh giá, không biết hỏi lúc nào), dẫn đến họ chọn tự xoay xở hoặc chấp nhận hiểu lơ mơ rồi đi tiếp.

**Giả thuyết nhóm chọn: A** — lý do: A là giả định nền mà directive đang đứng lên; danh sách ưu tiên chỉ có giá trị nếu chỗ vướng *phải* được người ngoài chỉ ra. Nếu B mới đúng thì chỉ đúng chỗ vướng cũng không đổi được gì. A cũng dễ bị bác bỏ hơn chỉ bằng một câu chuyện cụ thể.

**Điều gì phải đúng để giả thuyết đứng vững:**

1. Learner thực sự có vướng mắc mà tự họ không nêu ra được thành câu hỏi.
2. Chỗ vướng đó nhận ra được từ bên ngoài, không chỉ nằm trong đầu learner.
3. Được chỉ đúng chỗ vướng sẽ làm learner hành động khác đi, chứ không chỉ "biết thêm".

**Điều gì có thể khiến nhóm sửa hoặc bác bỏ giả thuyết:**

Learner tự gỡ được trong dưới 10 phút bằng AI Chat hoặc bạn học; hoặc họ biết rõ mình hổng chỗ nào nhưng vẫn không hỏi (→ nghiêng về Pain B); hoặc không kể được hậu quả nào và tình huống không lặp lại.

**Solution Parking Lot:**

| # | Hướng giải quyết có thể có                                                                             | AI / Không sử dụng AI |
| - | ------------------------------------------------------------------------------------------------------------- | ------------------------ |
| 1 | Danh sách ưu tiên tự sinh sau mỗi buổi từ tín hiệu học tập (chính directive)                      | AI                       |
| 2 | Ô "chỗ mình chưa chắc" cuối mỗi buổi, learner tự đánh dấu, tổng hợp thành danh sách           | Không sử dụng AI      |
| 3 | 10 phút mở đầu buổi sau đi qua 3 chỗ được đánh dấu nhiều nhất, không nêu tên ai             | Không sử dụng AI      |
| 4 | Cặp bạn học check-in nhau sau mỗi buổi theo một checklist cố định 3 câu                             | Không sử dụng AI      |
| 5 | Tóm tắt hội thoại AI Chat của learner thành "câu hỏi thật sự bạn muốn hỏi" để họ tự gửi đi | AI                       |

---

## 3. Conversation Guide — phiên bản cuối

*Bản đã sửa sau khi luyện phỏng vấn ở Chặng 3.*

**Tiêu chí tuyển người:** Chúng tôi cần nói chuyện với người đã **học một buổi có nội dung mới và sau đó ngồi lại tự ôn hoặc làm bài tập của buổi đó**, trong vòng **7** ngày gần đây.

**Recruitment check:** "Trong một tuần gần đây, có buổi học nào mà sau đó bạn phải ngồi lại tự xem lại nội dung hoặc làm bài tập không? Buổi gần nhất là khi nào?"

**Lời mở đầu:**

"Cảm ơn bạn dành thời gian. Mình đang tìm hiểu xem mọi người thực sự làm gì sau khi kết thúc một buổi học — không có đúng sai gì cả, mình chỉ muốn nghe lại một lần cụ thể gần đây. Mình sẽ hỏi nhiều về việc bạn đã làm hơn là bạn nghĩ gì. Chỗ nào bạn không muốn kể thì cứ bỏ qua nhé."

**Story opener:** "Kể mình nghe về lần gần nhất bạn ngồi lại sau một buổi học và nhận ra có phần mình chưa theo kịp — hôm đó cụ thể là thế nào?"

**Big 3 Questions:**

| # | Điều cần học                                                                   | Câu hỏi sẽ dùng                                                                                                                                                                |
| - | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | Learner có thật sự kẹt lâu và không tự gỡ được không?                 | "Từ lúc bạn nhận ra mình chưa hiểu phần đó cho tới lúc bạn dừng lại, bạn đã làm những gì? Khoảng bao lâu?"                                                  |
| 2 | Barrier là "không định vị được chỗ hổng" hay "biết nhưng không hỏi"? | "Lúc đó bạn có nghĩ tới việc hỏi ai không? Bạn đã làm gì và vì sao lại chọn như vậy?"                                                                         |
| 3 | Hậu quả có thật và tình huống có lặp không?                              | "Cuối cùng phần đó kết thúc thế nào — bài tập hoặc buổi sau có bị ảnh hưởng gì không? Lần gần nhất trước đó chuyện tương tự xảy ra là khi nào?" |

**Probe bank:**

- "Lúc đó chuyện gì xảy ra tiếp theo?"
- "Bạn đã làm gì?"
- "Vì sao bạn chọn cách đó?"
- "Phần nào khó nhất?"
- "Bạn đã thử cách nào khác chưa?"
- "Việc đó kéo theo hậu quả gì?"
- "Lần gần nhất trước đó là khi nào?"
- *(mới)* "Lúc định nhắn cho ai đó, bạn đã định viết gì? Viết tới đâu thì dừng, và vì sao cuối cùng không gửi?"
- *(mới)* "Lúc hỏi AI Chat, bạn gõ vào đó câu gì? Nó trả lời thế nào?"

**Ba phản xạ khi data lệch:**

| User đưa ra                                | Phản xạ | Cách quay lại evidence                                                                                        |
| -------------------------------------------- | --------- | --------------------------------------------------------------------------------------------------------------- |
| Lời khen                                    | Deflect   | "Cảm ơn bạn. Quay lại chỗ nãy — lúc đó bạn làm gì tiếp?"                                          |
| Câu chung chung hoặc lời hứa tương lai | Anchor    | "Lần gần nhất chuyện đó xảy ra là khi nào? Kể mình nghe lần đó nhé."                             |
| Ý tưởng hoặc feature request             | Dig       | "Nếu có cái đó thì nó giúp bạn làm được gì? Hiện tại chưa có thì bạn đang xử lý ra sao?" |

**Đã sửa gì so với bản trước khi luyện:**

| Câu cũ                                                                 | Vấn đề                                                                                          | Câu mới                                                                                                  |
| ------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| "Nếu có ai đó chỉ đúng chỗ bạn đang kẹt thì bạn thấy sao?" | Mời đánh giá solution; nhận về "chắc là có", không có hành vi nào                     | "Lúc đó bạn có nghĩ tới việc hỏi ai không? Bạn đã làm gì và vì sao lại chọn như vậy?" |
| "Bạn có hay bị như vậy không?"                                     | Hỏi tần suất chung chung, nhận về ước lượng cảm tính                                    | "Lần gần nhất trước đó chuyện tương tự xảy ra là khi nào? Kể mình nghe lần đó."         |
| Tiêu chí tuyển "trong vòng 14 ngày"                                 | Sau một tuần user đã bắt đầu quên chi tiết chuỗi hành động                            | Tiêu chí tuyển "trong vòng 7 ngày gần đây"                                                         |
| *(thêm mới)*                                                         | Chưa tách được "không biết mình hổng gì" với "biết nhưng không soạn nổi câu hỏi" | "Lúc định nhắn cho ai đó, bạn đã định viết gì? Vì sao cuối cùng không gửi?"              |

---

## 4. Practice Reflection

1. **Câu hỏi nào đã giúp user kể một tình huống cụ thể?**

   "Từ lúc bạn nhận ra mình chưa hiểu phần đó cho tới lúc bạn dừng lại, bạn đã làm những gì?" Câu này neo vào hai mốc — lúc nhận ra và lúc dừng — nên user buộc phải kể chuỗi hành động ở giữa thay vì đưa nhận xét chung.
2. **Chỗ nào mình cần làm tốt hơn ở lần phỏng vấn thật?**

   Bỏ hẳn các câu bắt đầu bằng "nếu có...". Khi nghe được một tín hiệu trái giả thuyết, phải đào ngay tại chỗ thay vì đi tiếp theo guide. Và để im lặng lâu hơn — hai lần mình lấp quá nhanh đều là lúc user đang định kể tiếp.
3. **Sau khi luyện, nhóm đã sửa Conversation Guide ở đâu và vì sao?**

   Bốn chỗ, xem bảng ở cuối phần 3: bỏ câu giả định vì nó mời đánh giá solution; đổi câu hỏi tần suất thành câu neo vào lần gần nhất vì câu cũ chỉ nhận về ước lượng; rút tiêu chí tuyển từ 14 ngày xuống 7 ngày vì sau một tuần user đã bắt đầu quên chi tiết; và thêm một câu về việc soạn câu hỏi để tách nhánh barrier mới phát hiện trong buổi phỏng vấn.

---

## 5. AI Support Log

**Cách mình dùng AI:**

Mình chọn Case C, chốt hướng đi, quyết định cấu trúc repo và duyệt từng phần diễn đạt trước khi đưa vào bài. AI đóng vai công cụ soạn nháp: dựng khung form bốn chặng theo đúng cấu trúc BTC, và viết bản nháp đầu cho capability trung tính, chuỗi Change, hai nhánh Pain, Evidence Map, Big 3 và Conversation Guide.

**Điểm nào AI làm sai hoặc hời hợt:**

Bản nháp Interview Record mà AI đưa ra chỉ là kịch bản mô phỏng, không phải dữ liệu phỏng vấn thật, nên không dùng được làm evidence và phải thay bằng buổi phỏng vấn thật. AI cũng không điền được tên nhóm, thành viên và mã người tham gia.

**Mình đã tự sửa thế nào:**

*(Phần này viết bằng chữ của mình — sửa diễn đạt nào, bỏ ý nào của AI, thay dữ liệu phỏng vấn ra sao.)*

................................................................................

---

## Ghi chú về bản ghi phỏng vấn

[interview/notes.md](interview/notes.md) chứa Interview Record của chính lượt mình làm interviewer.

- Người được phỏng vấn đã đồng ý cho ghi lại:  Có  /  **Không** — bạn ấy đồng ý nói chuyện và cho ghi chép tay, nhưng không thoải mái với việc bị ghi âm.
- Bài nộp này **chỉ có ghi chép (notes)**, không kèm file audio hoặc recording link.

> Không bắt buộc nộp transcript trong bài này.

---

## Cấu trúc repo

```
Track1_Day17_2A202601840_PhamTuanAnh/
├── README.md
├── interview/
│   └── notes.md
└── worksheets/            # bản làm việc trong lab (ngoài cấu trúc tối thiểu)
    ├── chang1-problem-hypothesis.md
    ├── chang2-conversation-guide.md
    ├── chang3-interview-practice.md
    └── chang4-reflection.md
```

---

## Kiểm tra trước khi nộp

- [X] Repo đúng tên `Track1_Day17_MHV_HoVaTen`
- [X] `README.md` đủ năm phần
- [X] `interview/notes.md` là notes của chính lượt bạn làm interviewer
- [ ] Bản ghi hoặc recording link mở được với giảng viên/TA — *không có, interviewee không đồng ý ghi âm; đã ghi rõ lý do ở mục trên*
- [X] Người được phỏng vấn đã đồng ý cho ghi lại *(đồng ý cho ghi chép, không đồng ý ghi âm)*
- [X] Conversation Guide không làm lộ solution và đã được sửa sau khi luyện
