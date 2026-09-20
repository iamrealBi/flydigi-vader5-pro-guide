<div class="site-hero">
  <h1>Flydigi Vader 5 Pro Guide</h1>
  <p>Hướng dẫn tiếng Việt dựa trên UI thật: Space Station, reWASD, gyro, macro, layer, trigger, troubleshooting và migrate profile.</p>
</div>

![Flydigi Space Station đang nhận VADER 5 Pro](images/01-device-home.png)

## Điểm khác của bản guide này

- **Ảnh UI thật** chụp trực tiếp từ VADER 5 Pro đang kết nối.
- Giữ tên tiếng Anh để bạn tìm đúng menu, nhưng giải thích bằng tiếng Việt dễ hiểu.
- Không dịch máy móc: ví dụ Pulse được giải thích là “tap target rất ngắn”, không chỉ gọi là “xung”.
- Phân biệt rõ tính năng **đã thấy trên UI** với capability **chỉ có trong code**.
- Có guide riêng để migrate Best.rewasd của Elden Ring.

### Ký hiệu

- **✅ Đã xác minh trên UI thật**
- **🧪 Có trong code/capability nhưng chưa thấy trên UI hiện tại**
- **⚠️ Phụ thuộc firmware / Engine / model / mode kết nối**

<div class="site-grid">
  <a class="site-card" href="#/guide"><b>🎮 Space Station từ A → Z</b><span>Mỗi mục đều có vị trí menu, ý nghĩa, ví dụ và ảnh thật.</span></a>
  <a class="site-card" href="#/glossary"><b>📖 Từ điển thuật ngữ</b><span>Pulse, Toggle, Dead Zone, Curve, Travel, Haptic… giải thích theo hành vi thực tế.</span></a>
  <a class="site-card" href="#/comparison"><b>⚖️ Flydigi vs reWASD</b><span>So capability và cách tránh chồng nhiều lớp remap.</span></a>
  <a class="site-card" href="#/migration"><b>🔁 Migrate Best.rewasd</b><span>Chuyển gameplay core Elden Ring sang Space Station theo mức xác minh.</span></a>
  <a class="site-card" href="#/troubleshooting"><b>🧰 Troubleshooting</b><span>Double input, mixed input, gyro drift, layer, macro, trigger và profile.</span></a>
</div>

## Bắt đầu ở đâu?

Nếu mới dùng:
1. đọc [Từ điển thuật ngữ](glossary.md) khi gặp từ lạ;
2. làm theo [Hướng dẫn Space Station](guide.md);
3. nếu đang dùng reWASD, đọc [So sánh](comparison.md);
4. nếu muốn chuyển profile Elden Ring, mở [Migration](migration.md);
5. lỗi ở đâu tra [Troubleshooting](troubleshooting.md).

## Một đính chính quan trọng so với bản đầu

Bản đầu từng trình bày **Trigger Haptics** như một phần chắc chắn có trong tab Trigger.

Sau khi kiểm tra lại UI thật:
- code Space Station có chuỗi Pistol/Rifle/Shotgun/Sword và Trigger Haptics;
- nhưng UI Trigger của VADER 5 Pro đang kiểm tra **không expose các lựa chọn đó**.

Guide mới đã sửa thành trạng thái **🧪 code-only / chưa thấy trên UI hiện tại**.

## Phiên bản kiểm tra

- VADER 5 Pro firmware: **7.2.2.1**
- Space Station hiển thị: **V5.0.1.1**
- reWASD đối chiếu: **9.5.0**
- rà soát: **21/09/2026**

> Đây là tài liệu cộng đồng, không phải tài liệu chính thức của Flydigi hoặc reWASD.
