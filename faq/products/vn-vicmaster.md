# VicMaster

## **Tổng quan**

### **VicMaster là gì?**

[VicMaster](https://www.vicmaster.xyz/), Ứng dụng Quản trị Phi tập trung, cung cấp giao diện người dùng chuyên nghiệp liệt kê tất cả các Masternode và Ứng viên Masternode. Người dùng có thể bầu chọn cho Masternode, xem thống kê hiệu suất của Masternode và gửi 50K VIC để trở thành Ứng viên Masternode.

### **Làm thế nào để tôi đăng nhập VicMaster?**

Truy cập [VicMaster](https://www.vicmaster.xyz/). Nhấp vào "Đăng nhập" ở góc trên cùng bên phải. Sau đó chọn phương thức đăng nhập: Ví Viction, Ledger, Trezor, Metamask hoặc TrustWallet.

### **Công suất của Ứng viên Masternode/Masternode là gì?**

Công suất của một ứng viên bằng tiền gửi ban đầu 50K VIC cộng với tổng số VIC được bầu chọn cho ứng viên đó.

### **Con số nào trong những số này trên VicMaster sẽ cho chúng ta biết node nào hoạt động tốt và node nào hoạt động kém?**

Trên VicMaster, nhấp vào một ứng viên để mở trang chi tiết. Cuộn xuống ‘Phần thưởng Masternode’. Kiểm tra ‘Số lượng chữ ký’ và ‘Lịch sử Slashing’ để xác định đây có phải là một Masternode tốt hay không.

Masternode sẽ ký tối đa 60 block mỗi epoch. Một Masternode tốt sẽ tạo ra khoảng 60 giao dịch được ký trong epoch đó. Phần thưởng cũng được tính toán dựa trên số lượng giao dịch được ký.

### **Checkpoint là gì??**

Sau mỗi chu kỳ 900 block (gọi là epoch), một checkpoint block sẽ được tạo. Sau đó, phần thưởng được phân phát cho Masternode và Người bầu chọn. Masternode lần lượt theo thứ tự tuần tự để tạo block, xác minh tất cả các block được tạo trong epoch và đếm số chữ ký.

Lưu ý rằng những người nắm giữ token bầu chọn trước checkpoint block sẽ không nhận được bất kỳ phần thưởng nào khi phần thưởng staking được phân bổ.

### **Tôi muốn dừng chạy node của mình.**

Nếu bạn muốn ngừng chạy node của mình, trước tiên bạn cần từ bỏ (resign) quản trị để lấy lại số tiền bị khóa. Truy cập VicMaster, vào trang chi tiết ứng viên của bạn và nhấp vào nút từ bỏ `Resign`. Số tiền của bạn sẽ khả dụng để rút sau 30 ngày (1.296.000 block).

Sau khi từ bỏ (resign) thành công, bạn có thể dừng node của mình. Nếu bạn chạy nó với lệnh tmn, chỉ cần chạy:

```
tmn remove
```

Lúc này, Masternode của bạn đã được chấm dứt.

## Các tính năng

### Trạng thái mạng lưới

Trên VicMaster, khu vực này hiển thị cho bạn block hiện tại, thời gian block, số lượng block trong mỗi epoch và checkpoint tiếp theo (kết thúc epoch).

#### Danh sách ứng viên

Danh sách ứng viên bao gồm mọi Masternode có đủ token được gửi để chạy Masternode, cũng như những Masternode đã từ bỏ (resign) chạy Masternode. Một ứng viên được yêu cầu phải nằm trong top 150 ứng viên Masternode được bình chọn nhiều nhất trên danh sách này để trở thành Masternode và kiếm phần thưởng. Người bầu chọn có thể sử dụng danh sách này để giúp lựa chọn ứng viên Masternode mà họ muốn stake token của mình.

`Mẹo: bầu chọn cho ứng viên Masternode được bình chọn nhiều nhất có thể làm giảm phần thưởng của bạn vì phần thưởng dành cho người bầu chọn trên mỗi token tỷ lệ nghịch với số lượng token được stake cho một Masternode cụ thể.`

#### Bầu chọn

Người bầu chọn muốn stake token của họ cho một Masternode chỉ cần nhấp vào ‘Bình chọn’ trên Masternode tương ứng và làm theo hướng dẫn được cung cấp.

#### Huỷ bầu chọn

Nếu bạn không muốn hỗ trợ một Masternode mà mình đã bầu chọn, bạn có thể huỷ bầu chọn bằng cách nhấp vào nút Huỷ bầu chọn (Unvote) trên trang của Masternode và nhập số lượng VIC bạn muốn huỷ bầu chọn.

`Cảnh báo: Sau khi huỷ bầu chọn, VIC của bạn sẽ bị khóa trong hợp đồng thông minh trong 48 giờ trước khi bạn có thể rút.`

### [Ứng viên](https://vicmaster.xyz/candidate/0x3e3d98a26deef510b720967f4c4dbc88f308a994) <a href="#candidate" id="candidate"></a>

#### Thông tin tổng quan

Phía trên cùng của trang, bạn có thể tìm thấy thông tin tổng quan về một Ứng viên Masternode. Người bầu chọn có thể sử dụng thông tin này để hiểu rõ hơn về các Ứng viên Masternode mà họ dự định bầu chọn.

#### Các số liệu <a href="#metrics" id="metrics"></a>

Khu vực số liệu hiển thị hiệu suất của Masternode. Phần này hữu ích để xem liệu Ứng viên Masternode có hoạt động tốt hay không.

#### Phần thưởng <a href="#rewards" id="rewards"></a>

Phần phần thưởng hiển thị ước tính phần thưởng mà Masternode đã nhận được. Nếu Masternode nhận được ít phần thưởng hơn các Masternode khác, có thể có vấn đề về hiệu suất.

#### Người bầu chọn <a href="#voters" id="voters"></a>

Trong phần dành cho người bầu chọn, bạn có thể xem danh sách những người stake VIC đã bầu chọn cho ứng viên này.

#### Giao dịch <a href="#transactions" id="transactions"></a>

Trong phần này, bạn có thể xem tất cả các giao dịch của ứng viên này.

### [Người bầu chọn](https://vicmaster.xyz/voter/0x82d83629f48b690226af91547cbfbfc8a52b73e6) <a href="#voter" id="voter"></a>

#### Thông tin tổng quan <a href="#general-information_1" id="general-information_1"></a>

Trên trang này, bạn có thể tìm thấy thông tin tổng quan về những người bầu chọn cụ thể.

`Mẹo: Là người bầu chọn, hãy sử dụng trang này để đảm bảo bạn đang nhận được phần thưởng xứng đáng.`

#### Ứng viên <a href="#candidates" id="candidates"></a>

Phần ứng viên hiển thị tất cả các Ứng viên Masternode đã được người bầu chọn này bầu chọn.

#### Phần thưởng <a href="#rewards_1" id="rewards_1"></a>

Phần phần thưởng hiển thị phần thưởng mà người bầu chọn đã nhận được.

`Mẹo: Nếu bạn bầu chọn một lượng VIC bằng nhau cho các Masternode khác nhau và thấy một Masternode nào đó mang lại ít phần thưởng hơn, thì bạn có thể đã bầu chọn cho một Masternode có vấn đề về hiệu suất và nên cân nhắc thay đổi lượt bầu chọn của mình.`

#### Giao dịch <a href="#transactions_1" id="transactions_1"></a>

Phần này hiển thị tất cả các giao dịch của người bầu chọn.

### [Cài đặt](https://vicmaster.xyz/setting) <a href="#settings" id="settings"></a>

#### Nhà cung cấp Mạng lưới <a href="#network-provider" id="network-provider"></a>

Sử dụng cài đặt để chọn nhà cung cấp mạng lưới bạn đang sử dụng cho VicMaster (ví dụ: Metamask, Viction Testnet, Mạng lưới Tùy chỉnh).

#### Thông tin tài khoản

Phần này sẽ hiển thị cho bạn thông tin về địa chỉ công khai và số dư VIC của bạn.

### [Đăng ký](https://vicmaster.xyz/apply) <a href="#apply" id="apply"></a>

Trang web này được sử dụng bởi những người nắm giữ VIC muốn đăng ký để trở thành Ứng viên Masternode.

### Tìm kiếm <a href="#search" id="search"></a>

Ở đầu trang, bạn có thể tìm thấy thanh tìm kiếm. Bạn có thể sử dụng thanh này để tìm kiếm Ứng viên hoặc Người bầu chọn theo địa chỉ tương ứng.

`Mẹo: Tìm kiếm sẽ không hoạt động nếu đầu vào của bạn không phải là địa chỉ.`
