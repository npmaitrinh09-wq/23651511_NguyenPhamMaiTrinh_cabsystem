# 23651511_NguyenPhamMaiTrinh_cabsystem
# 1. Hạn chế của hệ thống hiện tại
## a. Các nhược điểm của hệ thống
* Thực hiện thủ công, khách hàng khó theo dõi trạng thái chuyến đi, thông tin thanh toán chưa được quản lý tập trung và bộ phận vận hành gặp khó khăn khi muốn mở rộng hệ thống
## b. Tại sao cần hệ thống mới?
* Đáp ứng quy mô lớn: Phục vụ số lượng lớn khách hàng và tài xế, đồng thời dễ dàng phát triển thêm tính năng trong tương lai.
* Tự động hóa vận hành:Thay thế việc phân công tài xế thủ công bằng cơ chế tự động tìm kiếm, phân phối và xử lý ngoại lệ thông minh.
* Nâng cao trải nghiệm người dùng: Giúp khách hàng theo dõi trực quan trạng thái chuyến đi, còn tài xế dễ dàng nhận/từ chối chuyến xe.
* Quản lý thanh toán tập trung: Tích hợp thanh toán linh hoạt (tiền mặt/điện tử) và bảo mật thông tin nhạy cảm.
* Cải thiện giám sát & báo cáo: Cung cấp giao diện quản trị, thông báo đa kênh và báo cáo hiệu quả hoạt động cho ban lãnh đạo.
* Đảm bảo ổn định & bảo mật: Tăng khả năng mở rộng độc lập từng phần, chống quá tải và bảo mật dữ liệu, phân quyền chặt chẽ.


## 2. Bảng Stakeholder và Vai trò
| STT | Stakeholder | Vai trò |
| :---: | :--- | :--- |
| **1** | Ban Giám đốc | Nhà tài trợ, người ra quyết định|
| **2** | Khách hàng | Người tiêu dùng, người sử dụng cuối|
| **3** | Tài xế | Nhà cung cấp dịch vụ, người thực thi quy trình|
| **4** | Nhân viên vận hành | Người vận hành quy trình|
| **5** | Quản trị viên  | Người kiểm soát quy trình|
| **6** | Nhà cung cấp thanh toán | Nhà cung cấp tích hợp bên ngoài|
| **7** | Nhà cung cấp bản đồ / định vị | Nhà cung cấp dữ liệu bên ngoài|
| **8** | Nhà cung cấp dịch vụ thông báo | Nhà cung cấp dịch vụ truyền thông bên ngoài|

### Ma trận Matrix
```mermaid
quadrantChart
    title Ma trận Stakeholder - Power vs Interest
    x-axis "Quan tâm thấp" --> "Quan tâm cao"
    y-axis "Quyền lực thấp" --> "Quyền lực cao"

    quadrant-1 "Quản lý sát sao"
    quadrant-2 "Giữ sự hài lòng"
    quadrant-3 "Theo dõi tối thiểu"
    quadrant-4 "Cập nhật thông tin"

    "Ban Giám đốc": [0.85, 0.90]
    "Nhân viên vận hành": [0.78, 0.78]
    "Quản trị viên": [0.75, 0.72]

    "Khách hàng": [0.90, 0.35]
    "Tài xế": [0.85, 0.32]

    "Nhà cung cấp thanh toán": [0.42, 0.30]
    "Nhà cung cấp thông báo": [0.30, 0.22]
```
## Giải thích Ma trận:
* Quản lý sát sao: Ban Giám đốc, IT/DevOps, Nhân viên vận hành, Admin. Đây là nhóm có quyền lực và mức độ quan tâm cao, cần được trao đổi và phối hợp thường xuyên.
* Giữ sự hài lòng: Pháp chế, Kế toán/Tài chính. Nhóm có quyền lực tương đối cao nhưng không trực tiếp tham gia toàn bộ quy trình, cần đảm bảo yêu cầu được đáp ứng.
* Cập nhật thông tin: Khách hàng, Tài xế, CSKH. Nhóm có mức độ quan tâm cao nhưng quyền quyết định thấp, cần được cung cấp thông tin và hỗ trợ thường xuyên.
* Theo dõi tối thiểu: Nhà cung cấp thanh toán, Bản đồ/định vị, Dịch vụ thông báo. Chủ yếu cung cấp dịch vụ hỗ trợ bên ngoài, cần theo dõi tình trạng dịch vụ và xử lý khi có sự cố.

## 3. Business Purpose
* **Tối ưu hóa hiệu suất vận hành:** Tự động hóa quá trình tìm kiếm và phân công tài xế phù hợp nhằm giảm thời gian chờ và nâng cao tỷ lệ hoàn thành chuyến.
* **Minh bạch hóa dòng tiền & Giao dịch tài chính:** Cung cấp hệ thống thanh toán đa dạng (tiền mặt, ví điện tử, thẻ) kết hợp cơ chế đối soát tự động, giúp quản lý doanh thu, chiết khấu và dòng tiền của tài xế một cách chính xác, rõ ràng.
* **Nâng cao trải nghiệm người dùng:** Cung cấp giao diện trực quan, tính năng theo dõi hành trình thời gian thực, hệ thống đánh giá hai chiều và dịch vụ hỗ trợ (CSKH) nhanh chóng nhằm tối ưu hóa sự hài lòng cho cả khách hàng lẫn tài xế.
* **Đảm bảo tuân thủ & Quản trị rủi ro:** Xây dựng hệ thống phân quyền chặt chẽ, kiểm soát dữ liệu người dùng và đảm bảo toàn bộ hoạt động vận hành tuân thủ nghiêm ngặt các quy định pháp lý của cơ quan quản lý nhà nước về lĩnh vực vận tải công nghệ.

## 4. Xác định phạm vi 7 tuần
### a. Module Quản lý Khách hàng
- **Quy trình Xác thực & Hồ sơ:** Hỗ trợ đăng ký, đăng nhập và quản lý thông tin cá nhân.
- **Quy trình Khởi tạo yêu cầu:** Cho phép khách hàng nhập điểm đón, điểm đến, chọn loại dịch vụ và gửi yêu cầu đặt xe.
- **Quy trình Theo dõi chuyến:** Cho phép khách hàng theo dõi trạng thái và thông tin chuyến đi.
- **Quy trình Đánh giá dịch vụ:** Cho phép khách hàng đánh giá tài xế sau khi chuyến hoàn thành.
### b. Module Quản lý Tài xế và Phương tiện
- **Quy trình Quản lý Hồ sơ:** Tiếp nhận và cập nhật thông tin tài xế, phương tiện.
- **Quy trình Quản lý Trạng thái & Vị trí:** Cập nhật trạng thái sẵn sàng của tài xế và thông tin vị trí phục vụ điều phối.
- **Quy trình Thực hiện chuyến:** Tài xế nhận hoặc từ chối chuyến và cập nhật trạng thái trong quá trình thực hiện.
### c. Module Tính cước và Thanh toán
- **Quy trình Tính cước:** Xác định số tiền khách hàng phải thanh toán dựa trên thông tin chuyến và loại dịch vụ.
- **Quy trình Thanh toán:** Hỗ trợ thanh toán bằng tiền mặt hoặc phương thức điện tử.
- **Quy trình Ghi nhận & Xử lý thanh toán:** Ghi nhận kết quả giao dịch, thông báo khi thanh toán thất bại và hỗ trợ xử lý lại theo chính sách.
### d. Module Thông báo
- **Quy trình Thông báo Khách hàng:** Gửi thông tin về yêu cầu đặt xe, trạng thái tài xế, chuyến đi và thanh toán.
- **Quy trình Thông báo Tài xế:** Gửi thông tin chuyến xe và các thay đổi liên quan đến chuyến.
### e. Module Vận hành, Quản trị & Báo cáo
- **Quy trình Giám sát vận hành:** Theo dõi chuyến đi, trạng thái tài xế và xử lý các trường hợp bất thường.
- **Quy trình Quản trị hệ thống:** Quản lý tài khoản, phân quyền và kiểm soát quyền truy cập.
- **Quy trình Quản lý giao dịch:** Tra cứu và theo dõi thông tin giao dịch.
- **Quy trình Báo cáo:** Tổng hợp dữ liệu về chuyến đi, giao dịch và doanh thu phục vụ quản lý.
## 5. Chuyển các yêu cầu thành yêu cầu nghiệp vụ
### a. Yêu cầu Quản lý Khách hàng
- **BRa01:** Cho phép khách hàng đăng ký, đăng nhập và quản lý thông tin cá nhân để sử dụng dịch vụ.
- **BRa02:** Hỗ trợ khách hàng tự tạo yêu cầu đặt xe để giảm phụ thuộc vào việc tiếp nhận và điều phối thủ công.
- **BRa03:** Cung cấp khả năng theo dõi trạng thái và thông tin chuyến đi trong quá trình sử dụng dịch vụ.
- **BRa04:** Thu thập đánh giá của khách hàng về tài xế sau khi chuyến đi hoàn thành.
### b. Yêu cầu Quản lý Tài xế và Phương tiện
- **BRb01:** Quản lý thông tin tài xế và phương tiện phục vụ hoạt động cung cấp dịch vụ.
- **BRb02:** Quản lý trạng thái và vị trí của tài xế để phục vụ việc tìm kiếm và phân công chuyến.
- **BRb03:** Cho phép tài xế tiếp nhận hoặc từ chối chuyến và cập nhật trạng thái trong quá trình thực hiện chuyến.
### c. Yêu cầu Tính cước và Thanh toán
- **BRc01:** Xác định số tiền khách hàng phải thanh toán dựa trên loại dịch vụ và thông tin chuyến đi.
- **BRc02:** Cần hỗ trợ thanh toán bằng tiền mặt và phương thức thanh toán điện tử thông qua nhà cung cấp dịch vụ thanh toán.
- **BRc03:** Cần ghi nhận kết quả thanh toán, thông báo khi giao dịch thất bại và hỗ trợ xử lý lại theo chính sách của doanh nghiệp.
### d. Yêu cầu Thông báo
- **BRd01:** Cung cấp thông tin cập nhật cho khách hàng trong các giai đoạn chính của quá trình đặt và thực hiện chuyến.
- **BRd02:** Cung cấp thông tin chuyến xe và các thay đổi liên quan cho tài xế để hỗ trợ quá trình điều phối và thực hiện chuyến.
### e. Yêu cầu Vận hành, Quản trị & Báo cáo
- **BRe01:** Giám sát các chuyến đi, trạng thái tài xế và xử lý các trường hợp bất thường trong quá trình vận hành.
- **BRe02:** Quản lý tài khoản và phân quyền truy cập theo vai trò để bảo vệ dữ liệu và chức năng của hệ thống.
- **BRe03:** Tổng hợp và cung cấp báo cáo về hoạt động chuyến đi, giao dịch và doanh thu để phục vụ công tác quản lý.
## 6. Phân rã yêu cầu chức năng
| STT | Chức năng chính | Chức năng con |
|---|---|---|
| 1 | Quản lý tài khoản và hồ sơ | Đăng ký tài khoản |
|  |  |  Đăng nhập |
|  |  |  Quản lý hồ sơ |
|  |  |  Đăng xuất |
| 2 | Quản lý đặt xe |  Đặt xe |
|  |  |  Theo dõi chuyến đi |
|  |  |  Xem lịch sử chuyến đi |
|  |  |  Thanh toán |
|  |  |  Đánh giá tài xế |
|  |  |  Hủy chuyến |
| 3 | Quản lý hoạt động tài xế |  Cập nhật trạng thái hoạt động |
|  |  |  Cập nhật vị trí |
|  |  |  Nhận hoặc từ chối chuyến |
|  |  |  Quản lý phương tiện |
|  |  |  Cập nhật trạng thái chuyến |
| 4 | Quản lý khách hàng, tài xế và phương tiện |  Quản lý khách hàng |
|  |  |  Quản lý tài xế |
|  |  |  Quản lý phương tiện |
| 5 | Giám sát và vận hành |  Giám sát chuyến đi |
|  |  |  Theo dõi trạng thái tài xế |
|  |  |  Xử lý trường hợp bất thường |
|  |  |  Tra cứu giao dịch |
| 6 | Báo cáo |  Xem báo cáo |
| 7 | Quản trị hệ thống |  Quản lý quyền truy cập |
|  |  |  Quản lý tài khoản |
  ## 7. Vẽ usecase
<img width="1200" height="694" alt="Use Case Diagram1" src="https://github.com/user-attachments/assets/de6b51c6-7821-4950-aef9-64e969bc48db" />

  ## 8. Đặc tả usecase
### UC01 – Đăng ký tài khoản
* Actor chính: Người dùng (Khách hàng, Tài xế)
* Mục tiêu : Tạo tài khoản để sử dụng dịch vụ đặt xe
* Tiền điều kiện : Người dùng chưa có tài khoản.
* Hậu điều kiện : Tài khoản Người dùng được tạo thành công.

**Luồng chính:**
| Người dùng | Hệ thống |
|---|---|
| 1. Người dùng chọn chức năng **Đăng ký tài khoản** | 2. Hệ thống hiển thị biểu mẫu đăng ký. |
| 3. Người dùng nhập thông tin cá nhân. | |
| 4. Người dùng gửi yêu cầu đăng ký]. | 5. Hệ thống kiểm tra tính hợp lệ của thông tin. |
| | 6. Hệ thống kiểm tra tài khoản đã tồn tại hay chưa. |
| | 7. Hệ thống tạo tài khoản |
| | 8. Hệ thống thông báo đăng ký thành công. |

**Luồng thay thế/ngoại lệ:**
- **5a.** Thông tin không hợp lệ → Hệ thống yêu cầu nhập lại.
- **6a.** Tài khoản đã tồn tại → Hệ thống thông báo và yêu cầu sử dụng thông tin khác.
- **7a.** Lỗi hệ thống → Không tạo được tài khoản.

### UC02 – Đăng nhập
* Actor chính: Người dùng (Khách hàng, Tài xế, Nhân viên vận hành, Quản trị viên)
* Mục tiêu : Xác thực người dùng trước khi sử dụng các chức năng yêu cầu tài khoản.
* Tiền điều kiện : Người dùng đã có tài khoản.
* Hậu điều kiện : Người dùng đăng nhập thành công.
  
**Luồng chính:**
| Người dùng | Hệ thống |
|---|---|
| 1. Người dùng chọn **Đăng nhập** | 2. Hệ thống hiển thị biểu mẫu đăng nhập. |
| 3. Người dùng nhập thông tin đăng nhập. | |
| 4. Người dùng gửi yêu cầu. | 5. Hệ thống kiểm tra thông tin. |
| | 6. Hệ thống xác thực tài khoản. |
| | 7. Hệ thống cho phép người dùng truy cập. |

**Luồng thay thế/ngoại lệ:**
- **5a.** Sai thông tin đăng nhập → Hệ thống thông báo lỗi.
- **6a.** Tài khoản không hợp lệ/bị khóa → Hệ thống từ chối đăng nhập.

### UC03 – Quản lý hồ sơ
* Actor chính: Người dùng (Khách hàng, Tài xế)
* Mục tiêu : Cho phép người dùng cập nhật thông tin cá nhân.
* Tiền điều kiện : Người dùng đã đăng nhập vào hệ thống.
* Hậu điều kiện : Thông tin cá nhân được cập nhật thành công.

**Luồng chính:**
| Người dùng | Hệ thống |
|---|---|
| 1. Người dùng chọn mục **Hồ sơ cá nhân**. | 2. Hệ thống hiển thị thông tin hiện tại của người dùng. |
| 3. Người dùng chọn chỉnh sửa. | |
| 4. Người dùng cập nhật thông tin mới. | |
| 5. Người dùng xác nhận lưu thay đổi. | 6. Hệ thống kiểm tra tính hợp lệ của thông tin. |
| | 7. Hệ thống lưu thông tin mới vào cơ sở dữ liệu |
| | 8. Hệ thống thông báo cập nhật thành công. |

**Luồng thay thế/ngoại lệ:**
- **6a.** Thông tin không hợp lệ → Hệ thống yêu cầu người dùng nhập lại.
- **7a.** Lỗi lưu dữ liệu → Hệ thống thông báo cập nhật thất bại và yêu cầu thử lại.

## 1. Khách hàng
### UC04 – Đặt xe
* Actor chính: Khách hàng
* Mục tiêu : Cho phép khách hàng tạo yêu cầu đặt xe.
* Tiền điều kiện : Khách hàng đã đăng nhập.
* Hậu điều kiện : Yêu cầu đặt xe được tạo và hệ thống bắt đầu tìm tài xế.

**Luồng chính:**
| Khách hàng | Hệ thống |
|---|---|
| 1. Khách hàng chọn chức năng **Đặt xe**. | 2. Hệ thống hiển thị giao diện đặt xe. |
| 3. Khách hàng nhập điểm đón. | |
| 4. Khách hàng nhập điểm đến. | |
| 5. Khách hàng lựa chọn loại xe. | 6. Hệ thống kiểm tra thông tin chuyến. |
| 7. Khách hàng xác nhận yêu cầu đặt xe. | 8. Hệ thống tiếp nhận yêu cầu. |
| | 9. Hệ thống bắt đầu tìm tài xế phù hợp. |
| | 10. Hệ thống thông báo trạng thái tìm tài xế cho khách hàng. |

**Luồng thay thế/ngoại lệ:**
- **3a.** Điểm đón không hợp lệ → Hệ thống yêu cầu nhập lại.
- **4a.** Điểm đến không hợp lệ → Hệ thống yêu cầu nhập lại.
- **5a.** Loại xe không khả dụng → Hệ thống yêu cầu lựa chọn loại xe khác.
- **9a.** Không tìm được tài xế → Hệ thống thông báo rõ ràng cho khách hàng.

### UC05 – Theo dõi chuyến đi
* Actor chính: Khách hàng
* Mục tiêu : Cho phép khách hàng theo dõi trạng thái chuyến và tài xế.
* Tiền điều kiện : Khách hàng đã tạo yêu cầu đặt xe.
* Hậu điều kiện : Thông tin trạng thái chuyến được hiển thị.

**Luồng chính:**
| Khách hàng | Hệ thống |
|---|---|
| 1. Khách hàng mở thông tin chuyến. | 2. Hệ thống hiển thị trạng thái tìm tài xế. |
| | 3. Khi tài xế nhận chuyến, hệ thống hiển thị thông tin tài xế. |
| | 4. Hệ thống hiển thị thời gian dự kiến tài xế đến. |
| | 5. Khi tài xế đến điểm đón, hệ thống cập nhật trạng thái. |
| | 6. Hệ thống tiếp tục cập nhật trạng thái trong quá trình thực hiện chuyến. |
| | 7. Khi chuyến hoàn thành, hệ thống thông báo trạng thái hoàn thành. |

**Luồng thay thế/ngoại lệ:**
- **3a.** Chưa có tài xế nhận chuyến → Hệ thống tiếp tục hiển thị trạng thái tìm tài xế.
- **4a.** Không xác định được thời gian dự kiến → Hệ thống thông báo dữ liệu chưa khả dụng.

### UC06 – Xem lịch sử chuyến đi
* Actor chính: Khách hàng
* Mục tiêu : Xem lại các chuyến đã thực hiện.
* Tiền điều kiện : Khách hàng đã đăng nhập.
* Hậu điều kiện : Lịch sử chuyến được hiển thị.

**Luồng chính:**
| Khách hàng | Hệ thống |
|---|---|
| 1. Khách hàng chọn **Lịch sử chuyến đi**. | 2. Hệ thống truy xuất lịch sử. |
| | 3. Hệ thống hiển thị danh sách chuyến. |
| 4. Khách hàng chọn một chuyến. | 5. Hệ thống hiển thị chi tiết chuyến. |
| | 6. Hệ thống hiển thị số tiền phải trả. |

**Luồng thay thế/ngoại lệ:**
- **2a.** Không có chuyến → Hệ thống thông báo chưa có lịch sử.
- **2b.** Lỗi truy xuất dữ liệu → Hệ thống thông báo không thể tải dữ liệu.

### UC07 – Thanh toán
* Actor chính: Khách hàng
* Actor phụ : Nhà cung cấp thanh toán bên ngoài
* Mục tiêu : Thanh toán chi phí chuyến đi.
* Tiền điều kiện : Chuyến đi đã hoàn thành và hệ thống xác định được số tiền phải trả.
* Hậu điều kiện : Kết quả thanh toán được ghi nhận.

**Luồng chính:**
| Khách hàng | Hệ thống |
|---|---|
| | 1. Chuyến đi được hoàn thành. |
| | 2. Hệ thống xác định số tiền khách hàng phải trả. |
| 3. Khách hàng chọn phương thức thanh toán. | |
| | 4. Nếu chọn tiền mặt → Hệ thống ghi nhận thanh toán tiền mặt. |
| | 5. Nếu chọn thanh toán điện tử → Hệ thống gửi yêu cầu đến nhà cung cấp thanh toán. |
| | 6. Nhà cung cấp xử lý giao dịch. |
| | 7. Nhà cung cấp trả kết quả cho hệ thống. |
| | 8. Hệ thống cập nhật trạng thái thanh toán. |
| | 9. Hệ thống thông báo kết quả cho khách hàng. |

**Luồng thay thế/ngoại lệ:**
- **5a.** Thanh toán điện tử thất bại → Hệ thống thông báo cho khách hàng.
- **5b.** Khách hàng thực hiện lại thanh toán theo chính sách của doanh nghiệp.
- **7a.** Không nhận được kết quả → Hệ thống xử lý theo cơ chế của doanh nghiệp.

### UC08 – Đánh giá tài xế
* Actor chính: Khách hàng
* Mục tiêu : Cho phép khách hàng đánh giá tài xế sau chuyến đi.
* Tiền điều kiện : Chuyến đi đã hoàn thành.
* Hậu điều kiện : Đánh giá được lưu vào hệ thống.

**Luồng chính:**
| Khách hàng | Hệ thống |
|---|---|
| 1. Khách hàng mở chuyến đã hoàn thành. | 2. Hệ thống hiển thị chức năng đánh giá. |
| 3. Khách hàng thực hiện đánh giá tài xế. | |
| 4. Khách hàng gửi đánh giá. | 5. Hệ thống kiểm tra thông tin. |
| | 6. Hệ thống lưu đánh giá. |
| | 7. Hệ thống thông báo đánh giá thành công. |

**Luồng thay thế/ngoại lệ:**
- **1a.** Chuyến chưa hoàn thành → Hệ thống không cho phép đánh giá.
- **5a.** Thông tin đánh giá không hợp lệ → Hệ thống yêu cầu nhập lại.

# 2. TÀI XẾ
### UC09 – Quản lý phương tiện cá nhân
* Actor chính: Tài xế
* Mục tiêu : Cho phép tài xế quản lý thông tin phương tiện của mình.
* Tiền điều kiện : Tài xế đã đăng nhập.
* Hậu điều kiện : Thông tin phương tiện được cập nhật.

**Luồng chính:**
| Tài xế | Hệ thống |
|---|---|
| 1. Tài xế chọn **Quản lý phương tiện**. | 2. Hệ thống hiển thị thông tin phương tiện. |
| 3. Tài xế thêm hoặc cập nhật thông tin. | |
| 4. Tài xế xác nhận. | 5. Hệ thống kiểm tra. |
| | 6. Hệ thống lưu thông tin. |
| | 7. Hệ thống thông báo thành công. |

**Luồng thay thế/ngoại lệ:**
- Thông tin không hợp lệ → Hệ thống yêu cầu nhập lại.
- Phương tiện không đáp ứng yêu cầu → Hệ thống thông báo.

### UC10 – Cập nhật trạng thái hoạt động
* Actor chính: Tài xế
* Mục tiêu : Cho phép tài xế chuyển sang trạng thái sẵn sàng nhận chuyến.
* Tiền điều kiện : Tài xế đã đăng nhập.
* Hậu điều kiện : Trạng thái hoạt động được cập nhật.

**Luồng chính:**
| Tài xế | Hệ thống |
|---|---|
| 1. Tài xế mở trạng thái hoạt động. | 2. Hệ thống hiển thị trạng thái hiện tại. |
| 3. Tài xế chọn **Sẵn sàng nhận chuyến**. | 4. Hệ thống cập nhật trạng thái. |
| | 5. Hệ thống đưa tài xế vào danh sách có thể nhận chuyến. |

**Luồng thay thế/ngoại lệ:**
- Tài xế không đủ điều kiện hoạt động → Hệ thống không cho phép chuyển trạng thái.

### UC11 – Cập nhật vị trí
* Actor chính: Tài xế
* Mục tiêu : Lưu vị trí tài xế để hỗ trợ tìm tài xế và dự kiến thời gian đến.
* Tiền điều kiện : Tài xế đã đăng nhập và cho phép hệ thống truy cập vị trí.
* Hậu điều kiện : Vị trí tài xế được cập nhật.

**Luồng chính:**
| Tài xế | Hệ thống |
|---|---|
| | 1. Hệ thống yêu cầu quyền truy cập vị trí. |
| 2. Tài xế cho phép truy cập. | |
| | 3. Hệ thống lấy vị trí hiện tại. |
| | 4. Hệ thống lưu/cập nhật vị trí. |
| | 5. Hệ thống sử dụng vị trí để hỗ trợ tìm tài xế phù hợp. |

**Luồng thay thế/ngoại lệ:**
- Không được cấp quyền vị trí → Hệ thống không thể cập nhật vị trí.
- Không xác định được vị trí → Hệ thống thông báo lỗi.

### UC12 – Nhận chuyến
* Actor chính: Tài xế
* Mục tiêu : Cho phép tài xế nhận yêu cầu chuyến phù hợp.
* Tiền điều kiện : Tài xế đang ở trạng thái sẵn sàng nhận chuyến.
* Hậu điều kiện : Chuyến được gán cho tài xế.

**Luồng chính:**
| Tài xế | Hệ thống |
|---|---|
| | 1. Hệ thống xác định chuyến phù hợp. |
| | 2. Hệ thống gửi thông báo chuyến mới cho tài xế. |
| 3. Tài xế xem thông tin chuyến. | |
| 4. Tài xế chọn Chấp nhận. | 5. Hệ thống kiểm tra chuyến. |
| | 6. Hệ thống gán chuyến cho tài xế. |
| | 7. Hệ thống cập nhật trạng thái chuyến. |
| | 8. Hệ thống thông báo cho khách hàng. |

**Luồng thay thế/ngoại lệ:**
- Chuyến đã được tài xế khác nhận → Hệ thống thông báo không còn khả dụng.
- Hết thời gian phản hồi → Hệ thống xử lý như không nhận chuyến.

### UC13 – Từ chối chuyến
* Actor chính: Tài xế
* Mục tiêu : Cho phép tài xế từ chối chuyến được đề xuất.
* Tiền điều kiện : Tài xế nhận được yêu cầu chuyến.
* Hậu điều kiện : Chuyến được trả lại cho cơ chế tìm tài xế.

**Luồng chính:**
| Tài xế | Hệ thống |
|---|---|
| | 1. Hệ thống gửi thông báo chuyến mới. |
| 2. Tài xế xem thông tin. | |
| 3. Tài xế chọn **Từ chối**. | 4. Hệ thống ghi nhận kết quả. |
| | 5. Hệ thống tiếp tục tìm tài xế phù hợp khác. |
| | 6. Khách hàng không cần tạo lại yêu cầu. |

**Luồng thay thế/ngoại lệ:**
- Không có tài xế khác phù hợp → Hệ thống thông báo cho khách hàng.

### UC14 – Cập nhật trạng thái chuyến
* Actor chính: Tài xế
* Mục tiêu : Cập nhật tiến trình thực hiện chuyến.
* Tiền điều kiện : Tài xế đã nhận chuyến và chuyến đang ở trạng thái cho phép cập nhật.
* Hậu điều kiện : Trạng thái chuyến được cập nhật và khách hàng nhận được thông tin.

**Luồng chính:**
| Tài xế | Hệ thống |
|---|---|
| 1. Tài xế nhận chuyến. | |
| 2. Tài xế di chuyển đến điểm đón. | |
| 3. Tài xế cập nhật Đã đến điểm đón. | 4. Hệ thống cập nhật trạng thái và thông báo cho khách hàng.|
| 5. Tài xế đón khách. | |
| 6. Tài xế cập nhật Đã đón khách. | 7. Hệ thống cập nhật trạng thái chuyến.|
| 8. Tài xế bắt đầu di chuyển. | |
| 9. Tài xế cập nhật Đang di chuyển. | 10. Hệ thống cập nhật trạng thái chuyến.|
| 11. Tài xế đến điểm trả. | |
| 12. Tài xế cập nhật Hoàn thành chuyến. | 13. Hệ thống cập nhật trạng thái và thông báo cho khách hàng. |

**Luồng thay thế/ngoại lệ:**
- Trạng thái không hợp lệ → Hệ thống từ chối cập nhật.
- Mất kết nối → Hệ thống xử lý theo chính sách được doanh nghiệp xác định.

# 3. NHÂN VIÊN VẬN HÀNH
### UC15 – Quản lý khách hàng
* Actor chính: Nhân viên vận hành
* Mục tiêu : Quản lý thông tin khách hàng trong hệ thống.
* Tiền điều kiện : Nhân viên vận hành đã đăng nhập và có quyền phù hợp.
* Hậu điều kiện : Thông tin khách hàng được xem hoặc cập nhật.

**Luồng chính:**
| Nhân viên vận hành | Hệ thống |
|---|---|
| 1. Nhân viên chọn **Quản lý khách hàng**. | 2. Hệ thống hiển thị danh sách khách hàng. |
| 3. Nhân viên tìm kiếm khách hàng. | 4. Hệ thống hiển thị thông tin. |
| 5. Nhân viên thực hiện thao tác được cấp quyền. | 6. Hệ thống kiểm tra quyền. |
| | 7. Hệ thống lưu thay đổi nếu có. |
| | 8. Hệ thống thông báo kết quả. |

**Luồng thay thế/ngoại lệ:**
- Không tìm thấy khách hàng → Hệ thống thông báo.
- Không đủ quyền → Hệ thống từ chối thao tác.

### UC16 – Quản lý tài xế
* Actor chính: Nhân viên vận hành
* Mục tiêu : Quản lý tài xế và hỗ trợ tạo tài khoản tài xế.
* Tiền điều kiện : Nhân viên vận hành đã đăng nhập.
* Hậu điều kiện : Thông tin tài xế được cập nhật.

**Luồng chính:**
| Nhân viên vận hành | Hệ thống |
|---|---|
| 1. Nhân viên chọn **Quản lý tài xế**. | 2. Hệ thống hiển thị danh sách tài xế. |
| 3. Nhân viên tìm kiếm tài xế. | |
| 4. Nhân viên xem hoặc cập nhật thông tin. | |
| 5. Nếu cần, nhân viên tạo tài khoản cho tài xế. | 6. Hệ thống kiểm tra dữ liệu. |
| | 7. Hệ thống lưu thông tin. |
| | 8. Hệ thống thông báo kết quả. |

**Luồng thay thế/ngoại lệ:**
- Thông tin không hợp lệ → Hệ thống yêu cầu nhập lại.
- Tài khoản đã tồn tại → Hệ thống thông báo.
- Không đủ quyền → Hệ thống từ chối thao tác.

### UC17 – Quản lý phương tiện
* Actor chính: Nhân viên vận hành
* Mục tiêu : Quản lý thông tin phương tiện trong hệ thống.
* Tiền điều kiện : Nhân viên vận hành đã đăng nhập.
* Hậu điều kiện : Thông tin phương tiện được cập nhật.

**Luồng chính:**
| Nhân viên vận hành | Hệ thống |
|---|---|
| 1. Nhân viên chọn **Quản lý phương tiện**. | 2. Hệ thống hiển thị danh sách phương tiện. |
| 3. Nhân viên tìm kiếm phương tiện. | |
| 4. Nhân viên xem hoặc cập nhật thông tin. | 5. Hệ thống kiểm tra dữ liệu. |
| | 6. Hệ thống lưu thay đổi. |
| | 7. Hệ thống thông báo kết quả. |

**Luồng thay thế/ngoại lệ:**
- Phương tiện không tồn tại → Hệ thống thông báo.
- Dữ liệu không hợp lệ → Hệ thống yêu cầu nhập lại.
- Không đủ quyền → Hệ thống từ chối.

### UC18 – Giám sát chuyến đi
* Actor chính: Nhân viên vận hành
* Mục tiêu : Theo dõi các chuyến đang diễn ra.
* Tiền điều kiện : Nhân viên vận hành đã đăng nhập.
* Hậu điều kiện : Thông tin chuyến được hiển thị để hỗ trợ vận hành.

**Luồng chính:**
| Nhân viên vận hành | Hệ thống |
|---|---|
| 1. Nhân viên chọn **Giám sát chuyến đi**. | 2. Hệ thống hiển thị các chuyến đang diễn ra. |
| 3. Nhân viên chọn chuyến cần theo dõi. | 4. Hệ thống hiển thị tài xế, trạng thái và thông tin chuyến. |
| | 5. Hệ thống cập nhật dữ liệu. |
| 6. Nhân viên theo dõi và hỗ trợ khi cần. | |

**Luồng thay thế/ngoại lệ:**
- Không có chuyến đang diễn ra → Hệ thống thông báo.
- Dữ liệu không cập nhật → Hệ thống hiển thị dữ liệu gần nhất.

### UC19 – Theo dõi trạng thái tài xế
* Actor chính: Nhân viên vận hành
* Mục tiêu : Kiểm tra trạng thái hoạt động của tài xế.
* Tiền điều kiện : Nhân viên vận hành đã đăng nhập.
* Hậu điều kiện : Trạng thái tài xế được hiển thị.

**Luồng chính:**
| Nhân viên vận hành | Hệ thống |
|---|---|
| 1. Nhân viên chọn **Theo dõi trạng thái tài xế**. | 2. Hệ thống hiển thị danh sách tài xế. |
| | 3. Hệ thống hiển thị trạng thái hoạt động. |
| 4. Nhân viên chọn tài xế cần xem. | 5. Hệ thống hiển thị vị trí và chuyến đang thực hiện nếu có. |
| 6. Nhân viên theo dõi trạng thái. | |

**Luồng thay thế/ngoại lệ:**
- Không tìm thấy tài xế → Hệ thống thông báo.
- Không có dữ liệu vị trí → Hệ thống hiển thị trạng thái gần nhất.

### UC20 – Xử lý trường hợp bất thường
* Actor chính: Nhân viên vận hành
* Mục tiêu : Hỗ trợ xử lý các chuyến bị lỗi hoặc trường hợp bất thường.
* Tiền điều kiện : Có chuyến hoặc trường hợp cần hỗ trợ.
* Hậu điều kiện : Trường hợp được xử lý hoặc chuyển cấp.

**Luồng chính:**
| Nhân viên vận hành | Hệ thống |
|---|---|
| 1. Nhân viên nhận thông tin trường hợp bất thường. | |
| 2. Nhân viên mở thông tin chuyến. | 3. Hệ thống hiển thị dữ liệu liên quan. |
| 4. Nhân viên kiểm tra nguyên nhân. | |
| 5. Nhân viên thực hiện phương án xử lý. | 6. Hệ thống cập nhật kết quả. |
| | 7. Hệ thống lưu vết thao tác. |

**Luồng thay thế/ngoại lệ:**
- Không thể xử lý → Chuyển cấp có thẩm quyền.
- Thiếu thông tin → Hệ thống yêu cầu bổ sung.
- Lỗi hệ thống → Hệ thống ghi nhận để xử lý.

### UC21 – Tra cứu lịch sử giao dịch
* Actor chính: Nhân viên vận hành
* Mục tiêu : Tra cứu lịch sử giao dịch thanh toán.
* Tiền điều kiện : Nhân viên đã đăng nhập và có quyền tra cứu.
* Hậu điều kiện : Thông tin giao dịch được hiển thị.

**Luồng chính:**
| Nhân viên vận hành | Hệ thống |
|---|---|
| 1. Nhân viên chọn **Tra cứu giao dịch**. | 2. Hệ thống hiển thị giao diện tra cứu. |
| 3. Nhân viên nhập điều kiện tìm kiếm. | 4. Hệ thống truy xuất dữ liệu. |
| | 5. Hệ thống hiển thị danh sách giao dịch. |
| 6. Nhân viên chọn giao dịch. | 7. Hệ thống hiển thị chi tiết. |

**Luồng thay thế/ngoại lệ:**
- Không tìm thấy giao dịch → Hệ thống thông báo.
- Không đủ quyền → Hệ thống từ chối truy cập.
- Lỗi truy xuất → Hệ thống thông báo lỗi.

# 4. QUẢN TRỊ VIÊN
### UC22 – Xem báo cáo
* Actor chính: Quản trị viên
* Mục tiêu : Theo dõi dữ liệu hoạt động của hệ thống.
* Tiền điều kiện : Người dùng có quyền xem báo cáo.
* Hậu điều kiện : Báo cáo được hiển thị.

**Luồng chính:**
| Quản trị viên | Hệ thống |
|---|---|
| 1. Người dùng chọn **Báo cáo**. | 2. Hệ thống hiển thị các loại báo cáo gồm số lượng chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả hoạt động của tài xế. |
| 3. Người dùng chọn loại báo cáo. | |
| 4. Chọn khoảng thời gian và điều kiện lọc. | 5. Hệ thống truy xuất dữ liệu. |
| | 6. Hệ thống tổng hợp dữ liệu. |
| | 7. Hệ thống hiển thị báo cáo. |

**Luồng thay thế/ngoại lệ:**
- Không có dữ liệu → Hệ thống thông báo.
- Điều kiện lọc không hợp lệ → Hệ thống yêu cầu nhập lại.

### UC23 – Quản lý quyền truy cập
* Actor chính: Quản trị viên
* Mục tiêu : Phân quyền và quản lý quyền hạn truy cập của các tài khoản trong hệ thống.
* Tiền điều kiện : Quản trị viên đã đăng nhập với quyền cao nhất.
* Hậu điều kiện : Quyền hạn của tài khoản được cập nhật và ghi nhận.

**Luồng chính:**
| Quản trị viên | Hệ thống |
|---|---|
| 1. Quản trị viên chọn **Quản lý quyền truy cập**. | 2. Hệ thống hiển thị danh sách vai trò và quyền hạn tương ứng. |
| 3. Quản trị viên chọn vai trò hoặc tài khoản cần phân quyền. | 4. Hệ thống hiển thị chi tiết các quyền hiện tại. |
| 5. Quản trị viên khóa hoặc chỉnh sửa quyền. | 6. Hệ thống kiểm tra tính hợp lệ của phân quyền. |
| 7. Quản trị viên xác nhận lưu thay đổi. | 8. Hệ thống lưu cấu hình quyền mới. |
| | 9. Hệ thống thông báo cập nhật quyền thành công. |

**Luồng thay thế/ngoại lệ:**
- **6a.** Xung đột hoặc không đủ thẩm quyền → Hệ thống từ chối thay đổi và hiển thị cảnh báo.
- **8a.** Lỗi hệ thống khi lưu → Hệ thống thông báo lỗi và yêu cầu thực hiện lại.

### UC24 – Quản lý tài khoản
* Actor chính: Quản trị viên
* Mục tiêu : Tạo mới, khóa, mở khóa hoặc cập nhật thông tin tổng quan của các tài khoản (khách hàng, tài xế, nhân viên).
* Tiền điều kiện : Quản trị viên đã đăng nhập và có quyền quản lý tài khoản.
* Hậu điều kiện : Trạng thái hoặc thông tin tài khoản được cập nhật trong hệ thống.

**Luồng chính:**
| Quản trị viên | Hệ thống |
|---|---|
| 1. Quản trị viên chọn **Quản lý tài khoản**. | 2. Hệ thống hiển thị danh sách tài khoản toàn hệ thống. |
| 3. Quản trị viên tìm kiếm và chọn tài khoản cần thao tác. | 4. Hệ thống hiển thị thông tin chi tiết tài khoản. |
| 5. Quản trị viên chọn hành động (Thêm mới, Khóa/Mở khóa, Cập nhật thông tin). | 6. Hệ thống kiểm tra dữ liệu hoặc trạng thái yêu cầu. |
| 7. Quản trị viên xác nhận thực thi. | 8. Hệ thống thực hiện thay đổi dữ liệu tài khoản. |
| | 9. Hệ thống thông báo kết quả thành công. |

**Luồng thay thế/ngoại lệ:**
- **5a.** Tài khoản đã tồn tại khi tạo mới → Hệ thống thông báo trùng lặp.
- **6a.** Dữ liệu nhập vào không hợp lệ → Hệ thống yêu cầu kiểm tra và nhập lại.
- **8a.** Không đủ quyền hạn thao tác → Hệ thống từ chối thực hiện.

### UC25 – Đăng xuất
* Actor chính: Người dùng (Khách hàng, Tài xế, Nhân viên vận hành, Quản trị viên)
* Mục tiêu: Kết thúc phiên đăng nhập và thoát khỏi hệ thống.
* Tiền điều kiện: Người dùng đã đăng nhập.
* Hậu điều kiện: Phiên đăng nhập của Người dùng được kết thúc.

**Luồng chính:**
| Người dùng | Hệ thống |
|---|---|
| 1. Người dùng chọn chức năng **Đăng xuất**. | 2. Hệ thống hiển thị yêu cầu xác nhận đăng xuất. |
| 3. Người dùng xác nhận đăng xuất. | 4. Hệ thống kết thúc phiên đăng nhập của Người dùng. |
| | 5. Hệ thống chuyển Người dùng về màn hình đăng nhập. |

**Luồng thay thế/ngoại lệ:**
- **3a.** Người dùng hủy đăng xuất → Hệ thống giữ nguyên phiên đăng nhập.
- **4a.** Lỗi hệ thống → Hệ thống thông báo không thể đăng xuất, Người dùng có thể thực hiện lại.

  ## 9. Phân tích quy trình nghiệp vụ
```mermaid
flowchart TD
    Start((Bắt đầu))

    subgraph KH["KHÁCH HÀNG"]
        direction TB
        K1[Đăng nhập]
        K2[Nhập điểm đón và điểm đến]
        K3[Chọn loại xe]
        K4[Xác nhận đặt xe]
        K5[Theo dõi trạng thái chuyến]
        K6[Chọn phương thức thanh toán]
        K7[Thực hiện thanh toán]
        K8[Đánh giá tài xế]
    end

    subgraph CAB["HỆ THỐNG CAB"]
        direction TB
        S1[Kiểm tra thông tin yêu cầu]
        G1{Thông tin hợp lệ?}
        S2[Tạo yêu cầu chuyến]
        S3[Tính cước ước tính]
        S4[Thông báo đang tìm tài xế]

        S5[Tìm và xếp hạng tài xế phù hợp]
        G2{Có tài xế phù hợp?}
        S6[Gửi yêu cầu chuyến]
        G3{Tài xế phản hồi?}
        G4{Chấp nhận chuyến?}

        S7[Gán chuyến cho tài xế]
        S8[Thông báo thông tin tài xế và ETA cho khách hàng]
        S9[Cập nhật trạng thái chuyến]
        S10[Thông báo khách hàng]

        S11[Chốt cước thực tế]
        G5{Phương thức thanh toán?}
        S12[Ghi nhận thanh toán tiền mặt]
        S13[Gửi yêu cầu thanh toán điện tử]
        G6{Thanh toán thành công?}
        S14[Ghi nhận thanh toán]
        S15[Thông báo kết quả thanh toán]

        S16[Lưu đánh giá]
        S17[Cập nhật dữ liệu báo cáo]
        S18[Thông báo không tìm được tài xế]
        S19[Thông báo thanh toán thất bại]
    end

    subgraph TX["TÀI XẾ"]
        direction TB
        D1[Cập nhật trạng thái sẵn sàng]
        D2[Nhận thông báo chuyến]
        D3[Xem thông tin chuyến]
        D5[Di chuyển đến điểm đón]
        D6[Cập nhật: Đã đến điểm đón]
        D7[Đón khách]
        D8[Cập nhật: Đang di chuyển]
        D9[Hoàn thành chuyến]
    end

    subgraph PAY["NHÀ CUNG CẤP THANH TOÁN"]
        direction TB
        P1[Xử lý giao dịch]
        P2[Trả kết quả giao dịch]
    end

    Start --> K1
    K1 --> K2
    K2 --> K3
    K3 --> K4
    K4 --> S1
    S1 --> G1

    G1 -- Không --> K2
    G1 -- Có --> S2
    S2 --> S3
    S3 --> S4
    S4 --> S5
    S5 --> G2

    G2 -- Không --> S18
    S18 --> End1((Kết thúc: Không có tài xế))

    G2 -- Có --> S6
    S6 --> D2
    D2 --> D3
    D3 --> G3

    G3 -- Không/Quá thời gian --> S5
    G3 -- Có --> G4

    G4 -- Không --> S5
    G4 -- Có --> S7

    S7 --> S8
    S8 --> K5
    S8 --> D5

    D5 --> D6
    D6 --> S9
    S9 --> S10
    S10 --> K5

    D6 --> D7
    D7 --> D8
    D8 --> S9

    D8 --> D9
    D9 --> S11
    S11 --> K6

    K6 --> G5

    G5 -- Tiền mặt --> S12
    S12 --> S14

    G5 -- Điện tử --> K7
    K7 --> S13
    S13 --> P1
    P1 --> P2
    P2 --> G6

    G6 -- Không --> S19
    S19 --> K7

    G6 -- Có --> S14

    S14 --> S15
    S15 --> K8
    K8 --> S16
    S16 --> S17
    S17 --> End2((Kết thúc))
```
  ## 10. Phân tích nguyên tắc nghiệp vụ
* **Quy tắc Phân công và Xử lý từ chối:** Hệ thống ưu tiên lựa chọn tài xế phù hợp dựa trên vị trí, trạng thái sẵn sàng và các tiêu chí vận hành được doanh nghiệp xác định. Nếu tài xế được đề xuất từ chối hoặc không phản hồi trong thời gian giới hạn, hệ thống phải tự động chuyển tiếp sang tài xế tiếp theo mà không làm gián đoạn hoặc yêu cầu khách hàng phải tạo lại yêu cầu.
* **Quy tắc Tách biệt Dữ liệu Thanh toán & Bảo mật:** Tuyệt đối không lưu trữ trực tiếp thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán nội bộ bên trong hệ thống CAB System. Mọi giao dịch điện tử phải được thực hiện thông qua liên kết bảo mật với nhà cung cấp cổng thanh toán độc lập bên ngoài.
* **Quy tắc Phân quyền và Kiểm soát Truy cập RBAC:** Mọi tác nhân (Khách hàng, Tài xế, Nhân viên vận hành) phải đi qua cổng định danh và xác thực an toàn. Các thao tác quản trị hệ thống nhạy cảm phải được phân quyền chặt chẽ theo vai trò (RBAC) để bảo vệ dữ liệu cá nhân, phương tiện và giao dịch.
* **Quy tắc Kiến trúc Độc lập & Ổn định:** Các thành phần chức năng (như Thanh toán, Thông báo, Đặt xe) phải được thiết kế dạng module mở rộng độc lập. Khi một sự cố xảy ra ở module phụ trợ (ví dụ lỗi cổng thanh toán hoặc lỗi gửi thông báo), hệ thống không được làm ngưng trệ toàn bộ nền tảng đặt xe và cho phép triển khai nâng cấp từng phần.
  
