# WebSocket-server

Để chạy dự án WebSocket sau khi tải về từ GitHub, bạn thực hiện theo các bước sau:

### Bước 1: Tải dự án từ GitHub

1. **Clone dự án từ GitHub** về máy tính của bạn, bạn thực hiện lệnh sau:

   ```bash
   https://github.com/BaoQuocZero/WebSocket-server.git
   ```

2. **Di chuyển vào thư mục dự án**:

   ```bash
   cd WebSocket-server
   ```

### Bước 2: Cài đặt các phụ thuộc

1. Dự án này sử dụng Node.js, vì vậy bạn cần cài đặt tất cả các package cần thiết bằng cách chạy lệnh sau:

   ```bash
   npm install
   ```

   Lệnh này sẽ đọc file `package.json` và cài đặt các thư viện như `ws` (WebSocket) cũng như các phụ thuộc khác.

### Bước 3: Chạy dự án

1. Sau khi cài đặt xong, bạn có thể chạy server bằng lệnh:

   ```bash
   node server.js
   ```

2. Mở trình duyệt và truy cập vào địa chỉ sau để kiểm tra ứng dụng:

   ```bash
   http://localhost:8080/index.html
   ```

   Giao diện chat sẽ hiện ra, và bạn có thể nhập tên người dùng rồi bắt đầu chat.

### Bước 4: Xử lý sự cố

- **Kiểm tra cổng**: Nếu cổng `8080` đã được sử dụng bởi một dịch vụ khác, bạn có thể thay đổi cổng trong file `server.js` bằng cách sửa giá trị biến `PORT`:

   ```javascript
   const PORT = 8080; // Thay đổi cổng tại đây nếu cần
   ```

- **Lỗi thiếu thư viện**: Nếu gặp lỗi không tìm thấy module, hãy chắc chắn rằng bạn đã chạy `npm install` để cài đặt tất cả các thư viện cần thiết.
