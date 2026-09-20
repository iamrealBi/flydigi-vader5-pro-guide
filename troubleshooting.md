# Troubleshooting & Best Practices — VADER 5 Pro

## Nguyên tắc lớn nhất: tách từng lớp ra để test

Pipeline có thể gồm:
1. controller hardware;
2. Space Station on-board mapping;
3. Windows/XInput;
4. reWASD;
5. Steam Input;
6. game.

Nếu bật tất cả cùng lúc, một lỗi nhỏ có thể nhìn giống lỗi controller.

Nếu gặp từ như Double Input, Mixed Input, Dead Zone, Toggle hoặc Virtual Controller, xem [Từ điển thuật ngữ](glossary.md).

---

## 1. Bấm một lần nhưng game nhận hai lần — Double Input

Triệu chứng:
- menu nhảy hai ô;
- bấm một lần thành hai;
- hai controller xuất hiện;
- input cảm giác “nhân đôi”.

Nguyên nhân thường gặp:
- Vader vật lý vẫn hoạt động;
- reWASD tạo Virtual Xbox;
- Steam Input lại tạo thêm lớp remap.

### Cách test sạch

1. tắt reWASD remap;
2. tắt Steam Input tạm thời;
3. mở joy.cpl;
4. xác nhận chỉ controller mong muốn phản hồi;
5. test Space Station;
6. bật lại từng lớp một.

Đừng sửa mapping trước khi biết chắc lỗi không phải double input.

---

## 2. Prompt Xbox/keyboard đổi liên tục — Mixed Input

Mixed Input = game nhận controller và keyboard/mouse cùng lúc.

Ví dụ:
- LS = controller;
- gyro = Mouse.

Triệu chứng:
- icon nút đổi Xbox ↔ keyboard;
- camera khựng;
- UI flicker;
- một input tạm chặn input kia.

Cách xử lý:
- thử gyro → Right Stick thay vì Mouse;
- hoặc dùng controller-only;
- hoặc map toàn bộ layout thành keyboard/mouse nếu game phù hợp.
## 3. M1/M2/M3/M4 bị nhận sai trong reWASD

Đảm bảo reWASD là 9.5.0 hoặc mới hơn trong nhánh hiện tại.

Release 9.5 chính thức sửa lỗi M1/M2 và M3/M4 trên Vader 5 Pro/Apex 5.

Nếu dùng Space Station:
- chọn đúng label vật lý;
- dùng Listen khi gán activation nếu UI yêu cầu;
- test từng M-button riêng.

![Button Mapping thật](images/02-button-mapping-overview.png)

---

## 4. Layer không quay về Main

Nếu muốn:
- giữ M2 → Shift 1;
- thả M2 → Main;

thì layer phải dùng **Hold**, không phải Toggle.

Toggle hoạt động như công tắc:
- bấm lần 1 → vào;
- bấm lần 2 → ra.

![Menu Layer](images/03-layer-menu.png)

---

## 5. Không hiểu Press Pulse / Release Pulse

Press Pulse:
- target được nhấn + nhả cực nhanh lúc source vừa được ấn xuống.

Release Pulse:
- target được nhấn + nhả cực nhanh lúc source được thả.

Nó **không giữ target** theo thời gian source đang được giữ.

![Activator thật](images/05-button-activators.png)

Nếu muốn target giữ theo source, dùng Direct.

---

## 6. Macro không chạy

Kiểm tra:
1. macro có nằm đúng layer không;
2. mapping có trỏ đúng macro không;
3. Trigger Mode đúng không;
4. action Press/Release hợp lệ không;
5. delay có hợp lý không;
6. game có nhận đúng input family không.

![Macro Editor](images/19-macro-editor.png)

### Combo bị nhả sớm

Nếu cần A + LB giữ cùng nhau:
- dùng Key Combination (Hold);
- không dùng Run Once.

### Loop dừng sai thời điểm

- Loop Stop on Release = thả là dừng ngay.
- Loop Finish Current Cycle = thả nhưng chạy hết vòng đang dở.
## 7. Gyro tự trôi

Triệu chứng:
- đặt controller yên;
- camera vẫn tự dịch.

Cách xử lý:
1. để controller yên khi kết nối;
2. Dead Zone 0% để quan sát baseline;
3. nếu drift, tăng 1%;
4. nếu còn, tăng 2%;
5. đừng tăng quá cao nếu không cần.

![Motion Control Basic](images/10-motion-basic.png)

Dead Zone cao làm mất micro-aim.

## 8. Gyro quá nhanh hoặc quá chậm

Đừng copy sensitivity reWASD = 1 thành một % cố định.

Quy trình:
1. Linear curve;
2. dead zone thấp;
3. chỉnh sensitivity;
4. sau đó mới chỉnh curve.

![Motion Control Advanced](images/11-motion-advanced.png)

Nếu:
- fine aim tốt nhưng quay nhanh yếu → tăng gain cuối curve;
- quay nhanh tốt nhưng micro-aim giật → giảm gain đầu curve.

## 9. Gyro đi ngược

Profile Best.rewasd nguồn:
- up → mouse down;
- down → mouse up.

Muốn giữ đúng hành vi nguồn:
- Invert Y = ON;
- Invert X = OFF.

---

## 10. Stick Drift

Test trước bằng joy.cpl.

Quy trình:
1. calibration;
2. xem tâm;
3. chỉ tăng Dead Zone vừa đủ;
4. sau đó mới tune curve.

![Stick Basic](images/06-stick-basic.png)

Không dùng Dead Zone lớn để che một lỗi calibration có thể sửa.

## 11. Diagonal không đạt như mong muốn

Thử Boundary:
- Circle = biên tròn;
- Rectangle = dễ đạt output lớn ở góc chéo.

![Stick Advanced](images/07-stick-advanced.png)
## 12. Trigger bắn quá trễ

Basic:
- thử FPS Instant;
- hoặc Rapid Response.

![Trigger Basic](images/08-trigger-basic.png)

Advanced:
- giảm Effective Travel;
- chỉnh Full Output/Output Range;
- thay từng thông số một.

![Trigger Advanced](images/09-trigger-advanced.png)

## 13. Travel Zone chạy nhưng LT/RT vẫn analog

Đây có thể là hành vi đúng.

Travel Zone:
- phát thêm action;
- analog LT/RT vẫn tiếp tục output.

Zone không đồng nghĩa “biến trigger thành nút digital”.

## 14. Không thấy Trigger Haptics

Đây **không phải lỗi của bạn**.

Sau khi kiểm tra UI thật của Vader 5 Pro hiện tại:
- không thấy Trigger Mode;
- không thấy Pistol/Rifle/Shotgun/Sword;
- không thấy scene haptic ở tab Trigger.

Các chuỗi này tồn tại trong code Space Station nhưng chưa được UI hiện tại expose.

Do đó đừng mất thời gian tìm một menu không có.

## 15. Trigger-Bound Grip Feedback khác Trigger Haptics thế nào?

Trigger-Bound Grip Feedback:
- LT/RT điều khiển rung ở grip;
- nằm trong Vibration.

Trigger Haptics:
- capability haptic ở trigger;
- hiện chưa thấy UI usable trên Vader 5 Pro đang kiểm tra.

![Vibration thật](images/12-vibration.png)

## 16. Không thấy X-Haptics

Code có X-Haptics Engine và các mode nâng cao, nhưng UI cấu hình chính hiện tại không có tab X-Haptics.

Xem nó như capability phụ thuộc model/Engine, không phải phần bắt buộc của guide.
## 17. Profile chỉnh rồi nhưng controller không đổi

Phân biệt:
- Local Profile;
- On-board Profile.

Local thay đổi không tự động nghĩa là controller đã được ghi.

Cần:
1. chỉnh local;
2. Apply to Controller;
3. chọn đúng slot;
4. chờ sync;
5. test lại.

![Profile Library thật](images/17-profile-manage.png)

## 18. Profile bị ghi đè nhầm

Trước thay đổi lớn:
- Export backup;
- ghi chú slot;
- đặt tên profile rõ;
- kiểm tra slot trước Apply.

## 19. Quick Profile Switching gây nhầm

Nếu bật FN + A/B/X/Y đổi profile:
- đổi ngoài combat;
- chờ profile switch xong;
- test một nút trước khi chơi tiếp.

## 20. Third-party Control / reWASD conflict

Nếu bật Allow Third-party Control:
- Space Station có thể pause config operation khi app khác takeover.

Nếu dùng reWASD:
- đừng vừa chỉnh Flydigi vừa remap live ở reWASD nếu không cần;
- xác định app nào đang sở hữu pipeline.

![Settings thật](images/15-settings.png)

## 21. Steam Input làm mapping sai

Nếu mapping đúng ngoài Steam nhưng sai trong game:
1. disable Steam Input tạm;
2. test lại;
3. chỉ bật lại nếu game cần.

Steam Input là thêm một lớp mapping khác.
## 22. joy.cpl nên kiểm tra gì?

Trước game:
- LS/RS đúng;
- LT/RT analog đúng;
- D-pad đúng;
- không có duplicate controller ngoài dự kiến.

joy.cpl không phải công cụ test hoàn hảo cho mọi M-button, nhưng rất tốt để xác nhận output controller cơ bản.

## 23. Firmware / calibration

Settings hiện cho:
- Automatic Stick Calibration;
- Stick Precision;
- Firmware 7.2.2.1;
- Component Firmware Versions;
- Firmware Update.

![Firmware component thật](images/16-firmware-components.png)

Không firmware update khi:
- pin yếu;
- kết nối chập chờn;
- app khác đang takeover.

## 24. Factory Reset

Chỉ dùng cuối cùng.

Có thể xóa:
- settings;
- calibration;
- pairing.

Backup trước.

---

## 25. Flow tìm lỗi nhanh

### Một nút không đúng

1. Current Layer?
2. Source nào?
3. Activator gì?
4. Target gì?
5. Macro nào?
6. joy.cpl?
7. reWASD OFF?
8. Steam Input OFF?
9. test lại.

### Camera/gyro sai

1. Mouse hay Right Stick?
2. Hold hay Toggle?
3. Invert?
4. Dead Zone?
5. Sensitivity?
6. Curve?

### Game bấm hai lần

1. physical controller;
2. virtual controller;
3. Steam Input;
4. device group;
5. hide/exclusive access.

---

## 26. Checklist ổn định cuối

- [ ] đúng firmware;
- [ ] có backup;
- [ ] Main mapping đúng;
- [ ] Layer dùng đúng Hold/Toggle;
- [ ] Macro đúng layer;
- [ ] Gyro không drift;
- [ ] Dead Zone vừa đủ;
- [ ] joy.cpl không double input;
- [ ] Steam Input được kiểm soát;
- [ ] reWASD chỉ bật khi có lý do rõ;
- [ ] game test thực tế trước khi coi config hoàn tất.
