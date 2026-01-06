### Sym link example

1. `ln -s <file_path> <symlink>` - lệnh tạo symlink

- Nhập `ln -s var/www/html/index.php link_to_index`. Sau khi ls -la sẽ xuất hiện symlink có tên link_to_index đang trỏ tới file gốc

<img width="573" height="100" alt="image" src="https://github.com/user-attachments/assets/992a1162-2bd3-40c2-896c-91dcea29d037" />

2. Khi đọc file symlink sẽ trả về nội dung file gốc

<img width="577" height="59" alt="image" src="https://github.com/user-attachments/assets/5e65cc6d-59de-43c0-afcc-c64f128581c0" />

3. Nội dung ghi vào file symlink sẽ ghi vào file gốc

<img width="461" height="47" alt="image" src="https://github.com/user-attachments/assets/2e24e87f-e890-44b5-9723-8a5e236b73d1" />

4. Thực thi bash script qua symlink

- Tạo 1 symlink mới link tới file /usr/bin/id

<img width="571" height="184" alt="image" src="https://github.com/user-attachments/assets/ad31f8fe-2664-40f6-8741-041746550d18" />

- Thực thi file link_to_id `./link_to_id` sẽ thực thi luôn file gốc

<img width="576" height="46" alt="image" src="https://github.com/user-attachments/assets/21fe6ac7-4eb6-4964-813f-1313973664a9" />

5. Sau khi xóa file symlink thì file gốc không bị xóa

<img width="464" height="100" alt="image" src="https://github.com/user-attachments/assets/e92a6e9a-6b81-41c0-a16f-ae2e1dad38c7" />

6. Tạo symlink đến folder /var/www/html

<img width="496" height="99" alt="image" src="https://github.com/user-attachments/assets/792e25fc-61fa-46a0-9ef4-7324e07ba9cf" />

- `ls -al` symlink link_to_html sẽ list ra những thứ có trong /var/www/html

<img width="495" height="105" alt="image" src="https://github.com/user-attachments/assets/7cd31233-bfec-4825-9783-2e71c6e84b60" />

7. Trong trường hợp symbolic link trỏ tới một thư mục, việc truy cập vào symlink này tương đương với truy cập trực tiếp vào thư mục gốc.

- Khi ghi file thông qua symlink, hệ điều hành sẽ theo đường dẫn mà symlink trỏ tới và ghi dữ liệu vào thư mục thật.

<img width="527" height="527" alt="image" src="https://github.com/user-attachments/assets/60f6d2dc-2392-41f7-93f0-8f32f4e713b6" />

- File được tạo sẽ xuất hiện trong thư mục đích mà symlink trỏ tới.

8. Zip symlink

- Tạo folder1 và folder2 trong /tmp, cd vào folder1, tạo symlink có tên link_to_passwd trỏ tới /etc/passwd, zip symlink link_to_passwd bằng lệnh `zip -y hack.zip link_to_passwd`

<img width="509" height="200" alt="image" src="https://github.com/user-attachments/assets/b88241f7-526c-4132-b9e5-f61faecd23f8" />

- cd vào folder2, copy file hack.zip vào folder2, `unzip hack.zip` sẽ vận chuyển được symlink từ folder1 qua folder2

<img width="313" height="83" alt="image" src="https://github.com/user-attachments/assets/295b0a6d-52b8-4079-ab73-fcbe7874c89e" />

<img width="493" height="247" alt="image" src="https://github.com/user-attachments/assets/2261e42f-7edb-44a4-a1c4-264fdff0d120" />

- Nếu khi tạo file zip không sử dụng option `-y`, công cụ `zip` sẽ theo symbolic link và đóng gói nội dung của file đích thay vì bản thân symlink.

- Do đó, khi giải nén ở thư mục khác, file được tạo ra sẽ là file thường và không còn giữ liên kết tới file gốc mà symlink trỏ tới.

- Test: `zip fail.zip link_to_passwd` (không sử dụng option `-y`). Sao chép file zip sang thư mục khác và giải nén. Kết quả: file được giải nén là file thường, không còn là symbolic link.

<img width="535" height="466" alt="image" src="https://github.com/user-attachments/assets/8f0085bd-7f36-48e5-8109-6d1033677f3b" />
