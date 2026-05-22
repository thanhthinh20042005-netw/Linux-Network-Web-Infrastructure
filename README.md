#  Linux Network & Web Infrastructure Deployment
[English Version](#-english-version) | [Tiếng Việt](#-tiếng-việt)

---

## 🇬🇧 English Version
# Personal Project: Secure Web Server Deployment in a Virtualized Linux Environment

A personal project simulating the deployment process of a secure enterprise-style Web Server using Linux virtualization technology, combined with system performance benchmarking and network evaluation.

## Technologies Used
- **Operating System:** Ubuntu Desktop 24.04 LTS
- **Hypervisor:** Oracle VM VirtualBox
- **Web Server:** Nginx
- **Security:** UFW (Uncomplicated Firewall)
- **Benchmarking Tool:** iPerf3

## Network Architecture
The project migrated the virtual network configuration from NAT mode to **Bridged Adapter** mode (Layer 2).  
This configuration allows the virtual machine to connect directly to the local router and obtain its own independent LAN IP address (`192.168.102.x`), separate from the host machine, enabling external devices to directly access the Web Server.

---

## 1. Practical Deployment

### Virtualization Hardware & Network Configuration
Configured optimized system resources (2 vCPUs, 3GB RAM, 128MB Video Memory) and switched the network mode to Bridged Adapter.

<img width="602" height="483" alt="virtualbox-setup" src="https://github.com/user-attachments/assets/11bb3f8a-17c8-4bd8-819c-aa3a9e8243ca" />

### Successful External Device Access (Mobile Phone)
The website content was customized by editing the HTML file (`index.html`) located at `/var/www/html/`.

<img width="602" height="437" alt="Picture6" src="https://github.com/user-attachments/assets/6fc95285-04d0-496d-aaa6-922a6ad01a18" />

Successfully accessed the website from a mobile phone using the VM’s internal LAN IP address.

<img width="340" alt="mobile-web" src="https://github.com/user-attachments/assets/c0c76474-3e7e-4f9c-a102-2c9e38d93456" />

---

## 2. Network Performance Benchmarking

Used **iPerf3** to perform quantitative network performance testing and evaluation (Throughput, Latency, and Packet Loss) between the Host Machine (Windows Client) and the Virtual Machine (Ubuntu Server).

### Benchmark Results (Metrics Table)

| Measured Metrics | Actual Result | Stability Evaluation |
| :--- | :--- | :--- |
| **Throughput (TCP)** | **3.61 Gbits/sec** | Outstanding transmission speed thanks to optimized virtual network drivers without bottlenecks. |
| **Jitter (UDP)** | **0.218 ms** | Extremely low latency variation, ensuring smooth and stable communication. |
| **Packet Loss (UDP)** | **0% (0 / 898)** | No packet loss occurred within the virtual LAN environment, ensuring high reliability. |

### iPerf3 Benchmark Evidence

- **TCP Throughput Test:**

<img width="602" height="392" alt="iperf3-tcp" src="https://github.com/user-attachments/assets/01ddbf76-bdab-4cc4-bf3a-b2ad06c34162" />

- **UDP Jitter & Packet Loss Test:**

<img width="602" height="307" alt="iperf3-udp" src="https://github.com/user-attachments/assets/a173475a-f38e-4061-997f-2f4bc88b2ecb" />

---

## 3. Key Takeaways from the Project
- Developed foundational Linux system administration and CLI (Command Line Interface) skills on Ubuntu.
- Gained practical networking troubleshooting experience, especially with NAT vs Bridged Adapter configurations.
- Applied system security principles based on the **Least Privilege Principle** using UFW by blocking all ports except port 80 for Web Server operation.
- Learned how to use specialized benchmarking tools to measure and interpret system/network performance metrics.

---

## 🇻🇳 Tiếng Việt

Dự án cá nhân mô phỏng quy trình triển khai một Web Server bảo mật trong môi trường doanh nghiệp sử dụng công nghệ ảo hóa Linux và thực hiện đánh giá hiệu năng hệ thống.

## Công nghệ sử dụng 
- **Operating System:** Ubuntu Desktop 24.04 LTS
- **Hypervisor:** Oracle VM VirtualBox
- **Web Server:** Nginx
- **Security:** UFW (Uncomplicated Firewall)
- **Benchmarking Tool:** iPerf3

## Kiến trúc mạng (Network Architecture)
Dự án chuyển đổi cấu hình card mạng từ NAT sang **Bridged Adapter** (Layer 2). Cấu hình này giúp máy ảo kết nối trực tiếp vào Router cục bộ, nhận một IP riêng trong dải mạng LAN (`192.168.102.x`) độc lập với máy thật, cho phép các thiết bị ngoại vi truy cập trực tiếp vào Web Server.

---

## 1. Triển khai thực tế

###  Cấu hình phần cứng ảo hóa & Mạng
Thiết lập tài nguyên tối ưu cho hệ thống (2 vCPUs, 3GB RAM, 128MB Video Memory) và chuyển đổi chế độ mạng sang Bridged Adapter.

<img width="602" height="483" alt="virtualbox-setup" src="https://github.com/user-attachments/assets/11bb3f8a-17c8-4bd8-819c-aa3a9e8243ca" />


###  Kết quả truy cập từ thiết bị ngoại vi (Điện thoại)
Trang web được tùy biến nội dung HTML (`index.html`) tại đường dẫn `/var/www/html/` 
<img width="602" height="437" alt="Picture6" src="https://github.com/user-attachments/assets/6fc95285-04d0-496d-aaa6-922a6ad01a18" />


Truy cập thành công từ điện thoại thông qua địa chỉ IP nội bộ của máy ảo.

<img width="340"  alt="mobile-web" src="https://github.com/user-attachments/assets/c0c76474-3e7e-4f9c-a102-2c9e38d93456" />


---

##  2. Kiểm thử hiệu năng mạng (Network Performance Benchmarking)

Sử dụng công cụ **iPerf3** để tiến hành đo lường định lượng và đánh giá hiệu năng mạng (Throughput, Latency, Packet Loss) giữa Máy thật (Windows Host - Client) và Máy ảo (Ubuntu VM - Server).



###  Kết quả đạt được (Metrics Table)

| Tham số đo lường (Metrics) | Kết quả thực tế (Actual Result) | Đánh giá độ ổn định (Stability) |
| :--- | :--- | :--- |
| **Throughput (TCP)** | **3.61 Gbits/sec** | Tốc độ truyền tải vượt trội nhờ tối ưu hóa driver mạng ảo, không bị thắt nút cổ chai (bottleneck). |
| **Jitter (UDP)** | **0.218 ms** | Độ biến động trễ cực kỳ nhỏ, kết nối diễn ra liên tục và mượt mà. |
| **Packet Loss (UDP)** | **0% (0 / 898)** | Không xảy ra hiện tượng mất mát dữ liệu trên Virtual LAN, đảm bảo độ tin cậy tuyệt đối. |

###  Hình ảnh minh chứng kết quả iPerf3
- **Kiểm thử băng thông TCP:**

<img width="602" height="392" alt="iperf3-tcp" src="https://github.com/user-attachments/assets/01ddbf76-bdab-4cc4-bf3a-b2ad06c34162" />


- **Kiểm thử độ trễ và mất gói với UDP:**


<img width="602" height="307" alt="iperf3-udp" src="https://github.com/user-attachments/assets/a173475a-f38e-4061-997f-2f4bc88b2ecb" />

---

## 3. Rút ra từ dự án 
- Làm chủ kỹ năng quản trị và dòng lệnh (CLI) cơ bản trên Ubuntu Linux.
- Có tư duy cấu hình và xử lý sự cố mạng thực tế (NAT vs Bridged Adapter).
- Tư duy bảo mật hệ thống theo nguyên tắc quyền tối thiểu (Least Privilege) bằng cách sử dụng UFW để đóng toàn bộ các cổng và chỉ mở duy nhất cổng 80 cho dịch vụ Web hoạt động.
- Biết cách sử dụng công cụ chuyên dụng để đo đạc, đọc hiểu số liệu hiệu năng hệ thống.
