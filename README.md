# WebSocket-server

### Hướng dẫn cài đặt Git và Node.js

Trước khi bạn có thể chạy dự án từ GitHub và cài đặt các phụ thuộc Node.js, hãy đảm bảo rằng bạn đã cài đặt **Git** và **Node.js**. Dưới đây là hướng dẫn chi tiết cho từng bước:

---

### Cài đặt Git (tùy chọn)

**Git** là công cụ quản lý mã nguồn phổ biến, giúp bạn clone dự án từ GitHub và quản lý phiên bản mã nguồn.

#### Đối với Windows:

1. Truy cập trang [tải Git cho Windows](https://git-scm.com/download/win).
2. Tải về file `.exe` và chạy để cài đặt.
3. Trong quá trình cài đặt, bạn có thể giữ nguyên các thiết lập mặc định.
4. Sau khi cài đặt xong, mở **Command Prompt** hoặc **Git Bash** và kiểm tra Git đã cài đặt thành công bằng lệnh:

   ```bash
   git --version
   ```

   Nếu hiển thị phiên bản Git, cài đặt đã thành công.

#### Đối với macOS:

1. Bạn có thể cài đặt Git qua **Homebrew** (nếu đã cài Homebrew). Chạy lệnh sau để cài đặt:

   ```bash
   brew install git
   ```

2. Kiểm tra cài đặt Git bằng cách chạy:

   ```bash
   git --version
   ```

#### Đối với Linux:

1. Chạy lệnh sau tùy vào hệ điều hành của bạn (Debian/Ubuntu hoặc CentOS/Fedora):

   - Đối với Debian/Ubuntu:

     ```bash
     sudo apt update
     sudo apt install git
     ```

   - Đối với CentOS/Fedora:

     ```bash
     sudo dnf install git
     ```

2. Kiểm tra cài đặt bằng lệnh:

   ```bash
   git --version
   ```

---

### Nếu không cài đặt git

1. Nhấn vào nút `<> Code`.
2. Nhấn vào nút `Download Zip`.
3. Giải nén và tiếp tục.

### Cài đặt Node.js

**Node.js** là môi trường chạy JavaScript trên server và cần thiết để chạy dự án WebSocket.

#### Đối với Windows và macOS:

1. Truy cập trang [tải Node.js](https://nodejs.org/), chọn phiên bản ổn định (LTS) và tải về file cài đặt.
2. Chạy file `.exe` (Windows) hoặc `.pkg` (macOS) để cài đặt. Trong quá trình cài đặt, giữ các thiết lập mặc định.
3. Sau khi cài đặt, mở **Command Prompt** (Windows) hoặc **Terminal** (macOS) và kiểm tra phiên bản Node.js và npm (Node Package Manager) bằng cách chạy:

   ```bash
   node --version
   npm --version
   ```

   Nếu hiển thị phiên bản Node.js và npm, cài đặt đã thành công.

#### Đối với Linux:

1. Chạy các lệnh sau để cài đặt Node.js thông qua **NodeSource**:

   - Đối với Ubuntu/Debian:

     ```bash
     curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
     sudo apt install -y nodejs
     ```

   - Đối với CentOS/Fedora:

     ```bash
     curl -fsSL https://rpm.nodesource.com/setup_lts.x | sudo bash -
     sudo yum install -y nodejs
     ```

2. Kiểm tra cài đặt bằng lệnh:

   ```bash
   node --version
   npm --version
   ```

---

### Tiếp tục với hướng dẫn chạy dự án

Sau khi đã cài đặt **Git** và **Node.js**, bạn có thể quay lại **Bước 1** của hướng dẫn ban đầu để tải về dự án từ GitHub và thực hiện các bước tiếp theo như cài đặt các phụ thuộc và chạy dự án.

Để chạy dự án WebSocket sau khi tải về từ GitHub, bạn thực hiện theo các bước sau:

### Bước 1: Tải dự án từ GitHub

1. **Clone dự án từ GitHub (bỏ qua nếu bạn đã `Download Zip`)** về máy tính của bạn, bạn thực hiện lệnh sau:

   ```bash
   https://github.com/BaoQuocZero/WebSocket-server.git
   ```

2. **Di chuyển vào thư mục dự án**:

   ```bash
   cd WebSocket-server
   ```

   Hoặc mở `cmd` trong thư mục gốc của dự án.

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
