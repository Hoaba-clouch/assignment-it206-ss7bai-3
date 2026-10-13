# [Vận dụng chuyên sâu - 3] LẬP KẾ HOẠCH SPRINT 5 CHO CHỨC NĂNG VÍ RIKKEIPAY

## Phần 1 - Phân tích

### 1. Planning Capacity của từng thành viên sau khi Hà báo nghỉ

*   **Tú**: 10 ngày × 6 giờ/ngày - 6 giờ (Hỗ trợ vận hành) = 54 giờ
*   **Vy**: 10 ngày × 6 giờ/ngày - 0 giờ = 60 giờ
*   **Khoa**: 9 ngày × 6 giờ/ngày - 4 giờ (Họp liên nhóm) = 50 giờ
*   **Hà**: (10 ngày - 2 ngày nghỉ) × 6 giờ/ngày - 0 giờ = 8 ngày × 6 giờ/ngày = 48 giờ

### 2. Tổng Planning Capacity của đội

Tổng Planning Capacity = 54 giờ (Tú) + 60 giờ (Vy) + 50 giờ (Khoa) + 48 giờ (Hà) = **212 giờ**

### 3. Khoảng Velocity dùng để dự báo

Velocity 4 Sprint gần nhất: 18, 20, 19, 15 Story Point (SP).

*   **Khoảng Velocity**: 15 – 20 SP
*   **Velocity trung bình**: (18 + 20 + 19 + 15) / 4 = 18 SP

## Phần 2 - Thiết kế

### 1. Sprint Goal

**Sprint Goal:** Đảm bảo khách hàng có thể thanh toán chuyến đi bằng ví RikkeiPay ổn định, đồng thời minh bạch trạng thái hoàn tiền và lịch sử giao dịch ví.

### 2. Các PBI được chọn vào Sprint 5 và lý do không chọn các PBI khác

#### PBI được chọn:

*   **PBI 1: Thanh toán chuyến đi bằng ví RikkeiPay** (8 SP)
    *   **Lý do chọn:** Trực tiếp giải quyết phàn nàn của khách hàng về lỗi thanh toán, là nền tảng cần thiết cho chức năng hoàn tiền và là trọng tâm của Sprint Goal.
*   **PBI 2: Hoàn tiền vào ví khi chuyến bị hủy** (5 SP)
    *   **Lý do chọn:** Trực tiếp giải quyết phàn nàn của khách hàng về việc không biết tiền đã về ví chưa khi chuyến bị hủy. PBI này phụ thuộc vào PBI 1.
*   **PBI 3: Xem số dư và lịch sử giao dịch ví** (3 SP)
    *   **Lý do chọn:** Cung cấp sự minh bạch và khả năng kiểm tra cho khách hàng về số dư và các giao dịch, bao gồm cả việc hoàn tiền, từ đó tăng niềm tin sử dụng ví. Phục vụ Sprint Goal.

**Tổng Story Point đã chọn:** 8 + 5 + 3 = **16 SP**. (Nằm trong khoảng dự báo 15-20 SP)

#### PBI không được chọn và lý do:

*   **PBI 4: Gửi Short Message Service (SMS) khi tài xế sắp đến** (3 SP)
    *   **Lý do không chọn:** Nhà cung cấp SMS chưa ký hợp đồng (phụ thuộc bên ngoài chưa sẵn sàng) và không phục vụ trực tiếp Sprint Goal về chức năng ví RikkeiPay.
*   **PBI 5: Giao diện chủ đề Tết** (2 SP)
    *   **Lý do không chọn:** Không phục vụ Sprint Goal chính về chức năng ví RikkeiPay. Việc thêm PBI này chỉ để lấp đầy Sprint là không phù hợp với nguyên tắc Sprint Goal hướng tới Outcome.
*   **PBI 6: Chat với tài xế** (5 SP)
    *   **Lý do không chọn:** Không phục vụ Sprint Goal về chức năng ví RikkeiPay và sẽ khiến tổng SP vượt quá khoảng dự báo (16 + 5 = 21 SP).

## Phần 3 - Phân rã PBI "Hoàn tiền vào ví khi chuyến bị hủy"

**PBI:** Hoàn tiền vào ví khi chuyến bị hủy (5 SP)

| # | Task                                                  | Đầu ra kiểm chứng được                                                                                                                              |
| : | :---------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | Phát triển chức năng tự động hoàn tiền vào ví.       | Module xử lý hoàn tiền đã được triển khai và kiểm thử đơn vị, khi một chuyến đi chuyển trạng thái "đã hủy" thì số dư ví của khách hàng tăng đúng số tiền tương ứng. |
| 2 | Phát triển chức năng gửi thông báo hoàn tiền trong ứng dụng. | Khách hàng nhận được thông báo trong ứng dụng hiển thị rõ số tiền đã được hoàn trả và ID giao dịch khi tiền về ví thành công.                     |
| 3 | Kiểm thử tích hợp chức năng hoàn tiền với thanh toán ví. | Bộ test case tích hợp bao gồm kịch bản thanh toán bằng ví, sau đó hủy chuyến và kiểm tra số dư ví/lịch sử giao dịch/thông báo hoàn tiền chạy đạt trên môi trường staging. |
