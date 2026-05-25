<img width="1705" height="668" alt="image" src="https://github.com/user-attachments/assets/d4f623e1-cf7b-414f-837f-e873913a2de0" />

- Bản chất: thay đổi thuộc tính (attribute) và lớp (class) của đối tượng (object)

- "Magic method" tự động được gọi khi 1 số action được thực hiện trên đối tượng (__toString, __destruct,__wakeup)

- Serialize

<img width="1562" height="816" alt="image" src="https://github.com/user-attachments/assets/c41e5b88-f4ef-4f14-90c7-1a3341f8428f" />

- Unserialize

<img width="1626" height="794" alt="image" src="https://github.com/user-attachments/assets/b6a571f2-790a-4dc5-b49b-62a7e27944b7" />

<img width="1600" height="954" alt="image" src="https://github.com/user-attachments/assets/f93a04a3-dfcc-45d5-aa39-552c4029d1d7" />

<img width="1721" height="1007" alt="image" src="https://github.com/user-attachments/assets/9ea3a781-e367-4cf4-999a-918d7202b492" />

<img width="1598" height="554" alt="image" src="https://github.com/user-attachments/assets/eb5cf568-a38b-4cb9-8229-7e514a3ebc4a" />

<img width="1694" height="616" alt="image" src="https://github.com/user-attachments/assets/8c6f6487-58fe-4620-895f-5b4126f4df63" />

- Tạo payload PHP Insecure Deserialization và tấn công

<img width="1883" height="737" alt="image" src="https://github.com/user-attachments/assets/05c0c4bf-eb07-462c-a9c9-b7692bd68762" />

<img width="1809" height="424" alt="image" src="https://github.com/user-attachments/assets/ab11cd49-407e-46b0-9d12-ed3de3b97df8" />

- Ví dụ tạo serializated data

<img width="520" height="454" alt="image" src="https://github.com/user-attachments/assets/97157a3c-3b68-4e35-9d0a-8acd51442900" />

sau khi chạy sẽ in ra serializated data: `O:10:"Calculator":1:{s:10:"expression";s:32:"echo file_get_contents('/flag');";}`

- Các kiểu tấn công php deserialization

thay đổi giá trị thuộc tính và lớp

hoán đổi đối tượng sang lớp khác

build payload ngược call graph
