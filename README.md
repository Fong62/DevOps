# 🚀 Quy trình Ci/CD: Jenkins, SonarQube, Nexus, Docker & Kubernetes

## 📌 Giới thiệu dự án
Đây là kho lưu trữ mã nguồn và các tệp cấu hình hạ tầng (Infrastructure as Code) cho đồ án môn học **Nhập môn DevOps**. Dự án hiện thực hóa một quy trình **Tích hợp liên tục (CI)** và **Triển khai liên tục (CD)** hoàn toàn tự động theo tiêu chuẩn công nghiệp.

Hệ thống giúp tự động hóa toàn bộ vòng đời phát triển phần mềm: từ khâu kiểm tra chất lượng mã nguồn, đóng gói sản phẩm, lưu trữ an toàn cho đến khi triển khai lên môi trường cluster.

## 🏗️ Kiến trúc luồng CI/CD
Luồng hoạt động của Pipeline được định nghĩa tự động hóa qua các bước sau:
1. **Source Control:** Developer đẩy mã nguồn (Push code) lên kho lưu trữ GitHub.
2. **Trigger Pipeline:** Jenkins tự động nhận diện thay đổi thông qua Webhook và kích hoạt quá trình Build.
3. **Code Quality Analysis:** Tích hợp **SonarQube** để quét mã nguồn, phát hiện bug, code smells và lỗ hổng bảo mật.
4. **Artifact Management:** Đóng gói ứng dụng và tự động đẩy bản build an toàn lên **Sonatype Nexus Repository**.
5. **Containerization:** Jenkins thực thi `Dockerfile` để build Docker Image và đẩy lên Docker Registry.
6. **Continuous Deployment:** Sử dụng `kubectl` để tự động triển khai (Deploy) Image mới nhất lên cụm **Kubernetes** thông qua các file cấu hình YAML.

## 🛠️ Công nghệ & Công cụ sử dụng
* **Quản lý mã nguồn:** Git & GitHub
* **CI/CD Server:** Jenkins
* **Quản lý chất lượng mã:** SonarQube
* **Lưu trữ Artifact:** Sonatype Nexus
* **Ảo hóa & Đóng gói:** Docker
* **Điều phối Container:** Kubernetes (Minikube / K8s Cluster)

## 📂 Cấu trúc thư mục (Repository Structure)
- `k8s/` : Các file cấu hình Kubernetes (deployment.yaml, service.yaml)
- `Dockerfile` : Cấu hình đóng gói ứng dụng thành Docker Image
- `Jenkinsfile` : Script định nghĩa toàn bộ luồng CI/CD (Pipeline as Code)
- `README.md` : Tài liệu dự án

## ⚙️ Hướng dẫn thiết lập cơ bản (Quick Setup)
1. Đảm bảo server/máy tính đã cài đặt sẵn Docker, Kubernetes, và Jenkins.
2. Clone repository này về máy bằng lệnh:
   `git clone https://github.com/Fong62/DevOps.git`
3. Cấu hình các Credentials (thông tin đăng nhập Docker Hub, SonarQube Token, Kubeconfig) trên Jenkins.
4. Tạo một *Pipeline Job* mới trên Jenkins và trỏ vào kho lưu trữ GitHub này. Jenkins sẽ tự động đọc file `Jenkinsfile` và thực thi quy trình.

## 📞 Liên hệ
**Nguyễn Hoàng Phong**
* **Email:** nguyenhoangphongsupham@gmail.com
* **LinkedIn:** [Nguyễn Hoàng Phong](https://www.linkedin.com/in/fong62/)
* **GitHub:** [Fong62](https://github.com/Fong62)
