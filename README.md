# CẤU HÌNH DHCP TRÊN HỆ ĐIỀU HÀNH CENTOS
## A. Đối với máy DHCP Server
1. Cấu hình IP tĩnh cho DHCP Server:
   1. Vào **Cài đặt** của CentOS, chọn tab **Network**.
   2. Mở phần cài đặt của mục **Wired** (hình bánh răng).
   3. Chuyển đến tab **IPv4**, nhập các thông tin *Address*, *Netmask*, *Gateway* ở mục **Addresses**.
   4. Nhấn **Apply** để lưu thông tin.
2. Mở terminal, chạy dưới quyền quản trị bằng lệnh `su`.
3. Di chuyển đến thư mục chứa mã nguồn và cấp quyền truy cập tập tin:
    ```bash
    chmod +x dhcp_manager.sh
    ```
4. Chạy chương trình
   ```bash
   ./dhcp_manager.sh
   ```
5. Chọn thao tác cần thực hiện và điền đầy đủ dữ liệu theo yêu cầu.
6. Khi màn hình trở về **Menu thao tác**, chọn lựa chọn **Start dịch vụ** (nếu DHCP Service chưa được bật) hoặc chọn **Restart dịch vụ** (nếu DHCP đã được bật) để áp dụng cấu hình mới nhất.

## B. Đối với máy client (CentOS)
1. Người dùng vào phần **Cài đặt Network** và tắt mạng, sau đó bật lại mạng.
2. Để kiểm tra địa chỉ IP, người dùng mở terminal, chạy lệnh `ifconfig`
    
    *Ví dụ:*
    ```shell
    [iamaclient@localhost ~]$ ifconfig
    ens33: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.1.50  netmask 255.255.255.0  broadcast 192.168.1.255
        inet6 fe80::be81:3160:3e02:6151  prefixlen 64  scopeid 0x20<link>
        ether 00:0c:29:63:43:d4  txqueuelen 1000  (Ethernet)
        RX packets 991  bytes 101994 (99.6 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 329  bytes 53403 (52.1 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
    ```
    Trong đó, `192.168.1.50` chính là địa chỉ IP của máy client

## C. [Link video demo và hướng dẫn](https://youtu.be/DGz6z28VVx4)

