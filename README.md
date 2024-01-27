# Hướng dẫn cài đặt AlphaGeometry trên Windows 10, 11

## Cài WSL và Ubuntu

Trên Windows 10 (11), ở ô Search gõ tìm kiếm “Turn Windows features on or off”. Ở hộp thoại Windows Features chọn “Windows Subsystem for Linux”.

![alt text]( https://github.com/asyvn/AlphaGeo/blob/main/WindowsFeatures.png?raw=true)![image](https://github.com/asyvn/AlphaGeo/assets/65102232/1391734f-8d73-476d-b16d-3283bca3b6ce)

Ở ô Search gõ “Terminal” để chạy cửa sổ lệnh của Windows. Kiểm tra phiên bản WSL bằng lệnh **wsl --version**.

Nếu ở phiên bản 1, gõ **wsl --update** để cập nhật.

Để cài Ubuntu, gõ **wsl --install** WSL sẽ ngầm định cài Ubuntu.

Khi được hỏi “Enter new UNIX username: “, gõ **username** bạn muốn và sau đó gõ mật khẩu. Lưu ý mật khẩu này sẽ dùng khi dùng lệnh sudo khi cài các gói cần thiết.

Khi xuất hiện dấu nhắc lệnh của Ubuntu dạng như sau: **technical@chuotbach:~$** nghĩa là cài đặt thành công.
