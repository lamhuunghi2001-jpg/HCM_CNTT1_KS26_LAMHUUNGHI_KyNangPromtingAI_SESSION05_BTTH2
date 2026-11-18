# XÂY DỰNG CHUỖI PROMPT VIẾT BÀI PR SẢN PHẨM CÔNG NGHỆ

## 1. Mục tiêu

- Thành thạo kỹ thuật Prompt Chaining để giải quyết những công việc phức tạp cần thực hiện qua nhiều bước.
- Biết cách thiết lập và truyền ngữ cảnh (Context) giữa các prompt để kết quả trước trở thành đầu vào cho bước tiếp theo.
- Nắm được cách xử lý khi AI bị ngắt giữa chừng và duy trì sự thống nhất về nội dung, giọng văn trong bài viết dài.

## 2. Bối cảnh bài toán

Phòng Marketing cần viết một bài PR chuyên sâu (khoảng 1000–1500 từ) để giới thiệu giải pháp AI Chatbot mới dành cho doanh nghiệp.

Nếu chỉ sử dụng một prompt để yêu cầu AI viết toàn bộ bài, nội dung có thể bị lặp ý, thiếu chiều sâu hoặc chưa tập trung vào nhu cầu của khách hàng.

Vì vậy, cần chia công việc thành 3 prompt riêng biệt: nghiên cứu khách hàng, lập dàn ý và triển khai bài viết. Kết quả của mỗi bước sẽ được sử dụng làm dữ liệu đầu vào bắt buộc cho bước tiếp theo.

## 3. Quy trình Prompt Chaining gồm 3 bước

### THÔNG TIN CHUNG (Điền một lần và sử dụng cho cả 3 bước)

- **[TÊN SẢN PHẨM]:** Tên giải pháp AI Chatbot Siêu Cấp Vip Pro
- **[MÔ TẢ NGẮN]:** Mô tả 2–3 câu về chức năng chính của sản phẩm.
- **[NGÀNH/QUY MÔ DOANH NGHIỆP]:** Ví dụ: bán lẻ, tài chính, doanh nghiệp vừa và lớn.
- **[TỪ KHÓA CHÍNH]:** Một từ khóa chính, ví dụ: AI chatbot cho doanh nghiệp.
- **[TỪ KHÓA PHỤ]:** Từ 3–5 từ khóa liên quan.
- **[TONE]:** Chuyên nghiệp, tin cậy; xưng hô là “chúng tôi” và gọi người đọc là “doanh nghiệp”.

---

### PROMPT 1: NGHIÊN CỨU KHÁCH HÀNG VÀ PAIN POINTS

**Vai trò:** Bạn là chuyên gia nghiên cứu thị trường B2B, có kinh nghiệm phân tích nhu cầu của doanh nghiệp.

**Thông tin sản phẩm:** Dán toàn bộ THÔNG TIN CHUNG ở trên.

**Nhiệm vụ:**

1. Xác định 2–3 nhóm khách hàng mục tiêu, bao gồm vai trò ra quyết định, quy mô và ngành nghề.
2. Liệt kê chính xác 5 pain points mà sản phẩm có thể giải quyết. Mỗi pain point phải đi kèm một tình huống cụ thể trong công việc hằng ngày của doanh nghiệp.
3. Phân tích hậu quả của từng vấn đề đối với hoạt động kinh doanh.
4. Liên kết từng pain point với tính năng sản phẩm có khả năng giải quyết vấn đề đó.
5. Đề xuất 8 từ khóa liên quan đến nhu cầu tìm kiếm của khách hàng.
6. Không tự tạo số liệu, dẫn chứng hoặc tính năng chưa có trong thông tin sản phẩm. Nếu thiếu dữ liệu, ghi rõ “CẦN XÁC MINH” hoặc “CẦN BỔ SUNG THÔNG TIN”.

**Yêu cầu đầu ra:**

Chỉ trả về đúng cấu trúc dưới đây, không thêm lời dẫn:

```text
[DỮ_LIỆU_1_BẮT_ĐẦU]

KHÁCH_HÀNG:
- K1: Tên nhóm | Vai trò ra quyết định | Quy mô/ngành | Mục tiêu kinh doanh.
- K2: Tên nhóm | Vai trò ra quyết định | Quy mô/ngành | Mục tiêu kinh doanh.
- K3: Tên nhóm | Vai trò ra quyết định | Quy mô/ngành | Mục tiêu kinh doanh (nếu có).

PAIN_POINTS:
- P1 | Mô tả vấn đề | Tình huống cụ thể | Hậu quả với doanh nghiệp | Tính năng sản phẩm giải quyết | Nhóm khách hàng liên quan (K1, K2...).
- P2 | Mô tả vấn đề | Tình huống cụ thể | Hậu quả với doanh nghiệp | Tính năng sản phẩm giải quyết | Nhóm khách hàng liên quan.
- P3 | Mô tả vấn đề | Tình huống cụ thể | Hậu quả với doanh nghiệp | Tính năng sản phẩm giải quyết | Nhóm khách hàng liên quan.
- P4 | Mô tả vấn đề | Tình huống cụ thể | Hậu quả với doanh nghiệp | Tính năng sản phẩm giải quyết | Nhóm khách hàng liên quan.
- P5 | Mô tả vấn đề | Tình huống cụ thể | Hậu quả với doanh nghiệp | Tính năng sản phẩm giải quyết | Nhóm khách hàng liên quan.

TỪ_KHÓA_GỢI_Ý:
Danh sách 8 từ khóa, ghi rõ từ khóa và pain point tương ứng với từng từ khóa.

[DỮ_LIỆU_1_KẾT_THÚC]
```

---

### PROMPT 2: LẬP DÀN Ý BÀI VIẾT PR

**Vai trò:** Bạn là biên tập viên nội dung PR chuyên về lĩnh vực công nghệ và Marketing B2B.

**Đầu vào bắt buộc:** Sử dụng nguyên văn toàn bộ khối dữ liệu của Prompt 1. Không tự ý thay đổi mã K1, K2, K3 và P1 đến P5. Không bổ sung pain point mới ngoài dữ liệu đã có.

**Dữ liệu từ bước 1:**

```text
[DÁN NGUYÊN KHỐI DỮ_LIỆU_1 VÀO ĐÂY]
```

**Thông tin chung:** Dán lại THÔNG TIN CHUNG.

**Nhiệm vụ:**

1. Lập dàn ý chi tiết cho bài PR có độ dài dự kiến 1000–1500 từ.
2. Đề xuất 3 phương án tiêu đề (Headline), sau đó chọn một tiêu đề phù hợp nhất.
3. Xây dựng đoạn mở đầu (Lead) tập trung vào vấn đề mà khách hàng đang gặp phải.
4. Sắp xếp các pain point từ P1 đến P5 vào những mục H2 hoặc H3 phù hợp.
5. Mỗi tiêu đề H2 phải có ý chính, chi tiết cụ thể cần triển khai, mã pain point liên quan, từ khóa sử dụng và số từ mục tiêu.
6. Phân bổ số từ hợp lý để tổng số từ của toàn bài nằm trong khoảng 1000–1500 từ.
7. Không đưa thêm tính năng, số liệu hoặc thông tin sản phẩm chưa được xác nhận.

**Quy tắc kiểm tra:**

- Mỗi pain point từ P1 đến P5 phải xuất hiện ít nhất một lần trong dàn ý.
- Từ khóa chính phải có trong Headline, Lead và ít nhất một tiêu đề H2.
- Các từ khóa phụ phải được phân bổ hợp lý, tránh lặp lại quá nhiều.
- Tổng số từ của các phần phải được tính rõ ràng. Số từ của H2 đã bao gồm các H3 bên trong, không cộng H3 thêm lần nữa.
- Nếu dữ liệu đầu vào còn thiếu, ghi rõ “CẦN BỔ SUNG THÔNG TIN”, không tự suy đoán.

**Yêu cầu đầu ra:**

Chỉ trả về đúng cấu trúc sau:

```text
[DỮ_LIỆU_2_BẮT_ĐẦU]

HEADLINE:
- Phương án 1: ...
- Phương án 2: ...
- Phương án 3: ...
- Tiêu đề được chọn: ...
- Lý do lựa chọn: ...

LEAD:
- Ý chính của đoạn mở đầu.
- Pain point được tập trung khai thác (mã P).
- Từ khóa chính cần xuất hiện.

DÀN_Ý:
- H2-1 | Tiêu đề | Ý chính cần triển khai | Mã P liên quan | Từ khóa sử dụng | Số từ mục tiêu.
  - H3-1.1 | Tiêu đề | Nội dung cần triển khai | Số từ mục tiêu.
  - H3-1.2 | Tiêu đề | Nội dung cần triển khai | Số từ mục tiêu.
- H2-2 | Tiêu đề | Ý chính cần triển khai | Mã P liên quan | Từ khóa sử dụng | Số từ mục tiêu.
  - H3-2.1 | Tiêu đề | Nội dung cần triển khai | Số từ mục tiêu.
- H2-3 ... Tiếp tục cho đến khi bao phủ đầy đủ các pain point.

CTA:
- Hành động mong muốn từ người đọc.
- Kênh liên hệ.
- Ưu đãi (nếu có thông tin xác thực).

KIỂM_TRA:
- Tổng số từ dự kiến: ...
- Phép tính phân bổ số từ: ...
- Pain point đã được đề cập: P1, P2, P3, P4, P5.
- Từ khóa chính đã được bố trí: ...
- Thông tin còn thiếu cần bổ sung: ...

[DỮ_LIỆU_2_KẾT_THÚC]
```

---

C - Context: Bạn là chuyên gia nghiên cứu thị trường B2B cấp cao. Hãy suy nghĩ từng bước một và tính toán chi tiết trước khi đưa ra kết luận. Thông tin sản phẩm: [dán THÔNG TIN CHUNG].

R - Request: Xác định 2 đến 3 nhóm khách hàng mục tiêu và 5 pain point mà sản phẩm giải quyết.

E - Explanation: Kết quả này là đầu vào bắt buộc cho Prompt 2 (lập dàn ý) nên phải đúng cấu trúc, mã K và P không được đổi về sau.

A - Action: Phân tích sản phẩm, suy ra nhóm khách hàng (vai trò, quy mô, ngành), với mỗi nhóm tìm tình huống công việc cụ thể gây ra pain point, gắn tính năng sản phẩm giải quyết tình huống đó. Chỗ cần số liệu mà chưa có thì ghi “CẦN XÁC MINH”, không bịa.

T - Tone: Khách quan, súc tích, không ngôn từ quảng cáo.

E - Extras: Chỉ trả về đúng khối dưới đây, không lời dẫn.

### PROMPT 3: VIẾT BÀI PR VÀ TỐI ƯU SEO

**Vai trò:** Bạn là copywriter chuyên viết nội dung PR trong lĩnh vực công nghệ, có kinh nghiệm triển khai bài viết chuẩn SEO cho khách hàng doanh nghiệp.

**Đầu vào bắt buộc:**

Sử dụng đầy đủ hai khối dữ liệu dưới đây:

1. DỮ_LIỆU_1: Kết quả nghiên cứu khách hàng và pain points từ Prompt 1.
2. DỮ_LIỆU_2: Kết quả lập dàn ý từ Prompt 2.

**Dữ liệu bước 1:**

```text
[DÁN NGUYÊN VĂN DỮ_LIỆU_1 VÀO ĐÂY]
```

**Dữ liệu bước 2:**

```text
[DÁN NGUYÊN VĂN DỮ_LIỆU_2 VÀO ĐÂY]
```

**BẢNG GIỮ NHẤT QUÁN (Áp dụng trong toàn bộ bài viết):**

- **Giọng văn:** Chuyên nghiệp, tin cậy, dễ hiểu. Không chuyển sang giọng quảng cáo quá mức hoặc cách diễn đạt suồng sã.
- **Xưng hô:** Sử dụng “chúng tôi” khi nói về đơn vị cung cấp và “doanh nghiệp” khi nói về khách hàng.
- **Tên sản phẩm:** Giữ nguyên tên sản phẩm đã cung cấp, không tự ý viết tắt hoặc đổi tên.
- **Thuật ngữ:** Sử dụng thống nhất các thuật ngữ chuyên ngành đã xuất hiện trong DỮ_LIỆU_1.
- **Nội dung:** Không tự thêm tính năng, cam kết, số liệu hoặc lợi ích chưa được xác nhận.
- **Số liệu:** Những thông tin còn thiếu phải giữ nguyên cụm từ “CẦN XÁC MINH”.
- **Cấu trúc:** Không tự ý thêm, bớt hoặc đảo thứ tự các mục H2 và H3 trong DỮ_LIỆU_2.

**QUY TẮC SEO:**

1. Từ khóa chính phải xuất hiện trong tiêu đề H1, 100 từ đầu tiên của bài viết và ít nhất một tiêu đề H2.
2. Mật độ từ khóa chính hướng đến khoảng 1–1,5%, nhưng phải ưu tiên cách diễn đạt tự nhiên, không cố nhồi nhét từ khóa.
3. Các từ khóa phụ được sử dụng đúng theo phân bổ trong dàn ý.
4. Sử dụng đúng cấu trúc H1, H2 và H3.
5. Mỗi đoạn văn không quá 4 câu, nội dung rõ ràng và dễ đọc.
6. Các tiêu đề phải liên kết với nội dung bên dưới, tránh đặt tiêu đề không đúng trọng tâm.
7. Không lặp lại cùng một ý ở nhiều phần chỉ để tăng số từ.

**CẤU TRÚC BÀI VIẾT BẮT BUỘC:**

- H1: Tiêu đề bài viết thu hút, có chứa từ khóa chính.
- Lead: Đoạn mở đầu hấp dẫn, đề cập trực tiếp đến pain point của khách hàng.
- Nội dung chính: Các phần H2 và H3 theo đúng thứ tự trong dàn ý.
- CTA: Lời kêu gọi hành động rõ ràng ở cuối bài.
- Tổng độ dài: Khoảng 1000–1500 từ, theo phân bổ trong DỮ_LIỆU_2.

**CÁCH TRIỂN KHAI:**

- Viết lần lượt từng phần theo dàn ý đã được duyệt.
- Mỗi phần cần phân tích rõ vấn đề, tình huống thực tế, hậu quả và cách sản phẩm hỗ trợ giải quyết.
- Các phần phải liên kết với nhau, không viết rời rạc hoặc lặp ý.
- Sau khi hoàn thành mỗi mục H2, ghi dòng đánh dấu tương ứng, ví dụ: `[HẾT H2-1]`, `[HẾT H2-2]`.
- Khi hoàn thành toàn bộ bài viết, ghi dòng `[KẾT_THÚC_BÀI]`.
- Không viết lời dẫn hoặc giải thích ngoài nội dung bài PR.

---

## 4. QUY TẮC XỬ LÝ KHI AI BỊ NGẮT QUÃNG (ĐẠT MAX TOKEN)

Trong quá trình tạo bài viết dài, AI có thể bị dừng giữa chừng do giới hạn số lượng token. Để không làm mất nội dung và tránh việc AI viết lại từ đầu, cần thực hiện các bước sau:

### Bước 1: Xác định vị trí bị ngắt

Kiểm tra câu trả lời gần nhất.

- Nếu đã xuất hiện dòng `[KẾT_THÚC_BÀI]`, bài viết đã hoàn thành.
- Nếu chưa có dòng `[KẾT_THÚC_BÀI]`, bài viết vẫn chưa hoàn chỉnh.
- Ghi lại mã H2 đang viết dở.
- Sao chép chính xác khoảng 30 từ cuối cùng mà AI đã tạo ra.
- Xác định câu cuối đã hoàn chỉnh hay vẫn còn dang dở.

### Bước 2: Sử dụng câu lệnh tiếp tục

Sao chép câu lệnh dưới đây, thay nội dung trong dấu ngoặc vuông bằng dữ liệu thực tế:

**PROMPT TIẾP TỤC:**

```text
Bạn đã bị ngắt giữa chừng do giới hạn độ dài phản hồi. Hãy tiếp tục bài viết ngay sau nội dung đã tạo ra.

Đoạn cuối đã viết: '[DÁN CHÍNH XÁC 30 TỪ CUỐI]'.

Trạng thái câu cuối: [ĐÃ HOÀN CHỈNH / CHƯA HOÀN CHỈNH].

Mục đang viết dở: [MÃ H2].

Yêu cầu:
1. Giữ nguyên toàn bộ nội dung đã viết trước đó, không viết lại từ đầu.
2. Sử dụng đoạn văn được cung cấp để xác định chính xác vị trí cần tiếp tục.
3. Nếu câu cuối chưa hoàn chỉnh, hãy hoàn thành câu đó trước khi triển khai ý tiếp theo. Nếu câu đã hoàn chỉnh, tiếp tục từ câu kế tiếp.
4. Không lặp lại đoạn văn đã có, không tóm tắt và không thêm lời chào.
5. Tiếp tục đúng mục đang viết dở, sau đó hoàn thành các mục còn lại theo thứ tự trong DỮ_LIỆU_2.
6. Giữ nguyên giọng văn, cách xưng hô, thuật ngữ và các quy tắc SEO đã quy định.
7. Không thay đổi nội dung hoặc thứ tự của dàn ý.
8. Tiếp tục ghi dấu [HẾT H2-n] sau mỗi mục và chỉ ghi [KẾT_THÚC_BÀI] khi toàn bộ bài viết đã hoàn thành.
```

### Bước 3: Xử lý khi ngữ cảnh bị mất hoặc AI bắt đầu lệch nội dung

Nếu cuộc trò chuyện quá dài khiến AI bắt đầu lặp ý, quên dữ liệu hoặc thay đổi giọng văn, có thể mở một cuộc trò chuyện mới.

Khi đó, cần cung cấp lại:

- Bảng giữ nhất quán của Prompt 3.
- Toàn bộ DỮ_LIỆU_1.
- Toàn bộ DỮ_LIỆU_2.
- Phần bài viết đã hoàn thành đến dòng `[HẾT H2-n]` gần nhất.
- Đoạn cuối cùng nếu đang viết dở một mục H2.

Sau đó sử dụng câu lệnh:

```text
Đây là phần tiếp theo của bài PR đang viết. Hãy đọc dữ liệu và nội dung đã cung cấp để tiếp tục viết từ mục H2-(n+1). Không viết lại nội dung cũ, không thay đổi dàn ý và phải giữ nguyên bảng giữ nhất quán.
```

### Bước 4: Kiểm tra nội dung sau khi ghép

Sau khi AI viết xong tất cả các phần, cần kiểm tra lại toàn bộ bài viết:

1. Đọc hai câu ở trước và sau vị trí nối để kiểm tra nội dung có liền mạch không.
2. Đảm bảo không có câu hoặc đoạn văn bị lặp.
3. Kiểm tra câu văn có bị thiếu chủ ngữ, vị ngữ hoặc mất ý không.
4. Kiểm tra giọng văn có thống nhất từ đầu đến cuối không.
5. Kiểm tra các tiêu đề H1, H2, H3 đúng theo dàn ý.
6. Kiểm tra từ khóa SEO, CTA và tổng số từ có đáp ứng yêu cầu không.
7. Đảm bảo bài viết có dòng `[KẾT_THÚC_BÀI]` ở cuối.

Nếu phát hiện lỗi, yêu cầu AI chỉnh sửa đúng phần bị lỗi, không viết lại toàn bộ bài.

---

## 5. KẾT QUẢ MONG MUỐN

Sau khi hoàn thành quy trình, bài PR cần đạt được những yêu cầu sau:

- Nội dung có cấu trúc rõ ràng, đúng độ dài từ 1000–1500 từ.
- Xác định đúng đối tượng khách hàng và các vấn đề mà sản phẩm có thể giải quyết.
- Dàn ý được xây dựng dựa trên dữ liệu nghiên cứu ở bước đầu tiên.
- Bài viết có đầy đủ Headline, Lead, H2, H3 và CTA.
- Từ khóa SEO được sử dụng hợp lý, không gây cảm giác lặp từ.
- Giọng văn chuyên nghiệp và thống nhất trong toàn bộ bài viết.
- Khi AI bị ngắt quãng, có thể tiếp tục từ đúng vị trí mà không phải viết lại từ đầu.

**KẾT LUẬN:**

Thông qua bài tập này, kỹ thuật Prompt Chaining giúp chia một công việc lớn thành nhiều bước nhỏ để AI xử lý lần lượt. Việc truyền dữ liệu giữa các prompt giúp nội dung có sự liên kết, hạn chế lặp ý và tránh sai lệch thông tin. Ngoài ra, các câu lệnh tiếp tục và bảng giữ nhất quán giúp duy trì nội dung khi viết những bài dài, đảm bảo bài PR hoàn chỉnh và đúng yêu cầu ban đầu.
