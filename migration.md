# Migrate Best.rewasd sang Flydigi Space Station

## 1. Profile nguồn
File: `Best.rewasd`
Game: Elden Ring
Process: `eldenring.exe`
reWASD appVersion: 9.5.0
Virtual output: Xbox 360

Profile dùng:
- Main layer.
- Shift 1.
- Shift 2.
- Gyro -> Mouse.
- Một command Toggle Gyro.

Không có logic nào trong file này cần hơn 3 Shift Layer.
Vì vậy Space Station đủ capacity để tái tạo cấu trúc hiện tại.

## 2. Mapping Main Layer - chính xác từ file

| Nút Flydigi | reWASD output | Space Station tương đương |
|---|---|---|
| Home | Keyboard HOME | Keyboard -> Home |
| Pair/Capture | X | Controller -> X |
| Back | B | Controller -> B |
| M4 | LS/L3 | Controller -> LS |
| M3 | Toggle gyro | Motion Control activation -> M3 -> Toggle |
| M2 | Hold Shift 1 | Layer -> Shift Layer 1 -> Hold |
| M1 | Hold Shift 2 | Layer -> Shift Layer 2 -> Hold |

Gyro:
- Gyro Up -> Mouse Down.
- Gyro Down -> Mouse Up.
- Gyro Left -> Mouse Left.
- Gyro Right -> Mouse Right.

Suy ra:
- Horizontal không đảo.
- Vertical đảo.

## 3. Tạo layer
Trong Advanced:
1. Mở menu Main Layer.
2. Create Shift Layer.
3. Tạo Shift Layer 1.
4. Create Shift Layer lần nữa.
5. Tạo Shift Layer 2.

Không cần Shift Layer 3.

#

## M2
Main Layer:
1. Chọn M2.
2. Add Trigger.
3. Direct.
4. Target Layer.
5. Shift Layer 1.
6. Activation Mode = Hold.

Mục tiêu:
- Giữ M2 -> Shift 1.
- Thả M2 -> Main.

#

## M1
Làm tương tự:
- M1 -> Shift Layer 2 -> Hold.

Không cần macro riêng để quay về Main; Hold layer tự quay lại khi release.

## 4. Main Layer button mapping
Home:
- Direct -> Keyboard -> Home.

Pair/Capture:
- Direct -> Controller -> X.

Back:
- Direct -> Controller -> B.

M4:
- Direct -> Controller -> LS.

## 5. Gyro tương đương Best.rewasd
Mở Motion Control ở Main Layer.

Thiết lập:
- Motion Control Mode = Mouse.
- Activation Mode = Toggle.
- Primary Activation Button = M3.
- Secondary = để trống.
- Invert Horizontal X = Off.
- Invert Vertical Y = On.
- Mouse Dead Zone = bắt đầu 0%.
- Response Curve = Linear.

#

## Sensitivity
Best.rewasd ghi:
- sensitivity = 1.
- sensitivityY = 1.
- smoothing = 1.

Không thể đổi trực tiếp các giá trị này sang % của Space Station.
Hai app dùng thang và pipeline khác nhau.

Điểm bắt đầu hợp lý:
- Space Station sensitivity: giữ mức hiện tại 20% để test.
- Deadzone 0%.
- Curve Linear.

Sau đó tune theo game.
Nếu drift khi controller nằm yên:
- tăng Dead Zone lên 1-2%.

Nếu aim quá chậm:
- tăng sensitivity trước khi sửa curve.

Nếu fine aim ổn nhưng quay nhanh quá chậm:
- dùng midpoint để tăng gain ở vùng motion cao.

## 6. Shift Layer 1
Best.rewasd mapping:

| Source | Output |
|---|---|
| A | D-pad Down |
| B | D-pad Right |
| X | D-pad Left |
| Y | D-pad Up |
| LB | A + LB |
| RB | A + RB |

#

## A/B/X/Y
Trong Shift Layer 1:
- A -> Direct -> Controller -> D-pad Down.
- B -> Direct -> Controller -> D-pad Right.
- X -> Direct -> Controller -> D-pad Left.
- Y -> Direct -> Controller -> D-pad Up.

#

## Macro A + LB
Manage Macros trong Shift Layer 1:
1. New Macro.
2. Trigger Mode = Key Combination (Hold).
3. Add Controller A.
4. Add Controller LB.
5. Save.

Sau đó:
- Chọn LB trong Shift Layer 1.
- Direct -> Macro -> macro A+LB.

Hành vi cần đạt:
- Giữ LB -> A và LB cùng được giữ.
- Thả LB -> cả hai release.

### Macro A + RB
Tạo macro thứ hai:
1. Trigger Mode = Key Combination (Hold).
2. Controller A.
3. Controller RB.

Mapping:
- RB -> Direct -> Macro A+RB.

Shift Layer 1 chỉ cần hai macro này.

## 7. Shift Layer 2
Best.rewasd mapping:

| Source | Output |
|---|---|
| A | A + D-pad Down |
| B | A + D-pad Right |
| X | A + D-pad Left |
| Y | A + D-pad Up |

Tạo bốn macro trong Shift Layer 2.

Macro 1:
- Key Combination (Hold).
- A.
- D-pad Down.

Macro 2:
- Key Combination (Hold).
- A.
- D-pad Right.

Macro 3:
- Key Combination (Hold).
- A.
- D-pad Left.

Macro 4:
- Key Combination (Hold).
- A.
- D-pad Up.Mapping Shift Layer 2:
- A -> Direct -> Macro A+D-pad Down.
- B -> Direct -> Macro A+D-pad Right.
- X -> Direct -> Macro A+D-pad Left.
- Y -> Direct -> Macro A+D-pad Up.

Lưu ý:
Macro phải chứa A ở output.
Không dựa vào native A/B/X/Y vì mapping source đã được thay bằng macro target.

## 8. Virtual Xbox 360 trong Best.rewasd
Best.rewasd dùng:
- virtual gamepad type = 360.

Đây là output layer của reWASD.
Không có mục cần copy 1:1 sang Space Station.

Trong Space Station:
- giữ controller ở PC/XInput mode bạn đang dùng bình thường.
- test bằng joy.cpl.
- xác nhận game chỉ thấy một controller.

Chỉ dùng reWASD Virtual Xbox 360 lại nếu:
- game có compatibility problem với output native;
- hoặc bạn cần workflow đặc thù của reWASD.

## 9. Thứ tự test
Test Main trước:
1. A/B/X/Y native.
2. Pair -> X.
3. Back -> B.
4. M4 -> LS.
5. Home -> Home key.

Sau đó M2:
1. giữ M2;
2. A/B/X/Y phải ra D-pad;
3. LB/RB phải ra combo;
4. thả M2;
5. A/B/X/Y trở về native.Test M1:
1. giữ M1;
2. A/B/X/Y phải ra A + D-pad tương ứng;
3. thả M1;
4. mapping trở về Main.

Test gyro:
1. M3 một lần -> gyro ON.
2. nghiêng trái -> mouse left.
3. nghiêng phải -> mouse right.
4. nghiêng lên -> mouse down theo profile nguồn.
5. nghiêng xuống -> mouse up.
6. M3 lần nữa -> gyro OFF.

## 10. Checklist trước Apply
- [ ] Main Layer có Home/Pair/Back/M4.
- [ ] M2 = Hold Shift 1.
- [ ] M1 = Hold Shift 2.
- [ ] Gyro Mouse + Toggle M3.
- [ ] Vertical inversion ON.
- [ ] Horizontal inversion OFF.
- [ ] Shift 1 A/B/X/Y đúng D-pad.
- [ ] Shift 1 LB macro A+LB.
- [ ] Shift 1 RB macro A+RB.
- [ ] Shift 2 có đủ 4 macro A+D-pad.
- [ ] Không có mapping thừa trên M3.
- [ ] Apply đúng on-board profile mong muốn.

## 11. Khác biệt không thể copy số học trực tiếp
Không copy 1:1:
- Gyro sensitivity.
- Gyro smoothing.
- Response curve.

Copy được 1:1 về logic:
- button mapping.
- layer entry/exit.
- macro combo.
- gyro direction.
- gyro toggle button.

## 12. Mục tiêu cuối
Khi migration hoàn tất, có thể tắt reWASD và profile vẫn giữ logic gameplay cốt lõi trên Vader 5 Pro.
Nếu một chức năng không hoạt động sau khi tắt reWASD, dùng checklist để xác định nó thuộc:
- on-board Flydigi;
- hay Windows-level behavior của reWASD.
