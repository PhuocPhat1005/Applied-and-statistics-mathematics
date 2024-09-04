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

