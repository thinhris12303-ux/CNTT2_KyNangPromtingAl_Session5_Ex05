# XÂY DỰNG CHIẾN DỊCH TRUYỀN THÔNG TUYỂN SINH KHÓA PYTHON CƠ BẢN BẰNG PROMPT CHAINING

## 1. Bối cảnh và thông tin đầu vào

Một trung tâm đào tạo lập trình muốn tổ chức chiến dịch truyền thông tuyển sinh khóa học Python cơ bản dành cho người mới bắt đầu.

| Tiêu chí | Thông tin |
|---|---|
| Sản phẩm | Khóa học Python cơ bản |
| Đối tượng | Sinh viên năm nhất |
| Độ tuổi | 18–20 |
| Thời lượng | 8 tuần |
| Mục tiêu | 100 lượt đăng ký tư vấn |
| Kênh truyền thông | Facebook và TikTok |
| Thời gian lập kế hoạch nội dung | 7 ngày |

**Nguyên tắc:** Không tự ý bổ sung hoặc thay đổi học phí, địa điểm, lịch học, chứng chỉ, cam kết việc làm hay thông tin khóa học chưa được cung cấp.

## 2. Sơ đồ chuỗi Prompt Chaining

```text
THÔNG TIN KHÓA HỌC (DỮ LIỆU GỐC)
              |
              v
PROMPT 1 – PHÂN TÍCH KHÁCH HÀNG MỤC TIÊU
Đầu ra: Chân dung, nhu cầu, khó khăn, hành vi, insight
              |
              v
PROMPT 2 – XÂY DỰNG THÔNG ĐIỆP TRUYỀN THÔNG
Đầu vào: Kết quả Prompt 1
Đầu ra: Insight trọng tâm, thông điệp chính, ý tưởng, CTA
              |
              v
PROMPT 3 – LẬP KẾ HOẠCH NỘI DUNG 7 NGÀY
Đầu vào: Kết quả Prompt 1 và Prompt 2
Đầu ra: Lịch đăng, chủ đề, mục tiêu, định dạng, kênh
              |
              v
PROMPT 4 – SẢN XUẤT NỘI DUNG QUẢNG CÁO
Đầu vào: Kết quả Prompt 1, 2 và 3
Đầu ra: 2 bài Facebook + 2 kịch bản TikTok
              |
              v
PROMPT 5 – KIỂM TRA TÍNH NHẤT QUÁN
Đầu vào: Toàn bộ kết quả Prompt 1–4
Đầu ra: Báo cáo kiểm tra và đề xuất chỉnh sửa
```

## 3. Triển khai chuỗi 5 Prompt

### Prompt 1 – Phân tích chân dung khách hàng mục tiêu

**Mục tiêu:** Xác định sinh viên năm nhất muốn gì, gặp khó khăn gì và điều gì khiến họ quan tâm đến Python.

**Nội dung Prompt 1:**

> Bạn là chuyên gia nghiên cứu thị trường trong lĩnh vực giáo dục và đào tạo công nghệ.
>
> Hãy phân tích chân dung khách hàng mục tiêu cho chiến dịch tuyển sinh khóa học Python cơ bản với thông tin:
> - Đối tượng: Sinh viên năm nhất.
> - Độ tuổi: 18–20.
> - Thời lượng khóa học: 8 tuần.
> - Mục tiêu chiến dịch: 100 lượt đăng ký tư vấn.
> - Kênh truyền thông: Facebook và TikTok.
>
> Yêu cầu phân tích:
> 1. Đặc điểm nhân khẩu học.
> 2. Nhu cầu và mong muốn.
> 3. Những khó khăn, rào cản khi học lập trình.
> 4. Hành vi sử dụng mạng xã hội.
> 5. Động lực khiến họ đăng ký tư vấn.
> 6. Đề xuất cách tiếp cận phù hợp.
>
> Không tự ý bổ sung thông tin khóa học chưa được cung cấp. Đầu ra phải có cấu trúc rõ ràng để sử dụng làm đầu vào cho Prompt 2.

**Kết quả Prompt 1 – Chân dung khách hàng mục tiêu**

| Thành phần | Phân tích |
|---|---|
| Đối tượng | Sinh viên năm nhất, 18–20 tuổi |
| Giai đoạn | Mới bước vào môi trường đại học |
| Kiến thức | Có thể chưa từng học lập trình hoặc chưa có nền tảng Python |
| Nhu cầu | Muốn tiếp cận công nghệ, học thêm kỹ năng và khám phá lĩnh vực lập trình |
| Khó khăn | Sợ code khó, không biết bắt đầu từ đâu, lo ngại không theo kịp kiến thức |
| Hành vi | Thường tiếp cận nội dung ngắn, trực quan, dễ hiểu trên TikTok và Facebook |
| Động lực | Muốn có lộ trình học rõ ràng và cơ hội tìm hiểu Python từ cơ bản |

**Insight khách hàng:**

> “Mình muốn học lập trình nhưng chưa biết bắt đầu từ đâu. Mình cần một khóa học phù hợp với người mới để có thể từng bước làm quen với Python.”

*Lưu ý: Đây là chân dung giả định phục vụ xây dựng chiến dịch, cần được kiểm chứng bằng khảo sát thực tế.*

### Prompt 2 – Xây dựng thông điệp truyền thông

**Mục tiêu:** Dựa trên chân dung khách hàng ở Prompt 1 để xây dựng thông điệp phù hợp với nhu cầu và nỗi lo của sinh viên.

**Nội dung Prompt 2:**

> Bạn là chuyên gia chiến lược thương hiệu và truyền thông giáo dục.
>
> Dựa trên toàn bộ kết quả phân tích khách hàng từ Prompt 1, hãy xây dựng thông điệp truyền thông cho khóa học Python cơ bản.
>
> Thông tin khóa học:
> - Đối tượng: Sinh viên năm nhất, 18–20 tuổi.
> - Thời lượng: 8 tuần.
> - Mục tiêu: 100 lượt đăng ký tư vấn.
> - Kênh: Facebook và TikTok.
>
> Yêu cầu:
> 1. Xác định insight quan trọng nhất.
> 2. Đề xuất một thông điệp truyền thông chính.
> 3. Giải thích vì sao thông điệp phù hợp với khách hàng.
> 4. Xác định 3 ý tưởng nội dung hỗ trợ thông điệp.
> 5. Đưa ra lời kêu gọi hành động (CTA).
>
> Thông điệp phải dễ nhớ, gần gũi, không phóng đại lợi ích và không tự ý thay đổi thông tin khóa học. Sử dụng kết quả Prompt 1 làm cơ sở, không phân tích lại khách hàng theo hướng khác.

**Kết quả Prompt 2 – Thông điệp truyền thông**

**Thông điệp chính:**

> **“Bắt đầu từ số 0 – Tự tin khám phá Python trong 8 tuần!”**

- **Insight:** Sinh viên muốn học lập trình nhưng chưa biết bắt đầu từ đâu và lo ngại kiến thức quá khó.
- **Ý tưởng nội dung hỗ trợ:**
  1. Python là gì? Vì sao người mới nên tìm hiểu?
  2. Những hiểu lầm phổ biến khiến sinh viên sợ học lập trình.
  3. Bắt đầu hành trình học Python cơ bản trong 8 tuần.
- **CTA:** Đăng ký tư vấn ngay hôm nay để tìm hiểu về khóa học Python cơ bản.

### Prompt 3 – Xây dựng kế hoạch nội dung trong 7 ngày

**Mục tiêu:** Chuyển thông điệp truyền thông thành lịch nội dung cụ thể trên Facebook và TikTok.

**Nội dung Prompt 3:**

> Bạn là chuyên gia lập kế hoạch Content Marketing.
>
> Hãy sử dụng:
> - Kết quả Prompt 1: Chân dung và insight khách hàng.
> - Kết quả Prompt 2: Thông điệp truyền thông chính và các ý tưởng nội dung.
>
> Xây dựng kế hoạch truyền thông trong 7 ngày trên Facebook và TikTok.
>
> Thông tin cố định:
> - Khóa học: Python cơ bản.
> - Đối tượng: Sinh viên năm nhất, 18–20 tuổi.
> - Thời lượng: 8 tuần.
> - Mục tiêu: 100 lượt đăng ký tư vấn.
>
> Yêu cầu:
> 1. Xây dựng lịch đăng nội dung cho 7 ngày.
> 2. Mỗi ngày có chủ đề, mục tiêu, nội dung chính và định dạng.
> 3. Phân bổ nội dung hợp lý giữa Facebook và TikTok.
> 4. Nội dung phải dẫn dắt khách hàng từ nhận biết đến quan tâm và đăng ký tư vấn.
> 5. Tất cả nội dung phải bám sát thông điệp chính.
>
> Trình bày bằng bảng. Không tự ý thay đổi thông tin khóa học.

**Kết quả Prompt 3 – Lịch nội dung 7 ngày**

| Ngày | Kênh | Chủ đề | Mục tiêu |
|---|---|---|---|
| 1 | Facebook | Python là gì? | Nhận biết |
| 2 | TikTok | Người mới có học được lập trình không? | Thu hút |
| 3 | Facebook | 3 lý do nên tìm hiểu Python | Giáo dục |
| 4 | TikTok | Một dòng code Python đầu tiên | Tạo hứng thú |
| 5 | Facebook | Những nỗi sợ khi bắt đầu học code | Giải đáp |
| 6 | TikTok | Hành trình khám phá Python trong 8 tuần | Cân nhắc |
| 7 | Facebook | Mời đăng ký tư vấn khóa học | Chuyển đổi |

### Prompt 4 – Viết bài Facebook và kịch bản TikTok

**Mục tiêu:** Tạo nội dung quảng cáo hoàn chỉnh dựa trên lịch đăng và thông điệp đã thống nhất.

**Nội dung Prompt 4:**

> Bạn là chuyên gia sáng tạo nội dung quảng cáo trên Facebook và TikTok.
>
> Hãy sử dụng toàn bộ kết quả của Prompt 1, Prompt 2 và Prompt 3 để sản xuất nội dung.
>
> **Phần A – Facebook**
> - Viết 2 bài đăng quảng cáo.
> - Bài 1 tập trung vào nỗi lo của người mới bắt đầu.
> - Bài 2 tập trung vào lời mời tìm hiểu và đăng ký tư vấn.
> - Mỗi bài có tiêu đề thu hút, nội dung, CTA và hashtag phù hợp.
>
> **Phần B – TikTok**
> - Viết 2 kịch bản video dài 30–45 giây.
> - Mỗi kịch bản gồm: thời gian, hình ảnh, lời thoại và chữ xuất hiện trên màn hình.
> - Kịch bản 1 tập trung vào việc xóa bỏ nỗi sợ học lập trình.
> - Kịch bản 2 giới thiệu cơ hội tìm hiểu khóa học Python cơ bản trong 8 tuần và CTA đăng ký tư vấn.
>
> Quy định:
> - Giữ nguyên thông điệp: “Bắt đầu từ số 0 – Tự tin khám phá Python trong 8 tuần!”
> - Giọng văn trẻ trung, gần gũi với sinh viên năm nhất.
> - Không tự ý thêm học phí, địa điểm, lịch học, chứng chỉ hoặc cam kết việc làm.
> - Không tạo ra thông tin khóa học chưa được cung cấp.

**Kết quả Prompt 4 – Nội dung quảng cáo**

#### A. Hai bài đăng Facebook

**Facebook – Bài đăng 1: Đánh vào nỗi lo của người mới**

**BẠN MUỐN HỌC LẬP TRÌNH NHƯNG KHÔNG BIẾT BẮT ĐẦU TỪ ĐÂU?**

Bạn từng nghĩ lập trình chỉ dành cho những người giỏi Toán hay có kiến thức công nghệ từ trước?

Thực tế, ai cũng cần một điểm bắt đầu!

Python là một ngôn ngữ lập trình phù hợp để bạn tìm hiểu khi mới bước vào thế giới công nghệ.

Nếu bạn là sinh viên năm nhất và đang muốn khám phá lập trình, hãy bắt đầu hành trình của mình với khóa học Python cơ bản trong 8 tuần.

**Bắt đầu từ số 0 – Tự tin khám phá Python trong 8 tuần!**

**Đăng ký tư vấn ngay hôm nay để tìm hiểu thêm về khóa học!**

#Python #HocLapTrinh #SinhVienNamNhat #LapTrinhChoNguoiMoi

**Facebook – Bài đăng 2: Mời tìm hiểu và đăng ký tư vấn**

**8 TUẦN – MỘT KHỞI ĐẦU MỚI VỚI PYTHON!**

Bạn là sinh viên năm nhất và muốn làm quen với lập trình?

Đừng để nỗi lo “mình chưa biết gì về code” ngăn cản bạn khám phá một kỹ năng mới.

Khóa học Python cơ bản với thời lượng 8 tuần là cơ hội để bạn tìm hiểu và bắt đầu hành trình tiếp cận lập trình.

Không cần phải chờ đến khi biết mọi thứ mới bắt đầu. Hãy bắt đầu từ những điều cơ bản!

**Bắt đầu từ số 0 – Tự tin khám phá Python trong 8 tuần!**

**Đăng ký tư vấn ngay để tìm hiểu thông tin khóa học!**

#PythonCoBan #HocPython #SinhVien #CongNghe

#### B. Hai kịch bản video TikTok

**TikTok – Kịch bản 1: Người mới có học được lập trình không?**

*Thời lượng dự kiến: 35–40 giây.*

| Thời gian | Hình ảnh | Lời thoại |
|---|---|---|
| 0–5 giây | Sinh viên nhìn màn hình máy tính | “Muốn học lập trình nhưng nhìn code là thấy sợ?” |
| 5–12 giây | Hiện các dòng code trên màn hình | “Bạn nghĩ mình phải giỏi Toán hoặc biết code từ trước?” |
| 12–22 giây | Chuyển cảnh sang màn hình Python | “Thực ra, ai cũng có thể bắt đầu tìm hiểu lập trình từ những kiến thức cơ bản.” |
| 22–32 giây | Hiện chữ Python cơ bản – 8 tuần | “Nếu bạn là sinh viên năm nhất, hãy thử khám phá Python với khóa học cơ bản trong 8 tuần.” |
| 32–40 giây | Hiện thông điệp và CTA | “Bắt đầu từ số 0 – Tự tin khám phá Python trong 8 tuần! Đăng ký tư vấn ngay nhé!” |

**TikTok – Kịch bản 2: 8 tuần khám phá Python**

*Thời lượng dự kiến: 35–45 giây.*

| Thời gian | Hình ảnh | Lời thoại |
|---|---|---|
| 0–5 giây | Chữ “Bạn đã từng muốn học Python?” | “Bạn muốn tìm hiểu Python nhưng chưa biết bắt đầu như thế nào?” |
| 5–15 giây | Sinh viên sử dụng laptop | “Đừng lo nếu bạn chưa có nền tảng lập trình. Điều quan trọng là bắt đầu tìm hiểu từ những kiến thức cơ bản.” |
| 15–27 giây | Hiện đồ họa khóa học | “Khóa học Python cơ bản có thời lượng 8 tuần, dành cho sinh viên năm nhất từ 18 đến 20 tuổi.” |
| 27–37 giây | Hiện thông điệp chính | “Bắt đầu từ số 0 – Tự tin khám phá Python trong 8 tuần!” |
| 37–45 giây | Hiện lời kêu gọi hành động | “Đăng ký tư vấn ngay để tìm hiểu thêm về khóa học nhé!” |

### Prompt 5 – Kiểm tra tính nhất quán chiến dịch

**Mục tiêu:** Đánh giá xem tất cả nội dung có thống nhất với chân dung khách hàng, thông điệp và thông tin khóa học hay không.

**Nội dung Prompt 5:**

> Bạn là chuyên gia kiểm duyệt chiến lược truyền thông và đảm bảo chất lượng nội dung.
>
> Hãy kiểm tra toàn bộ kết quả từ Prompt 1 đến Prompt 4.
>
> Đối chiếu theo các tiêu chí:
> 1. Chân dung khách hàng: Nội dung có đúng đối tượng sinh viên năm nhất, 18–20 tuổi không?
> 2. Insight: Nội dung có giải quyết nỗi lo không biết bắt đầu học lập trình không?
> 3. Thông điệp: Có duy trì thông điệp chính xuyên suốt không?
> 4. Kế hoạch: Nội dung 7 ngày có dẫn dắt từ nhận biết đến đăng ký tư vấn không?
> 5. Facebook và TikTok: Nội dung có phù hợp với đặc điểm từng nền tảng không?
> 6. Thông tin khóa học: Có tự ý thêm hoặc thay đổi dữ liệu không?
> 7. CTA: Có hướng đến mục tiêu 100 lượt đăng ký tư vấn không?
>
> Hãy lập bảng gồm: Tiêu chí, kết quả kiểm tra, vấn đề phát hiện và đề xuất chỉnh sửa.
>
> Nếu phát hiện lỗi, hãy đưa ra phiên bản chỉnh sửa cụ thể.
>
> Cuối cùng, đưa ra kết luận về mức độ nhất quán của chiến dịch và khả năng đáp ứng mục tiêu.

**Kết quả Prompt 5 – Báo cáo kiểm tra tính nhất quán**

| Tiêu chí | Kết quả kiểm tra | Đánh giá |
|---|---|---|
| Đối tượng | Sinh viên năm nhất 18–20 tuổi | Đạt |
| Insight | Giải quyết nỗi sợ học lập trình | Đạt |
| Thông điệp | Duy trì thông điệp 8 tuần | Đạt |
| Kế hoạch | Có nội dung 7 ngày | Đạt |
| Facebook | Có 2 bài quảng cáo | Đạt |
| TikTok | Có 2 video 30–45 giây | Đạt |
| Thông tin khóa học | Không thêm học phí, địa điểm hay cam kết | Đạt |
| CTA | Hướng đến đăng ký tư vấn | Đạt |

**Đề xuất cải thiện:**

- Bổ sung đường dẫn hoặc biểu mẫu đăng ký tư vấn thực tế khi trung tâm cung cấp.
- Theo dõi số lượt đăng ký tư vấn mỗi ngày để điều chỉnh nội dung.
- Kiểm tra phản hồi, lượt xem và tương tác để tối ưu nội dung Facebook và TikTok.
- Thống nhất cách gọi khóa học và thông điệp trên tất cả bài đăng.

**Kết luận:** Chiến dịch đạt yêu cầu về tính nhất quán trong thiết kế. Tuy nhiên, chưa thể khẳng định sẽ đạt 100 lượt đăng ký tư vấn nếu chưa triển khai và đo lường thực tế.

## 4. Tổng kết quy trình Prompt Chaining

| Prompt | Nhiệm vụ | Đầu ra chuyển tiếp |
|---|---|---|
| Prompt 1 | Phân tích khách hàng | Chân dung và insight |
| Prompt 2 | Xây dựng thông điệp | Thông điệp chính và CTA |
| Prompt 3 | Lập kế hoạch nội dung | Lịch đăng 7 ngày |
| Prompt 4 | Sản xuất quảng cáo | 2 bài Facebook + 2 video TikTok |
| Prompt 5 | Kiểm tra chất lượng | Báo cáo nhất quán |

### Lợi ích của Prompt Chaining

1. Chia một nhiệm vụ lớn thành các nhiệm vụ nhỏ, dễ kiểm soát.
2. Đảm bảo AI phải phân tích khách hàng trước khi tạo nội dung.
3. Giữ thông điệp xuyên suốt toàn bộ chiến dịch.
4. Hạn chế việc AI tự ý thay đổi thông tin khóa học.
5. Dễ dàng kiểm tra, chỉnh sửa và nâng cấp từng bước.

## 5. Kết luận

Prompt Chaining giúp xây dựng chiến dịch truyền thông tuyển sinh có quy trình rõ ràng, logic và nhất quán. Thay vì yêu cầu AI thực hiện tất cả trong một prompt, ta chia thành 5 bước liên tiếp, trong đó đầu ra của bước trước trở thành đầu vào của bước sau.

Đây là cách ứng dụng AI hiệu quả trong Content Marketing và truyền thông tuyển sinh.
