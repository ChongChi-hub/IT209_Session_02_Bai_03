# Bài 3: Cài đặt Nginx và cấu hình Website tĩnh cơ bản

### 1. Cài đặt Nginx
```bash
sudo apt update
sudo apt install nginx -y
```

### 2. Tạo thư mục mã nguồn và file `index.html`
```bash
sudo mkdir -p /var/www/ptit-web/html
sudo nano /var/www/ptit-web/html/index.html
```
*(Lưu ý: File `index.html` đính kèm trong repository này chính là mã nguồn cần copy vào đường dẫn trên)*

### 3. Tạo cấu hình Server Block
```bash
sudo nano /etc/nginx/sites-available/ptit-web.conf
```
*(File `ptit-web.conf` đính kèm trong repository này là cấu hình để lắng nghe cổng 80 và trỏ thư mục root về `/var/www/ptit-web/html`)*

### 4. Kích hoạt cấu hình và vô hiệu hoá mặc định
Tạo symlink sang thư mục sites-enabled:
```bash
sudo ln -s /etc/nginx/sites-available/ptit-web.conf /etc/nginx/sites-enabled/
```

Xóa cấu hình mặc định để không bị xung đột cổng 80:
```bash
sudo rm /etc/nginx/sites-enabled/default
```

### 5. Kiểm tra và tải lại Nginx
Kiểm tra cú pháp cấu hình Nginx:
```bash
sudo nginx -t
```
Reload dịch vụ Nginx:
```bash
sudo systemctl reload nginx
```

### 6. Kết quả truy cập Web
*Lưu ý: Vì thẻ visa của em bị khoá nên không thể tạo droplet để chạy thử nghiệm trang web này.*
