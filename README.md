# Ứng dụng quản lý bài viết

Đây là một ứng dụng web để quản lý bài viết, cho phép người dùng đăng ký, đăng nhập và thực hiện các thao tác CRUD (Tạo, Đọc, Cập nhật, Xóa) trên các bài viết của chính họ.

---

## Hướng dẫn Bắt đầu

Để chạy ứng dụng, hãy làm theo các bước sau:

1.  **Clone repository và submodules**:
    Mở terminal và chạy các lệnh sau để clone dự án và cập nhật các submodules:
    ```bash
    git clone https://github.com/letrung2004/aucontech-intern-test.git
    cd aucontech-intern-test
    git submodule update --init --recursive
    git submodule update --recursive --remote
    ```

---

## Hướng dẫn Chạy Ứng dụng

### Backend (Spring Boot)

1.  **Cấu hình cơ sở dữ liệu**:
    * Tạo database MySQL mới:
        ```sql
        CREATE DATABASE blog_managent;
        ```
    * Mở file `application.yaml` trong thư mục `backend/src/main/resources/` và cập nhật thông tin cấu hình database:
        ```yaml
        spring:
          datasource:
            url: "jdbc:mysql://localhost:3306/blog_managent"
            username: root
            password: YOUR_PASS_WORD
        ```
    * **Lưu ý**: Dự án sử dụng file `application.yaml`. Các cấu hình `jwt` đã được định nghĩa sẵn trong file này.

2.  **Khởi động Backend**:
    Mở terminal `cd` vào trong thư mục `backend` và chạy lệnh sau:
    ```bash
    ./mvnw spring-boot:run
    ```
    Ứng dụng sẽ chạy mặc định trên cổng **8080**.

### Frontend

1.  **Cài đặt dependencies**:
    Mở một terminal khác, di chuyển vào thư mục `frontend` và cài đặt các gói cần thiết:
    ```bash
    npm install
    ```
2.  **Khởi động Frontend**:
    Chạy lệnh sau để khởi động ứng dụng:
    ```bash
    npm run dev
    ```
    Ứng dụng sẽ chạy mặc định trên cổng **5173**.

---

## Chức năng

---

## Hướng dẫn Kiểm tra

* Truy cập `/register` để tạo tài khoản.
* Truy cập `/login` để đăng nhập.
* **JWT** được lưu trong **Local Storage** sau khi đăng nhập thành công.


## Kiểm tra Dữ liệu

* Kiểm tra bảng `users` và `posts` trong database.
* Token JWT được gửi kèm trong header `Authorization: Bearer <token>` khi gọi các API cần xác thực.

---

## Lưu ý

* Mật khẩu được hash bằng **BCrypt**.
* **CORS** đã được cấu hình để cho phép frontend gọi API.
