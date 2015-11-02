#Cài đặt và cấu hình Postfix

- Mặc định trên CentOS 6 Minimal đã cài đặt Postfix, tuy nhiên nếu vì lý do gì mà không tồn tại, ta có thể cài đặt bằng lệnh:

**yum -y install postfix**

- Để Postfix có thể chạy tốt ta sẽ sửa file cấu hình của Postfix bằng lệnh vi:

**vi /etc/postfix/main.cf**

- Đến dòng 75 bỏ dấu **#** và đổi hostname thành tên máy của bạn:

<img src="http://i.imgur.com/IudhJ3e.png">

- Đến dòng 83 bỏ dấu # và đổi mydomain thành tên domain của bạn:

<img src="http://i.imgur.com/Rnbw9rz.png">

- Đến dòng 99 bỏ dấu #, ở đây myorigin sẽ trỏ đến 1 biến là my domain:

<img src="http://i.imgur.com/WUi3HzQ.png">

- Đến dòng 116 đổi thêm dấu # phía trước và đến dòng 113 bỏ dấu **#** đi để mail sẽ được lắng nghe trên tất cả các cổng của server, chứ không chỉ lắng nghe trên localhost

<img src="http://i.imgur.com/7UJHPtG.png">

- Đến dòng 164 thêm dấu **#** phía trước và xuống xòng 165 bỏ dấu **#** phía trước để đích đến của mail có cả mydomain:

<img src="http://i.imgur.com/pN0cZkn.png">

- Đến dòng 264 bỏ dấu **#** và sửa dải mạng thành dải mạng bạn muốn cho sử dụng dịch vụ mail

<img src="http://i.imgur.com/bLLTgEo.png">

- Đến dòng 419 bỏ dấu **#** để sử dụng Maildir(Mail Directory).

<img src="http://i.imgur.com/Pk24hP5.png">

- Đến dòng 569 ta thêm banner cho smtp để khi người dùng kết nối với SMTP họ sẽ biết đang kết nối đến mail server nào:

<img src="http://i.imgur.com/ZztPXH8.png">

- Sau đó để hạn chế dung lượng của mỗi email và mailbox, ta thêm vào phía cuối các dòng sau:

<img src="http://i.imgur.com/8TaMxU8.png">

- Ở đây mình để dung lượng tối đa của mail là 10M và của mailbox là 1G

- Để xác thực cho SMTP ta thêm vào phía cuối các dòng như sau:

<img src="http://i.imgur.com/DXihg2q.png">

- Sau đó ta save lại và start dịch vụ, và cho dịch vụ chạy cùng khi server khởi động:

<img src="http://i.imgur.com/0a2ScH1.png">
