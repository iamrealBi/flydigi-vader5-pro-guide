# Từ điển thuật ngữ Flydigi / reWASD — hiểu theo hành vi thực tế

> Trang này không dịch từng chữ. Mục tiêu là giải thích: khi bạn bấm, giữ, thả hoặc xoay tay cầm thì game thực sự nhận được gì.

## Ký hiệu xác minh

- **✅ Đã xác minh trên UI thật**: đã thấy trực tiếp trên Flydigi Space Station với VADER 5 Pro của bộ tài liệu này.
- **🧪 Có trong code/capability nhưng chưa thấy trên UI hiện tại**: không nên coi là tính năng chắc chắn có trên máy bạn.
- **⚠️ Phụ thuộc model / firmware / Engine / chế độ kết nối**: có thể hiện hoặc hoạt động khác tùy điều kiện.

## Direct — tác dụng kéo dài đúng bằng thời gian bạn giữ nút

Direct có thể hiểu là: **giữ nút nguồn bao lâu thì hành động đích được giữ bấy lâu**.

Ví dụ M4 → LS:
- giữ M4 2 giây → game nhận LS bị giữ khoảng 2 giây;
- thả M4 → LS được nhả.

Đây là kiểu gần nhất với việc đổi một nút thành một nút khác.

![Các kiểu kích hoạt thật trong Space Station](images/05-button-activators.png)

## Single Press — nhấn một lần rồi nhả

Space Station chờ một lần **ấn xuống + nhả ra ngắn** rồi mới kích hoạt action.

Điểm cần hiểu:
- khác Direct vì action không bám theo toàn bộ thời gian bạn giữ;
- có thể có một độ trễ nhỏ vì hệ thống cần phân biệt Single Press với Double Press.

## Double Press — nhấn hai lần đủ nhanh

Không phải giữ hai nút. Nó nghĩa là:
1. bấm;
2. nhả;
3. bấm lần hai trong khoảng thời gian cho phép;
4. action Double Press mới chạy.

## Long Press — giữ đủ lâu mới chạy

Long Press chỉ kích hoạt sau khi nút được giữ vượt qua một ngưỡng thời gian.

Dùng cho action phụ hoặc thao tác bạn không muốn bấm nhầm.
## Press Pulse — vừa ấn xuống thì target được “tap” một lần rất ngắn

Pulse thường bị dịch thành “xung”, nhưng “xung” không giúp người mới hình dung.

Hãy hiểu **Press Pulse** như sau:

> Vừa ấn nút vật lý xuống → Space Station tự tạo một cú nhấn + nhả rất nhanh ở target.

Quan trọng:
- dù ngón tay vẫn giữ nút vật lý, target **không bị giữ theo**;
- target chỉ được “chạm” một lần rồi tự nhả.

Ví dụ M4 → phím E bằng Press Pulse:
- bạn giữ M4 3 giây;
- game vẫn chỉ nhận **một cú E ngắn lúc M4 vừa được ấn xuống**.

Nó gần với khái niệm “tap once” hơn là “hold”.

## Release Pulse — thả nút mới target được “tap” một lần

Giống Press Pulse nhưng thời điểm phát cú nhấn ngắn là **lúc bạn nhả source**.

Ví dụ:
- ấn M4: chưa phát E;
- giữ bao lâu cũng được;
- thả M4: phát một cú E rất ngắn.

## Toggle — bấm một lần bật, lần sau tắt

Toggle nên hiểu như **công tắc ON/OFF**.

Ví dụ gyro:
- bấm M3 lần 1 → gyro ON;
- thả M3 → gyro vẫn ON;
- bấm M3 lần 2 → gyro OFF.

## Hold — chỉ có hiệu lực trong lúc đang giữ

Trong Layer:
- giữ M2 → vào Shift Layer;
- thả M2 → tự quay về Main Layer.

Đây là kiểu gần giống việc giữ Shift trên bàn phím.

## Layer — một bộ mapping khác trong cùng profile

Layer là **lớp cấu hình**.

Cùng nút A có thể:
- ở Main Layer = A bình thường;
- ở Shift Layer = D-pad Down.

![Menu layer thật](images/03-layer-menu.png)
## Shift Layer — lớp phụ được bật bằng Hold hoặc Toggle

Shift Layer không phải phím Shift bàn phím. Nó là một bộ mapping phụ.

Vader 5 Pro UI hiện tại cho tạo tối đa 3 Shift Layer ngoài Main Layer.

## Target — đầu ra mà source sẽ biến thành

Target là **thứ game/Windows sẽ nhận** sau khi mapping.

Ví dụ:
- Controller → LS;
- Keyboard → một phím;
- Mouse → click;
- Layer → chuyển lớp;
- Macro → chạy chuỗi hành động;
- Turbo → bấm lặp;
- Disable → không phát gì.

![Khu vực chọn loại đầu ra](images/18-mapping-target-types.png)

## Turbo / Rapid Fire — tự bấm lặp khi giữ

Turbo biến một lần giữ thành nhiều lần bấm liên tiếp:
- giữ A;
- hệ thống phát A, A, A, A... theo interval.

Không nên hiểu Turbo là “tăng lực” của nút.

## Macro — kịch bản gồm nhiều input

Macro là **chuỗi thao tác** Space Station phát thay bạn.

Ví dụ:
1. Press A;
2. chờ 50 ms;
3. Press LB;
4. Release A;
5. Release LB.

![Macro editor thật](images/19-macro-editor.png)

## Key Combination (Hold) — giữ nhiều target cùng lúc

Dùng khi một source cần giữ nhiều đầu ra đồng thời.

Ví dụ profile Elden Ring:
- giữ LB ở Shift Layer;
- output giữ A + LB;
- thả source → cả A và LB cùng nhả.

## Run Once (Until Complete) — chạy một lần hết sequence

Bấm source một lần → macro chạy từ đầu tới cuối một lần.

Phù hợp combo có trình tự cố định.

## Loop (Stop on Release)

Macro lặp trong lúc giữ source. Thả source → dừng ngay, kể cả đang giữa một vòng.

## Loop (Finish Current Cycle)

Macro lặp trong lúc giữ. Khi thả:
- không bắt đầu vòng mới;
- vòng đang chạy được phép hoàn tất.
## Press / Release trong Macro

- **Press** = đưa target vào trạng thái đang được giữ.
- **Release** = nhả target đã Press.

Một macro cần Press/Release hợp lý để tránh nút bị “kẹt”.

## Push / Center trong Macro

Dùng cho input analog:
- Push = đẩy stick theo hướng/giá trị;
- Center = đưa stick về tâm.

## Delay — khoảng chờ giữa hai bước macro

Delay là thời gian nghỉ giữa các action.

Quá ngắn:
- game có thể bỏ sót input.

Quá dài:
- combo cảm giác chậm.

## Dead Zone — vùng chuyển động nhỏ bị bỏ qua

Dead Zone, hay “vùng chết”, nên hiểu là:

> vùng quanh tâm được coi như bằng 0 để bỏ qua rung/drift nhỏ.

Dead Zone lớn hơn:
- chống drift tốt hơn;
- nhưng micro-aim kém nhạy hơn.

![Stick Basic](images/06-stick-basic.png)

## Stick Drift — stick tự phát tín hiệu khi không chạm

Triệu chứng:
- nhân vật tự đi;
- camera tự quay;
- joy.cpl không đứng đúng tâm.

Ưu tiên calibration trước, sau đó mới tăng Dead Zone vừa đủ.

## Response Curve — cách biến mức input thành mức output

Response Curve không đơn giản là “độ nhạy”.

Nó trả lời câu hỏi:
- input 20% thì muốn output bao nhiêu?
- input 70% thì muốn output bao nhiêu?

Bạn có thể làm đầu curve nhẹ để aim mịn, cuối curve dốc để vẫn quay nhanh.

![Stick Advanced](images/07-stick-advanced.png)

## Midpoint — điểm trung gian để uốn curve

Midpoint là điểm X/Y đặt giữa đầu và cuối curve.

UI Vader 5 Pro hiện tại cho tối đa 2 midpoint ở các editor đã kiểm tra.

## Boundary — hình dạng biên tối đa của stick

- Circle: biên tròn, analog tự nhiên hơn.
- Rectangle: giúp góc chéo dễ đạt output lớn hơn.

Boundary khác Dead Zone.
## Zone Mapping — chia vùng stick để mỗi vùng làm việc khác

Ví dụ:
- vùng dưới 70% = đi bình thường;
- vùng trên 80% = Sprint.

Hoặc chia theo hướng Up/Down/Left/Right/chéo.

## 8-way / 4-way / 4-way Overlap

- 8-way = 8 hướng, gồm cả chéo.
- 4-way = 4 hướng chính.
- 4-way Overlap = vùng giáp ranh có thể kích hoạt hai hướng cạnh nhau cùng lúc.

## Trigger Travel — quãng cò đi từ thả tới bóp

Travel trong ngữ cảnh trigger là **hành trình vật lý của cò**.

Không nên hiểu theo nghĩa thông thường của từ “hành trình”.

## Effective Travel — phần hành trình cò thực sự được dùng

Ví dụ:
- cò vật lý đi 0–100%;
- đặt Effective Travel 0–60%;
- chỉ cần bóp tới khoảng 60% đã dùng hết dải input đã cấu hình.

![Trigger Advanced](images/09-trigger-advanced.png)

## Output Range — khoảng tín hiệu đầu ra

Input Range và Output Range là hai thứ khác nhau.

Bạn có thể dùng 0–60% hành trình vật lý nhưng scale thành 0–100% output.

## Travel Zones — chia cò thành vùng bóp nhẹ / vừa / mạnh

UI Advanced hiện có 3 zone:
- Light Press;
- Medium Press;
- Heavy Press.

Zone có thể phát action phụ trong lúc LT/RT analog vẫn tiếp tục output.

## Linear

Input tăng đều → output tăng đều.

Đây là baseline nên thử trước khi chỉnh custom curve.

## FPS Instant

Preset rút ngắn phần cò cần bóp để đạt phản hồi bắn nhanh.

Phù hợp shooter khi không cần điều khiển analog tinh tế.

## Rapid Response

Preset đạt output cao sớm hơn Linear nhưng vẫn giữ cảm giác có hành trình.

![Trigger Basic](images/08-trigger-basic.png)
## Gyro / Motion Control — điều khiển bằng chuyển động tay cầm

Gyro đọc việc bạn xoay controller.

Space Station có thể biến chuyển động thành:
- Mouse;
- Left Stick;
- Right Stick.

![Motion Control Basic](images/10-motion-basic.png)

## Sensitivity — cùng một góc xoay sẽ tạo output nhiều hay ít

Sensitivity cao hơn:
- xoay tay cùng một góc;
- camera/con trỏ đi xa hơn.

Không copy số sensitivity 1:1 giữa reWASD và Space Station.

## Smoothing — làm mượt dao động

Smoothing lọc rung nhỏ để aim mượt hơn.

Quá nhiều smoothing có thể làm cảm giác bị trễ/nặng.

## Invert X / Invert Y — đảo hướng

- Invert X: trái ↔ phải.
- Invert Y: lên ↔ xuống.

Best.rewasd trong bộ tài liệu đang dùng đảo Y.

## Native Grip Vibration — rung phần tay nắm theo cơ chế bình thường

Đây là rung ở grip/thân controller.

Nó không đồng nghĩa với lực cản ở trigger.

![Vibration thật](images/12-vibration.png)

## Trigger-Bound Grip Feedback — bóp cò thì grip rung theo

Tên này dễ gây hiểu nhầm.

Nó **không có nghĩa trigger tự tạo lực cản**.

Nó nghĩa trạng thái LT/RT được dùng để điều khiển rung ở phần grip.

## Haptic — phản hồi xúc giác chi tiết

Haptic rộng hơn rung motor đơn giản. Nó có thể mô phỏng nhịp, va chạm, texture hoặc cảm giác theo ngữ cảnh.
## Trigger Haptics — phản hồi xúc giác ở cò

**🧪 Trạng thái xác minh hiện tại:**

Trong code/chuỗi giao diện Space Station có:
- Trigger Mode;
- Pistol / Rifle / Shotgun / Sniper / Sword...;
- Trigger Travel / Frequency / Force.

Nhưng trên tab Trigger thật của VADER 5 Pro đang kiểm tra **không xuất hiện các lựa chọn này**.

Vì vậy:
- nếu bạn không thấy Trigger Haptics thì không phải bạn tìm sai menu;
- guide không còn coi đây là tính năng chắc chắn có trên UI Vader 5 Pro hiện tại.

## X-Haptics

Code Space Station có các chuỗi liên quan:
- real-time audio haptics;
- adaptive trigger;
- UDP / telemetry haptics.

**🧪 Nhưng trong màn hình cấu hình Vader 5 Pro đã chụp, không có tab X-Haptics riêng.**

Do đó phần này chỉ được ghi là capability phụ thuộc Engine/model/firmware.

## On-board Profile — profile nằm trong controller

On-board nghĩa là **lưu trên tay cầm**.

Khi đã Apply xuống slot, profile không chỉ còn là bản đang chỉnh trên máy.

## Local Profile — profile nằm ở thư viện local

Local Profile có thể đã được chỉnh/lưu nhưng controller **chưa nhận**.

![Profile Library thật](images/17-profile-manage.png)

## Apply to Controller — ghi bản local xuống tay cầm

Đây là bước chuyển từ:
- bản đang chỉnh trên máy;
sang
- bản thật sự nằm trong on-board slot.

Đừng nhầm Save local với Apply.

## Calibration — hiệu chuẩn

Calibration giúp firmware biết:
- đâu là tâm;
- đâu là biên;
- giá trị nào nên coi là 0/max.

## Stick Precision — độ phân giải dữ liệu stick

8/9/10/11/12-bit là mức độ chi tiết của dữ liệu stick.

Bit cao hơn không tự động bảo đảm aim tốt hơn nếu game/firmware/nhiễu không tận dụng được.
## Firmware — phần mềm chạy bên trong controller/component

Firmware khác Space Station:
- Space Station là UI/app;
- firmware chạy trong controller, RF/SI/receiver hoặc component tương ứng.

![Firmware components thật](images/16-firmware-components.png)

## Third-party Control — cho phần mềm khác takeover/remap

Khi bật, Space Station có thể tạm dừng thao tác profile trong lúc app khác kiểm soát thiết bị.

reWASD khuyến nghị bật tùy chọn takeover khi dùng Vader 5 Pro với reWASD.

## Virtual Controller — tay cầm ảo do phần mềm tạo

Ví dụ reWASD có thể tạo Virtual Xbox 360 / Xbox One / DualShock / Switch Pro.

Game có thể coi thiết bị ảo như một controller riêng.

## Double Input — một lần bấm bị tính hai lần

Thường xảy ra khi game cùng lúc nhận:
- controller vật lý;
- controller ảo;
- hoặc thêm một lớp Steam Input.

Triệu chứng:
- menu nhảy hai ô;
- một lần bấm thành hai;
- input bị nhân đôi.

## Mixed Input — controller và keyboard/mouse cùng lúc

Ví dụ:
- di chuyển bằng controller;
- gyro phát Mouse.

Một số game xử lý tốt; một số game đổi prompt hoặc giật camera.

## Native Input — đầu vào gốc của thiết bị

Native = controller gửi input gốc, không cần giả lập thành thiết bị khác.

## Simulate — tạo ra giá trị input mô phỏng

Space Station có thể mô phỏng:
- stick;
- trigger analog;
- mouse movement;
- wheel;
- vibration.

## Bảng nhớ nhanh

| Từ | Hiểu ngắn gọn |
|---|---|
| Direct | Giữ source bao lâu thì giữ target bấy lâu |
| Press Pulse | Vừa ấn source → target được tap 1 lần rất ngắn |
| Release Pulse | Thả source → target được tap 1 lần rất ngắn |
| Toggle | Bấm 1 lần bật, lần sau tắt |
| Hold | Chỉ có hiệu lực trong lúc đang giữ |
| Dead Zone | Vùng nhỏ bị bỏ qua để chống drift |
| Response Curve | Cách input được biến thành output |
| Travel | Quãng cò đi từ thả tới bóp |
| Zone | Một vùng input có action riêng |
| Macro | Chuỗi nhiều input theo kịch bản |
| On-board | Lưu trong controller |
| Local | Lưu trên máy/app |
| Apply | Ghi bản local xuống controller |
| Haptic | Phản hồi xúc giác chi tiết |
| Mixed Input | Controller + keyboard/mouse cùng lúc |
| Virtual Controller | Tay cầm do phần mềm giả lập |
