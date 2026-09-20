# Flydigi Space Station vs reWASD 9.5.0 — nên dùng cái nào?

## Phạm vi so sánh

So sánh này áp dụng cho:
- Flydigi VADER 5 Pro;
- Space Station UI đang được kiểm tra trực tiếp;
- reWASD 9.5.0.

Theo release notes chính thức:
- reWASD 9.4.0 thêm hỗ trợ chính thức cho Vader 5 Pro;
- reWASD 9.5.0 phát hành ngày 13/08/2026;
- 9.5 sửa lỗi nhận nhầm M1/M2 và M3/M4 trên Vader 5 Pro/Apex 5.

Nếu thuật ngữ như Virtual Controller, Shift Layer, Mixed Input khó hiểu, xem [Từ điển thuật ngữ](glossary.md).

---

## Khác biệt nền tảng

### Space Station

Space Station là công cụ “gần phần cứng” hơn.

Mạnh ở:
- on-board profile;
- M1–M4, LM/RM;
- stick/trigger tuning;
- gyro;
- vibration;
- lighting;
- calibration;
- firmware.

### reWASD

reWASD là remapping framework cấp Windows.

Mạnh ở:
- virtual controller;
- profile tự đổi theo process/game;
- group nhiều thiết bị;
- shortcut;
- nhiều lớp Shift;
- workflow keyboard/mouse/controller;
- Flick Stick;
- các logic hệ điều hành.

---

## Bảng capability

| Khả năng | Space Station Vader 5 Pro | reWASD 9.5 |
|---|---|---|
| On-board profile | ✅ Native | Không phải trọng tâm |
| 4 profile slot trên controller | ✅ | Không quản lý như Flydigi slot |
| M1–M4 / LM / RM | ✅ Native | ✅ Hỗ trợ |
| Shift Layer | ✅ Main + tối đa 3 Shift | ✅ Nhiều Shift hơn |
| Hold / Toggle layer | ✅ | ✅ |
| Single / Double / Long | ✅ | ✅ |
| Triple Press | Không thấy trên UI | ✅ |
| Press / Release Pulse | ✅ | Có cách mapping tương đương khác |
| Multi-button Shortcut | Hạn chế hơn | ✅ Mạnh |
| Macro | ✅ | ✅ |
| Turbo / Rapid Fire | ✅ | ✅ |
| Stick curve | ✅ | ✅ |
| Stick zone | ✅ | ✅ |
| Trigger curve / zone | ✅ | ✅ |
| Gyro → Mouse | ✅ | ✅ |
| Gyro → Stick | ✅ | ✅ |
| Flick Stick | Không thấy | ✅ |
| Virtual Xbox/DS/ Switch | Không phải chức năng chính | ✅ |
| Group keyboard + mouse + controller | Không | ✅ |
| Auto đổi config theo EXE | Không thấy | ✅ Autodetect |
| Vibration native | ✅ | Có routing/tuning tùy output |
| Lighting | ✅ | Không phải trọng tâm |
| Firmware/calibration | ✅ | Không |
## Khi nào Space Station tốt hơn?

Dùng Space Station làm chính nếu:
- chỉ dùng Vader 5 Pro;
- muốn controller tự mang profile;
- muốn M-button ổn định;
- muốn chỉnh stick/trigger/gyro;
- muốn ít lớp phần mềm nhất.

Lợi ích lớn nhất:
> game nhận controller gần với native hơn, giảm nguy cơ double input.

## Khi nào reWASD tốt hơn?

Giữ reWASD nếu bạn cần:
- profile tự đổi khi mở từng game;
- virtual Xbox 360 / Xbox One / DS4 / Switch Pro;
- keyboard + mouse + controller thành một group;
- Triple Press;
- Shortcut nhiều nút;
- Flick Stick;
- desktop/system workflow;
- logic phức tạp vượt on-board Flydigi.

## “Virtual Controller” nghĩa là gì?

reWASD có thể tạo một controller ảo mà Windows/game nhìn thấy như thiết bị riêng.

Ví dụ:
- controller vật lý = Vader;
- reWASD tạo Virtual Xbox 360;
- game có thể thấy Xbox 360 ảo.

Nếu game thấy cả vật lý + ảo cùng lúc, có thể xảy ra **double input**.

## Group of Devices là gì?

reWASD cho phép nhóm 2–4 thiết bị.

Ví dụ:
- keyboard;
- mouse;
- Vader 5 Pro.

Sau đó một Shift Layer có thể thay đổi mapping của cả group.

Đây là thứ Space Station không được thiết kế để thay thế.

---

## Gyro: hai phần mềm khác nhau thế nào?

### Space Station

Ưu điểm:
- cấu hình trực tiếp cho Vader;
- Mouse / Left Stick / Right Stick;
- Hold / Toggle;
- curve;
- activation buttons.

### reWASD

Ưu điểm:
- hệ sinh thái virtual controller;
- Flick Stick;
- virtual gyro scenario;
- nhiều workflow kết hợp với mouse/controller.

Không copy số Sensitivity giữa hai app theo tỷ lệ 1:1.

---

## Layer: 3 Shift có đủ không?

Với profile Best.rewasd hiện tại:
- chỉ cần 2 Shift Layer;
- Space Station đủ.

Nếu config tương lai cần nhiều trạng thái phức tạp:
- reWASD linh hoạt hơn.

---

## Trigger Haptics: lưu ý đặc biệt

Bản guide cũ từng liệt kê Trigger Haptics như chức năng thực tế của Vader 5 Pro.

Sau khi kiểm tra UI thật:
- tab Trigger chỉ thấy Regular Response / Curve / Travel Zones;
- không thấy menu Pistol/Rifle/Shotgun/Sword.

Do đó phần này hiện được đánh dấu **🧪 code-only / chưa expose**.

Đây là ví dụ vì sao guide mới luôn phân biệt:
- capability có trong code;
- capability đã thấy trên UI thật.
## Kiến trúc khuyến nghị nếu chỉ chơi bằng Vader 5 Pro

1. Space Station xử lý phần hardware-native.
2. Apply profile xuống controller.
3. Tắt reWASD remap.
4. Tắt Steam Input tạm để test.
5. kiểm tra joy.cpl.
6. mở game.
7. chỉ thêm reWASD khi bạn xác định rõ thiếu capability nào.

## Nếu bắt buộc dùng cả hai

Cấu trúc sạch:

**Flydigi**
- M-button;
- stick;
- trigger;
- gyro nếu không cần workflow reWASD;
- calibration.

**reWASD**
- virtual controller;
- Autodetect;
- device group;
- shortcut/logic Windows.

Tránh mapping cùng một nút ở cả hai nơi theo hai ý nghĩa khác nhau.

Ví dụ xấu:
- M1 là Shift 1 trong Flydigi;
- đồng thời M1 là Shift 2 trong reWASD.

Khi lỗi, bạn gần như không biết layer nào gây ra.

---

## Với Elden Ring + Best.rewasd của bộ tài liệu này

Space Station tái tạo được phần gameplay chính:
- M4 → LS;
- M2 → Hold Shift Layer 1;
- M1 → Hold Shift Layer 2;
- A/B/X/Y mapping theo layer;
- combo A + LB/RB;
- gyro → mouse;
- Toggle gyro.

Điểm chưa nên khẳng định 1:1:
- sensitivity số học;
- smoothing số học;
- system-level behavior;
- virtual Xbox pipeline.

Đọc [Migration Guide](migration.md) để làm từng bước.

---

## Nguồn reWASD chính thức

- Release 9.5.0: https://www.rewasd.com/releases/release-9.5.0
- Release history: https://www.rewasd.com/releases
- Vader 5 Pro support từ 9.4: https://www.rewasd.com/releases/release-9.4.0
- Group of Devices: https://www.help.rewasd.com/how-to-remap/group-of-devices.html
- Gyroscope: https://www.help.rewasd.com/how-to-remap/gyroscope.html
- Virtual Controller: https://www.help.rewasd.com/basic-functions/virtual-controller.html

Ngày rà soát: 21/09/2026.
