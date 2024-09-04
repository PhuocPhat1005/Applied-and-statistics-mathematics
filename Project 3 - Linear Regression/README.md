# <center>Đồ án 3: Linear Regression</center>

## Mục lục

1. [Nội dung đồ án](#c1)
    - [Mô tả dữ liệu](#c11)
    - [Yêu cầu](#c12)
2. [Quy định nộp bài](#c2)
3. [Quy định chấm bài](#c3)

## Nội dung đồ án <a class="anchor" id="c1"></a>
Mục tiêu của đồ án là tìm hiểu các yếu tố ảnh hưởng đến thành tích học tập của sinh viên (Academic Student Performance Index). Các yếu tố ảnh hưởng có thể là số giờ học tập/nghiên cứu, hoạt động ngoại khóa, số giờ ngủ, số bài kiểm tra mẫu đã luyện tập...

### Mô tả dữ liệu <a class="anchor" id="c11"></a>
#### Dữ liệu Thành tích sinh viên (Student Performance)
* Bộ dữ liệu có 10000 dòng và 6 cột. Ý nghĩa và kiểu dữ liệu của từng cột được thể hiện ở bảng sau:

    | **STT** |          **Thuộc tính**          |                                                                       **Mô tả**                                                                      | **Kiểu dữ liệu** |
    |---------|----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|------------------|
    |    1    | Hours Studied                    | Tổng số giờ học của mỗi sinh viên                                                                                                                    |      Integer     |
    |    2    | Previous Scores                  | Điểm số học sinh đạt được trong các bài kiểm tra trước đó                                                                                            |      Integer     |
    |    3    | Extracurricular Activities       | Sinh viên có tham gia hoạt động ngoại khóa không (Có hoặc Không)                                                                                     |      Boolean     |
    |    4    | Sleep Hours                      | Số giờ ngủ trung bình mỗi ngày của sinh viên                                                                                                         |      Integer     |
    |    5    | Sample Question Papers Practiced | Số bài kiểm tra mẫu mà học sinh đã luyện tập                                                                                                         |      Integer     |
    |    6    | Performance Index                | Thước đó thành tích tổng thể cho mỗi sinh viên. Chỉ số thể hiện thành tích học tập, nằm trong đoạn [10, 100]. Chỉ số này tỉ lệ thuận với thành tích. |       Float      |

    Reference: [Student Performance](https://www.kaggle.com/datasets/nikhil7280/student-performance-multiple-linear-regression).
#### Dữ liệu sử dụng cho đồ án
Trong đồ án này, dữ liệu trên đã được thực hiện tiền xử lý chuyển đổi kiểu dữ liệu cho thuộc tính `Extracurricular Activities`.

Sau khi tiền xử lý, bộ dữ liệu được chia ngẫu nhiên thành 2 tập với tỉ lệ 9:1. Trong đó, 9 phần cho tập huấn luyện, 1 phần cho tập kiểm tra.

Sinh viên được cung cấp 2 tập tin:
- `train.csv`: Chứa 9000 mẫu dùng để huấn luyện mô hình.
- `test.csv`: Chứa 1000 mẫu dùng để kiểm tra mô hình.

Đoạn mã nguồn sau để thể hiện 5 mẫu dữ liệu đầu tiên trong tập `train.csv`.
```python!=
import pandas as pd
train = pd.read_csv('train.csv')
train.head()
```
### Yêu cầu <a class="anchor" id="c12"></a>
Trong đồ án này, sinh viên được yêu cầu thực hiện:

1. Thực hiện phân tích khám phá dữ liệu (1 điểm)
- Sử dụng thống kê để phân tích dữ các đặc trưng.
- Sử dụng biểu đồ (bar, box, heatmap, scatter, line...) để phân tích/quan sát các đặc trưng.
- ...

2. Xây dựng mô hình *dự đoán chỉ số thành tích* **sử dụng mô hình hồi quy tuyến tính** (6 điểm)
- Yêu cầu 2a: Sử dụng toàn bộ 5 đặc trưng (2 điểm)
	- Huấn luyện 1 lần duy nhất cho 5 đặc trưng trên cho toàn bộ tập huấn luyện (`train.csv`).
	- Thể hiện công thức cho mô hình hồi quy (tính $y\ (\text{Student Performance})$ theo 5 đặc trưng).
	- Báo cáo **1 kết quả trên tập kiểm tra (`test.csv`)** cho mô hình vừa huấn luyện được.

- Yêu cầu 2b: Xây dựng mô hình sử dụng duy nhất 1 đặc trưng, tìm mô hình cho kết quả tốt nhất (2 điểm)
	- Thử nghiệm trên toàn bộ (5) đặc trưng đề bài cung cấp.
	- Yêu cầu sử dụng **k-fold Cross Validation** (**k** tối thiểu là 5) để tìm ra đặc trưng tốt nhất.
	- Báo cáo **5 kết quả tương ứng cho 5 mô hình** từ k-fold Cross Validation (lấy trung bình).
	
	<center>

	| STT | Mô hình với 1 đặc trưng 		| MAE  |
	|:---:|:-------------------------------:|:----:|
	|  1  | Hours Studied			        |      |
	|  2  | Previous Scores			        |      |
	|  3  | Extracurricular Activities		|	   |
	|  4  | Sleep Hours						|	   |
	|  5  | Sample Question Papers Practiced|      |

	</center>

	- Thể hiện công thức cho mô hình hồi quy theo đặc trưng tốt nhất (tính $y$ theo đặc trưng tốt nhất tìm được).
    - Báo cáo **1 kết quả trên tập kiểm tra (`test.csv`)** cho mô hình tốt nhất tìm được.

- Yêu cầu 2c: Sinh viên tự xây dựng/thiết kế mô hình, tìm mô hình cho kết quả tốt nhất (2 điểm)
	- Xây dựng `m` mô hình khác nhau (tối thiểu 3), đồng thời khác mô hình ở 2a và 2b.
		- Mô hình có thể là sự kết hợp của 2 hoặc nhiều đặc trưng.
		- Mô hình có thể sử dụng đặc trưng đã được chuẩn hóa hoặc biến đổi (bình phương, lập phương...).
		- Mô hình có thể sử dụng đặc trưng được tạo ra từ 2 hoặc nhiều đặc trưng khác nhau (cộng 2 đặc trưng, nhân 2 đặc trưng...).
		- ...
	- Gợi ý: Dựa vào phần phân tích khám phá dữ liệu đã thực hiện bên trên.

	- Yêu cầu **sử dụng phương pháp k-fold Cross Validation** (**k** tối thiểu là 5) để tìm ra mô hình tốt nhất trong `m` mô hình mà sinh viên xây dựng/thiết kế.

	- Báo cáo **`m` kết quả tương ứng cho `m` mô hình** từ k-fold Cross Validation (lấy trung bình).

	<center>

	| STT |           Mô hình          | MAE  |
	|:---:|:--------------------------:|:----:|
	|  1  | Sử dụng 2 đặc trưng (a, b) |      |
	| ... | ...                        |      |
	|  m  | ...                        |      |

	</center>

	- Thể hiện công thức cho mô hình hồi quy tốt nhất mà sinh viên tìm được.
	- Báo cáo **1 kết quả trên tập kiểm tra (`test.csv`)** cho mô hình tốt nhất tìm được.


- <ins>Lưu ý:</ins>
    - Kết quả báo cáo là độ đo MAE.
	- Ở câu 2c, mô hình sử dụng 2 đặc trưng trên đặc trưng (a, b) và (b, c) cũng **chỉ được tính là một mô hình** sử dụng 2 đặc trưng. Tương tự cho các số lượng đặc trưng khác.
    

3. Báo cáo về kết quả, đánh giá và nhận xét các mô hình đã xây dựng (3 điểm)
    - Báo cáo cần có thông tin cá nhân (họ và tên, MSSV), số trang và tài liệu tham khảo (cần chỉ định cụ thể tài liệu được sử dụng cho phần nào trong bài làm).
    - Liệt kê TẤT CẢ thư viện đã sử dụng và lý do sử dụng chúng.
	- Liệt kê TẤT CẢ hàm đã sử dụng/đã cài đặt và mô tả các hàm đó (kể cả các hàm từ thư viện). Các hàm tính toán từ NumPy có thể được lược bỏ.
    - Báo cáo và nhận xét kết quả từ TOÀN BỘ các mô hình xây dựng được (có $1 + (5 + 1) + (m + 1)$ kết quả)
    - Với yêu cầu 2b và 2c: Giải thích hoặc nêu giả thuyết (có logic) cho mô hình đạt kết quả tốt nhất ở mỗi yêu cầu.
	- Với yêu cầu 2c: Trình bày toàn bộ quá trình và lý do trích chọn/thiết kế các đặc trưng cho `m` mô hình mà sinh viên xây dựng. Sinh viên có thể sử dụng các thuật toán/phương pháp có sẵn nhưng phải trình bày lại phương pháp đó trong báo cáo.
## Quy định nộp bài <a class="anchor" id="c2"></a>
- Thực hiện toàn bộ bài làm trên 1 tập tin Jupyter Notebook `MSSV.ipynb` đính kèm.
    - Tập tin Jupyter Notebook cần cung cấp các thông tin cá nhân: họ và tên, MSSV, lớp.
    - Giữ nguyên tổ chức bài làm (thứ tự các phần, câu) trong tập tin `MSSV.ipynb` đính kèm. Tự ý xóa hoặc thay đổi tổ chức sẽ bị trừ điểm.
    - Bổ sung bài làm vào các phần để trống chỉ định (sinh viên có thể tạo thêm code cell hoặc Markdown cell nếu cần)

- Sinh viên nộp tập tin `MSSV.zip` được nén từ thư mục MSSV chứa các tập tin sau:
    1. Báo cáo toàn bộ bài làm: `MSSV.pdf`
    2. Mã nguồn: `MSSV.ipynb`
    
- Ví dụ minh họa cây thư mục bài nộp sau khi giải nén tập tin `MSSV.zip` như sau:
    ```
    MSSV
    ├── MSSV.pdf
    └── MSSV.ipynb
    ```
## Quy định chấm bài <a class="anchor" id="c3"></a>
Đây là đồ án chiếm 10%.

Những trường hợp sau đây sẽ bị 0 điểm toàn bộ đồ án:
- Nộp sai quy định.
- Không có tập tin mã nguồn (`MSSV.ipynb`).
- Không có tập tin báo cáo (`MSSV.pdf`).
- Thực thi mã nguồn báo lỗi.

<font style="color:red">**LƯU Ý: SAO CHÉP BÀI LÀM CỦA NHAU VÀ BÀI LÀM TRÊN INTERNET SẼ BỊ 0 ĐIỂM TOÀN BỘ PHẦN THỰC HÀNH**</font>
