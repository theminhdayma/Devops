# Bước 1: Sử dụng Image Node.js chính thức làm ảnh nền (Base Image)
# Sử dụng phiên bản 'alpine' để kích thước image nhẹ nhất có thể.
FROM node:18-alpine

# Bước 2: Thiết lập thư mục làm việc bên trong Container
WORKDIR /app

# Bước 3: Copy file package.json và package-lock.json (nếu có) vào trước
# Việc này giúp tận dụng Docker cache cho các node_modules
COPY package*.json ./

# Bước 4: Cài đặt các dependencies đã định nghĩa trong package.json
RUN npm install

# Bước 5: Copy toàn bộ mã nguồn còn lại của ứng dụng vào thư mục làm việc
COPY . .

# Bước 6: Thông báo cổng mà Container sẽ lắng nghe khi chạy
EXPOSE 3000

# Bước 7: Lệnh để khởi chạy ứng dụng khi Container bắt đầu
CMD ["npm", "start"]