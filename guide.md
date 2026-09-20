# Flydigi Space Station - Vader 5 Pro Complete Guide

## 1. Cấu trúc tổng thể
Space Station hiện tách cấu hình thành bốn lớp khái niệm:
1. On-board Profile: cấu hình thực sự được ghi xuống tay cầm.
2. Local Profile Library: cấu hình lưu cục bộ để chỉnh sửa/copy/import/export.
3. Main Layer + Shift Layers: ngữ cảnh mapping trong mỗi profile.
4. Global Settings: thiết lập áp dụng cho toàn bộ profile.

Vader 5 Pro hiện có 4 on-board profile.
Có thể bật Quick Profile Switching để dùng FN + A/B/X/Y chuyển nhanh profile 1/2/3/4.

Local Profile Library cho phép:
- New Profile.
- Copy.
- Edit.
- Rename.
- Export backup.
- Import backup.
- Restore/replace.
- Apply to Controller.

Lưu ý quan trọng:
- Local editing tự lưu vào máy nhưng chưa ghi xuống controller.
- Chỉ khi chọn Apply to Controller thì profile mới ghi vào on-board slot.
- Trước khi overwrite, Space Station có cơ chế backup profile on-board hiện tại.

## 2. Basic và Advanced
Basic phù hợp khi cần:
- Remap nút đơn giản.
- Preset stick/trigger.
- Gyro cơ bản.
- Vibration và lighting.

Advanced mở thêm:
- Nhiều activator trên cùng một nút.
- Shift layer.
- Macro target.
- Turbo target.
- Simulate analog/mouse/vibration.
- Custom response curve.
- Stick zone mapping.
- Trigger travel zones.
- Advanced gyro curve.

Nếu đã quen reWASD, nên dùng Advanced làm giao diện chính.

## 3. Layer
Mỗi profile có:
- Main Layer.
- Tối đa 3 Shift Layer.

Mỗi Shift Layer có thể lưu riêng:
- Button mappings.
- Stick zones.
- Trigger zones.
- Macros.

Layer có thể Reset hoặc Delete độc lập.
Khi reset layer, các mapping/zone/macro trong layer đó bị xóa.

### Chuyển layer
Target Layer hỗ trợ:
- Hold: giữ nút để ở Shift Layer; thả ra quay về layer trước.
- Toggle: nhấn một lần để vào, nhấn lần nữa để quay lại.

Không phải activator nào cũng cho phép layer switch.
Space Station cảnh báo:
- Pulse trigger không dùng để chuyển layer.
- Một số kiểu Toggle activator xung đột với Toggle layer switch.
- Với layer tạm thời, Direct hoặc Long Press là lựa chọn an toàn.
- Với chuyển layer duy trì, Single/Double Press + Toggle layer là phù hợp.

## 4. Button Mapping - Advanced
Chọn một nút vật lý ở hình controller rồi thêm Trigger Action.

Các activator:
- Direct: active trong lúc giữ nút.
- Single Press: kích hoạt sau một lần nhấn ngắn và nhả.
- Double Press: hai lần nhấn trong cửa sổ thời gian.
- Long Press: giữ đủ lâu mới kích hoạt.
- Press Pulse: phát một xung ngắn khi nhấn.
- Release Pulse: phát một xung ngắn khi nhả.
- Toggle: nhấn lần đầu bật, nhấn lần sau tắt.

Một nút có thể có nhiều Trigger Action cùng lúc.

### Target của mapping
Space Station hiện expose các target:
- Controller.
- Keyboard.
- Mouse.
- Media.
- Turbo.
- Layer.
- Macro.
- Simulate.
- Disable.

Controller target gồm:
- LT/LB/RT/RB.
- A/B/X/Y.
- D-pad.
- LS/RS.
- Các input controller tương thích khác.

Keyboard target dùng để gán phím Windows/game trực tiếp.
Mouse target gồm:
- Left/Right/Middle.
- Side button Back/Forward.
- Các mouse action được hỗ trợ bởi mapping UI.

Media target gồm:
- Play/Pause.
- Next/Previous Track.
- Stop.
- Volume +/-.
- Mute.
- Sleep/Wake.

Disable dùng để vô hiệu hóa native action của nút.

### Turbo
Turbo phát target lặp lại theo interval.
Một số trigger type không hỗ trợ Turbo.
UI khuyến nghị Direct, Long Press hoặc Toggle khi dùng Turbo.

#

## Simulate
Simulate có thể tạo:
- Left/Right Stick deflection.
- Linear LT/RT.
- Mouse movement.
- Mouse wheel.
- Vibration output.

Đây là tính năng mạnh khi cần analog output mà không muốn viết macro nhiều bước.

## 5. Stick - Basic
Mỗi stick có thể chỉnh riêng Left/Right.

Controller Emulation có các preset:
- Standard.
- Smooth.
- Fast.
- Dynamic.
- Gentle.

Ý nghĩa thực dụng:
- Standard: cân bằng.
- Smooth: mềm ở vùng center, hợp aim/chạy xe chính xác.
- Fast: tăng phản hồi sớm, hợp FPS/platform.
- Dynamic: center chính xác nhưng mid-range nhanh.
- Gentle: giảm saturation gắt gần full tilt.Stick Basic còn có:
- Center Dead Zone.
- Boundary: Circle hoặc Rectangle.
- Invert Horizontal X.
- Invert Vertical Y.
- Outer-ring Mapping.

Outer-ring Mapping:
- Gán action khi stick đi vào vùng ngoài.
- Có thể chỉnh độ rộng outer ring.
- Phù hợp Sprint, Run, modifier hoặc action khi đẩy stick hết biên.

Ngoài Controller Emulation, UI còn có Keyboard WASD mode cho game cũ không hỗ trợ analog stick.

## 6. Stick - Advanced
Advanced Stick có ba khối:
1. Response Curve.
2. Zone Mapping.
3. Stick Settings.

Response Curve:
- Linear mặc định.
- Tối đa 2 midpoint trong UI hiện tại của Vader 5 Pro.
- Có Add Point, Remove Point, Reset Line.
- Dùng để kiểm soát gain từ center tới full tilt.

Stick Settings:
- Boundary Rectangle/Circle.
- Invert X/Y.
- Các thuộc tính tương ứng của stick hiện tại.

### Zone Mapping
Các Direction Mode:
- 8-way.
- 4-way.
- 4-way Overlap.

Có thể tạo nhiều segment theo hướng và radial range.
Mỗi segment có target riêng.

Ứng dụng:
- Stick ngoài 80% = Sprint.
- Hướng chéo = macro riêng.
- Low radius = đi bộ, high radius = chạy.
- 4-way overlap = cho phép hai hướng cạnh nhau cùng kích hoạt ở biên.

## 7. Trigger - Basic
Chọn Both Triggers, LT hoặc RT.

Regular Response presets:
- Linear.
- FPS Instant.
- Rapid Response.

Linear:
- Toàn bộ hành trình cho output tuyến tính.

FPS Instant:
- Rút ngắn hành trình đầu để đạt firing nhanh.

Rapid Response:
- Đạt output tối đa sớm hơn preset Linear.

## 8. Trigger - Advanced
Advanced Trigger cho:
- Custom response curve.
- Effective Travel.
- Output Range.
- Response Start.
- Full Output point.
- Tối đa 2 midpoint.
- Ba Travel Zones.

Travel Zones:
- Light Press.
- Medium Press.
- Heavy Press.

Zone target chạy thêm trong khi analog LT/RT curve vẫn tiếp tục output.
Điều này khác remap trigger thành nút digital: analog vẫn còn.

Ví dụ:
- Light = Aim.
- Medium = Fire.
- Heavy = Macro hoặc action thứ ba.

Khi thay đổi input range, ba zone sẽ scale tương ứng.

## 9. Trigger Haptics
Space Station có trigger haptic scene riêng:
- Pistol, Rifle, Shotgun, Sniper Rifle.
- Machine Gun, Light Machine Gun, Submachine Gun.
- Sword, Blade, Dagger, Axe, Club.Trigger haptic có thể chỉnh:
- Trigger Travel: Short/Medium/Long.
- Trigger Frequency: Low/Medium/High.
- Trigger Force.
- Activation Mode: Once/Loop tùy scene.

Xung đột cần nhớ:
- Trigger haptics và Trigger-Bound Grip Feedback không thể active đồng thời.
- Bật một bên có thể yêu cầu tắt bên kia.

## 10. Motion Control / Gyro
Target mode:
- Off.
- Left Stick.
- Right Stick.
- Mouse.

Activation:
- Hold.
- Toggle.

Có tối đa 2 Activation Buttons:
- Primary.
- Secondary.

Basic Mouse gyro:
- Sensitivity.
- Mouse Dead Zone.
- Invert X.
- Invert Y.

Advanced gyro thêm:
- Response Curve.
- Tối đa 2 midpoint trong UI hiện tại.

### Tune gyro thực tế
Không đổi sensitivity từ reWASD sang Space Station theo tỷ lệ 1:1.
Hai app dùng scale khác nhau.

Quy trình tune:
1. Chọn Mouse.
2. Deadzone 0-2% nếu gyro ổn định.
3. Curve Linear trước.
4. Tắt acceleration trong game nếu có.
5. Chọn một điểm cố định trong game.
6. Xoay controller theo góc quen thuộc.
7. Tăng/giảm sensitivity tới khi tốc độ aim tự nhiên.
8. Chỉ thêm midpoint khi cần fine aim + fast turn khác nhau.

Nếu camera đi ngược theo chiều dọc:
- bật Invert Vertical Y.
Nếu ngang ngược:
- bật Invert Horizontal X.

## 11. Vibration
Có ba nhánh chính:
- Native Grip Vibration.
- Left Trigger-Bound Grip Feedback.
- Right Trigger-Bound Grip Feedback.

Mỗi nhánh có On/Off và Strength.
Có Test Vibration để kiểm tra trực tiếp.

## 12. X-Haptics
Space Station hiện có lớp X-Haptics cần local Engine.

Các mode được expose:
- Real-time Audio Haptics.
- Adaptive Trigger.
- UDP Haptics.

Real-time Audio:
- Biến âm thanh thành haptic.
- Có grip/trigger channel.
- Strength.
- Style.
- Grip attenuation khi trigger đang nhấn.
- Auto sleep và thời gian chờ.

Adaptive Trigger:
- Sustained trigger resistance.
- Cấu hình strength.
- Có cài/gỡ cấu hình theo scope.

UDP Haptics:
- Dùng telemetry game, phù hợp racing/sim.
- Có preset Standard và Custom.
- Custom expose strength/sensitivity/curve khi Engine descriptor hỗ trợ.

Có Global profile và per-game profile.
Per-game profile ưu tiên global khi game đang chạy.

## 13. Lighting
Modes:
- Default.
- Streaming.
- Breathing.
- Gradient.
- Solid.
- Off.

Gradient/Breathing cho phép nhiều màu.
Có:
- Color picker RGB.
- Saturation.
- Brightness.
- Cycle Speed.
- Add/Remove color.

## 14. Macro
Macro được lưu riêng theo từng layer.
Giới hạn xác nhận được từ UI:
- Tối đa 10 macro mỗi layer.
- Tổng timeline của một macro không vượt 65,535 ms.

Macro action có thể được:
- Add thủ công.
- Record từ controller.
- Reorder bằng drag.
- Chỉnh delay từng action.

Action type:
- Press.
- Release.
- Push analog direction.
- Center/recenter.Macro target có thể gồm:
- Controller buttons.
- Stick directions.
- Linear trigger values.
- Keyboard.
- Mouse.
- Media.
- Turbo.
- Layer operation.

Trigger Mode:
- Key Combination (Hold).
- Run Once (Until Complete).
- Loop (Stop on Release).
- Loop (Finish Current Cycle).

Key Combination (Hold):
- Press các target theo thứ tự.
- Giữ chúng trong lúc trigger đang giữ.
- Release toàn bộ khi thả trigger.

Run Once:
- Chạm một lần để chạy hết sequence.
- Không ngắt giữa sequence.

Loop Stop on Release:
- Lặp liên tục.
- Thả nút thì dừng ngay, kể cả giữa cycle.

Loop Finish Current Cycle:
- Lặp khi giữ.
- Thả nút thì hoàn thành cycle hiện tại rồi mới dừng.Macro editor kiểm tra consistency:
- Press/Push phải có Release/Center tương ứng nếu sequence yêu cầu.
- Không cho release trước press.
- Không cho cùng target start lại khi chưa kết thúc.
- Không cho timestamp đi ngược.
- Delay phải là số nguyên không âm.

Macro có thể Copy to Other Layers.
Bản copy độc lập với macro nguồn sau khi copy.
Share-code import/export hiện được đánh dấu coming soon.

## 15. Global Settings
Controller Settings:
- Quick Profile Switching.
- Turbo Button Features.
- Map Logo to XBOX Button.
- Allow Third-party Control.
- Controller Sleep.

Quick Profile Switching:
- FN + A/B/X/Y đổi profile 1/2/3/4.

Turbo Button Features:
- Cho phép Turbo key set rapid fire.
- Cho phép set extension buttons theo flow trực tiếp trên controller.

Third-party Control:
- Khi bật, Space Station tạm dừng thao tác profile nếu app khác đang takeover controller.Controller Sleep:
- 1 minute.
- 5 minutes.
- 15 minutes.
- 1 hour.
- 3 hours.
- Never.

Global Stick Settings:
- Automatic Stick Calibration.
- Stick Precision: 8/9/10/11/12 bit.
- Precision áp dụng cho tất cả profiles.

Standalone Actions:
- Factory Reset.
- Electronic Manual.
- Firmware Update.

Factory Reset xóa:
- Controller settings.
- Calibration data.
- Pairing information.

Firmware page đọc:
- Main firmware.
- Receiver/RF/SI/screen components tùy thiết bị.
- Có sequential firmware update và recovery flow.

## 16. Quy trình tạo profile từ đầu
1. Chọn một on-board slot chưa dùng.
2. Backup profile hiện tại.
3. Chọn Advanced.
4. Tạo Shift Layer cần dùng.
5. Cấu hình button mapping.
6. Cấu hình Stick.
7. Cấu hình Trigger.
8. Cấu hình Motion Control.
9. Tạo Macro.
10. Kiểm tra Vibration/Haptics.11. Chọn Lighting.
12. Test từng layer trước khi Apply.
13. Apply profile xuống controller.
14. Mở joy.cpl kiểm tra input native.
15. Mở game và test từng nhóm chức năng.

## 17. Thứ tự tune tối ưu
Đừng tune mọi thứ cùng lúc.

Thứ tự nên dùng:
1. Button mapping.
2. Stick deadzone.
3. Stick curve.
4. Trigger response.
5. Gyro sensitivity/deadzone.
6. Layer.
7. Macro.
8. Haptics.

Lý do:
- Nếu mapping cơ bản chưa ổn, macro/layer khó debug.
- Nếu stick/gyro chưa ổn, bạn dễ nhầm lỗi input với lỗi macro.
- Haptics nên làm cuối vì không ảnh hưởng logic control.

## 18. Khi nào nên dùng Basic
Dùng Basic nếu:
- Chỉ muốn preset.
- Không dùng macro/layer.
- Muốn profile dễ bảo trì.
- Cấu hình cho người khác sử dụng.

Dùng Advanced nếu:
- Muốn tái tạo Best.rewasd.
- Muốn nhiều action trên một nút.
- Muốn zone/curve riêng.
- Muốn macro hoặc layer.
