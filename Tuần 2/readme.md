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
Audio số (Digital Audio) là âm thanh được biểu diễn dưới dạng dữ liệu số (0 và 1) thay vì tín hiệu liên tục như âm thanh analog.

Âm thanh ngoài đời thực là sóng cơ học → micro chuyển thành tín hiệu điện analog → sau đó được chuyển đổi sang dạng số bằng bộ chuyển đổi **ADC (Analog-to-Digital Converter).**

#### Bản chất vật lý:
Âm thanh là **sóng cơ học lan truyền trong môi trường (không khí)**, đặc trưng bởi:

* Tần số (Frequency – Hz) → quyết định cao độ
* Biên độ (Amplitude) → quyết định độ to
* Pha (Phase)
#### Bản chất toán học:
Audio số được tạo ra bằng 3 quá trình chính:
1. Lấy mẫu (Sampling)
2. Lượng tử hoá (Quantization)
3. Mã hoá nhị phân (Encoding)

#####  Sampling (Lấy mẫu):
- Khái niệm: Là quá trình lấy các giá trị biên độ của sóng âm tại các thời điểm cách đều nhau.
- Tần số lấy mẫu:
* Đơn vị: Hz (số mẫu / giây)
* 44.1 kHz → chuẩn CD
* 48 kHz → chuẩn video
* 96 kHz → audio chất lượng cao
- Định lý Nyquist
Tần số lấy mẫu phải ≥ 2 lần tần số cao nhất của tín hiệu\
Ví dụ:\
Tai người nghe tối đa ~20 kHz
→ Cần sampling ≥ 40 kHz
→ Vì vậy chuẩn 44.1 kHz được sử dụng trong CD.

3. Quantization (Lượng tử hóa)
Sau khi lấy mẫu, giá trị biên độ sẽ được làm tròn về một mức gần nhất.
- Bit depth (Độ sâu bit)
Cách tính số lượng tử: $Số mức = 2^{bit}$

| Bit depth | Số mức        | Ứng dụng    |
| --------- | ------------- | ----------- |
| 8-bit     | 256 mức       | Âm thanh cũ |
| 16-bit    | 65,536 mức    | CD          |
| 24-bit    | ~16 triệu mức | Studio      |

Bit depth càng cao → âm thanh càng mượt, ít nhiễu lượng tử.

4. Encoding (Mã hoá):
Mỗi mẫu sau khi lượng tử hóa được biểu diễn bằng chuỗi nhị phân.\
Ví dụ:\
16-bit → mỗi mẫu = 16 bit\
44.1 kHz → 44,100 mẫu/giây

5. Định dạng file audio số
- Không nén (Lossless – giữ nguyên dữ liệu)
* WAV
* AIFF
* FLAC
- Nén mất dữ liệu (Lossy)
* MP3
* AAC
* OGG
