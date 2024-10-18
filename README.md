# WebSocket-server

Đây là một đoạn code sử dụng Node.js để tạo một ứng dụng web cơ bản với sự kết hợp giữa HTTP server và WebSocket. Cùng phân tích từng phần:

### 1. Khai báo thư viện
```javascript
const WebSocket = require('ws');
const http = require('http');
const fs = require('fs');
const path = require('path');
```
- **WebSocket**: Thư viện WebSocket dùng để tạo server WebSocket, hỗ trợ giao tiếp thời gian thực giữa server và client.
- **http**: Thư viện HTTP gốc của Node.js dùng để tạo một HTTP server.
- **fs**: Thư viện File System để đọc/ghi file.
- **path**: Thư viện hỗ trợ xử lý đường dẫn file.

### 2. Tạo HTTP server
```javascript
const server = http.createServer((req, res) => {
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
    const filePath = path.join(__dirname, req.url);
    fs.readFile(filePath, (err, data) => {
      if (err) {
        res.writeHead(404);
        res.end('Không tìm thấy trang');
        return;
      }

      let contentType = 'text/plain';
      if (req.url.endsWith('.css')) {
        contentType = 'text/css';
      } else if (req.url.endsWith('.js')) {
        contentType = 'application/javascript';
      } else if (req.url.endsWith('.png')) {
        contentType = 'image/png';
      } else if (req.url.endsWith('.jpg') || req.url.endsWith('.jpeg')) {
        contentType = 'image/jpeg';
      }

      res.writeHead(200, { 'Content-Type': contentType });
      res.end(data);
    });
  }
});
```
- Đây là HTTP server phục vụ các file tĩnh như `index.html`, CSS, JS, hình ảnh...
- Nếu URL là `/` hoặc `/index.html`, nó sẽ phục vụ file `index.html`.
- Nếu là các yêu cầu khác, server sẽ tìm file tương ứng với URL được yêu cầu và xác định loại file (CSS, JS, hình ảnh...) để trả về đúng MIME type cho trình duyệt.

### 3. Tạo WebSocket server
```javascript
const wss = new WebSocket.Server({ server });
```
- **WebSocket server** được tạo, chia sẻ cùng một HTTP server để có thể xử lý cả giao thức HTTP và WebSocket.

### 4. Xử lý kết nối WebSocket
```javascript
let clients = [];
const clientNames = new Map();

wss.on('connection', (ws) => {
  clients.push(ws);
  console.log('Một client đã kết nối');
  ws.send('Vui lòng nhập tên của bạn:');
```
- Khi một client kết nối, nó sẽ được thêm vào mảng `clients` để theo dõi các kết nối.
- Server gửi yêu cầu để client nhập tên.

### 5. Nhận tên người dùng
```javascript
  ws.once('message', (name) => {
    const trimmedName = name.toString().trim();
    clientNames.set(ws, trimmedName);
    console.log(`${trimmedName} đã kết nối`);
    broadcast(`${trimmedName} đã tham gia vào phòng chat`, ws);
    ws.send(`Chào mừng ${trimmedName}! Bạn có thể bắt đầu gửi tin nhắn.`);
  });
```
- Lần đầu tiên nhận tin nhắn từ client, server hiểu đó là tên người dùng.
- Tên người dùng được lưu trong `clientNames` và phát thông báo cho tất cả các client khác.

### 6. Xử lý tin nhắn từ client
```javascript
  ws.on('message', (message) => {
    const name = clientNames.get(ws) || 'Unknown';
    const trimmedMessage = message.toString().trim();
    if (trimmedMessage.length > 0) {
      console.log(`${name}: ${trimmedMessage}`);
      broadcast(`${name}: ${trimmedMessage}`, ws);
    }
  });
```
- Mỗi khi nhận được tin nhắn, server sẽ phát tin nhắn này đến tất cả các client trừ người gửi.

### 7. Xử lý ngắt kết nối
```javascript
  ws.on('close', () => {
    const name = clientNames.get(ws) || 'Unknown';
    console.log(`${name} đã ngắt kết nối`);
    clients = clients.filter((client) => client !== ws);
    clientNames.delete(ws);
    broadcast(`${name} đã rời khỏi phòng chat`, ws);
  });
```
- Khi một client ngắt kết nối, server sẽ xóa client đó khỏi danh sách và thông báo cho những client khác.

### 8. Hàm phát sóng tin nhắn
```javascript
function broadcast(message, sender) {
  clients.forEach((client) => {
    if (client !== sender && client.readyState === WebSocket.OPEN) {
      client.send(message);
    }
  });
}
```
- Hàm `broadcast` gửi tin nhắn đến tất cả các client ngoại trừ người gửi tin nhắn.

### 9. Khởi động server
```javascript
const PORT = 8080;
server.listen(PORT, () => {
  console.log(`HTTP và WebSocket Server đang lắng nghe trên cổng ${PORT}`);
});
```
- Server lắng nghe trên cổng 8080.

Tóm lại, đoạn code này thiết lập một server Node.js với HTTP để phục vụ file tĩnh và WebSocket để tạo phòng chat thời gian thực. Người dùng kết nối sẽ nhập tên, gửi và nhận tin nhắn qua WebSocket.
