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

1. Sampling (Lấy mẫu):
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

2. Quantization (Lượng tử hóa)
Sau khi lấy mẫu, giá trị biên độ sẽ được làm tròn về một mức gần nhất.
- Bit depth (Độ sâu bit)
Cách tính số lượng tử: $Số mức = 2^{bit}$

| Bit depth | Số mức        | Ứng dụng    |
| --------- | ------------- | ----------- |
| 8-bit     | 256 mức       | Âm thanh cũ |
| 16-bit    | 65,536 mức    | CD          |
| 24-bit    | ~16 triệu mức | Studio      |

Bit depth càng cao → âm thanh càng mượt, ít nhiễu lượng tử.

3. Encoding (Mã hoá):
Mỗi mẫu sau khi lượng tử hóa được biểu diễn bằng chuỗi nhị phân.\
Ví dụ:\
16-bit → mỗi mẫu = 16 bit\
44.1 kHz → 44,100 mẫu/giây

#### Định dạng file audio số
- Không nén (Lossless – giữ nguyên dữ liệu)
* WAV
* AIFF
* FLAC
- Nén dữ liệu (Lossy)
* MP3
* AAC
* OGG
* 
### Sampling Rate
Sampling Rate là số lần đo (lấy mẫu) tín hiệu âm thanh trong 1 giây, đơn vị là **Hz (Hertz).**\
Kí hiệu : $Fs$

#### Bản chất toán học:
Âm thanh thực tế là dạng sóng tín hiệu liên tục $x(t)$\
Và sau khi số hoá: $x[n]=x(nT)$\
Trong đó:
* $T = \frac{1}{f_s}$ (chu kỳ)
* $n$ là số mẫu
Tức là ta chỉ giữ lại các giá trị tại những thời điểm rời rạc.

#### Ý nghĩa của Sampling Rate trong Digital Audio
Đảm bảo tái tạo chính xác tín hiệu Sampling Rate quyết định khả năng hệ thống số ghi lại và khôi phục tín hiệu analog ban đầu.\
Theo định lý lấy mẫu của Harry Nyquist: $f_s \ge 2f_{max}$\
Mục đích ở đây là:
* Tránh aliasing
* Giữ nguyên thông tin tần số
* Cho phép tái tạo lại tín hiệu bằng nội suy sinc
* Nếu chọn sai sampling rate → mất thông tin không thể khôi phục.

### FFT (Fast Fourier Transform)
Biến đổi Fourier nhanh (FFT - Fast Fourier Transform) là thuật toán hiệu quả cao dùng để tính toán Biến đổi Fourier rời rạc (DFT), chuyển đổi tín hiệu từ miền thời gian sang miền tần số.\
DFT: $X[k] = \sum_{n=0}^{N-1} x[n] e^{-j 2\pi kn/N}$
#### Tại sao cần FFT trong Speech?
Speech chứa nhiều thành phần tần số:
* Pitch
* Formant
* Harmonics
* FFT giúp:
  * Phân tích phổ
  * Tạo spectrogram
* Tính MFCC

## Waveform, Spectrogram, MFCC
### Waveform
Waveform (dạng sóng) là **hình ảnh đồ họa** mô tả **sự biến đổi của tín hiệu (âm thanh, điện từ) theo thời gian**, thể hiện các đặc tính như tần số, biên độ và pha. Nó được dùng để phân tích sóng (sine, vuông, răng cưa) và là nền tảng trong xử lý tín hiệu. Ngoài ra, Waveform còn là tên phần mềm sản xuất âm nhạc (DAW)
<img width="1132" height="602" alt="image" src="https://github.com/user-attachments/assets/b87fbfd1-45ad-4eda-b58c-d2a527249c44" />
Biểu diễn:\
Trục X: thời gian\
Trục Y: biên độ.

#### Lợi ích của Waveform trong xử lý giọng nói:
Quan sát cấu trúc tổng thể của tín hiệu, Waveform giúp:

* Nhìn thấy đoạn bắt đầu và kết thúc lời nói
* Phát hiện khoảng im lặng (silence)
* Quan sát sự thay đổi năng lượng theo thời gian

### Spectrogram
Spectrogram (biểu đồ sóng âm) là công cụ trực quan hóa phổ tần số của tín hiệu theo thời gian, cho phép nhìn thấy cường độ âm thanh (biên độ) ở các tần số khác nhau.\
Biểu diễn: Trục X hiển thị thời gian, trục Y hiển thị tần số, và màu sắc biểu thị cường độ/năng lượng (thường là dB).
<img width="330" height="227" alt="image" src="https://github.com/user-attachments/assets/e0b445b6-a6e2-4bdc-b494-bc7afa6f85ff" />
Spectrogram được tạo bằng cách:
* Chia tín hiệu thành các frame ngắn (20–30ms)
* Áp dụng cửa sổ (windowing)
* Tính FFT cho từng frame
* Ghép phổ theo trục thời gian
#### Lợi ích của Spectrogram
Biểu đồ phổ (Spectrogram) có thể được sử dụng để phân tích kết quả của việc truyền tín hiệu thử nghiệm qua bộ xử lý tín hiệu như bộ lọc nhằm kiểm tra hiệu suất của nó.

### MFCC
MFCC là một cách để trích xuất các đặc trưng giọng nói thường được sử dụng trong các model nhận dạng giọng nói hay phân loại giọng nói. Ví dụ như sau, trong một dataset có hơn 10 file voice khác nhau. MFCC sẽ hỗ trợ trong việc phân biệt các âm tiết khác nhau trong các data voice đấy.
<img width="1400" height="458" alt="image" src="https://github.com/user-attachments/assets/6f8d8485-fd0b-4a2e-b7b3-0907b688a6a5" />
Có thể thấy sự quan trong của MFCC trong công cuộc xử lý âm thanh giọng nói khi nó giúp ta làm mịn phổ âm thanh đồng thời tính đến các đặc tính của thính giác con người.

## Voice Activity Detection
Voice Activity Detection (VAD) là kỹ thuật phát hiện sự hiện diện hoặc vắng mặt của lời nói của con người, được sử dụng trong xử lý lời nói. Các ứng dụng chính của VAD là trong phân tách người nói , mã hóa lời nói và nhận dạng lời nói.\
Theo đúng pipeline:\
Audio input → VAD → Feature Extraction (MFCC) → Speaker Recognition

### Nguyên lý hoạt động
VAD thường hoạt động theo từng frame ngắn (10–30 ms).\
Quy trình cơ bản:
* Chia tín hiệu thành các frame
* Trích xuất đặc trưng (features)
* Phân loại frame:
* Speech
* Non-speech

### Các phương pháp VAD:
* Energy-based VAD
* Zero Crossing Rate (ZCR)
* Spectral-based VAD
* Machine Learning / Deep Learning VAD

### Ứng dụng thực tế
* Trợ lý ảo (Alexa, Google Assistant)
* Hệ thống call center
* Hệ thống ghi âm thông minh
* Speech-to-Text
* Speaker verification
