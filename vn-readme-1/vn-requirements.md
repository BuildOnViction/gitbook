---
description: Dưới đây là các yêu cầu cơ bản để chạy Masternode.
---

# Requirements

## Cấu hình phần cứng đề xuất

* Kết nối internet trực tiếp
* CPU 16 nhân
* RAM 32GB
* Ổ nhớ SSD dùng cho dữ liệu trên blockchain ([https://docs.viction.xyz/masternode/chain-data-snapshots](https://docs.viction.xyz/masternode/chain-data-snapshots))
* Yêu cầu tối thiểu: 1TB
* Yêu cầu đề xuất: 2TB trở lên

{% hint style="info" %}
**Lưu ý**

Nếu bạn đang chạy một node trong Testnet, RAM 2CPU/8GB là đủ
{% endhint %}

Chúng tôi khuyến nghị bạn nên sử dụng các nhà cung cấp dữ liệu đám mây phổ biến vì độ tin cậy và thời gian hoạt động liên tục. Bạn có thể bắt đầu với một vài server dưới đây:

* **DigitalOcean**: CPU được tối ưu hóa dạng droplet 32GB/16CPU
* **Amazon EC2**: C5 instance
* **Google Cloud Engine**: n1-highcpu-16

Việc thiết lập Masternode trên máy có cấu hình yếu hơn có thể dẫn đến hiệu suất kém, ảnh hưởng đáng kể đến hiệu suất mạng lưới và phần thưởng được trả về cho Masternode.

Nếu bạn có môi trường cấp sản xuất khác ngoài nhà cung cấp đám mây theo ý muốn, vui lòng trò chuyện trên [Gitter](https://gitter.im/Viction) cùng chúng tôi.

{% hint style="info" %}
**Một số thông tin cần thiết**

Masternode có một số nhiệm vụ nhất định cần xử lý (xác thực, tạo block, v.v.) theo thời gian. Masternode của bạn phải có khả năng xử lý tất cả các nhiệm vụ được chỉ định, ngược lại phần thưởng sẽ bị ảnh hưởng. Tuy nhiên, các thông số kỹ thuật vượt quá yêu cầu của Masternode sẽ không mang lại phần thưởng lớn hơn.
{% endhint %}

## Bảo trì Masternode <a href="#maintenance" id="maintenance"></a>

Tất cả các hệ thống CNTT đều yêu cầu bảo trì. Trách nhiệm của chủ sở hữu là bảo trì thường xuyên và node có đủ:

* Dung lượng ổ đĩa để lưu trữ dữ liệu blockchain mới
* Công suất xử lý giúp chuỗi luôn vận hành ở tốc độ tối ưu
* Giám sát để có thể phản ứng nhanh chóng khi có sự cố xảy ra
* Các biện pháp bảo mật như tường lửa, vá lỗi bảo mật hệ điều hành, SSH thông qua keypairs, v.v.

Ngoài ra chủ sở hữu cần đảm bảo các yếu tố khác (Mà không được liệt kê trong danh sách này)
