# How to Verify & Publish Contract Source Code on VicScan

## Phát hành Token trên VicIssuer

Để phát hành Token trên VicIssuer, hãy đảm bảo bạn đã hoàn thành các bước trước đó. Sau khi hoàn thành, hãy tiến hành bước cuối cùng được nêu dưới đây. Để biết thêm chi tiết, hãy tham khảo hướng dẫn [tại đây](https://github.com/DucDuongCoin98/Viction\_VI/blob/main/faq/products/vicissuer/README.md)

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.41.17.png" alt="" width="563"><figcaption></figcaption></figure>

Đảm bảo tất cả thông tin là chính xác, sau đó nhấp vào nút Phát hành Token (**Issue Token**). <mark style="color:yellow;">**Mã hợp đồng chỉ hiển thị ở bước này**</mark>. Do đó, bạn nên sao chép và lưu trữ mã nguồn vào tệp của mình. Bạn sẽ cần mã này để xác minh hợp đồng sau này.

{% hint style="warning" %}
**Nếu bạn không sao chép mã nguồn ở đây, sẽ không có cách nào để quay lại và sao chép lại.**
{% endhint %}

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.41.56 (1).png" alt="" width="563"><figcaption></figcaption></figure>

Cho phép kết nối với trang web, sau đó xác nhận việc triển khai hợp đồng mới thông qua cửa sổ bật lên ví. Sau khi hoàn tất, một cửa sổ bật lên thành công sẽ được hiển thị.

<div>

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.44.23.png" alt="" width="563"><figcaption></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.44.55 (1).png" alt=""><figcaption></figcaption></figure>

</div>

**Xem (View)** hợp đồng tại bảng điều khiển của **VicIssuer**. Nhấn vào địa chỉ hợp đồng để xem trên trình khám phá

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.45.15.png" alt=""><figcaption></figcaption></figure>

## Xác minh & Công bố Mã nguồn Hợp đồng trên VicScan

**Bước 1:** Nhấp vào tab Hợp đồng (**Contract**) và nhấp vào nút Xác minh & Công bố (**Verify & Publish**)

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.46.55.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.48.01.png" alt=""><figcaption></figcaption></figure>

**Bước 2**: Điền các thông tin sau

* **Địa chỉ hợp đồng (Contact Address):** Địa chỉ hợp đồng sẽ được **tự động lấy (automatically)**.
* **Tên hợp đồng (Contract Name):** Tên hợp đồng phụ thuộc vào loại **token** bạn tạo trên **Viction Issuer**:
* **MyVRC25Mintable:** Đối với token **có thể phát hành thêm (Reissueable)** (được chọn khi phát hành)
* **MyVRC25:** Đối với token **không thể phát hành thêm (Non-issuable)**
* **Trình biên dịch (Complier)**: Chọn phiên bản trình biên dịch **v0.7.6** để xác minh \*\*hợp đồng được phát hành (contract is issued) \*\*từ VicIssuer.
* **Tối ưu hóa (Optimization):** Giữ mặc định là **Không (No)**. Tham khảo [![](https://cdn.sstatic.net/Sites/ethereum/Img/favicon.ico?v=40dede55262c)'Runs (Optimizer) ' và 'Optimization' khi xác minh mã nguồn trên Etherscan.](https://ethereum.stackexchange.com/questions/64172/runs-optimizer-and-optimization-while-verifying-source-code-on-etherscan)
* Nhấp vào " **Thêm Mã nguồn Solidity**" **(Add Solidity Source Code)** để nhập mã nguồn.
* **Tên file**: Có thể đặt bất kỳ tên nào, không chứa **khoảng trắng** \*\*(space) \*\*hoặc **ký tự đặc biệt (special characters)**.
*   **Mã nguồn Solidity (Solidity Source Code)**: Sao chép và dán mã nguồn từ màn hình VicIssuer.

    <figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.52.59.png" alt=""><figcaption></figcaption></figure>

**Bước 3**: Xác minh hợp đồng thành công

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.55.52.png" alt=""><figcaption></figcaption></figure>
