# Báo cáo tuần 2
## Speech signal và Audio số (Digital Audio)
### Speech signal
Theo cách giải nghĩa thông thường, **Speech signal** (hay còn được gọi là **Tín hiệu tiếng nói**) là tín hiệu âm thanh được phát ra khi con người nói, mang các thông tin về:
* Nội dung ngôn ngữ
* Cảm xúc
* Đặc điểm người nói

Trong CNTT, speech signal được xem là một **tín hiệu thời gian (time-domain signal)** có thể được xử lý bằng các kỹ thuật **Xử lý tín hiệu số (Digital Signal Processing – DSP).**

#### Bản chất vật lý của Speech Signal:
Speech signal bản chất là một sóng âm cơ học
* Lan truyền trong không khí
* Là dao động áp suất theo thời gian\
Speech Signal có thể được biểu diễn dưới dạng toán học như sau: $s(t)$ \
Trong đó:
* $t$ là thời gian
* $s(t)$ là biên độ (áp suất âm)

#### Đặc trưng của Speech Signal
1. Tính không dừng (Non-stationary)
* Tín hiệu thay đổi theo thời gian
* Nhưng có thể xem gần như dừng trong 10–30 ms
2. Dải tần số (Frequency Range)\
**Dải tần số (frequency range)** là khoảng các giá trị tần số (Hz) mà tín hiệu tiếng nói chứa năng lượng.
* Người: ~80 Hz – 8 kHz
* Thông tin quan trọng (Con người có thể hiểu được nội dung) : < 4 kHz

#### Speech Signal trong CNTT:
Speech Signal được dùng trong: voice detection, Voice verification, Speech-to-text,...

##### Quy trình xử lý Speech Signal:
1. Thu âm (Microphone)
2. Số hoá (Analog-to-Digital Converter)
3.Tiền xử lý
* Pre-emphasis
* Framing
* Windowing
* Trích đặc trưng
4. Mô hình hóa (HMM, DNN, Transformer)

### Digital Audio (Audio số)
