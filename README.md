# 🌐 Social App Backend

## 📂 Git Repository
Bạn có thể truy cập mã nguồn dự án tại: [GitHub Repository](https://github.com/ducanhduocdochu/social)

## 📝 Tổng quan dự án
Dự án được xây dựng với kiến trúc **Microservice**, đảm bảo hiệu suất cao và dễ mở rộng. Hệ thống được chia thành các dịch vụ độc lập với những chức năng cụ thể:

### 🏗️ Phân tách kiến trúc microservice
- **🔑 Auth-server**: Xử lý định danh và phân quyền người dùng.
- **💾 Backend-server**: Cung cấp các API phục vụ tính năng chính của ứng dụng.
- **🔔 Web-socket-server**: Xử lý thông báo thời gian thực, kết hợp với RabbitMQ.

### 🛠️ Công nghệ và cơ sở hạ tầng
#### 🗄️ Cơ sở dữ liệu:
- **📚 MongoDB**: Lưu trữ dữ liệu phi cấu trúc (NoSQL) cho các đối tượng như bài viết, bình luận.
- **🗃️ PostgreSQL**: Sử dụng cho dữ liệu quan hệ với tính toàn vẹn cao phù hợp cho đối tượng người dùng.

#### ⚡ Bộ nhớ đệm:
- **🧠 Redis**: Được sử dụng làm bộ nhớ đệm, tối ưu hóa tốc độ truy xuất dữ liệu.

#### 📝 Ghi log:
- **📜 Máy chủ Discord**: Dùng để ghi log và theo dõi hoạt động hệ thống.

#### 📡 Thông báo thời gian thực:
- **🐇 RabbitMQ** kết hợp với **🔗 WebSocket** để đảm bảo thông báo thời gian thực, độ trễ thấp.

### 🔍 Chi tiết các dịch vụ
#### 🔐 **Auth-server**: [GitHub Repository](https://github.com/ducanhduocdochu/auth-social-network)
- Xử lý định danh người dùng (authentication) với các API liên quan đến đăng nhập, đăng ký.
- Hỗ trợ phân quyền (authorization) với các vai trò khác nhau.
- Đảm bảo bảo mật thông qua mã hóa dữ liệu nhạy cảm.

#### 🖥️ **Backend-server**: [GitHub Repository](https://github.com/ducanhduocdochu/logic-social-network)
- Cung cấp các API phục vụ người dùng:
  - 📝 Đăng bài, chỉnh sửa và xóa bài viết.
  - 💬 Bình luận, thích, chia sẻ nội dung.
  - 👥 Quản lý mối quan hệ: theo dõi, kết bạn.
  - 🔔 Hệ thống thông báo (notification).
- Tối ưu hóa hiệu suất với các truy vấn cơ sở dữ liệu phức tạp.

#### 🔔 **Web-socket-server**: [GitHub Repository](https://github.com/ducanhduocdochu/socket-server-social-network)
- Quản lý thông báo thời gian thực giữa người dùng.
- Kết hợp **🐇 RabbitMQ** làm hàng đợi tin nhắn (message queue) để xử lý các tác vụ đồng thời.
- Đảm bảo tính ổn định của hệ thống khi tải cao.

### 🎨 Frontend: [GitHub Repository](https://github.com/ducanhduocdochu/client-web-social-network)
- Giao diện người dùng được xây dựng với **⚛️ ReactJS**, cung cấp trải nghiệm tương tác mượt mà.
- Quản lý trạng thái ứng dụng với **🛠️ Redux**, đảm bảo luồng dữ liệu nhất quán.
- Sử dụng các thư viện UI để tăng tốc độ phát triển và cải thiện tính thẩm mỹ của giao diện.

