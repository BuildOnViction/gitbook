# Masternodes

### **Viction có các Masternode không? Chúng làm việc như thế nào?**

Có, Viction có tối đa 150 Masternode tuân theo cơ chế Proof of Stake Voting (POSV) cho phép phí giao dịch thấp và thời gian xác nhận giao dịch ngay lập tức. Masternode tạo, xác minh và xác thực các block mới trên Viction blockchain.

* **Ứng viên Masternode (Masternode Candidates)**: Bất kỳ tài khoản nào cũng có thể gửi 50.000 VIC sử dụng VicMaster để trở thành Ứng viên Masternode. Một ứng viên có thể huỷ yêu cầu trở thành Masternode, nhưng VIC sẽ bị khóa trong 30 ngày tiếp theo (1.296.000 block) sau khi từ bỏ.
* **Trở thành Masternode**: Ứng viên trở thành Masternode khi thuộc top 150 Ứng viên được bầu chọn nhiều nhất mỗi epoch. Người đã trở thành Masternode vẫn có thể huỷ vai trò của mình, nhưng token sẽ bị khóa trong 30 ngày tiếp theo sau khi từ bỏ.
* **Phần thưởng**: Phần thưởng mà Masternode nhận được trong mỗi epoch tỷ lệ thuận với số lượng chữ ký.

Các Viction Masternode bắt đầu ký các block và nhận phần thưởng block khi Mainnet phát hành vào ngày 14 tháng 12 năm 2018.

### **Masternode trong hệ sinh thái Viction là gì?**

Masternode Viction là một máy chủ sử dụng công suất tính toán nhằm đóng góp cho mạng lưới. Nhiệm vụ của nó là tạo và ký các block. Đổi lại các Masternode sẽ nhận được phần thưởng dưới dạng VIC.

Các Masternode được bầu chọn theo cơ chế đồng thuận PoSV (PoSV consensus) thông qua Dapp quản trị VicMaster (governance Dapp Vicmaster) của chúng tôi.

### **Lợi ích từ việc chạy Masternode là gì?**

Masternode đóng góp vào mạng lưới và nhận được phần thưởng block đáng kể cho nhiệm vụ này. Phần thưởng này dự kiến sẽ vượt quá chi phí vận hành cơ sở hạ tầng. Tuy nhiên, chủ sở hữu Masternode cần đầu tư vào Viction bằng cách gửi tối thiểu 50.000 VIC và stake chúng trong thời gian dài.

Sau lần gửi tiền đầu tiên, nếu tài khoản không trở thành Masternode (có ít lượt bầu chọn hơn 150 Ứng viên được bầu chọn nhiều nhất) thì tài khoản đó sẽ không nhận được phần thưởng. Vì vậy, các Ứng viên được khuyến khích nỗ lực hết mình nhằm thể hiện khả năng hỗ trợ Viction lọt vào top 150 Ứng viên được bầu chọn nhiều nhất.

### **Vì sao chọn 150 Masternode? Vì sao lại tăng từ con số 99 ban đầu?**

Quyết định này dựa trên việc cân nhắc giữa tính phi tập trung và khả năng mở rộng của mạng lưới. Về mặt phi tập trung, 150 tốt hơn 99. Tuy nhiên, yếu tố quan trọng hơn là khả năng mở rộng. Chúng tôi cũng tăng số lượng Masternode để phù hợp hơn với giải pháp sharding trong tương lai.

Ngoài ra, 150 cũng là [Con số Dunbar](https://en.wikipedia.org/wiki/Dunbar's\_number)

### **Phần thưởng Masternode đến từ đâu? Chúng có đến từ sàn DEX không?**

Phần thưởng block sẽ đến từ nguồn dự trữ 17 triệu VIC trong 8 năm - điều này đã được quyết định kể từ genesis block. [Economics paper ](https://docs.google.com/document/d/197Cu57A6OYPoEQbrUVr067qNVEzP\_FEwaDCFff7hnlM/edit)của chúng tôi trình bày chi tiết con số này.

### **Phần thưởng Masternode được trả vào lúc nào?**

Người vận hành Masternode và người bầu chọn sẽ nhận được phần thưởng mỗi epoch. Một epoch được biểu thị là 900 block với block time là 2 giây (\~ 30 phút).

### **Cách để kiểm tra phần thưởng của tôi?**

Bạn có thể kiểm tra phần thưởng Masternode/staking của mình bằng Ví Viction. Ngoài ra, bạn có thể sử dụng VicMaster hoặc VicScan.

### **Các Masternode nhận được những phần thưởng gì?**

Mỗi epoch bao gồm 900 block, sẽ thưởng tổng cộng 250 VIC trong hai năm đầu tiên. Số tiền 250 VIC này được chia cho tất cả các Masternode theo tỷ lệ thuận với số lượng chữ ký mà họ ký trong epoch.

Ví dụ: Chỉ với 25 Masternode có hiệu suất bằng nhau, mỗi Masternode sẽ được thưởng 10 VIC. Với 125 Masternode, mỗi Masternode sẽ nhận được 2 VIC mỗi epoch.

Vui lòng tham khảo [Economics paper](https://docs.google.com/document/d/197Cu57A6OYPoEQbrUVr067qNVEzP\_FEwaDCFff7hnlM/edit) của chúng tôi để biết thêm chi tiết về phần thưởng Masternode.

### **Phần thưởng Masternode sẽ được phân chia như thế nào giữa cơ sở hạ tầng Masternode (node owner) và người bầu chọn?**

Tỷ lệ chia phần thưởng được thiết lập giữa những người nắm giữ token và các Masternode được bầu chọn để nhận được sự hỗ trợ từ họ. Tổng phần thưởng đạt được của mỗi Masternode sẽ được chia thành ba phần:

* **Phần thưởng Cơ sở hạ tầng (Infrastructure Reward):** 40% đầu tiên thuộc về người vận hành Masternode. Đây là khoản chi phí để duy trì hoạt động của Masternode.
* **Phần thưởng Staking (Staking Reward):** 50% thứ hai được đưa vào nhóm những người staking cho Masternode đó. Số VIC này được chia tỷ lệ thuận với lượng token stake của mỗi người. Bản thân Masternode cũng nhận được phần thưởng theo tỷ lệ cho khoản 50K VIC ban đầu của mình.
* **Phần thưởng Quỹ hội (Foundation Reward):** 10% cuối cùng được chuyển đến một tài khoản đặc biệt do Quỹ hội Masternode kiểm soát. Quỹ hội Masternode do công ty Viction điều hành trong giai đoạn đầu.

### **Lợi nhuận đầu tư ROI dự kiến cho Masternode và các Staker là bao nhiêu?**

Phần thưởng cho mỗi Masternode sẽ thay đổi linh hoạt và phụ thuộc vào nhiều yếu tố như: số lượng Masternode trong mạng lưới, hiệu quả ký block, tổng số lượt bầu chọn mỗi Masternode.

Vui lòng tham khảo [Economics paper ](https://docs.google.com/document/d/197Cu57A6OYPoEQbrUVr067qNVEzP\_FEwaDCFff7hnlM/edit)của chúng tôi để biết thêm chi tiết về phần thưởng Masternode. Tài liệu phân tích 3 tình huống có thể xảy ra với 50, 100 và 150 Masternode; và số lượt bầu chọn tổng thể khác nhau.

Dưới đây là một ví dụ.

**Tình huống:** 150 Masternode; 12,5 triệu token bầu chọn (tổng cộng 20 triệu token bị khóa).

Phần thưởng đạt được mỗi epoch (900 block):

* `Masternode = 0,6667 VIC`
* `Người bầu chọn với 1 nghìn VIC được stake = 0,00625 VIC`

Phần thưởng ước tính đạt được mỗi tuần:

* `Masternode = 224 VIC`
* `Người bầu chọn với 1 nghìn VIC được stake = 2,1 VIC`

Phần thưởng ước tính đạt được mỗi năm:

* `Masternode = 11.680 VIC`
* `Người bầu chọn với 1 nghìn VIC được stake = 109,5 VIC (10,95% hàng năm)`
* `Người bầu chọn với 50 nghìn VIC được stake = 5.475 VIC`
* `Tổng phần thưởng cho một Masternode với khoản gửi 50 nghìn VIC: 11.680 + 5.475 = 17.155 VIC (34,31% hàng năm)`

## **Ứng viên Masternode (Masternode Candidate)**

### **Ứng viên Masternode là gì? Sự khác biệt giữa Ứng viên Masternode và Masternode là gì?**

Ứng viên Masternode là bất kỳ chủ sở hữu node nào đặt 50.000 VIC để được liệt kê trên [VicMaster.](https://vicmaster.xyz/)

Một Ứng viên chỉ trở thành Masternode khi lọt top 150 Ứng viên Masternode được bầu chọn nhiều nhất mỗi epoch. Chỉ những Masternode được bầu chọn này mới có thể ký các block và nhận được phần thưởng block.

### **Làm thế nào để trở thành Masternode?**

Bước đầu tiên để trở thành Masternode là trở thành Ứng viên Masternode. Để trở thành Ứng viên Masternode, bạn cần:

* Chạy phần mềm Viction trên máy tính có đáp ứng yêu cầu phần cứng tối thiểu nhất định
* Đặt 50.000 VIC vào hợp đồng thông minh thông qua VicMaster

Danh sách Ứng viên Masternode sẽ có sẵn trên Dapp quản trị, [VicMaster.](https://vicmaster.xyz/) Bước tiếp theo là được bầu chọn để trở thành 150 Ứng viên với số bầu chọn nhiều nhất.

### **Tôi có cần dùng máy tính của mình để chạy một node không?**

Chúng tôi đề xuất bạn sử dụng nhà cung cấp IaaS ("đám mây") theo lựa chọn của mình (như Amazon AWS, Digital Ocean, Google Cloud GCE, Vultr, v.v.). Máy chủ phải được kết nối internet trực tiếp (địa chỉ IP công khai, không có NAT) và hoạt động liên tục 100%.

Nếu bạn có sẵn một môi trường sản xuất khác ngoài nhà cung cấp đám mây, vui lòng chia sẻ thêm chi tiết trên [Github](https://github.com/BuildOnViction) của chúng tôi.

### **Yêu cầu phần cứng để chạy một node là gì?**

Xử lý giao dịch chủ yếu phụ thuộc vào CPU. Do đó, chúng tôi đề xuất bạn dùng các máy chủ được tối ưu hóa CPU.

* Kết nối internet trực tiếp (IP công khai, không có NAT)
* CPU 16 nhân
* RAM 32GB
* Bộ nhớ SSD

Chúng tôi đề xuất bạn sử dụng các nhà cung cấp dịch vụ đám mây phổ biến vì độ tin cậy và thời gian hoạt động của họ gần như 100%. Những máy chủ này sẽ là điểm khởi đầu tốt:

* **DigitalOcean:** Droplet được tối ưu hóa CPU 32GB/16CPU
* **Amazon EC2**: Instance C5
* **Google Cloud Engine**: n1-highcpu-16

Thiết lập một Ứng viên Masternode trên máy yếu hơn có thể dẫn đến hiệu suất kém, ảnh hưởng đáng kể đến phần thưởng của chủ sở hữu và hiệu suất của chuỗi.

**Lưu ý**: Nếu bạn đang chạy một node trong Testnet, 2CPU/8GB RAM là đủ.

### **Làm thế nào để các Ứng viên Masternode trở thành Masternode?**

Khi đã là Ứng viên Masternode, bạn cần có sự hỗ trợ của cộng đồng Viction dưới hình thức bầu chọn. 150 Ứng viên được bầu chọn nhiều nhất trong mỗi giai đoạn, được gọi là một epoch (900 block, thời gian block 2 giây), sẽ được thăng cấp lên thành các Masternode. Danh sách này sẽ thay đổi linh hoạt theo từng epoch. Chỉ 150 Masternode được chọn mới có thể ký các block và nhận được phần thưởng dưới dạng VIC.

### **Tôi có thể tìm hướng dẫn Masternode mới nhất hoặc hướng dẫn thiết lập Masternode ở đâu?**

Tìm thêm thông tin chi tiết về tmn [tại đây](../../vn-readme-1/run-a-full-node/create-a-viction-masternode.md)

### **Lệnh chạy full node với 'tmn'?**

`tmn start --name node_name --net mainnet --pkey your_private_key`

Tôi đã cài đặt tmn nhưng không tìm thấy trong đường dẫn.

Xem [tại đây](https://docs.viction.xyz/masternode/run-a-full-node/create-a-viction-masternode)

\*\*Tôi đã dừng node bằng tmn stop nhưng tmn status vẫn hiển thị đang chạy. \*\*

Bạn có thể chạy `tmn --debug stop` và gửi nhật ký cho chúng tôi. Chúng tôi sẽ giúp bạn điều tra vấn đề.

### **Tôi có cần hai ví để chạy Masternode không?**

Vì lý do bảo mật, nên dùng hai ví. Bạn có thể tạo ví của mình ở bất cứ đâu, nhưng quy tắc duy nhất là bạn cần hai ví. Một cho Masternode và một ví để gửi 50K (tài khoản này sẽ nhận được phần thưởng).

### **'Địa chỉ Coinbase' là gì?**

'Địa chỉ Coinbase' là địa chỉ công khai được sử dụng để chạy node của bạn và đăng ký nó vào hệ thống.

Chúng tôi đề xuất bạn sử dụng hai địa chỉ khi chạy các node. Địa chỉ công khai hoặc 'địa chỉ Coinbase' sẽ chỉ nhận phí giao dịch. Địa chỉ riêng tư là nơi bạn gửi 50K VIC ban đầu và là nơi phần thưởng block sẽ được tích luỹ.

{% hint style="info" %}
Tóm lại chúng ta cần 2 địa chỉ ví. **Địa chỉ Ví A** được sử dụng để ký block trong full node đã được thiết lập. **Địa chỉ Ví B** chứa 50K VIC để đăng nhập vào **VIC Master** & stake số VIC này để đề xuất full node trở thành master node. Chúng tôi sẽ nhập **địa chỉ ví A** vào trường **địa chỉ oinbase** trong cửa sổ bật lên "**Trở thành Ứng viên**"
{% endhint %}

### **Tôi nhận thấy rằng chúng tôi cần một ví khác cho Masternode với cụm từ ghi nhớ khác. Giả sử chúng ta sử dụng một ví cứng, chúng ta sẽ cần một ví cứng khác với cụm từ ghi nhớ khác?**

Bạn nên sử dụng một tài khoản trống riêng cho Masternode của mình vì nó chỉ nhận phí giao dịch - chúng tôi gọi là địa chỉ công khai hoặc 'địa chỉ coinbase' trong tài liệu.

Phần thưởng block được gửi đến tài khoản được kết nối với VicMaster đã thực hiện khoản tiền gửi ban đầu - địa chỉ 'riêng tư'.

### **Tôi có thể sử dụng cùng một cặp địa chỉ (địa chỉ công khai tmn + địa chỉ gửi tiền ban đầu) cho tất cả các node của mình không? Hoặc tôi phải chuyển mã thông báo sang ví khác và bắt đầu node thứ hai?**

Không. Bạn phải sử dụng các địa chỉ 'coinbase' công khai khác nhau. Nhưng bạn có thể sử dụng cùng một địa chỉ gửi tiền ban đầu ('riêng tư'), khi đó tất cả phần thưởng sẽ được chuyển đến một địa chỉ duy nhất.

### **Tôi đã hoàn thành tất cả các bước thiết lập một node. Tại sao tôi không tìm thấy node của mình trên VicMaster?**

Bạn phải đăng ký để trở thành Ứng viên Masternode trên [VicMaster](https://vicmaster.xyz/)

### **Tôi có cần gửi 50K VIC trước hay sau khi chạy 'tmn' trong VPS không?**

Sau đó. Node của bạn phải được đồng bộ hóa hoàn toàn trước khi đăng ký.

### **Làm cách nào để kiểm tra trạng thái đồng bộ hóa blockchain từ node?**

Bạn có thể xem nhật ký (log) của node nhưng cách dễ dàng hơn là sử dụng trang web [VICStats](https://stats.viction.xyz/) hoặc lệnh gọi eth.blockNumber API của nó.

### **Nếu chủ sở hữu Masternode gửi 60K VIC thay vì 50K trên node của mình, họ có thể rút số dư 10K VIC sau này không?**

Có thể.

### **Cách để đổi tên node là gì?**

Bạn có thể thực hiện việc này trên VicMaster. Truy cập vào trang Masternode của bạn trên VicMaster, nếu bạn đã đăng nhập VicMaster bằng tài khoản chủ sở hữu, bạn có thể nhấp vào nút bên cạnh tên Masternode để chỉnh sửa thông tin.

### **Nếu trạng thái node của tôi là 'Đề xuất', ở checkpoint tiếp theo nó có thay đổi trạng thái không?**

Có, nếu bạn nằm trong top 150 Masternode được bầu chọn nhiều nhất.

### **Tại sao một node được đánh dấu 'Slashed'?**

Với Slashing v2.0, một Masternode không tạo bất kỳ block nào trong một epoch, do đó làm chậm mạng 10 giây tại mỗi lượt của nó sẽ bị phạt (không có phần thưởng) trong 5 epoch tiếp theo.

Lưu ý: một Masternode bị Slashed vẫn có thể ký các giao dịch trực tuyến nhưng sẽ không nhận được phần thưởng khi làm như vậy.

Sau khi bị Slashed trong 5 epoch, Masternode sẽ được phân tích để quay trở lại. Nếu Masternode bị Slashed đã ký bất kỳ giao dịch nào trong epoch cuối cùng (nghĩa là nó đã hoạt động trở lại), nó sẽ trở lại trạng thái Masternode và nhận phần thưởng bình thường. Nếu không, nó sẽ bị Slashed thêm 5 epoch nữa. Điều này có thể xảy ra miễn là node chưa hoạt động trở lại hoặc bị loại khỏi top 150.

Một số lý do khiến bị Slashed có thể là do Masternode không có phần mềm Viction chính xác, thiếu bộ nhớ hoặc Masternode bị sập do thiếu bảo trì và vận hành của chủ sở hữu Masternode.

### **Làm thế nào để cập nhật Masternode lên phiên bản mới nhất?**

Chạy lệnh này: `pip3 install -U tmn && tmn update && tmn start`

### **Số lượng Node được phép chạy?**

Bạn có thể chạy nhiều node tùy ý.

### **Làm thế nào để tôi từ bỏ Masternode?**

Nếu bạn không muốn duy trì Masternode nữa, bạn có thể từ bỏ trên VicMaster. Masternode của bạn sẽ ngừng tạo phần thưởng và số tiền gửi của bạn sẽ bị khóa trong 30 ngày (1.296.000 block). Sau thời gian khóa, bạn sẽ có thể rút lại 50.000 VIC của mình.

### **Tôi có thể đóng hoàn toàn node, sau đó khởi động lại một node hoàn toàn mới với địa chỉ Coinbase hoàn toàn riêng biệt mà không bị phạt không?**

Không. Node cũ của bạn sẽ bị phạt (50K tiền gửi ban đầu bị khóa 30 ngày) và phải đăng ký lại node mới.

### **Liệu có thể di chuyển một Masternode sau đó, chẳng hạn như sao lưu và khởi động từ một địa chỉ IP khác?**

Có thể.

### **Nếu không đủ VIC cho một Masternode, tôi có thể stake VIC của mình không?**

Có thể. Người nắm giữ token có thể stake VIC và nhận phần thưởng.

Để stake VIC, bạn cần bầu chọn cho các Ứng viên Masternode bằng cách gửi VIC đến từng địa chỉ bầu chọn riêng của ứng viên bằng cách sử dụng DApp quản trị chính thức VicMaster (governance Dapp VicMaster). 150 Ứng viên được bầu chọn nhiều nhất sẽ trở thành các Masternode. Người nắm giữ token cũng có thể hủy bầu chọn cho các Ứng viên, nhưng các token sẽ bị khóa trong 96 epoch / 8.640 block tiếp theo (khoảng 48 giờ) sau khi huỷ bầu chọn.

Tiền gửi token Masternode và tất cả các token được sử dụng để bầu chọn cho Masternode sẽ tham gia chương trình staking, và kiếm được phần thưởng block trong mỗi epoch, cộng với bất kỳ khoản phí nào. Các token được sử dụng để bầu chọn cho các Ứng viên không trở thành Masternode sẽ không nhận được phần thưởng staking.
