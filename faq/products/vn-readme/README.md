---
description: >-
  VicIssuer cung cấp giao diện người dùng thân thiện và cơ sở dữ liệu hạ tầng
  (back-end) để phát hành token VRC20 & VRC25 chỉ trong vài bước.
---

# VicIssuer

Dưới đây là một vài tính năng của VicIssuer:

* **Giao diện Thân thiện (User-Friendly Interface)**: Phát hành token VRC20 hoặc VRC25 chỉ trong vài bước đơn giản.
* **Không cần biết lập trình (No Coding Experience Required)**: Không cần kiến thức nền tảng về lập trình hợp đồng thông minh.
* **Tùy chỉnh Token (Token Customization Options)**: Tùy chỉnh tổng cung token, tên token và phí giao dịch tối thiểu thông qua giao diện của VicIssuer.

### **Các loại Token trên Viction**

Trước khi phát hành token, hãy đảm bảo bạn biết về các loại token khả dụng trên Viction và sự khác biệt giữa chúng.

**VRC20 (cũ):** VRC20 là một tiêu chuẩn token tương đương với ERC20 được xây dựng trên nền tảng Viction blockchain. Người nắm giữ token VRC20 cần phải nắm giữ một lượng nhỏ VIC để trả một lượng gas fee.

**VRC25**: VRC25 tạo ra trải nghiệm mượt mà cho người dùng bằng cách cho phép người nắm giữ token thanh toán phí giao dịch bằng chính token đó mà không cần phải giữ bất kỳ VIC nào trong ví của mình.

**Bảng so sánh**

|                                           | **VRC20**      | **VRC25**                                                                                      |
| ----------------------------------------- | -------------- | ---------------------------------------------------------------------------------------------- |
| **Yêu cầu Kỹ thuật để Tích hợp Dapp**     | **Thấp**       | **Vừa phải**                                                                                   |
| **Yêu cầu Kỹ thuật để Niêm yết trên Sàn** | **Thấp**       | **Vừa phải**                                                                                   |
| **Phí giao dịch**                         | **Native VIC** | <p><strong>Bằng chính token đang giao dịch</strong></p><p><strong>(Không cần VIC)</strong></p> |

### PHÁT HÀNH (ISSUE)

**Bước 1:** Truy cập [https://issuer.viction.xyz/](https://issuer.viction.xyz/) và nhấp vào **Issue New Token**.

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-26 at 00.41.26.png" alt=""><figcaption></figcaption></figure>

**Bước 2:** Đăng nhập vào ví của bạn.

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-26 at 00.44.53.png" alt=""><figcaption></figcaption></figure>

**Bước 3:** Điền thông tin token bao gồm Tên Token, Ký hiệu Token, Tổng cung Token, Số thập phân, Loại Token VRC20 (cũ) hoặc VRC25.

* Ký hiệu của token contract là ký hiệu hợp đồng token phải được biết đến, ví dụ: “MYT”. Tương đương với mã token và thường giới hạn trong 5 ký tự.
* Số thập phân đề cập đến mức độ chia hết của một token, từ 0 (hoàn toàn không chia hết) đến 18 hoặc thậm chí cao hơn tùy theo nhu cầu. Về mặt kỹ thuật, số thập phân là số chữ số xuất hiện sau dấu thập phân khi hiển thị giá trị của token.
* Để tìm hiểu sự khác biệt giữa các loại token có thể phát hành thêm/ không thể phát hành thêm, VRC20(cũ)/ VRC25, bạn có thể di chuột lên biểu tượng thông tin (i) và nhấp vào liên kết "Differences?".

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-26 at 00.50.40.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-26 at 00.51.13.png" alt=""><figcaption></figcaption></figure>

**Cảnh báo:** Phí phát hành token có thể thay đổi tùy thuộc vào chi phí triển khai hợp đồng thông minh.

**Bước 4:** VicIssuer sẽ yêu cầu xác nhận thông tin token. Vui lòng kiểm tra cẩn thận tất cả các tiêu chí trước khi nhấp vào "Phát hành token" và đợi hợp đồng được triển khai.

Đối với token VRC25, nếu bạn muốn xác minh và công bố mã nguồn hợp đồng trên VicScan, vui lòng sao chép mã nguồn từ phần **Xem lại Mã (Code Review)**. Bạn có thể tham khảo hướng dẫn [tại đây](broken-reference).

{% hint style="warning" %}
Nếu bạn không sao chép mã nguồn ở giai đoạn này, bạn sẽ không thể quay lại và sao chép sau đó.
{% endhint %}

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.41.56 (2).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** Bất kỳ nhà phát triển (developer) nào có kinh nghiệm phát triển và triển khai hợp đồng thông minh có thể tham khảo tài liệu tham khảo [Tiêu chuẩn & Đặc điểm Kỹ thuật](https://docs.viction.xyz/developer-guide/standards-and-specification) của chúng tôi để tùy chỉnh hợp đồng token đã triển khai.
{% endhint %}

### **CÁC BƯỚC DƯỚI ĐÂY CHỈ DÀNH CHO VRC25 TOKEN**

* **Bước 5:** Bạn sẽ nhận được thông báo khi token được phát hành thành công. Nhấp vào "Xem chi tiết" để kiểm tra tóm tắt của token bao gồm số lượng người nắm giữ, giao dịch, v.v. Đối với token VRC25, chọn **Áp dụng để thanh toán phí bằng token** \*\*(Apply to pay fee by token) \*\*cho tích hợp VIC ZeroGas.
* **Bước 6:** Sau khi được triển khai, người phát hành cần đồng ý rằng phí cho tất cả các giao dịch đến hợp đồng token vừa được triển khai sẽ được thanh toán bằng token đã phát hành. Sau khi các điều kiện được thỏa thuận, hãy chuyển sang bước tiếp theo bằng cách nhấp vào "Tôi hiểu".
* **Bước 7:** Người phát hành token cần đặt cọc tối thiểu 10 VIC. Số VIC này không thể được rút lại. VIC được giữ trong nhóm tiền ký quỹ sẽ được khấu trừ để trả cho các Masternode để xử lý giao dịch.
* **Bước 8:** Bây giờ, token VRC25 mới có thể được sử dụng. Bạn có thể chỉnh sửa phí giao dịch trong chính token. Bạn có thể thay đổi con số này bất kỳ lúc nào trong thời gian hoạt động của token.
* **Bước 9:** Trong bảng điều khiển quản lý token, có các node để tương tác với token, chẳng hạn như chuyển token và đặt cọc thêm VIC để thanh toán phí giao dịch sau này. Đừng quên thường xuyên kiểm tra số dư của tiền đặt cọc VRC25 vì các giao dịch sẽ không được xử lý nếu số dư còn lại không đủ để thanh toán phí giao dịch.

### **QUYÊN GÓP VIC ĐỂ TRẢ PHÍ GIAO DỊCH VRC25**

Nếu không đủ tiền VIC để thanh toán phí giao dịch sau này, bất kỳ người nắm giữ token nào cũng có thể gửi thêm VIC vào hợp đồng VicIssuer để tiếp tục thực hiện giao dịch.

Truy cập vào tab "**Quyên góp phí VRC-25**" \*\*(Donate VRC-25 fee) \*\*từ trang chủ của VicIssuer. Nhập tên của token để quyên góp VIC, sau đó nhập số tiền quyên góp. Lưu ý rằng phí giao dịch trong Viction gần như bằng 0, 1 VIC có thể hỗ trợ hàng nghìn giao dịch.

![](https://lh5.googleusercontent.com/PL-tz1-aPJlSOOaNlMBgj3He75quhYhHTv9DXzNAvlwlvfZ8iXD-XmznFiq7K5hFhtzqGP8GMBXcrvobrE8-MfNqtygA48BI7OnjY9DYY5v5Up1V9k0cd3QkkQfxTNG36VYWbdy3)
