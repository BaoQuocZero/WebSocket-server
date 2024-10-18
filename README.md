# WebSocket-server

Để chạy dự án WebSocket sau khi tải về từ GitHub, bạn thực hiện theo các bước sau:

### Bước 1: Tải dự án từ GitHub

1. **Clone dự án từ GitHub** về máy tính của bạn. Giả sử link GitHub của bạn là `https://github.com/username/WebSocket-server`, bạn thực hiện lệnh sau:

   ```bash
   git clone https://github.com/username/WebSocket-server
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

### Bước 5: Đẩy thay đổi lên GitHub (nếu cần)

Sau khi thực hiện các thay đổi, nếu muốn đẩy ngược lại lên GitHub, bạn có thể sử dụng các lệnh sau:

1. **Thêm thay đổi vào git**:

   ```bash
   git add .
   ```

2. **Commit thay đổi**:

   ```bash
   git commit -m "Cập nhật dự án WebSocket-server"
   ```

3. **Đẩy thay đổi lên GitHub**:

   ```bash
   git push origin main
   ```

Dự án của bạn sẽ được cập nhật trên GitHub và sẵn sàng cho những người khác tải về và sử dụng.
