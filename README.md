# Smart_Power_Supply_Station_Using_ESP32_with_IoT_Integration
A smart, battery-powered DC power supply station based on ESP32 with IoT integration. The system features an adjustable 1–12V/3A DC output.
Giai đoạn 1: Lên ý tưởng hệ thống
- vi điều khiển chính, module ESP32 gắn trên mạch chính mà không cần dùng vi điều khiển rời
- dùng 4 viên pin 18650 mắc nối tiếp, phần quản lý sạc và bảo vệ v.v sẽ để riêng ở phần pin, không bỏ vào mạch chính
- điện áp đầu ra, điều chỉnh được từ 1 - 12V (không quan tâm hạ xuống 0V tuyệt đối)
- Phần công suất hạ áp sẽ không gắn module có sẳn, thay vào đó lắp các linh kiện trên mạch và sẽ dùng IC điều khiển tích hợp MOSFET bên trong
- điều chỉnh nằm cơ chế núm xoay bằng tay (có thể xem xét dùng biến trở hoặc rotery encoder gì đó)
- dòng điện đầu ra tối đa chỉ cần 3A, đo bằng cảm biến đo dòng thích hợp, gửi về Vi điều khiển sau đó hiển thị lên OLED
- phần iot chủ yếu là firmware, xong hết sẽ tới
- Phần vỏ 3D không quá quan tâm, cuối cùng xong hết sẽ tới nó

Giai đoạn 2: Lựa chọn linh kiện
- 4 pin 18650 mắc nối tiếp
- MCU: ESP32-WROOM-32D
- Màn OLED 0.98" I2C
- Module dùng để nuôi MCU: MP1584EN - 3.3V, gắn module trên PCB luôn.
- Module dùng để đo dòng: ACS712 - 5A, gắn module trên PCB, hoặc có thể xem xét thiết kế lại trên PCB
- IC công suất Buck chọn LM2596T-adj vì nó dễ thực hiện, phần linh kiện bên ngoài
- Phần núm xoay chọn Rotary Encoder và thiết kế một mạch điều khiển riêng
