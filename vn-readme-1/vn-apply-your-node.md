---
description: >-
  Sau khi full node hoạt động, bạn cần đăng ký để nó đủ điều kiện trở thành
  Masternode.
---

# Apply Your Node

Masternode sẽ nhận được một lượng lớn phần thưởng block, có khả năng vượt quá chi phí vận hành cơ sở hạ tầng. Tuy nhiên, để chạy được Masternode, bạn cần có VIC khởi điểm ít nhất 50.000 VIC và stake chúng trong thời gian dài. Hơn nữa, sau khoản tiền gửi ban đầu để trở thành Validator, nếu fullnode của bạn không nằm trong top 150 Masternode nắm giữ/uỷ thác nhiều VIC nhất, nó sẽ không được thăng cấp thành Masternode và không nhận được phần thưởng. Do đó, các Ứng viên được khuyến khích làm mọi cách có thể nhằm hỗ trợ Viction lọt vào top 150 ứng viên được bầu chọn nhiều nhất.

### Yêu cầu <a href="#requirements" id="requirements"></a>

Để có một Ứng viên Masternode, các yêu cầu sau đây phải được đáp ứng:

* Người nắm giữ token phải có một node đang hoạt động - tham khảo cách chạy node [tại đây](run-a-full-node/)
* Người nắm giữ token phải nắm giữ một lượng token tối thiểu theo yêu cầu (50,000 VIC). 50,000 VIC này được gửi vào Hợp đồng Thông minh bầu chọn.
* Phải nằm trong top 150 Ứng viên Masternode được uỷ thác nhiều nhất trong hệ thống. Việc voting của những người nắm giữ token được tính thông qua một Dapp bầu chọn cho phép những người nắm giữ token gửi VIC thông qua cơ chế hợp đồng thông minh.

### Đăng ký trở thành Masternode <a href="#applying-to-become-a-masternode" id="applying-to-become-a-masternode"></a>

Bạn có thể đăng ký để trở thành Masternode bằng cách truy cập [VicMaster](https://vicmaster.xyz/). Kết nối ví có số tiền bạn muốn gửi.

{% hint style="danger" %}
Lưu ý

Ví thực hiện khoản tiền gửi ban đầu sẽ là ví nhận phần thưởng block.
{% endhint %}

Ở góc trên cùng bên phải, nhấp vào **Become a Candidate**.

Nhập số lượng VIC bạn muốn gửi (tối thiểu 50,000).

Nhập địa chỉ ví [coinbase ](https://docs.viction.xyz/faq/masternode-and-voting/masternode#what-is-the-coinbase-address)của bạn. Đây là địa chỉ của tài khoản mà Masternode của bạn đang sử dụng. Nếu đang chạy node với `tmn`, bạn chỉ cần chạy lệnh `tmn inspect` để lấy địa chỉ này.

{% hint style="warning" %}
Lưu ý quan trọng:

Vì lý do bảo mật, chúng tôi khuyên bạn nên sử dụng một địa chỉ ví mới cho Masternode / địa chỉ coinbase. Đây không phải là tài khoản sẽ nhận phần thưởng. Phần thưởng được gửi đến tài khoản sẽ thực hiện khoản tiền gửi ban đầu 50,000 VIC.
{% endhint %}

Xác nhận bằng cách đăng kí trở thành Masternode và tiến hành thanh toán.

Full node của bạn sẽ được hiện trên VicMaster. Mọi người có thể theo dõi chi tiết và bầu chọn/uỷ thác cho nó.

Một full node trở thành Masternode khi nó thuộc top 150 full node được bình chọn/uỷ thác VIC nhiều nhất trong mỗi epoch.

{% hint style="info" %}
Lưu ý:

Epoch là một khoảng thời gian gồm 900 block (\~ 30 phút) bắt đầu từ block #1.
{% endhint %}

Nếu node của bạn nằm trong top 150 Ứng viên được bình chọn/uỷ thác nhiều nhất tại checkpoint giữa hai epoch, nó sẽ được thăng cấp thành Masternode và bắt đầu tham gia vào việc tạo block ở epoch tiếp theo.

### Về việc dừng vận hành Masternode <a href="#resigning-your-masternode" id="resigning-your-masternode"></a>

Trong trường hợp bạn không muốn vận hành Masternode của mình, trước tiên bạn cần thoát khỏi hệ thống quản trị để lấy lại số tiền bị khóa. Truy cập VicMaster, vào trang Candidate detail và nhấp vào nút **Resign**. Số tiền của bạn có để rút được sau 30 ngày kể từ khi dừng vận hành Masternode (1.296.000 block).

Sau khi dừng vận hành Masternode thành công, bạn có thể dừng node của mình. Nếu bạn chạy với `tmn`, chỉ cần chạy lệnh:

`tmn remove`

Lúc này, bạn đã dừng Masternode của bạn.
