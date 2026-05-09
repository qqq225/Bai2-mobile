# Môn: Phát triển ứng dụng với mã nguồn mở-TEE0421

Lớp: 58KTPM

**Bài tập 02:** 
# SỬ DỤNG DJANGO ĐỂ TẠO WEB QUẢN LÝ TIỆM CẦM ĐỒ
## deadline : 23h59 ngày 09 tháng 5 năm 2026.
A. TỔ CHỨC CSDL CHO HỆ THỐNG QUẢN LÝ TIỆM CẦM ĐỒ: viết tay ra giấy, lấy điện thoại chụp lại, upload ảnh lên github (đã nói về các nghiệp vụ trên lớp, ghi bảng)
  <img width="1920" height="2560" alt="image" src="https://github.com/user-attachments/assets/29dd9465-5154-41ba-8323-d9c968caf478" />
 
B. SỬ DỤNG DOCKER TRÊN UBUNTU ĐỂ: 
Bước 1: Thiết lập cấu trúc thư mục
<img width="562" height="77" alt="image" src="https://github.com/user-attachments/assets/c9144248-b0b6-4a1d-9519-6347efe7990f" />
BƯỚC 2: CÁC FILE CẤU HÌNH DOCKER
Tạo file thư viện: sudo nano app/requirements.txt
<img width="1082" height="238" alt="image" src="https://github.com/user-attachments/assets/2e088373-fd6e-43b1-bf34-ab149046ed22" />
File app/Dockerfile:
<img width="1016" height="527" alt="image" src="https://github.com/user-attachments/assets/0dd5a35b-bbd8-4992-9ed4-cb754ba20118" />
File docker-compose.yml:
<img width="1456" height="677" alt="image" src="https://github.com/user-attachments/assets/00e3b78c-3bfa-46d5-a2dd-7f912690786e" />
BƯỚC 3: KHỞI TẠO DỰ ÁN DJANGO
Chạy lệnh này để tạo bộ khung dự án: sudo docker compose run web django-admin startproject my_system .
<img width="1466" height="377" alt="image" src="https://github.com/user-attachments/assets/038913fc-4804-49a9-b448-04df7689a3d9" />
BƯỚC 4: CẤU HÌNH CHI TIẾT CÁC FILE TRONG DJANGO
- Cấu hình Database file setting.py
   <img width="1475" height="759" alt="image" src="https://github.com/user-attachments/assets/f698ad8c-de24-4345-b5ce-1be6ff216897" />
- Xây dựng Models (KH, Lai, GD):
  <img width="1466" height="690" alt="image" src="https://github.com/user-attachments/assets/1f10461e-4e7b-4e59-9f05-d469e38e958b" />
- Kích hoạt trong Admin:
  <img width="1028" height="387" alt="image" src="https://github.com/user-attachments/assets/96970994-3a27-4556-bfd0-92187970d31c" />
BƯỚC 5: CHẠY DOCKER và KIỂM THỬ
   <img width="1466" height="138" alt="image" src="https://github.com/user-attachments/assets/b057766c-9bc0-4041-836d-1bc2e1c290a8" />
- Đồng bộ cơ sở dữ liệu:
    <img width="1457" height="575" alt="image" src="https://github.com/user-attachments/assets/d5811bc7-6777-4210-a8e3-fd059661fce9" />
- Tạo tài khoản quản trị đăng nhập trên django:
    <img width="1473" height="305" alt="image" src="https://github.com/user-attachments/assets/b194bc52-5548-4267-a303-d88670c604af" />
- Kết quả truy cập:
<img width="1741" height="842" alt="image" src="https://github.com/user-attachments/assets/c4e48032-e0db-4327-b3d9-892fe57d788b" />
<img width="1722" height="652" alt="image" src="https://github.com/user-attachments/assets/3ea70e2d-88c1-4c18-ba2a-08c3f9873d2a" />
- Chỉnh sửa dữ liệu các bảng trên Django và kiểm tra bên phpadmin:
  <img width="1801" height="952" alt="image" src="https://github.com/user-attachments/assets/ad2988ab-b297-4cb8-8e06-ca12fe9e0424" />
  <img width="1754" height="860" alt="image" src="https://github.com/user-attachments/assets/d70d7a74-6563-4481-8905-2165aa895854" />

BƯỚC 6: Xây dựng trang web liệt kê danh sách các con nợ quá hạn:
1. Tạo thư mục chứa Template:
   <img width="767" height="45" alt="image" src="https://github.com/user-attachments/assets/84c27976-19ea-4308-afc4-1e56fef2b5af" />
2.Tạo file Template HTML
<img width="1463" height="701" alt="image" src="https://github.com/user-attachments/assets/4e57ab09-dd3f-48b2-8a27-756cd3bcac2f" />
3. Viết View xử lý dữ liệu:
<img width="1163" height="520" alt="image" src="https://github.com/user-attachments/assets/fc3e9c61-ed16-48ab-922d-2aced6855026" />
4. Cấu hình URL
<img width="1463" height="643" alt="image" src="https://github.com/user-attachments/assets/a214f733-678f-441f-8723-56fd120ae61f" />
5. Khai báo Template Path trong Settings.py
<img width="1469" height="757" alt="image" src="https://github.com/user-attachments/assets/d36c9c58-2522-4393-91eb-5cde0ff77879" />
6. Restart lại Docker để cập nhật:
<img width="1780" height="500" alt="image" src="https://github.com/user-attachments/assets/85e1f339-8f46-42f3-b230-92ce2444bb5b" />
BƯỚC 7: PUBLIC KẾT QUẢ LÊN DOMAIN THÔNG QUA CLOUDFLARE:
1. Tải và cài đặt Cloudflared CLI
   + wget https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb
   + sudo dpkg -i cloudflared-linux-amd64.deb
2. Đăng nhập và Ủy quyền (Login):
   + cloudflared tunnel login
   + Sau khi nhập xong lệnh sẽ hiện ra 1 đường link, copy và dán lên trình duyệt sau đó ủy quyền cho domain:
     <img width="1576" height="790" alt="image" src="https://github.com/user-attachments/assets/ab57b11c-ccea-4dfb-a6d9-5d36c74b6fe8" />

3. Tạo Tunnel
   + cloudflared tunnel create django-tunnel
   + sau khi chạy lệnh trên sẽ hiện ra chuỗi id là 1 dãy ký tự, copy lại dùng cho bước tiếp
4. Cấu hình Tunnel (Config)
   + nano ~/.cloudflared/config.yml
   + dán id vừa nhận được vào code:
     <img width="1020" height="365" alt="image" src="https://github.com/user-attachments/assets/a65a3533-0514-409f-bba7-2b9e91a68b07" />
5. Cấu hình DNS (Kích hoạt domain): cloudflared tunnel route dns django-tunnel phamtrunghieuktp.id.vn
6. Chạy Tunnel: cloudflared tunnel run django-tunnel

===> Kết quả:
