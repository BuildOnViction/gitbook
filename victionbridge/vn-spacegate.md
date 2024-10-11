# Spacegate

SpaceGate hỗ trợ người dùng chuyển tài sản từ blockchain này sang blockchain khác, đặc biệt là từ **TOMOE (mạng Ethereum) sang VIC (mạng Viction)**. Bạn có thể tìm hiểu thêm về TOMOE trong phần bên dưới.

Ngoài TOMOE, SpaceGate còn hỗ trợ các token khác như C98 (Coin98) và SAROS (Saros), với các mạng lưới chuyển đổi sau:

* TOMOE (Ethereum) -> VIC(Viction)
* C98 (BEP20) <> C98 (VRC25) <> C98 (ERC20)
* SAROS (VRC25) <> SAROS (SPL)

## **Cách chuyển đổi token trên SpaceGate?** <a href="#f27w4dkreqca" id="f27w4dkreqca"></a>

{% hint style="info" %}
* Để sử dụng cầu nối đa chuỗi, bạn cần phải trả một số loại phí như sau: phí giao thức, phí chuyển đổi (phí rút) và phí mạng (được tính bằng token gốc của mỗi blockchain, ví dụ BNB để chuyển đổi C98 Bep20 sang các token khác, ETH cho C98 ERC20, SOL cho C98 SPL và MATIC cho C98 PRC20). Vui lòng xem chi tiết hơn về phí [tại đây](https://docs.coin98.com/products/spacegate/faqs)
* Mỗi tài sản sẽ có giới hạn về số lượng token trong một lần giao dịch\
  \- Đối với C98, bạn có thể chuyển đổi tối thiểu **10 C98** và tối đa **50.000 C98** cho mỗi giao dịch. - Đối với VIC, bạn có thể chuyển đổi tối thiểu **10 VIC** và tối đa **5.000** VIC mỗi giao dịch.
{% endhint %}

Vui lòng tham khảo hướng dẫn chi tiết về cách giao dịch trên SpaceGate dưới đây:

{% embed url="https://docs.coin98.com/v/vn/san-pham/spacegate/huong-dan-chuyen-doi-tokens-tren-spacegate" %}

## TOMOE là gì?

VIC-wrapped ETH, hay còn gọi là TOMOE, là một token ERC20 được lưu trữ trên blockchain Ethereum và được neo bởi một lượng token VIC gốc (trên Viction blockchain) có giá trị tương đương. Nói cách khác, 1 TOMOE luôn luôn có giá trị bằng 1 VIC gốc.

{% hint style="info" %}
Địa chỉ hợp đồng TOMOE

[0x05d3606d5c81eb9b7b18530995ec9b29da05faba](https://etherscan.io/address/0x05d3606d5c81eb9b7b18530995ec9b29da05faba)
{% endhint %}

**Sự khác biệt giữa TOMOE và VIC?**

* VIC: Là token mặc định - được phát hành và sử dụng trên mạng lưới Viction.
* TOMOE: Là một token ERC20 được phát hành trên mạng lưới Ethereum. TOMOE có giá trị tương đương 1:1 với VIC.
* Để có trải nghiệm DeFi tốt nhất trên Viction, bạn nên chuyển đổi TOMOE > VIC.
