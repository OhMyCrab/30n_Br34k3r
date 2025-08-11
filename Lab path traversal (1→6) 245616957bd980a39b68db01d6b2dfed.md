# Lab path traversal (1→6)

Path: Đường đi

Absolute path: Đường dẫn bắt đầu từ thư mục gốc

Relative path: Đường dẫn phụ thuộc vào vị trí hiện tại

.  //tượng trưng cho đường dẫn đến thư mục hiện tại

.. //tượng trưng cho đường dẫn đến thư mục cha của thư mục hiện tại

* Nguyên nhân cốt lõi: Untrusted data rơi vào những hàm xử lý đường dẫn tập tin

* Hậu quả: Hacker có thể thao túng được file path. Phụ thuộc vào logic chương trình

* Ngữ cảnh: Unsafe method

Read - readfile()

Write - file_put_content()

RCE - ???

# level1:

![image.png](/images/image%20104.png)

![image.png](/images/image%20105.png)

![image.png](/images/image%20106.png)

![image.png](/images/image%20107.png)

# level2:

![image.png](/images/image%20108.png)

-  Hàm strpos trong đoạn code trên để tìm xem hacker có nhập .. , nếu có in ra Hack detected.

![image.png](/images/image%20109.png)

- Sửa đường dẫn images/flag.png thành /etc/passwsd

![image.png](/images/image%20110.png)

![image.png](/images/image%20111.png)

# level3(RCE được):

![image.png](/images/image%20112.png)

Có upload file, thử upload 1 file php

![image.png](/images/image%20113.png)

- Xem config tại file apche2.conf

![image.png](/images/image%20114.png)

- Tại dòng 43 tất cả các file đều không xử lý gì hết

![image.png](/images/image%20115.png)

- Sau khi phân tích source code:

+ Cho phép user upload tập tin vào thư mục $album và không có lớp sàng lọc filter nào

![image.png](/images/image%20116.png)

+ Tuy nhiên lại không thể nào chạy được mod-php ở trong folder /var/www/html/upload/ vì đã bị block bằng các config của apache2.conf

+ Cho phép kiểm soát đường dẫn $album bằng việc khai thác Path Traversal

![image.png](/images/image%20117.png)

→Tìm cách cho file shell.php ra ngoài /var/www/html/upload để thoát khỏi khối cấu hình mod-php

B1: Bắt request post upload file chuyển sang repeater 

B2: Chỉnh đường dẫn $album sao cho lùi về đến var/www/html (Nơi thực thi được code php)

![image.png](/images/image%20118.png)

![image.png](/images/image%20119.png)

B3: Truy cập đường dẫn /shell.php

![image.png](/images/image%20120.png)
