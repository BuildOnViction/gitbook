# \[VN] PoSV Consensus

Viction sử dụng một phương thức đồng thuận gọi là Proof-of-Stake Voting (PoSV) khuyến khích tất cả người nắm giữ VIC tích cực tham gia staking trên mạng lưới có tổng cộng 150 Masternode.

## Tổng quan

Viction là một blockchain tương thích EVM được hỗ trợ bởi cơ chế đồng thuận Proof-of-Stake Voting (PoSV) có khả năng mở rộng, cho phép mọi hợp đồng thông minh tương thích với Ethereum xác nhận giao dịch gần như tức thời. 150 Masternode này bảo mật cho Viction blockchain và có các yêu cầu sau:

* Người nắm giữ token cần 50,000 VIC để chạy một Masternode
* Người nắm giữ token có thể bầu chọn/uỷ thác cho Masternode
* Full Node được có nắm giữ số lượng VIC nhiều nhất (thông qua bầu chọn/uỷ thác sẽ được chọn làm Masternode)
* Masternode tạo block theo round-robin và sử dụng xác thực kép (double validation) để ngăn chặn các hoạt động gian lận
* Masternode hoàn thành xác thực block sẽ được nhận thưởng bằng VIC

Một trong những tính năng chính quan trọng nhất của Viction là khả năng tăng hiệu suất hoạt động của blockchain với giao thức đồng thuận PoSV:

* Đạt ít nhất 2.000 TPS trong khi vẫn tăng cường bảo mật thông qua Xác thực kép (Double Validation)
* Block time 2 giây và mỗi giao dịch được xác nhận trong vòng 4 giây

## Xác thực kép (Double Validation)

Xác thực kép (double validation) cung cấp một lớp xác thực đáng tin cậy để nâng cao bảo mật thông qua tính phân tán ngẫu nhiên phân bố đồng đều. Cụ thể, khi một Masternode tạo ra một block, block đó phải được xác minh bởi một Masternode khác được chọn ngẫu nhiên trong số các Masternode trước khi được thêm vào blockchain. Xác thực kép (double validation) tăng cường bảo mật của Viction, giảm thiểu rủi ro chia tách chuỗi và các cuộc tấn công nothing-at-stake, giúp Viction bảo mật hơn so với các PoS blockchain khác.
