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

   Hoặc mở `cmd` trong thư mục gốc `...WebSocket-server\` của dự án.

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

## Giải thích code của file server.js 

![Giải thích ngôn ngữ của chúa](https://media.giphy.com/media/8JrizwqvdF64cxhFSx/giphy.gif)

Đoạn mã này thiết lập một server Node.js vừa phục vụ các file tĩnh qua HTTP vừa tạo một WebSocket server để hỗ trợ giao tiếp thời gian thực giữa các client (như một phòng chat). Dưới đây là giải thích chi tiết từng phần của mã:

### Phần 1: Thiết lập HTTP Server để phục vụ file tĩnh
```javascript
const http = require('http');
const fs = require('fs');
const path = require('path');

const server = http.createServer((req, res) => {
  // Nếu truy cập vào root (/) hoặc /index.html, phục vụ file index.html
  if (req.url === '/' || req.url === '/index.html') {
    fs.readFile(path.join(__dirname, 'index.html'), (err, data) => {
      if (err) {
        res.writeHead(500);
        res.end('Lỗi máy chủ');
        return;
      }
      res.writeHead(200, { 'Content-Type': 'text/html' });
      res.end(data);
    });
  } else {
    // Đối với các yêu cầu khác (như file CSS, JS, hình ảnh), phục vụ file tương ứng
    const filePath = path.join(__dirname, req.url);
    fs.readFile(filePath, (err, data) => {
      if (err) {
        res.writeHead(404);
        res.end('Không tìm thấy trang');
        return;
      }

      // Xác định loại nội dung dựa trên phần mở rộng file
      let contentType = 'text/plain';
      if (req.url.endsWith('.css')) {
        contentType = 'text/css';
      } else if (req.url.endsWith('.js')) {
        contentType = 'application/javascript';
      } else if (req.url.endsWith('.png')) {
        contentType = 'image/png';
      } else if (req.url.endsWith('.jpg') || req.url.endsWith('.jpeg')) {
        contentType = 'image/jpeg';
      } // Thêm các loại MIME khác nếu cần

      res.writeHead(200, { 'Content-Type': contentType });
      res.end(data);
    });
  }
});
```

- **Giải thích**:
  - Tạo một HTTP server phục vụ các file tĩnh. 
  - Nếu truy cập vào root hoặc `/index.html`, server sẽ trả về `index.html`.
  - Với các file khác (như `.css`, `.js`, `.png`, `.jpg`), server trả về file tương ứng dựa trên đường dẫn của request. MIME type của file được xác định để trình duyệt biết cách hiển thị đúng nội dung.

### Phần 2: Thiết lập WebSocket Server
```javascript
const WebSocket = require('ws');

// Sử dụng HTTP server để tạo WebSocket server
const wss = new WebSocket.Server({ server });

let clients = [];                  // Danh sách client kết nối
const clientNames = new Map();      // Map để lưu tên người dùng của từng client

wss.on('connection', (ws) => {
  clients.push(ws);                // Thêm client mới vào danh sách
  console.log('Một client đã kết nối');
  ws.send('Vui lòng nhập tên của bạn:'); // Gửi yêu cầu nhập tên khi client kết nối

  // Xử lý khi client gửi tên
  ws.once('message', (name) => {
    const trimmedName = name.toString().trim();    // Xử lý tên để loại bỏ khoảng trắng
    clientNames.set(ws, trimmedName);              // Lưu tên vào clientNames
    console.log(`${trimmedName} đã kết nối`);
    broadcast(`${trimmedName} đã tham gia vào phòng chat`, ws);  // Thông báo cho các client khác
    ws.send(`Chào mừng ${trimmedName}! Bạn có thể bắt đầu gửi tin nhắn.`);
  });

  // Xử lý tin nhắn chat
  ws.on('message', (message) => {
    const name = clientNames.get(ws) || 'Unknown';
    const trimmedMessage = message.toString().trim();
    if (trimmedMessage.length > 0) {
      console.log(`${name}: ${trimmedMessage}`);
      broadcast(`${name}: ${trimmedMessage}`, ws);
    }
  });

  // Xử lý khi client ngắt kết nối
  ws.on('close', () => {
    const name = clientNames.get(ws) || 'Unknown';
    console.log(`${name} đã ngắt kết nối`);
    clients = clients.filter((client) => client !== ws);  // Xóa client khỏi danh sách
    clientNames.delete(ws);                               // Xóa tên khỏi clientNames
    broadcast(`${name} đã rời khỏi phòng chat`, ws);      // Thông báo cho các client khác
  });

  // Xử lý lỗi
  ws.on('error', (err) => {
    console.error(`Lỗi: ${err}`);
  });
});
```

- **Giải thích**:
  - Tạo WebSocket server sử dụng HTTP server vừa tạo.
  - Khi một client kết nối:
    - Thêm client vào danh sách `clients`.
    - Yêu cầu client nhập tên và lưu tên vào `clientNames`.
    - Khi client gửi tin nhắn, server truyền tin nhắn này đến tất cả client khác.
  - Nếu client ngắt kết nối, server xóa client khỏi danh sách và gửi thông báo cho các client khác.

### Phần 3: Hàm phát sóng tin nhắn đến tất cả client
```javascript
function broadcast(message, sender) {
  clients.forEach((client) => {
    if (client !== sender && client.readyState === WebSocket.OPEN) {
      client.send(message);
    }
  });
}
```

- **Giải thích**:
  - Hàm này gửi tin nhắn đến tất cả client khác (trừ người gửi).
  - Điều kiện `client.readyState === WebSocket.OPEN` đảm bảo rằng tin nhắn chỉ được gửi đến các client đang mở kết nối.

### Phần 4: Khởi động Server
```javascript
const PORT = 8080;
server.listen(PORT, () => {
  console.log(`Server is listening on port ${PORT}`);
  console.log(`http://localhost:${PORT}`);
  console.log(`http://localhost:${PORT}/index.html`);
});
```

- **Giải thích**:
  - Server HTTP và WebSocket bắt đầu lắng nghe trên cổng 8080.
  - Khi server chạy thành công, console sẽ hiển thị đường dẫn truy cập.

Với mã này, bạn có thể phục vụ các file tĩnh và tạo phòng chat với WebSocket, nơi nhiều client có thể gửi và nhận tin nhắn thời gian thực.
