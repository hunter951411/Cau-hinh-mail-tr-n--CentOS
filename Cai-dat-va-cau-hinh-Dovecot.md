#Cài đặt và cấu hình Dovecot

- Cài đặt Dovecot:

  **#yum -y install dovecot**

- Cấu hình file config

  **vi /etc/dovecot/dovecot.conf**

- Nếu sử dụng IPv6 khai bái địa chỉ cần dùng

Cấu hình file authen:

  **vi /etc/dovecot/conf.d/10-auth.conf**

- Dòng 9 loại bỏ # và đổi yes thành no để cho phép chứng thực văn bản đơn giản.

<img src="http://i.imgur.com/UgKqsMD.png">

- Dòng 97 thêm login vào phía sau để xác định cơ chế xác thực login

<img src="http://i.imgur.com/EamYqnS.png">

- Cấu hình file mail

  **#vi /etc/dovecot/conf.d/10-mail.conf**

- Dòng 30 bỏ **#** và thêm maildir:~/Maildir cho mail_location

<img src="http://i.imgur.com/tvk02Zn.png">

- Cấu hình file master

  **vi /etc/dovecot/conf.d/10-master.conf**

- Dòng 88-90 bỏ **#** và sửa như trên hình:

<img src="http://i.imgur.com/bteYr3Q.png">

- Lưu cấu hình sau đó start dịch vụ và cho dịch vụ chạy cùng khi server khởi động

<img src="http://i.imgur.com/6g9rOy8.png">
