# Blockchain Platform Comparison

Tổng quan so sánh Blockchain: Viction, Ethereum, EOS, Cardano và Tendermint.

## Bitcoin, Ethereum và Blockchain

Công nghệ Blockchain, nền tảng của Bitcoin, đã phát triển trong hơn một thập kỷ qua và trở thành một trong những công nghệ đột phá và quan trọng nhất hiện nay, có khả năng tác động đến mọi ngành công nghiệp, từ tài chính đến sản xuất, chăm sóc sức khỏe và các tổ chức giáo dục. Ra mắt vào năm 2015 bởi Vitalik Buterin, Ethereum là nền tảng blockchain công khai đáng chú ý nhất sau Bitcoin. Ethereum cung cấp ngôn ngữ lập trình Turing hoàn chỉnh để viết các hợp đồng thông minh. Các hợp đồng này có thể được thực thi tự động dựa trên một bộ tiêu chí được thiết lập trên blockchain Ethereum.

Mặc dù đạt được đà phát triển mạnh mẽ và những lời hứa hẹn của Bitcoin và Ethereum, nhưng vẫn còn những vấn đề nội tại, đặc biệt liên quan đến hiệu suất xử lý giao dịch. Cả Bitcoin và Ethereum đều sử dụng Proof-of-Work (PoW) trong thuật toán đồng thuận của họ, đòi hỏi lượng sức mạnh tính toán khổng lồ để tạo ra một block. Mặt khác, Bitcoin và Ethereum hiện tại cung cấp hiệu suất xử lý giao dịch rất kém, chỉ khoảng 10 giao dịch mỗi giây, không thể so sánh với các hệ thống thanh toán điện tử truyền thống như VISA và MasterCard.

## Chuyển sang Proof-of-Stake thân thiện với môi trường hơn và hiệu quả hơn <a href="#e443" id="e443"></a>

Proof-of-Stake (PoS) nhằm mục đích cung cấp giao thức đồng thuận thân thiện với môi trường và hiệu quả hơn. Với PoS, người tạo ra block mới “[việc lựa chọn người tạo ra block mới hoạt động theo cách xác định trước, dựa trên khối lượng tài sản họ nắm giữ (stake)](https://steemkr.com/blockchain/@sheydboss/a-very-brief-history-of-blockchain-technology-everyone-should-read)”. Một số công ty ủng hộ đáng chú ý của sự thay đổi này là [EOS](https://eos.io/), [Ethereum Casper FFG](https://arxiv.org/pdf/1710.09437.pdf), [Cardano](https://www.cardano.org/en/home/), [Tendermint](https://tendermint.com/).

Các giải pháp blockchain này không chỉ cố gắng cung cấp các giải pháp tiết kiệm năng lượng và chi phí mà còn hứa hẹn giải quyết cả vấn đề hiệu suất của blockchain. Mặc dù có một số điểm tương đồng liên quan đến PoS giữa các blockchain này, nhưng vẫn còn nhiều điểm khác biệt cần được phân tích.

Trong bài viết này, chúng tôi sẽ chỉ ra cách Viction cạnh tranh với EOS, Ethereum, Cardano và Tendermint. Các khía cạnh được sử dụng để so sánh bao gồm giao thức đồng thuận, phi tập trung hóa, bảo mật, khả năng mở rộng/hiệu suất, lộ trình phát triển và hệ sinh thái.

![](<../../.gitbook/assets/Platform Comparision.png>)

## Tổng quan về Viction <a href="#b088" id="b088"></a>

Ngành công nghiệp blockchain và cơ sở hạ tầng của Internet Giá trị (Internet of Value) đang được xây dựng nhanh chóng trên toàn cầu. Nhiều người cho rằng môi trường hiện tại khá giống với thời kỳ xây dựng Internet vào cuối những năm 90, với những người tiên phong và nhà sáng tạo cùng tập hợp lại để xây dựng một tương lai mới. Mục tiêu của Viction là trở thành một phần dẫn đầu của hiện tượng này bằng cách kết hợp liền mạch một hệ sinh thái các ứng dụng, với các token được mã hóa được sử dụng bởi hàng triệu người dùng chính thống và kiến trúc cơ sở hạ tầng blockchain độc đáo, cho phép thanh toán nhanh chóng, không quẹt thẻ và lưu trữ giá trị an toàn, phi tập trung và đáng tin cậy.

> Viction hướng đến việc trở thành một blockchain công khai tương thích với EVM về các ưu điểm sau: phí giao dịch thấp, thời gian xác nhận nhanh, xác thực kép (double validation) và tính ngẫu nhiên để đảm bảo bảo mật. Viction Labs hình dung một hệ sinh thái gồm các DApp khác nhau chạy trên cơ sở hạ tầng Viction blockchain.

Cụ thể, giải pháp của Viction giải quyết tắc nghẽn hiệu suất xử lý giao dịch trong Ethereum, cản trở việc áp dụng nó vào các ngành công nghiệp, đặc biệt là tài chính. Về chi tiết, Viction là một giao thức đồng thuận hiệu quả và được bảo mật, giải quyết các hạn chế chính sau của các blockchain cổ điển:

* _Hiệu quả: Hiệu suất xử lý nhỏ của Bitcoin và Ethereum cản trở nghiêm trọng việc áp dụng rộng rãi các loại tiền điện tử này._
* _Thời gian xác nhận:_ _Bitcoin mất trung bình 1 giờ để xác nhận một giao dịch vì việc xác nhận một Bitcoin block yêu cầu 5 block tiếp theo được tạo sau đó. Trong khi Ethereum sử dụng thời gian block nhỏ hơn, thời gian xác nhận trung bình vẫn tương đối cao, khoảng 13 phút. Những thời gian xác nhận lâu này cản trở nhiều ứng dụng quan trọng (đặc biệt là các ứng dụng hợp đồng thông minh)._
* _Tạo phân nhánh (fork): Vấn đề về chuỗi phân nhánh (fork) tiêu tốn năng lượng tính toán, thời gian và tạo ra các lỗ hổng tiềm ẩn cho các loại tấn công khác nhau._

[Theo tài liệu kỹ thuật](https://viction.xyz/files/technical-whitepaper-1.0.pdf), Viction đề xuất Proof-of-Stake Voting (PoSV) consensus, là một giao thức blockchain dựa trên PoS với cơ chế bầu chọn công bằng, đảm bảo bảo mật nghiêm ngặt và xác suất đồng đều. Giao thức đồng thuận này có những điểm mới chính sau:

* _Xác thực kép (Double Validation) để tăng cường bảo mật và giảm thiểu rủi ro tạo ra các phân nhánh (fork)._
* _Tính ngẫu nhiên để đảm bảo phân công lao động công bằng giữa các Masternode và ngăn chặn các cuộc tấn công bắt tay (handshaking attacks)._
* _Thời gian xác nhận nhanh và các điểm kiểm tra hiệu quả để đạt tính hoàn tất hoặc điều chỉnh lại_

## Tổng quan về EOS.IO <a href="#c0a8" id="c0a8"></a>

[Kiến trúc blockchain EOS.IO được thiết kế để cho phép chia tỷ lệ theo chiều dọc và chiều ngang của các ứng dụng phi tập trung](https://github.com/EOSIO/Documentation/blob/master/TechnicalWhitePaper.md). Nó đạt được điều này bằng cách tạo ra một cấu trúc như hệ điều hành, trên đó các ứng dụng có thể được xây dựng. EOS.IO cung cấp một nền tảng blockchain có khả năng mở rộng lên tới hàng triệu giao dịch mỗi giây, loại bỏ phí của người dùng và cho phép triển khai và bảo trì các ứng dụng Phi tập trung nhanh chóng và dễ dàng, trong một blockchain được quản trị. EOS.IO, do Daniel Larimer dẫn đầu, dựa vào giao thức đồng thuận Delegated Proof-of-Stake (DPoS), bắt nguồn từ Bitshares DPoS. Hiệu suất của nó hứa hẹn đạt đến hàng triệu giao dịch mỗi giây với một hệ sinh thái các DApp phong phú hoạt động trên nền tảng của nó.

## Tổng quan về Cardano <a href="#cda2" id="cda2"></a>

Cardano là dự án blockchain công khai và tiền điện tử phi tập trung, mã nguồn mở toàn phần đầu tiên dựa trên công trình nghiên cứu học thuật được bình duyệt và được triển khai bằng ngôn ngữ lập trình Haskell. Nó được phát triển bởi IOHK phối hợp với nhiều trường đại học. Cardano sử dụng giao thức đồng thuận Proof-of-Stake (PoS) an toàn, cụ thể là Ouroboros. Ouroboros được hỗ trợ bởi các nghiên cứu chuyên sâu và các công thức toán học vững chắc cùng các bằng chứng cung cấp độ tin cậy cao hơn về bảo mật và khả năng mở rộng. [Cardano hứa hẹn cho phép các nhà phát triển (developer) xây dựng các hợp đồng và ứng dụng phi tập trung, đồng thời chạy chúng trong một môi trường riêng tư, có thể mở rộng, hợp pháp, bảo mật và chi phí thấp](https://www.cryptomorrow.com/2017/10/10/is-cardano-better-than-ethereum/). Một mặt, Cardano Ouroboros hướng đến quyền riêng tư của người dùng. Mặt khác, nó cũng tính đến nhu cầu của các nhà quản lý để dễ dàng nâng cấp hệ thống. Do đó, Cardano tuyên bố là [giao thức đầu tiên cân bằng các yêu cầu này theo một cách tinh tế và hiệu quả, tiên phong cho một cách tiếp cận mới cho tiền điện tử.](https://cardanofoundation.org/protocol/#technological-innovation)

## Tổng quan về Tendermint <a href="#f783" id="f783"></a>

[Tendermint được thiết kế để trở thành một nền tảng blockchain dễ sử dụng, dễ hiểu, hiệu suất cao và hữu ích cho nhiều ứng dụng phân tán.](https://tendermint.readthedocs.io/projects/tools/en/master/introduction.html) Tendermint hướng đến việc sao chép an toàn và nhất quán một ứng dụng trên nhiều máy. Tính bảo mật nghĩa là Tendermint hoạt động ngay cả khi tối đa 1/3 số máy bị lỗi theo các cách tùy ý. Tính nhất quán nghĩa là mọi máy không bị lỗi đều nhìn thấy cùng một nhật ký giao dịch và tính toán cùng một trạng thái. Hai thuộc tính này đóng vai trò quan trọng trong khả năng chịu lỗi của nhiều ứng dụng, từ tiền tệ đến bầu cử, điều phối cơ sở hạ tầng và hơn thế nữa.

Tendermint bao gồm một bộ máy đồng thuận được gọi là Tendermint Core và một giao diện ứng dụng chung. Tendermint Core dựa vào PoS và [Hệ thống chịu lỗi Byzantine (BFT)](https://medium.com/loom-network/understanding-blockchain-fundamentals-part-1-byzantine-fault-tolerance-245f46fe8419) để đảm bảo mọi máy lưu trữ các giao dịch giống nhau theo cùng một thứ tự. Mặt khác, giao diện ứng dụng cho phép xử lý các giao dịch bằng bất kỳ ngôn ngữ lập trình nào. Do đó, các nhà phát triển (developer) có thể sử dụng Tendermint để sao chép trạng thái của máy trạng thái BFT cho các ứng dụng được viết bằng bất kỳ ngôn ngữ lập trình và môi trường phát triển nào phù hợp với họ.

## Tiêu chí So sánh <a href="#id-4c41" id="id-4c41"></a>

### Thuật toán Đồng thuận <a href="#id-2ab4" id="id-2ab4"></a>

Thuật toán đồng thuận là cơ chế cốt lõi của bất kỳ tiền điện tử phi tập trung nào. Nó duy trì tính nhất quán, không thay đổi và bảo mật của blockchain trên tất cả các full node của hệ thống phi tập trung. Blockchain Bitcoin với Proof-of-Work cung cấp tính bảo mật và phi tập trung nhưng khả năng mở rộng của nó lại hạn chế. Kể từ đó, nhiều giao thức đồng thuận đã được đề xuất để tận dụng. Các cơ chế này bao gồm nhiều biến thể của các giao thức đồng thuận dựa trên Proof-of-Stake được tìm thấy trong các dự án nói trên. Các giao thức này không chỉ nhằm mục đích giải quyết vấn đề lãng phí năng lượng của Bitcoin và Ethereum hiện tại mà còn nhằm cải thiện hiệu suất xử lý giao dịch.

### Phi tập trung <a href="#id-4da0" id="id-4da0"></a>

Một trong những sự thật khiến blockchain Bitcoin trở thành chủ đề được quan tâm lớn là tính phi tập trung của nó. Khác với các hệ thống tập trung hiện có và/hoặc những gì chúng ta gọi là "hệ thống phân tán đóng", Bitcoin hoạt động trên một hệ thống phi tập trung "mở" hoặc _"không cần cấp phép"_, nơi bất kỳ node nào cũng có thể tham gia và rời block mạng, và việc tham gia- rời block của các node trở thành \_"hoạt động hàng ngày" \_mà hệ thống phải xử lý. Bằng cách này, vấn đề điểm hỏng duy nhất tồn tại trong các hệ thống tập trung có thể được loại bỏ. Do đó, hệ thống càng phi tập trung thì khả năng khả dụng của dữ liệu và chịu lỗi càng cao.

### Bảo mật <a href="#bbcc" id="bbcc"></a>

Một trong những ứng dụng tiên phong và dễ thấy của blockchain là trong ngành tài chính. Tổng vốn hóa thị trường hiện tại của tiền điện tử là hơn 300 tỷ đô la Mỹ, điều này khuyến khích những kẻ xâm nhập hoặc tấn công hệ thống. Có nhiều loại tấn công vào các hệ thống này như chi tiêu trùng lặp, không có gì để mất, spam, DDoS và tấn công tầm xa. Các hệ thống tiền điện tử dựa trên blockchain không chỉ phải đối phó với những cuộc tấn công này mà còn phải đảm bảo tính ổn định của hệ thống, bao gồm cả tính an toàn và tính sống động.

### Khả năng mở rộng/Hiệu suất <a href="#id-55b8" id="id-55b8"></a>

Các công nghệ tài chính hiện nay như Visa và Master có thể xử lý hàng nghìn giao dịch mỗi giây, điều này chắc chắn vượt trội so với hiệu suất xử lý giao dịch kém của Bitcoin và Ethereum. Do đó, để các công nghệ blockchain này được áp dụng rộng rãi hơn trong ngành tài chính cũng như các ngành khác như logistics và sản xuất, thì công nghệ blockchain phải tận dụng khả năng mở rộng/hiệu suất của nó. Do đó, chúng tôi coi hiệu suất là một trong những tiêu chí then chốt để đánh giá sự thành công của một hệ thống blockchain.

### Lộ trình Phát triển <a href="#id-1d77" id="id-1d77"></a>

Nói chung, lộ trình phát triển công nghệ là một kỹ thuật lập kế hoạch linh hoạt để hỗ trợ lập kế hoạch chiến lược và dài hạn, bằng cách kết hợp các mục tiêu ngắn hạn và dài hạn với các giải pháp công nghệ cụ thể. Lộ trình phát triển là một trong những khía cạnh quan trọng để đánh giá tiềm năng cũng như tầm nhìn của một dự án.

### Hệ sinh thái <a href="#id-08c1" id="id-08c1"></a>

Tất cả các dự án blockchain được đề cập ở trên đều đang xây dựng cơ sở hạ tầng mà các DApp khác có thể được xây dựng trên đó. Cơ sở hạ tầng và sự hỗ trợ càng mạnh thì càng có nhiều DApp có thể dựa vào đó để tạo ra một hệ sinh thái mạnh mẽ. Hơn nữa, một hệ sinh thái các DApp mạnh mẽ sẽ thu hút nhiều người dùng hơn cho cơ sở hạ tầng, do đó thúc đẩy cải tiến và đòi hỏi sự phát triển của cơ sở hạ tầng nền tảng. Mỗi dự án blockchain ở trên đều cung cấp giao thức đồng thuận dựa trên PoS có thể xử lý hàng nghìn giao dịch mỗi giây, do đó hứa hẹn nhiều tiềm năng cho các DApp trong hệ sinh thái.
