# Brief thiết kế UI – App quản lý tài chính cá nhân

Oct 25, 2026 · @Justin Tran

## Bối cảnh và phạm vi

Tài liệu này dùng làm đầu vào cho Claude Design để thiết kế giao diện MVP. Nội dung nghiệp vụ chi tiết nằm trong PRD; brief chỉ giữ những gì người thiết kế cần biết.

**Sản phẩm.** App ghi chép thu chi cá nhân, kết hợp chia hóa đơn với bạn bè. Mọi khoản tiền giữa hai người chỉ có hiệu lực khi cả hai xác nhận. Tiền bạn bè trả lại cho hóa đơn là hoàn tiền, được trừ vào chi tiêu, không tính là thu nhập. Tên app chưa chốt; trong thiết kế dùng tên tạm và để chỗ cho logo sản phẩm.

**Đơn vị phát triển.** SCTech. (盛晟科技國際有限公司), Đài Bắc.

**Phạm vi thiết kế đợt này:** toàn bộ màn hình MVP.

| Hạng mục | Yêu cầu |
| --- | --- |
| Nền tảng | App di động iOS và Android, thiết kế theo khung iPhone 390 × 844 làm chuẩn |
| Ngôn ngữ | Tiếng Trung phồn thể (mặc định) và tiếng Anh |
| Tiền tệ | TWD và USD; ví dụ trong thiết kế dùng TWD (NT$) |
| Chế độ màu | Sáng và tối |
| Ngoài phạm vi | Ngân sách, khoản định kỳ, lịch, chia theo phần trăm/phần, nhóm (Phase 2 trở đi) |

## Nhận diện thương hiệu

App là sản phẩm của SCTech nhưng hướng tới người dùng phổ thông, nên kế thừa màu của công ty với giọng điệu thân thiện hơn website (website hướng doanh nghiệp, giao dịch tài chính).

**Bảng màu** (lấy từ logo và website SCTech)

| Vai trò | Màu | Ghi chú |
| --- | --- | --- |
| Màu chính | Cam #EC642C | Nút chính, nút thêm giao dịch, điểm nhấn |
| Màu phụ | Tím #8474F2 | Mọi thứ liên quan đến bạn bè và chia hóa đơn |
| Chữ chính | Gần đen #111111 |  |
| Nền | Trắng ngà #FAF9F6 | Màu nền website SCTech; chế độ tối dùng nền xám đậm tương ứng |
| Lỗi, cảnh báo | Đỏ tách biệt rõ với màu cam chính | Tránh để nút chính và thông báo lỗi trông giống nhau |

**Lưu ý văn hóa về màu số tiền.** Ở Đài Loan, thị trường chứng khoán dùng đỏ cho tăng và xanh lá cho giảm, ngược với Mỹ. Vì vậy không dùng riêng màu đỏ/xanh để phân biệt thu và chi; luôn kèm dấu (+ / −) và nhãn hoặc icon.

**Chữ.** Cần font hỗ trợ tốt tiếng Trung phồn thể: PingFang TC (iOS), Noto Sans TC (Android). Chữ Latin và chữ số dùng font hệ thống (SF Pro, Roboto). Số tiền dùng chữ số đều chiều rộng (tabular) để các cột thẳng hàng.

**Giọng điệu.** Gọn gàng, đáng tin, thân thiện; không phô trương như app giao dịch chứng khoán. Hình minh họa cho trạng thái trống có thể dùng hai khối hình tròn bo của logo (cam và tím) làm chất liệu.

## Nguyên tắc UX

- **Trạng thái luôn nhìn thấy được.** Mọi record hai chiều có nhãn trạng thái rõ ràng: Chờ xác nhận, Đã chấp nhận, Bị từ chối, Đã thu hồi, Đã hủy. Năm trạng thái dùng màu và icon nhất quán trên toàn app.
- **Con số không gây khó hiểu.** Chi tiêu của hóa đơn luôn hiển thị kèm phần giải thích, ví dụ "Chi thực NT$100 · Đã chi NT$300, được hoàn NT$200". Không bao giờ hiển thị hoàn tiền như thu nhập.
- **Ai đang chờ ai.** Màn hình chi tiết hóa đơn phải cho thấy ngay mỗi người đang ở bước nào: chưa phản hồi, đã chấp nhận nhưng chưa trả, đã trả một phần, đã trả đủ, đã từ chối.
- **Thao tác chính nhanh.** Ghi một khoản chi cá nhân trong tối đa 3 lần chạm sau khi nhập số tiền. Nút thêm giao dịch luôn có mặt.
- **Hành động không thể hoàn tác cần xác nhận.** Chấp nhận record (khóa số tiền), từ chối, yêu cầu hủy, xóa tài khoản đều có bước xác nhận và nói rõ hệ quả.
- **Riêng tư.** Nút ẩn số tiền trên mọi màn hình có số liệu; khi ẩn, số tiền hiển thị dạng \*\*\*\*.
- **Hai ngôn ngữ.** Chữ tiếng Anh thường dài hơn tiếng Trung 1,5 đến 2 lần; layout phải chịu được cả hai mà không cắt chữ ở các nút, nhãn trạng thái, tab.
- **Tính năng chưa có vẫn rõ ràng.** Tab Nhập bằng ảnh hiển thị với nhãn Sắp ra mắt, không trông như bị lỗi.

## Điều hướng

Đề xuất thanh điều hướng dưới gồm 5 tab, nút Thêm nằm giữa và nổi bật bằng màu chính. Tab Hóa đơn gom mọi thứ liên quan đến tiền qua lại với bạn bè, kể cả yêu cầu xác nhận đang chờ, có badge số lượng.

&#91;embedded content: Sơ đồ màn hình MVP · onboarding và 5 tab\]

Người thiết kế có thể đề xuất cách điều hướng khác nếu hợp lý hơn, miễn là yêu cầu xác nhận đang chờ và nút Thêm luôn dễ thấy.

## Màn hình và trạng thái cần vẽ

Xếp theo thứ tự ưu tiên thiết kế: luồng chia hóa đơn và record hai chiều là phần khác biệt và khó nhất, nên làm trước.

### 1. Chia hóa đơn (ưu tiên cao nhất)

- **Tạo hóa đơn:** nhập tổng tiền, danh mục, ngày, tên hóa đơn, ảnh hóa đơn (tùy chọn). Chọn người tham gia từ danh sách bạn bè, tối đa 15 người tính cả người trả; công tắc "Tính phần của tôi". Chọn cách chia: chia đều hoặc theo số tiền cụ thể.
- **Xem trước:** phần của từng người, ghi chú phần chênh lệch làm tròn thuộc người trả. Trạng thái lỗi khi tổng các phần không khớp tổng tiền.
- **Chi tiết hóa đơn:** tổng tiền, chi thực của người trả, danh sách người tham gia với trạng thái từng người (chưa phản hồi, đã chấp nhận, đã trả một phần, đã trả đủ, đã từ chối kèm lý do, người trả tự chịu). Nút Nhắc thanh toán, công tắc nhắc tự động.
- **Xử lý khi có người từ chối:** bottom sheet cho người trả chọn Chia lại hoặc Đóng phần chia.
- **Danh sách Hóa đơn chưa thu đủ** (góc nhìn người trả) và **Bạn cần trả** (góc nhìn người tham gia), có tổng số tiền ở đầu danh sách.
- **Thanh toán:** sheet "Đã trả" cho người tham gia nhập số tiền (cho phép trả một phần, không vượt quá phần còn phải trả); sheet "Đã nhận" cho người trả xác nhận.

### 2. Record hai chiều

- **Danh sách yêu cầu:** hai tab Gửi đến tôi và Tôi đã gửi, badge số lượng chờ xử lý.
- **Chi tiết yêu cầu:** người gửi, loại, số tiền, ngày, ghi chú. Nút Chấp nhận (kèm chọn danh mục nếu là chi tiêu) và Từ chối.
- **Sheet từ chối:** lý do chọn nhanh (Sai số tiền, Không phải giao dịch của tôi, Đã thanh toán rồi, Khác) và ô nhập tự do, bắt buộc khi chọn Khác.
- **Record bị từ chối** ở phía người tạo: nhãn trạng thái, lý do, nút Tạo lại.
- **Yêu cầu hủy** một record đã chấp nhận và màn hình bên kia đồng ý hoặc từ chối hủy.
- **Tạo chuyển tiền / tặng tiền:** chọn bạn, số tiền, danh mục, ghi chú.

### 3. Ghi chép cá nhân

- **Màn hình nhập:** chuyển Chi tiêu / Thu nhập, bàn phím số tiền lớn, lưới danh mục, ngày, ghi chú. Tab Nhập bằng ảnh với nhãn Sắp ra mắt và popup giới thiệu.
- Trạng thái lỗi khi lưu khoản chi chưa chọn danh mục.

### 4. Tổng quan (dashboard)

- Chọn kỳ (tuần, tháng, năm), tổng thu, tổng chi, chênh lệch.
- Biểu đồ tròn phân bổ chi theo danh mục, biểu đồ cột xu hướng theo tháng.
- Thẻ hóa đơn: người khác còn nợ mình, mình còn phải trả.
- Trạng thái trống cho người dùng mới, trạng thái đang ẩn số tiền.

### 5. Bạn bè

- Danh sách bạn, tìm theo username hoặc số điện thoại, mã QR của tôi, quét QR, chia sẻ link mời.
- Lời mời kết bạn đến và đi; chặn người dùng.
- Chi tiết một người bạn: lịch sử record chung, hóa đơn chưa xong giữa hai người.
- Cảnh báo khi hủy kết bạn mà còn hóa đơn chưa thanh toán xong.

### 6. Onboarding và cài đặt

- Đăng nhập, đăng ký email, SSO Google và Apple, xác minh email, chọn username, chọn tiền tệ và ngôn ngữ.
- Cài đặt: hồ sơ, tiền tệ (khóa khi đã có giao dịch, cần trạng thái bị khóa kèm giải thích), ngôn ngữ, quản lý danh mục, thông báo theo từng loại, khóa app bằng sinh trắc học, ẩn số tiền.
- Xóa tài khoản kèm cảnh báo nếu còn hóa đơn chưa thanh toán xong.
- Trung tâm thông báo.

### Trạng thái chung cần có

- Trống, đang tải, lỗi mạng.
- Chữ dài: tên người dùng dài, tên hóa đơn dài, giao diện tiếng Anh.
- Số lớn: NT$1.250.000; hóa đơn đủ 15 người.
- Chế độ sáng và tối.

## Đầu ra và cách làm việc với Claude Design

**Đầu ra mong muốn, theo thứ tự**

1. **Design system:** màu (sáng và tối), cỡ chữ, khoảng cách, bo góc; các component cốt lõi: nút, ô nhập, hiển thị số tiền, nhãn trạng thái (5 trạng thái record), dòng danh sách, avatar bạn bè, bottom sheet, thanh điều hướng.
2. **Luồng chia hóa đơn** đầy đủ các màn hình ở mục 1.
3. **Luồng record hai chiều** ở mục 2.
4. **Ghi chép cá nhân và Tổng quan.**
5. **Bạn bè, onboarding, cài đặt.**
6. **Hai ngôn ngữ:** ít nhất màn hình Tạo hóa đơn, Chi tiết hóa đơn và Tổng quan được vẽ bằng cả tiếng Trung phồn thể và tiếng Anh để kiểm tra layout.

**Cách làm việc.** Đưa vào Claude Design: bản PRD (PDF), brief này, và file logo SCTech. Làm từng bước theo thứ tự trên, chốt design system trước rồi mới vẽ màn hình, để các màn hình sau dùng chung component.

**Prompt mẫu cho phiên đầu tiên**

```
Tôi đính kèm PRD, brief thiết kế và logo công ty SCTech.
Hãy thiết kế design system cho app di động (iOS/Android, khung 390x844):
- Màu chính cam #EC642C, màu phụ tím #8474F2 (dùng cho mọi thứ liên quan bạn bè và chia hóa đơn), chữ #111111, nền #FAF9F6, kèm phiên bản tối.
- Font hỗ trợ tiếng Trung phồn thể (PingFang TC / Noto Sans TC), số tiền dùng chữ số tabular.
- Không dùng riêng màu đỏ/xanh để phân biệt thu và chi; luôn có dấu +/- và nhãn.
- Component: nút, ô nhập, hiển thị số tiền (NT$), nhãn 5 trạng thái record (Chờ xác nhận, Đã chấp nhận, Bị từ chối, Đã thu hồi, Đã hủy), dòng danh sách, avatar, bottom sheet, thanh điều hướng 5 tab với nút Thêm ở giữa.
Giao diện mặc định bằng tiếng Trung phồn thể. Giọng điệu gọn gàng, đáng tin, thân thiện.
Sau khi tôi duyệt design system, chúng ta sẽ vẽ luồng chia hóa đơn.
```
