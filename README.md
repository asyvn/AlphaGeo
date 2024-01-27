# Hướng dẫn cài đặt AlphaGeometry trên Windows 10, 11

## Cài WSL và Ubuntu

Trên Windows 10 (11), ở ô Search gõ tìm kiếm “Turn Windows features on or off”. Ở hộp thoại Windows Features chọn “Windows Subsystem for Linux”.

![alt text](https://github.com/asyvn/AlphaGeo/blob/main/WindowsFeatures.png?raw=true)

Ở ô Search gõ “Terminal” để chạy cửa sổ lệnh của Windows. Kiểm tra phiên bản WSL bằng lệnh **wsl --version**.

Nếu ở phiên bản 1, gõ **wsl --update** để cập nhật.

Để cài Ubuntu, gõ **wsl --install** WSL sẽ ngầm định cài Ubuntu.

Khi được hỏi “Enter new UNIX username: “, gõ **username** bạn muốn và sau đó gõ mật khẩu. Lưu ý mật khẩu này sẽ dùng khi dùng lệnh sudo khi cài các gói cần thiết.

Khi xuất hiện dấu nhắc lệnh của Ubuntu dạng như sau: **technical@chuotbach:~$** nghĩa là cài đặt thành công.

## Cài alphageometry
Tại dấu nhắc lệnh Ubuntu, gõ các lệnh sau:
    **sudo apt update**
Sau lệnh này, cài mc và virtualenv và python3-pip
    **sudo apt install mc python3-virtualenv python3-pip**

Tải gói alphageometry
    **git clone https://github.com/google-deepmind/alphageometry**

Sau lệnh trên gói alphageometry được tải về máy. Dùng lệnh ls để kiểm tra, sau đó dung lệnh cd để vào thư mục alphageometry.
    **cd alphageometry**

### Cài các gói yêu cầu của alphagometry
  **pip install --require-hashes -r requirements.txt**

Lưu ý cảnh báo lỗi ở đây, nếu có gói nào thiếu sẽ phải cài lại.

Dùng máy Windows, download 03 file checkpoint_10999999, geometry.757.model, geometry.757.vocab theo đường dẫn https://bit.ly/alphageometry. 

Lưu vào thư mục trên Windows, trong ví dụ lưu vào D:\ag.

Trên cửa sổ lệnh chạy **mc** và tạo thư mục **ag_ckpt_vocab** ở trong thư mục **alphageometry**. Sau đó mở panel còn lại để chọn **/mnt** đến ổ **d/ag** và copy 03 file nói trên sang thư mục **ag_ckpt_vocab**.

![image](https://github.com/asyvn/AlphaGeo/blob/main/mc.png?raw=true)

**Cài đặt meliad**

Ở cửa sổ lệnh Ubuntu, chạy:
   **MELIAD_PATH=meliad_lib/meliad
   mkdir -p $MELIAD_PATH
   git clone https://github.com/google-research/meliad $MELIAD_PATH
   export PYTHONPATH=$PYTHONPATH:$MELIAD_PATH**

Sau khi cài, trong thư mục **alphagometry** sẽ có thư mục **meliad_lib/meliad**.

**Chỉnh sửa file alphagometry.py**
   **nano alphagometry.py**
   
Tìm dòng ['third_party/py/meliad/transformer/configs'], sửa thành ['medialib/meliad/transformer/configs'],

![image](https://github.com/asyvn/AlphaGeo/blob/main/nano1.png?raw=true)

Chỉnh sửa file run.sh
nano run.sh
Thêm dấu # vào đầu các dòng
   pip install --require-hashes -r requirements.txt
   gdown --folder https://bit.ly/alphageometry
   
   mkdir -p $MELIAD_PATH
   git clone https://github.com/google-research/meliad $MELIAD_PATH

![image](https://github.com/asyvn/AlphaGeo/blob/main/nano2.png?raw=true)

Lưu lại file và chạy file **run.sh**:
   **bash run.sh**

Khi đó chương trình sẽ solve ở mode alphageometry.

(26.01.2024)
