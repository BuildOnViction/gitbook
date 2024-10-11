---
description: >-
  Slashing Masternode là cơ chế áp dụng “hình phạt” nhằm đảm bảo hiệu quả hoạt
  động của mạng lưới
---

# Viction Slashing Mechanism

Slashing v2.0 là cơ chế xử phạt các Masternode không tạo ra bất kỳ block nào trong một Epoch, gây ra sự chậm trễ 10 giây cho mạng lưới mỗi khi đến lượt masternode này. Một Masternode bị Slash sẽ không nhận được phần thưởng trong 5 Epoch tiếp theo.

{% hint style="info" %}
Lưu ý: Masternode bị Slash vẫn có thể ký xác nhận giao dịch nếu đang online, nhưng sẽ không nhận được phần thưởng cho đến khi việc Slash hết hiệu lực.
{% endhint %}

Sau 5 Epoch bị Slash, Masternode sẽ được hệ thống phân tích và cho phép quay trở lại mạng lưới. Nếu Masternode bị slashed đã ký bất kỳ giao dịch nào trong Epoch gần nhất (cho thấy nó đã hoạt động trở lại), trạng thái Masternode được khôi phục và tiếp tục nhận được phần thưởng như bình thường. Ngược lại, nếu Masternode chưa ký bất kỳ giao dịch nào trong Epoch gần nhất thì sẽ tiếp tục bị slashed trong vòng 5 Epoch tiếp theo. Điều này xảy ra cho đến khi node hoạt động trở lại hoặc bị loại khỏi nhóm 150 validator được bình chọn nhiều nhất.

Nguyên nhân dẫn đến Slash có thể do Masternode không sử dụng đúng phần mềm Viction, thiếu bộ nhớ hoặc Masternode bị lỗi do thiếu bảo trì bởi chủ sở hữu Masternode.

{% hint style="info" %}
Trên VicMaster, nhấp vào một ứng viên (candidate) để truy cập vào trang của ứng viên này. Cuộn xuống đến ‘Masternode Rewards’. Xem xét ‘Sign number’ và ‘Slashing history’ trong phần Masternode Rewards để xác định node tốt hay xấu.
{% endhint %}

Masternode có thể ký tối đa 60 block mỗi Epoch. Một Masternode tốt sẽ tạo khoảng 60 giao dịch ký xác nhận giao dịch trong Epoch đó. Phần thưởng cũng được tính toán dựa trên số lượng giao dịch đã ký.
