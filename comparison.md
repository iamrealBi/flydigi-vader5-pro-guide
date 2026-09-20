# Flydigi Space Station vs reWASD 9.5.0

## Bối cảnh
So sánh này áp dụng cho:
- Flydigi Vader 5 Pro.
- Space Station web UI hiện đang kết nối trực tiếp controller.
- reWASD 9.5.0, bản hiện hành ngày 2026-09-21.

reWASD 9.4.0 thêm hỗ trợ chính thức Vader 5 Pro.
reWASD 9.5.0 sửa lỗi M1/M2 và M3/M4 trên Vader 5 Pro/Apex 5.

## Bảng capability

| Hạng mục | Flydigi Space Station | reWASD 9.5 |
|---|---|---|
| On-board profile | Rất mạnh, ghi trực tiếp vào 4 slot | Không phải thế mạnh chính với Vader |
| Local profile library | Có | Có Profile/Config |
| Auto theo EXE | Không thấy trong mapping profile thường | Có Autodetect |
| Virtual controller | Không phải mục tiêu chính | Xbox 360/One, DS3/DS4, Switch Pro |
| Group nhiều device | Không | Có keyboard/mouse/controller group |
| Shift layer | Main + tối đa 3 Shift | Tới 10 Shift overlays theo Help hiện hành |
| Hold/Toggle layer | Có | Có, thêm Custom |
| Single/Double/Long | Có | Có |
| Triple Press | Không thấy | Có |
| Press/Release action | Press Pulse/Release Pulse | Start Press/Release Press |
| Multi-button Shortcut | Không thấy như hệ thống shortcut riêng | Có |
| Controller target | Có | Có |
| Keyboard/Mouse target | Có | Có |
| Media target | Có | Có |
| Turbo | Có | Có Rapid Fire Turbo |
| Toggle mapping | Có | Có Rapid Fire Toggle |
| Macro | Có, 10/layer | Có Combo/Key Combo |
| Stick curve | Có | Có |
| Stick zones | Rất mạnh, 4/8-way segments | Low/Medium/High zones + directions |
| Trigger zones | 3 zone Light/Medium/Heavy | Low/Medium/High zones |
| Gyro -> Mouse | Có | Có |
| Gyro -> Stick | Có | Có |
| Flick Stick | Không thấy | Có |
| Haptics native Flydigi | Rất mạnh | Giới hạn hơn |
| X-Haptics | Audio/Adaptive/UDP | Không tương đương Flydigi-native |
| Lighting | Native | Có một số LED customization |
| Firmware/calibration | Native đầy đủ | Không thay thế firmware utility Flydigi |
## Điểm Space Station thắng rõ ràng

#

## 1. Hardware-native
Space Station hiểu trực tiếp:
- M1/M2/M3/M4.
- LM/RM.
- Stick precision.
- Controller calibration.
- Trigger feedback.
- Lighting.
- Firmware.

Điều này giảm số lớp phần mềm giữa controller và game.

#

## 2. On-board portability
Sau khi apply xuống controller:
- Profile nằm trong tay cầm.
- Có thể chuyển bằng FN + A/B/X/Y.
- Không cần reWASD profile để các mapping on-board hoạt động.

Đây là ưu thế lớn nếu:
- chơi nhiều máy;
- dùng Steam Big Picture;
- remote gaming;
- không muốn background remapper.

#

## 3. Trigger và haptics
Space Station có:
- custom trigger curve;
- 3 travel zones;
- trigger scenes;
- grip feedback;
- X-Haptics audio;
- adaptive trigger;
- UDP telemetry.

reWASD không thay thế được toàn bộ lớp haptic/firmware-native này.

## Điểm reWASD thắng rõ ràng

#

## 1. Windows-level automation
Autodetect gắn profile với một hoặc nhiều EXE.
Khi app được focus, reWASD có thể tự apply config.
Tính năng này cần Background Agent.

Space Station on-board profile không có logic focus-EXE tương đương trong UI hiện tại.

#

## 2. Virtual controller
reWASD có thể emulate:
- Xbox 360.
- Xbox One.
- DualShock 3.
- DualShock 4.
- Nintendo Switch Pro.

Điều này hữu ích khi game chỉ hỗ trợ một loại controller hoặc cần virtual DS4 gyro.

#

## 3. Multi-device
reWASD có thể group 2-4 thiết bị:
- keyboard;
- mouse;
- controller;
- nhiều controller.

Shift layer có thể tác động đồng thời lên cả group.

#

## 4. Logic mapping nâng cao
reWASD có:
- Triple Press.
- Shortcut 2/3/4 nút.
- nhiều Shift overlay hơn.
- Custom shift exit.
- Launch App command.
- Radial Menu.
- Flick Stick.
- workflow desktop/system rộng hơn.
## Activator: khác nhau thực tế

Space Station:
- Direct.
- Single Press.
- Double Press.
- Long Press.
- Press Pulse.
- Release Pulse.
- Toggle.

reWASD:
- Single.
- Double.
- Triple.
- Long.
- Start Press.
- Release Press.
- Toggle/Turbo qua Rapid Fire.

Nếu cấu hình chỉ cần Single/Double/Long/Toggle:
- Space Station đã đủ.

Nếu cần Triple hoặc Shortcut phức tạp:
- reWASD linh hoạt hơn.

## Layer
Space Station:
- Main + 3 Shift.
- Hold/Toggle.
- layer chứa riêng mapping, stick zone, trigger zone, macro.

reWASD:
- nhiều overlay hơn;
- Hold/Toggle/Custom;
- layer có inheritance controls chi tiết hơn.

Best.rewasd của bạn chỉ dùng 2 Shift.
Vì vậy Space Station đủ capacity để migrate toàn bộ logic layer hiện tại.
## Macro
Space Station phù hợp:
- combo controller;
- sequence;
- loop;
- hold-combination;
- analog stick/trigger;
- macro theo layer;
- chạy on-board theo capability controller.

reWASD phù hợp:
- combo hệ thống rộng hơn;
- phối hợp keyboard/mouse/controller;
- workflow cùng Autodetect;
- device grouping.

Với Best.rewasd hiện tại, macro đều đơn giản:
- A + LB.
- A + RB.
- A + D-pad direction.
Space Station xử lý được trực tiếp.

## Gyro
Best.rewasd hiện:
- gyro -> mouse;
- horizontal bình thường;
- vertical đảo;
- M3 toggle gyro.

Space Station hỗ trợ đúng mô hình:
- Mouse target.
- Toggle activation.
- Primary button M3.
- Invert Vertical Y.

Khác biệt:
- sensitivity scale không tương đương 1:1;
- reWASD có thêm Flick Stick và nhiều virtual-output scenario.

## Độ phụ thuộc phần mềm
Space Station on-board:
- phù hợp để chạy controller-native sau khi apply.

reWASD:
- các virtual mapping/autodetect phụ thuộc driver/background software.
- tài liệu reWASD khuyến nghị hide physical controller khi virtual output để tránh input trùng trong nhiều scenario.
## Nên dùng cái nào cho bạn?

#

## Vader 5 Pro + Elden Ring
Khuyến nghị:
1. Space Station làm primary.
2. Migrate Best.rewasd vào on-board profile.
3. Test game không có reWASD trước.
4. Chỉ bật reWASD nếu thiếu một capability thật sự cần thiết.

Lý do:
- Best.rewasd chỉ dùng 2 layer, Space Station đủ.
- Các macro hiện tại đều tái tạo được.
- Gyro toggle tái tạo được.
- M4 -> LS tái tạo được.
- Keyboard Home tái tạo được.
- Controller-specific tuning tốt hơn trong Space Station.

#

## Khi vẫn nên dùng reWASD
Giữ reWASD nếu bạn cần:
- profile tự đổi theo từng game;
- virtual DS4/Xbox/Switch;
- keyboard + mouse + controller group;
- Triple Press;
- multi-button Shortcut;
- Flick Stick;
- app launch / desktop workflows.

#

## Khi kết hợp cả hai
Cấu trúc sạch nhất:
- Space Station: hardware-native.
- reWASD: Windows-level logic chưa có trong Flydigi.

Tránh:
- M1 vừa là Shift trong Flydigi vừa là Shift khác trong reWASD.
- M3 vừa toggle gyro ở Flydigi vừa có macro reWASD.
- tạo virtual Xbox nếu không có lý do rõ ràng.
- để physical + virtual controller cùng phát input vào game nếu game dễ bị double input.

## Kết luận
Với profile hiện tại của bạn, Space Station đã đủ khả năng thay reWASD cho phần gameplay cốt lõi.
reWASD vẫn mạnh hơn như một remapping framework cấp Windows, nhưng không còn bắt buộc chỉ để khai thác đầy đủ Vader 5 Pro.
