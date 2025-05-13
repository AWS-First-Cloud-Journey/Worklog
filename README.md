# Hướng dẫn Theo dõi Thời gian Thực tập  và Daily Report

## Theo dõi Thời gian Thực tập

### Sheet "Thông tin Thực tập"

Tạo sheet đầu tiên để theo dõi thông tin tổng quan:

1. **Thông tin cơ bản**:
   - Họ tên thực tập sinh
   - Email/Số liên lạc
   - Vị trí thực tập
   - Người hướng dẫn/Mentor

2. **Thời gian thực tập**:
   - Ngày bắt đầu: [ví dụ: 01/06/2025]
   - Ngày kết thúc dự kiến: [ví dụ: 31/08/2025]
   - Tổng số tuần: [công thức tự động tính]
   - Số giờ yêu cầu mỗi tuần: [ví dụ: 40 giờ]

3. **Bảng theo dõi tiến độ**:
   - Tạo bảng tính tự động hiển thị số ngày đã thực tập
   - Tổng số giờ đã làm việc (công thức lấy từ Daily Tasks)
   - Tỷ lệ hoàn thành (% thời gian đã thực hiện)

## Cách viết Daily Report

### Setup Sheet "Daily Report"

1. **Cấu trúc cột chính**:
   - Ngày (Date)
   - Tuần thứ (Week #) - tự động tính từ ngày bắt đầu
   - Thời gian bắt đầu làm việc (Check-in)
   - Thời gian kết thúc (Check-out)
   - Tổng giờ làm việc (Total Hours)
   - Mục tiêu trong ngày (Daily Goals)
   - Công việc đã hoàn thành (Tasks Completed)
   - Khó khăn gặp phải (Challenges)
   - Giải pháp áp dụng (Solutions)
   - Kế hoạch cho ngày mai (Tomorrow's Plan)
   - Liên kết tài liệu (Documents/Resources)
   - Phản hồi từ mentor (Mentor Feedback)

2. **Công thức tự động**:
   - Tính tuần: `=CEILING((A2-$InfoSheet.B2)/7,1)` (với A2 là ô ngày và InfoSheet.B2 là ngày bắt đầu)
   - Tổng giờ làm việc: `=IF(AND(D2<>"",C2<>""), (D2-C2)*24, "")`

### Mẫu Daily Report

| Ngày | Tuần # | Check-in | Check-out | Tổng giờ | Mục tiêu trong ngày | Công việc đã hoàn thành | Khó khăn | Giải pháp | Kế hoạch ngày mai |
|------|-------|----------|-----------|----------|---------------------|-------------------------|----------|-----------|-------------------|
| 13/05/2025 | 1 | 8:30 | 17:30 | 9 | 1. Tìm hiểu EC2<br>2. Setup môi trường | 1. Hoàn thành lab EC2<br>2. Cài đặt AWS CLI | Gặp lỗi khi kết nối SSH đến instance | Sửa security group rules | 1. Tìm hiểu S3<br>2. Làm lab về S3 |

## Best Practices cho Daily Report

1. **Các nội dung cần báo cáo hàng ngày**:
   - Công việc cụ thể đã làm (be specific)
   - Liên kết đến code, tài liệu đã tạo
   - Đánh dấu tiến độ theo roadmap đào tạo
   - Các vấn đề gặp phải và cách giải quyết

2. **Mẫu cấu trúc report hiệu quả**:
   ```
   Hôm nay tôi đã:
   - Tìm hiểu về [dịch vụ AWS] trong [X giờ]
   - Hoàn thành [tên bài lab] với kết quả [mô tả kết quả]
   - Gặp vấn đề về [mô tả vấn đề] và giải quyết bằng [giải pháp]
   
   Kế hoạch ngày mai:
   - Tiếp tục tìm hiểu về [dịch vụ AWS]
   - Triển khai [tên dự án/lab]
   
   Câu hỏi/hỗ trợ cần thiết:
   - [Liệt kê câu hỏi cần mentor giải đáp]
   ```

3. **Hướng dẫn viết báo cáo hiệu quả**:
   - Ngắn gọn, tập trung vào kết quả
   - Định lượng được (số giờ, số bài lab, % hoàn thành)
   - Đánh giá chính xác khả năng của bản thân
   - Nêu rõ điểm cần hỗ trợ thêm

## Tự động hóa và Nhắc nhở

1. **Tự động tính toán thời gian**:
   - Tạo dashboard tổng hợp số giờ theo tuần/tháng
   - Công thức báo động khi số giờ thấp hơn yêu cầu

2. **Nhắc nhở daily report**:
   - Thiết lập thông báo Google Calendar vào cuối ngày
   - Tạo template có sẵn để điền nhanh

3. **Báo cáo tự động cho mentor**:
   - Thiết lập tự động chia sẻ báo cáo cuối tuần
   - Sử dụng Apps Script để gửi email tổng hợp hàng tuần

## Mẫu Weekly Summary Report

Thêm sheet "Weekly Summary" để tổng hợp công việc mỗi tuần:

1. **Cấu trúc cột**:
   - Tuần thứ (Week #)
   - Ngày bắt đầu - Ngày kết thúc
   - Tổng số giờ làm việc
   - Thành tựu chính (Key Achievements)
   - Dịch vụ AWS đã học
   - Kỹ năng đạt được
   - Mục tiêu tuần tới
   - Phản hồi của mentor

2. **Công thức tự động tính tổng giờ theo tuần**:
   ```
   =SUMIFS('Daily Report'!E:E,'Daily Report'!B:B,A2)
   ```

Đội admin (anh Hoàng và anh Thiện) sẽ tiến hành điểm danh mỗi ngày (các bạn lên văn phòng, các bạn online vẫn ghi worklog sẽ được kiểm tra vào lúc đánh giá thực tập)

Hiện thị trong report ít nhất 60 ngày (tổng thời gian thực tập là 90 ngày)
