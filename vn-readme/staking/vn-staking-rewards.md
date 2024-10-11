# \[VN] Staking Rewards

## Lịch trình Phát hành Token

* **Theo cam kết ban đầu lúc gọi vốn**: Tổng số lượng token tại genesis block được lưu hành là 55 triệu token VIC; thêm 12 triệu token được dự trữ cho đội ngũ và sẽ được phân phối dần trong 4 năm; và 16 triệu token khác được dự trữ cho các đối tác chiến lược và được xem là một phần của quỹ xây dựng hệ sinh thái. Phần 17 triệu token được dự trữ làm phần thưởng block trong 8 năm. Số lượng token lưu hành vào cuối năm thứ 8 sau genesis block là 100 triệu token VIC.

> Sau mainnet: phần thưởng block năm thứ nhất và thứ hai là 4 triệu VIC hàng năm; phần thưởng block cho năm thứ 3, 4, 5 là 2 triệu VIC hàng năm; và phần thưởng block cho năm thứ 6, 7, và 8 là 1 triệu VIC hàng năm. Sau đó, phần thưởng block sẽ dừng hoặc kích hoạt ở mức không quá 1 triệu VIC hàng năm.

* **Thực hiện**: Mỗi epoch bao gồm 900 block, sẽ thưởng tổng cộng 250 VIC trong hai năm đầu tiên. 250 VIC sẽ được chia cho tất cả các Masternode tỷ lệ thuận với số chữ ký mà họ ký trong suốt epoch. Phần thưởng đạt được bởi mỗi Masternode sẽ được chia thành ba phần. Phần đầu tiên chiếm 40%, gọi là “Infrastructure Rewards,” sẽ thuộc về Masternode. Phần thứ hai chiếm 50%, gọi là “Staking Rewards,” sẽ dành cho người dùng đã stake VIC cho Masternode đó, chia theo tỷ lệ dựa trên số lượng token stake so với tổng số token stake. Phần cuối cùng chiếm 10%, gọi là “Foundation Reward,” sẽ dành cho Masternode Foundation, ban đầu được vận hành bởi Viction Lab Pte Ltd.
* **Tần suất Nhận Thưởng**: Cứ mỗi Epoch (khoảng 30 phút), người dùng đã stake VIC và các Masternode sẽ được nhận phần thưởng tự động.

## Công thức Tính lượng VIC thưởng

Để đơn giản hóa việc minh họa, giả sử:

* Tổng số VIC được staking cho tất cả các Masternode là bằng nhau
* Số lượng chữ ký của tất cả các Masternode trong các trường hợp là bằng nhau

Tất cả các Masternode nhận được cùng một phần thưởng được chia (R) và phần Infrastructure Reward giống nhau. Ngoài ra, phần thưởng cho Staker với 1.000 VIC được staking là bằng nhau bất kể họ vote cho Masternode nào.

### Trường hợp 1: 50 Masternode, tổng 2,5 triệu VIC được staked, tổng cộng 5 triệu VIC bị khóa\*\*

**Phần thưởng mỗi Epoch:**

* Infrastructure Reward Masternode = 0,4 \* 5 = 2 VIC
* Dành cho người dùng stake 1k VIC = (0,5 \* 5 \* 1000) / 100k = 0,025 VIC
* Phần thưởng staking MN với 50k VIC được stake = 50 \* 0,025 = 1,25 VIC

**Phần thưởng mỗi tuần:**

* Phần thưởng cơ sở hạ tầng MN = 336 \* 2 = 672 VIC
* Dành cho Người bầu chọn với 1k lượt bầu chọn = 336 \* 0,025 = 8,4 VIC
* Phần thưởng staking MN 50k VIC được gửi vào = 336 \* 1,25 = 420 VIC

**Phần thưởng mỗi năm:**

* Phần thưởng cơ sở hạ tầng MN = 17.520 \* 2 = 35.040 VIC
* Dành cho Người bầu chọn với 1k VIC được gửi vào = 17.520 \* 0,025 = 438 VIC
* Phần thưởng staking MN với 50k VIC được gửi vào = 17.520 \* 1,25 = 21.900 VIC
* Tổng phần thưởng cho mỗi MN với 50k VIC được gửi vào = 35.040 + 21.900 = 56.940 VIC

### Trường hợp 2: 100 Masternode, 3 triệu token được stake, tổng cộng 8 triệu token bị khóa.

**Phần thưởng mỗi epoch:**

* Phần thưởng cơ sở hạ tầng MN = 0,4 \* 2,5 = 1 VIC
* Dành cho người dùng stake 1k VIC = (0,5 \* 2,5 \* 1000) / 80k = 0,015625
* Phần thưởng staking MN với D = 50k VIC được gửi vào: 50 \* 0,015625 = 0,78125 VIC

**Phần thưởng mỗi tuần:**

* Phần thưởng cơ sở hạ tầng MN = 336 \* 1 = 336 VIC
* Dành cho người dùng stake 1k VIC = 336 \* 0,015625 = 5,25 VIC
* Phần thưởng staking MN với D = 50k VIC được gửi vào: 336 \* 0,78125 = 262,5 VIC

**Phần thưởng mỗi năm:**

* Phần thưởng cơ sở hạ tầng MN = 17.520 \* 1 = 17.520 VIC
* Dành cho người dùng stake 1k VIC = 17.520 \* 0,015625 = 273,75 VIC
* Phần thưởng staking MN với D = 50k VIC được gửi vào: 17.520 \* 0,78125 = 13.687,5 VIC
* Tổng phần thưởng trên mỗi MN với D = 50k VIC được gửi vào: 17.520 + 13 687,5 = 31.208 VIC

### Trường hợp 3: 150 Masternode, 12,5 triệu token được stake, tổng cộng 20 triệu token bị khóa.

**Phần thưởng mỗi epoch:**

* Phần thưởng cơ sở hạ tầng MN = 0,4 \* 1,6667 = 0,6667 VIC
* Dành cho người dùng stake 1k VIC = (0,5 \* 1,6667 \* 1000) / 133.333 = 0,00625 VIC
* Phần thưởng staking MN với 50k VIC được gửi vào: 50 \* 0,00625 = 0,3125 VIC

**Phần thưởng mỗi tuần:**

* Phần thưởng cơ sở hạ tầng MN = 336 \* 0,6667 = 224 VIC
* Dành cho người dùng stake 1k VIC = 336 \* 0,00625 = 2,1 VIC
* Phần thưởng staking MN với D = 50k VIC được gửi vào: 336 \* 0,3125 = 105 VIC

**Phần thưởng mỗi năm:**

* Phần thưởng cơ sở hạ tầng MN = 17520 \* 0,6667 = 11.680 VIC
* Dành cho người dùng stake 1k VIC = 17520 \* 0,00625 = 109,5 VIC
* Phần thưởng staking MN với D = 50k VIC được gửi vào: 17.520 \* 0,3125 = 5.475 VIC
* Tổng phần thưởng trên mỗi MN với D = 50k VIC được gửi vào: 11.680 + 5.475 = 17.155 VIC
