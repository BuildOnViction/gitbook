# VicScan (Explorer)

## **Các câu hỏi chung**

### **VicScan là gì?**

[VicScan](https://vicscan.xyz/) là một trình khám phá block (block explorer) cho Viction. Nó khá giống với EtherScan được sử dụng trên mạng lưới Ethereum, nếu bạn đã quen thuộc với công cụ này.

VicScan cung cấp giao diện thân thiện để khám phá Viction blockchain. Từ góc nhìn của người dùng, VicScan mang lại tính minh bạch vì tất cả thông tin block, giao dịch, finality (tính hoàn tất), hợp đồng thông minh, Dapp và thông tin token đều được đọc từ Viction và hiển thị tại đây. Ngoài ra, VicScan cung cấp các hình ảnh trực quan kỹ thuật và số liệu hữu ích về hiệu suất của Viction, người nắm giữ token và các chức năng khác.

### **TxHash là gì? Làm thế nào để kiểm tra TxHash?**

TxHash là viết tắt của 'transaction hash' và còn được gọi là ID giao dịch.

Một ví dụ về TxHash: `0xedab9e59d4567e9ced8d61caefe20e1e2a3fe95cceaaeabc98466ef3f03c0eca`

Để kiểm tra TxHash, hãy thực hiện theo các bước sau:

Trên [VicScan](https://vicscan.xyz/), hãy đến thanh tìm kiếm với biểu tượng kính lúp. Dán transaction hash (TxHash) vào thanh tìm kiếm và nhấp vào biểu tượng hoặc nhấn NHẬP (ENTER). Chi tiết giao dịch của bạn sẽ hiển thị.

Ví dụ: [https:/vicscan.xyz/txs/0xedab9e59d4567e9ced8d61caefe20e1e2a3fe95cceaaeabc98466ef3f03c0eca](https://https/vicscan.xyz/txs/0xedab9e59d4567e9ced8d61caefe20e1e2a3fe95cceaaeabc98466ef3f03c0eca)

## Các tính năng

### [Trang chủ](https://https/vicscan.xyz/)

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-26 at 00.59.17.png" alt=""><figcaption></figcaption></figure>

Đây là trang chủ của VicScan. Giữa trang, bạn có thể tìm thấy một ô tìm kiếm cho phép bạn tìm bất cứ thứ gì theo địa chỉ của nó. Bên dưới ô tìm kiếm, một vài số liệu tổng hợp hiển thị tổng số tài khoản, token, hợp đồng và block.

### [Giao dịch](https://https/vicscan.xyz/txs) <a href="#transactions" id="transactions"></a>

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-26 at 01.01.08.png" alt=""><figcaption></figcaption></figure>

Khi tra cứu một giao dịch riêng lẻ, trang sẽ liệt kê các thông tin sau: - ID giao dịch. - Phương thức giao dịch . - Giao dịch chứa block. - Thời gian giao dịch. - Địa chỉ gửi giao dịch . - Địa chỉ nhận giao dịch - Số tiền giao dịch VIC. - Phí giao dịch.

### [Tài khoản](https://https/vicscan.xyz/accounts) <a href="#accounts" id="accounts"></a>

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-26 at 00.59.17 (1).png" alt=""><figcaption></figcaption></figure>

#### [Tất cả tài khoản](https://https/vicscan.xyz/accounts) <a href="#all-accounts" id="all-accounts"></a>

Tất cả các tài khoản tồn tại trên chuỗi. Trang liệt kê các thông tin sau: - Thứ hạng tài khoản. - Địa chỉ tài khoản. - Thẻ công khai - Số dư tài khoản VIC. - Tỷ lệ tổng cung - Số lượng giao dịch tài khoản.

#### [Tất cả Masternode](https://https/vicscan.xyz/masternodes) <a href="#all-masternodes" id="all-masternodes"></a>

Tất cả các tài khoản Masternode tồn tại trên chuỗi. Trang liệt kê các thông tin sau: - Thứ hạng tài khoản (dựa trên dung lượng) - Địa chỉ tài khoản. - Tên tài khoản. - Trạng thái tài khoản - Dung lượng tài khoản - Liên kết tài khoản với chủ sở hữu Masternode - Tài khoản được liên kết với block được ký mới nhất của Masternode.

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-26 at 01.03.30.png" alt=""><figcaption></figcaption></figure>

#### [Hợp đồng được kiểm chứng(Verified Contracts)](https://https/vicscan.xyz/contracts) <a href="#verified-contracts" id="verified-contracts"></a>

Trang VicScan cung cấp thông tin về tất cả các hợp đồng thông minh đã được kiểm chứng trên chuỗi Viction. Để được hiển thị ở đây, hợp đồng cần được chủ sở hữu chủ động xác minh thủ công. Các thông tin chi tiết được liệt kê bao gồm: Trang liệt kê các thông tin sau: - Thứ hạng tài khoản (sắp xếp theo số Txn) - Địa chỉ tài khoản. - Tên hợp đồng tài khoản. - Thẻ công khai - Số dư tài khoản tại VIC. - Số lượng giao dịch tài khoản. - Ngày xác minh hợp đồng tài khoản. - Trình biên dịch tài khoản

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-26 at 01.04.04.png" alt=""><figcaption></figcaption></figure>

### [Các Token](https://https/vicscan.xyz/tokens) <a href="#tokens" id="tokens"></a>

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-26 at 01.06.35.png" alt=""><figcaption></figcaption></figure>

Danh sách các token trên Viction bao gồm TRC20, TRC21 và TRC721 cùng với thông tin về các giao dịch chuyển token.

#### [Token VRC20/21/25](https://www.vicscan.xyz/tokens) <a href="#all-tokens" id="all-tokens"></a>

Đây là danh sách tất cả các token TRC20/21/25 đang hoạt động trên chuỗi Viction. Trang liệt kê các thông tin sau: - Thứ hạng token (dựa trên Vốn hóa thị trường) - Tên token - Loại token - Giá token - Thay đổi token trong 24h - khối lượng giao dịch của token trong 24 giờ - Vốn hóa thị trường token - Người nắm giữ token

#### [Token VRC721](https://www.vicscan.xyz/tokens/vrc721) <a href="#tokens-transfers" id="tokens-transfers"></a>

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-26 at 09.21.54.png" alt=""><figcaption></figcaption></figure>

VicScan cũng cung cấp thông tin về tất cả các token TRC721 trên chuỗi Viction. Trang này liệt kê các thông tin sau: - Thứ hạng token (dựa trên tổng số lượng token được chuyển trong 24h) - Tên token - Loại token - Tổng số lần chuyển token - Số lần chuyển token trong 24h - Người nắm giữ token - Tổng cung token

### [Các Block](https://https/vicscan.xyz/blocks) <a href="#blocks" id="blocks"></a>

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-26 at 09.24.51.png" alt=""><figcaption></figcaption></figure>

VicScan cung cấp danh sách tất cả các block trên Viction blockchain. Trang liệt kê các thông tin sau: - Chiều cao block (chỉ số). - Tuổi block. - Số giao dịch trong block. - Người tạo block. - Tổng gas sử dụng trong block. - tính hoàn tất.

#### Tính hoàn tất (Finality)

Phần trăm mạng lưới đã xác thực block này. Khi đạt 75%, block đã đạt đến trạng thái hoàn tất và được thêm vĩnh viễn vào chuỗi.

#### [Epoch](https://https/vicscan.xyz/epochs) <a href="#block" id="block"></a>

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-26 at 09.27.14.png" alt=""><figcaption></figcaption></figure>

Danh sách tất cả các epoch trên Viction. Trang liệt kê các thông tin sau: - Số epoch - Số block bắt đầu - Số block kết thúc - Thời gian epoch - Số lượng masternode - Số người bầu chọn - Số node bị slashed\\
