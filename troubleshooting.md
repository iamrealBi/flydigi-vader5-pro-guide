# Troubleshooting & Best Practices - Vader 5 Pro

## 1. Nguyên tắc debug
Mỗi lần chỉ kiểm tra một lớp:
1. Controller hardware.
2. Space Station on-board mapping.
3. Windows/joy.cpl.
4. reWASD nếu có.
5. Steam Input.
6. Game.

Nếu bật tất cả cùng lúc, rất khó biết lỗi nằm ở đâu.

## 2. Double input
Triệu chứng:
- menu nhảy hai ô;
- một lần bấm thành hai lần;
- game thấy hai controller;
- Steam hiển thị native Vader và virtual Xbox cùng lúc.

Nguyên nhân thường gặp:
- Space Station đã remap;
- reWASD lại tạo virtual controller;
- physical controller chưa bị hide;
- Steam Input tiếp tục remap.

Cách test sạch:
1. Exit reWASD remap.
2. Tắt Steam Input tạm thời cho game.
3. Mở joy.cpl.
4. Xác nhận chỉ controller mong muốn phản hồi.
5. Test Space Station profile.
6. Bật lại từng lớp một.

## 3. Mixed keyboard/mouse + controller
Space Station tự cảnh báo một số game không xử lý tốt mixed input.

Triệu chứng:
- prompt đổi Xbox <-> keyboard liên tục;
- camera khựng khi gyro-to-mouse;
- nút controller ngừng nhận khi keyboard mapping chạy;
- UI flicker.

Cách xử lý:
- ưu tiên controller-only mapping nếu game hỗ trợ;
- gyro -> Right Stick thay vì Mouse nếu mixed input gây lỗi;
- hoặc map toàn bộ layout sang keyboard/mouse nếu game bắt buộc một input family;
- test trong game trước khi kết luận profile lỗi.

Elden Ring thường nên test kỹ gyro-to-mouse cùng controller output.

## 4. M1/M2/M3/M4 sai
Nếu dùng reWASD:
- đảm bảo đang ở reWASD 9.5.0;
- 9.5 đã sửa lỗi M1/M2 và M3/M4 cho Vader 5 Pro/Apex 5.

Nếu dùng Space Station:
- dùng Listen khi gán activation;
- nhấn đúng nút vật lý;
- kiểm tra label M1/M2/M3/M4 trên UI.

## 5. Layer không quay về Main
Với Space Station:
- nếu muốn layer chỉ active khi giữ, chọn Hold;
- đừng chọn Toggle nếu mong release tự quay lại.

Best.rewasd của bạn:
- M2 = Hold Shift 1.
- M1 = Hold Shift 2.

Nếu thả M1/M2 mà vẫn ở Shift:
- kiểm tra Activation Mode của Layer target.

## 6. Layer Toggle bị kẹt
Toggle yêu cầu lần nhấn kế tiếp để quay lại.
Nếu dùng trigger type không tương thích, Space Station sẽ chặn hoặc cảnh báo.

Best practice:
- Direct + Hold cho temporary modifier.
- Single/Double + Toggle cho mode switch rõ ràng.

## 7. Macro không chạy
Kiểm tra theo thứ tự:
1. Macro có nằm đúng layer không?
2. Mapping đang trỏ đúng Macro ID không?
3. Trigger Mode có phù hợp không?
4. Macro có vượt timeline 65,535 ms không?
5. Action press/release có hợp lệ không?
6. Game có chấp nhận input family của macro không?

Macro Space Station độc lập theo layer.
Copy macro sang layer khác tạo bản copy độc lập.

## 8. Combo Hold bị nhả sớm
Với combo kiểu Best.rewasd:
- A + LB;
- A + RB;
- A + D-pad.

Dùng Trigger Mode:
- Key Combination (Hold).

Không dùng Run Once nếu muốn giữ combo tới khi thả source button.

## 9. Loop macro không dừng đúng
Hai kiểu:
- Loop Stop on Release: thả là cắt ngay.
- Loop Finish Current Cycle: thả nhưng cycle hiện tại chạy xong.

Chọn nhầm kiểu có thể làm bạn tưởng macro bị lag.

## 10. Gyro drift
Triệu chứng:
- camera tự trôi khi đặt tay cầm yên.

Cách xử lý:
1. Đặt controller yên khi kết nối.
2. Deadzone 0% để đo baseline.
3. Nếu drift, tăng 1%.
4. Nếu còn, tăng 2%.
5. Không tăng quá cao nếu không cần.

Deadzone quá lớn làm mất micro-aim.

## 11. Gyro quá nhanh/chậm
Không copy sensitivity reWASD = 1 thành một % cố định.

Tune:
- Linear curve.
- Deadzone thấp.
- chỉnh sensitivity trước.
- sau đó mới thêm midpoint.

Nếu center aim tốt nhưng fast turn yếu:
- tăng gain vùng motion cao bằng curve.

Nếu fast turn tốt nhưng fine aim giật:
- giảm gain đầu curve.

## 12. Gyro đi ngược
Best.rewasd của bạn cố ý:
- up -> mouse down;
- down -> mouse up.

Do đó Space Station:
- Invert Vertical Y = ON.
- Invert Horizontal X = OFF.

Nếu muốn cảm giác tự nhiên khác profile cũ:
- có thể tắt Y inversion, nhưng đó không còn là migrate 1:1.

## 13. Stick drift
Test trong joy.cpl trước game.

Space Station:
- Center Dead Zone.
- Automatic Stick Calibration.
- Manual calibration flow.
- Stick Precision 8-12 bit.

Quy trình:
1. Calibration.
2. Test center.
3. Deadzone nhỏ nhất đủ hết drift.
4. Tune curve sau.

Không dùng deadzone lớn để che lỗi calibration nếu controller có thể calibrate lại.

## 14. Stick diagonal không đạt 100%
Thử Boundary:
- Rectangle nếu game cần full diagonal.
- Circle nếu muốn analog tròn tự nhiên.

Advanced Zone Mapping có thể tạo 4/8-way digital zones nếu game cần hướng rời rạc.

## 15. Trigger bắn quá trễ
Basic:
- thử FPS Instant hoặc Rapid Response.

Advanced:
- giảm Effective Travel.
- đưa Full Output point sớm hơn.
- giữ Output Range phù hợp.

Đừng đồng thời chỉnh quá nhiều tham số.
Test từng thay đổi.

## 16. Trigger action và analog cùng chạy
Đây có thể là hành vi đúng.

Travel Zone target:
- chạy thêm action;
- analog LT/RT curve vẫn output.

Nếu bạn muốn trigger chỉ thành digital button:
- thiết kế mapping khác;
- hoặc disable/neutralize analog output theo capability phù hợp.

## 17. Haptic conflict
Trigger Haptics và Trigger-Bound Grip Feedback xung đột.

Nếu bật Trigger Haptics:
- Space Station có thể yêu cầu tắt Trigger-Bound Grip Feedback.

Nếu bật Trigger-Bound Grip Feedback:
- có thể phải tắt haptic scene.

X-Haptics effect có priority khi enable.

## 18. X-Haptics không mở
X-Haptics cần local Engine.

Kiểm tra:
- Engine đã cài.
- Engine version tương thích.
- Engine đang chạy.
- Space Station đọc được capability.
- assets X-Haptics đã tải.

Nếu Engine unavailable:
- hardware mapping cơ bản vẫn có thể dùng;
- chỉ X-Haptics/feature phụ thuộc Engine bị ảnh hưởng.

## 19. Profile không ghi xuống controller
Phân biệt:
- Local editing.
- On-board profile.

Local changes không tự đồng nghĩa đã ghi xuống controller.

Cần:
1. Save local profile.
2. Apply to Controller.
3. Chọn đúng on-board slot.
4. Chờ Configuration synced.

Nếu apply fail:
- reconnect controller;
- refresh device information;
- retry sync.

## 20. Profile bị ghi đè
Trước khi apply:
- Export backup.
- đặt tên local profile rõ ràng.
- kiểm tra slot.

Naming khuyến nghị:
- ER-Main.
- ER-Gyro.
- FPS.
- Desktop.

## 21. Quick Profile Switching
Nếu bật:
- FN + A/B/X/Y = slot 1/2/3/4.

Nếu game nhận input lạ khi đổi:
- thực hiện combo ngoài combat;
- chờ profile switch hoàn tất;
- test input trước khi tiếp tục.

## 22. Third-party takeover
Setting:
- Allow Third-party Control.

Khi third-party app takeover:
- Space Station có thể pause on-board profile operations để tránh conflict.

Nếu dùng reWASD song song:
- hiểu rõ app nào đang sở hữu/remap input;
- đừng chỉnh profile Flydigi cùng lúc với một app đang takeover nếu UI báo pause.

## 23. Steam Input
Nếu mapping hoạt động ngoài Steam nhưng sai trong game:
- kiểm tra Steam Input.
- test Disabled trước.
- sau đó bật lại nếu game cần.

Steam Input là một remap layer khác.
Nó có thể:
- đổi button;
- tạo virtual behavior;
- làm bạn tưởng Flydigi mapping sai.

## 24. reWASD virtual controller
Nếu dùng virtual controller:
- tránh để physical + virtual cùng điều khiển một player nếu game không hỗ trợ.
- tài liệu reWASD khuyến nghị hide physical gamepad trong nhiều virtual-output scenario.

Nếu không cần virtual controller:
- với Vader 5 Pro, ưu tiên native/on-board để đơn giản hóa pipeline.

## 25. joy.cpl checklist
Trước game:
- controller xuất hiện đúng.
- LS/RS đúng.
- LT/RT analog đúng.
- D-pad đúng.
- không có controller duplicate ngoài dự kiến.

## 26. Quy trình tìm lỗi nhanh
Nếu một nút không đúng:
1. Xác định current layer.
2. Xác định physical source.
3. Xem activator.
4. Xem target.
5. Nếu target Macro, mở Macro ID.
6. Test joy.cpl.
7. Tắt reWASD.
8. Tắt Steam Input.
9. Test lại.
10. Chỉ sau đó mới sửa profile.

## 27. Backup trước khi thử nghiệm
Trước thay đổi lớn:
- Export local profile.
- ghi chú on-board slot đang dùng.
- tránh Factory Reset trừ khi thật sự cần.

Factory Reset có thể xóa:
- settings.
- calibration.
- pairing information.

## 28. Best practice cho Elden Ring profile này
Giữ logic đơn giản:
- Main = gameplay bình thường.
- M2 = Shift 1.
- M1 = Shift 2.
- M3 = gyro toggle.
- M4 = LS.
- macro chỉ dùng cho combo đã có trong Best.rewasd.

Không thêm Turbo vào combat mapping nếu không có mục đích cụ thể.
Không thêm custom curve trước khi migration cơ bản đã pass test.

## 29. Khi nào quay lại reWASD
Quay lại reWASD cho phần thiếu nếu cần:
- Autodetect theo Elden Ring.exe.
- Triple Press.
- Shortcut nhiều nút.
- Virtual controller.
- Device grouping.
- Flick Stick.
- system/app commands.

Không cần quay lại chỉ vì:
- M1-M4;
- 2 Shift layer;
- macro A+button;
- gyro toggle;
- deadzone/curve;
- trigger zones.

Space Station hiện đã cover các mục đó.

## 30. Checklist ổn định cuối cùng
- [ ] Firmware controller ổn.
- [ ] Profile được backup.
- [ ] Mapping Main đúng.
- [ ] Layer Hold đúng.
- [ ] Macro đúng layer.
- [ ] Gyro direction đúng.
- [ ] Deadzone không gây drift.
- [ ] joy.cpl không double input.
- [ ] Steam Input đã được kiểm soát.
- [ ] reWASD chỉ bật nếu thực sự cần.
- [ ] Game test ít nhất 10-15 phút không lỗi mode switch.
