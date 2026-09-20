# Migrate Best.rewasd sang Flydigi Space Station — bản đã kiểm tra lại

## Mục tiêu

Tái tạo **logic gameplay cốt lõi** của Best.rewasd trên VADER 5 Pro bằng Space Station.

Profile nguồn:
- game: Elden Ring;
- process: eldenring.exe;
- reWASD: 9.5.0;
- output nguồn: Virtual Xbox 360;
- có Main Layer + 2 Shift Layer;
- gyro → mouse;
- M3 dùng để Toggle gyro.

Nếu chưa quen Direct / Hold / Toggle / Macro, đọc [Từ điển thuật ngữ](glossary.md) trước.

---

## 1. Trạng thái xác minh từng mapping

| Source trong Best.rewasd | Output | Trạng thái khi chuyển sang Space Station |
|---|---|---|
| M4 | LS/L3 | ✅ Đã xác minh trên UI, hiện có mapping M4 → LS |
| M2 | Hold Shift 1 | ✅ Space Station có Layer + Hold |
| M1 | Hold Shift 2 | ✅ Space Station có Layer + Hold |
| M3 | Toggle gyro | ✅ Motion Control có Toggle; activation cần gán M3 |
| A/B/X/Y trong Shift 1 | D-pad | ✅ Khả thi |
| LB/RB trong Shift 1 | A + LB/RB | ✅ Macro Hold phù hợp |
| A/B/X/Y trong Shift 2 | A + D-pad | ✅ Macro Hold phù hợp |
| Home | Keyboard Home | ⚠️ Source Home không hiện trên visual Button Mapping đang kiểm tra |
| Pair/Capture | X | ⚠️ Source Pair/Capture không hiện trên visual Button Mapping hiện tại |
| Back | B | ⚠️ Source Back không hiện trên visual Button Mapping hiện tại |

Điểm quan trọng:

> “Có trong Best.rewasd” không tự động nghĩa là “source đó được Space Station UI hiện tại cho chọn”.

Do đó migration chính xác nhất hiện nay là **migrate gameplay core trước**, còn Home/Pair/Back phải kiểm tra lại nếu UI/firmware sau này expose.

---

## 2. Chuẩn bị trước khi sửa

1. Chọn đúng on-board slot.
2. Export backup.
3. Chọn **Advanced**.
4. Tạm tắt reWASD remap khi test.
5. Tạm tắt Steam Input nếu đang debug double input.

![Màn hình cấu hình Advanced](images/02-button-mapping-overview.png)
## 3. Tạo hai Shift Layer

Bấm **Main Layer** → Create Shift Layer hai lần.

![Menu Layer thật](images/03-layer-menu.png)

Cần:
- Main Layer;
- Shift Layer 1;
- Shift Layer 2.

Không cần layer thứ ba.

### M2 → Shift Layer 1

Trong Main:
1. chọn M2;
2. Add Trigger;
3. chọn kiểu phù hợp để giữ;
4. Target = Layer;
5. chọn Shift Layer 1;
6. Activation Mode = Hold.

Hành vi mong muốn:
- giữ M2 → vào Shift 1;
- thả M2 → về Main.

### M1 → Shift Layer 2

Làm tương tự:
- giữ M1 → Shift 2;
- thả → Main.

**Không dùng Toggle** nếu bạn muốn thả nút là tự quay về.

---

## 4. M4 → LS

Đây là mapping đã thấy trực tiếp trên UI.

![M4 đang map sang LS](images/04-button-mapping-m4.png)

Cấu hình:
- Source = M4;
- Activator = Direct;
- Target = Controller;
- Output = LS.

Direct ở đây nghĩa là:
- giữ M4 → LS bị giữ;
- thả M4 → LS nhả.

---

## 5. Gyro → Mouse và M3 Toggle

Mở **Motion Control**.

![Motion Control Basic](images/10-motion-basic.png)

Thiết lập mục tiêu:
- Mode = Mouse;
- Activation Mode = Toggle;
- Primary Activation Button = M3;
- Secondary = trống;
- Invert X = Off;
- Invert Y = On;
- Dead Zone = bắt đầu 0%;
- Curve = Linear.

### Vì sao Invert Y = On?

Best.rewasd nguồn có:
- gyro up → mouse down;
- gyro down → mouse up.

Do đó để giữ hành vi cũ, trục dọc cần đảo.

### Sensitivity

Không đổi reWASD sensitivity = 1 thành một phần trăm cố định.

Điểm bắt đầu:
- giữ mức Space Station hiện tại;
- test trong game;
- chỉnh Sensitivity trước;
- sau đó mới chỉnh Curve.

Nếu controller nằm yên mà camera trôi:
- thử Dead Zone 1%;
- nếu còn, thử 2%.

![Motion Control Advanced](images/11-motion-advanced.png)
## 6. Shift Layer 1

Best.rewasd cần:

| Source | Output |
|---|---|
| A | D-pad Down |
| B | D-pad Right |
| X | D-pad Left |
| Y | D-pad Up |
| LB | A + LB |
| RB | A + RB |

### A/B/X/Y

Trong Shift Layer 1:
- A → D-pad Down;
- B → D-pad Right;
- X → D-pad Left;
- Y → D-pad Up.

Dùng Direct vì muốn output tồn tại trong lúc giữ source.

### LB → A + LB

Tạo Macro trong Shift Layer 1:
- Trigger Mode = Key Combination (Hold);
- target 1 = A;
- target 2 = LB.

Sau đó:
- LB → Macro vừa tạo.

### RB → A + RB

Tạo macro tương tự:
- A;
- RB.

![Macro Editor](images/19-macro-editor.png)

Key Combination (Hold) phù hợp vì:
- giữ LB/RB source → combo cùng được giữ;
- thả source → cả hai target được nhả.

---

## 7. Shift Layer 2

Best.rewasd cần:

| Source | Output |
|---|---|
| A | A + D-pad Down |
| B | A + D-pad Right |
| X | A + D-pad Left |
| Y | A + D-pad Up |

Tạo 4 macro kiểu **Key Combination (Hold)**:
1. A + D-pad Down;
2. A + D-pad Right;
3. A + D-pad Left;
4. A + D-pad Up.

Sau đó map:
- source A → macro 1;
- B → macro 2;
- X → macro 3;
- Y → macro 4.

Lưu ý:
- output A phải nằm bên trong macro;
- không trông chờ native A tiếp tục chạy sau khi source đã được remap.
## 8. Home / Pair-Capture / Back — xử lý thế nào?

Bản cũ từng hướng dẫn:
- Home → Keyboard Home;
- Pair/Capture → X;
- Back → B.

Sau khi rà UI thật, ba source này **không xuất hiện trên visual Button Mapping hiện tại**.

Vì vậy không nên bảo người đọc “bấm Home trên hình controller” khi UI không có.

Cách xử lý thực tế:
1. ưu tiên hoàn tất phần gameplay core trước;
2. kiểm tra firmware/UI mới nếu sau này các system button được expose;
3. nếu ba mapping này thật sự cần, có thể giữ reWASD chỉ cho phần Windows-level đó.

Đây là một trường hợp dùng hybrid hợp lý:
- Space Station = gameplay/hardware;
- reWASD = system button chưa được Space Station expose.

---

## 9. Virtual Xbox 360 trong Best.rewasd

Best.rewasd tạo Virtual Xbox 360.

Space Station không cần “copy” mục này.

Khi test bản Flydigi:
1. tắt reWASD remap;
2. giữ Vader ở mode PC/XInput phù hợp;
3. mở joy.cpl;
4. đảm bảo chỉ input mong muốn phản hồi;
5. mở Elden Ring.

Chỉ bật lại virtual controller nếu bạn xác định rõ game cần nó.

---

## 10. Thứ tự test

### Main Layer

1. A/B/X/Y native.
2. M4 → LS.
3. M1/M2 chưa giữ → nút bình thường.
4. test LT/RT/stick.

### Shift Layer 1

1. giữ M2;
2. A/B/X/Y phải thành D-pad;
3. LB/RB phải phát combo;
4. thả M2;
5. A/B/X/Y trở về Main.

### Shift Layer 2

1. giữ M1;
2. A/B/X/Y phải phát A + D-pad;
3. thả M1;
4. trở về Main.

### Gyro

1. bấm M3 → gyro ON;
2. xoay trái/phải kiểm tra X;
3. ngẩng/hạ kiểm tra Y;
4. bấm M3 lần nữa → OFF.
## 11. Checklist trước Apply

- [ ] Đúng on-board slot.
- [ ] Có backup.
- [ ] M4 = Direct → LS.
- [ ] M2 = Hold Shift 1.
- [ ] M1 = Hold Shift 2.
- [ ] Shift 1 A/B/X/Y đúng D-pad.
- [ ] Shift 1 LB/RB đúng macro A + shoulder.
- [ ] Shift 2 đủ 4 macro.
- [ ] Gyro = Mouse.
- [ ] Gyro = Toggle.
- [ ] M3 là activation button.
- [ ] Invert Y ON nếu muốn giữ đúng Best.rewasd.
- [ ] joy.cpl không double input.
- [ ] Home/Pair/Back chưa được coi là đã migrate nếu UI chưa expose.

## 12. Cái gì copy logic được và cái gì không?

### Copy logic tốt
- M-button mapping;
- layer Hold;
- macro combo;
- gyro direction;
- gyro Toggle.

### Không copy số học 1:1
- gyro sensitivity;
- smoothing;
- response curve;
- timing cảm giác giữa hai app.

### Chưa xác minh 1:1
- Home/Pair/Back source;
- virtual controller pipeline;
- system-level behavior.

## Kết quả mong muốn

Sau migration core:
- Elden Ring vẫn có layer/macro/gyro chính;
- reWASD không còn bắt buộc cho gameplay core;
- nếu cần, reWASD chỉ xử lý phần Windows-level chưa được Flydigi expose.
